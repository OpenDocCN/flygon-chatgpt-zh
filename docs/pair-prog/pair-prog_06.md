



# Angular 的 HttpClient



![image](img/image017.jpg)

图片由[Gerd Altmann](https://pixabay.com/users/geralt-9301/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=2528410)提供，来自[Pixabay](https://pixabay.com/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=2528410)

现在让我们考虑一下 Angular 的 HttpClient，它大量使用 RxJS。事实上，HttpClient 通常是新的 Angular 开发人员首次接触 RxJS 的地方。这可能是一个决定性的体验。

所以，我想看看它在使用 Angular 的 HttpClient 时如何处理一些常见的编码模式。

即使你不是 Angular 开发人员，这个过程也值得理解。

## 一个典型的 Angular 服务

对于这个示例，我决定从一个空白网页开始，看看我能写多少少量的代码。记住 Copilot 需要知道它正在处理的文件类型，我立即告诉 VS Code 这是一个 TypeScript 文件，方法是点击窗口右下角的文件类型，并从提供的选项中选择 TypeScript。

接下来，我在文件顶部输入了以下注释：

// 在根目录提供服务

Copilot 立即给了我三行代码：

[@Injectable](http://twitter.com/Injectable "Twitter profile for @Injectable")({

providedIn: 'root'

})

它停在那里；我猜它在等待我提供更多信息。我决定不这样做，只是按下了 Tab 键，它回应如下：

export class ApiService {

// API 地址

private apiUrl = '[`api.github.com/users'`](https://api.github.com/users%27);

constructor(private http: HttpClient) {}

// 获取用户

getUser(username: string): Observable<User> {

return this.http.get<User>(`${this.apiUrl}/${username}`);

}

// 获取仓库

getRepos(username: string): Observable<Repo[]> {

return this.http.get<Repo[]>

(`${this.apiUrl}/${username}/repos`);

}

}

这一切都很酷，但不是我想要的。不过我也不能抱怨太多，因为我没有给它任何其他信息。我决定保留这个类，但暂时移除了两个函数。这样整个文件看起来像这样：

// 在根目录提供服务

@Injectable({

providedIn: 'root'

}) export class ApiService {

// API 地址

private apiUrl = 'https://api.github.com/users';

constructor(private http: HttpClient) {}

}

如果你在跟着做，你会注意到 Copilot 并不会自动导入任何 Angular 标识符。好消息是 VS Code 会为我做这个工作。或者也许我可以说服 Copilot 来做这个。如果我在文件顶部输入 import 会怎么样呢？

当我这样做时，没有任何变化。也许另一个提示会有所帮助。我在文件顶部添加了一个注释和一个单词 import。Copilot 自动建议了剩下的部分。

// Angular 服务

import { Injectable } from '[@angular/core](http://twitter.com/angular/core "Twitter profile for @angular/core")';

import { HttpClient } from '[@angular/common](http://twitter.com/angular/common "Twitter profile for @angular/common")/http';

现在导入已经处理好了，我可以继续进行实验的其余部分了。

## 一个简单的 HTTP GET

每当我构建演示应用程序时，我总是苦恼于在哪里找到可以展示的体面远程数据 API。我很少有时间或倾向去构建我自己的，所以我喜欢寻找一些有趣、有趣或两者兼有的东西。

如果我简单地要求 Copilot 为我找点什么，它会提供给我什么？我移除了 apiUrl 变量及其注释。然后在类的顶部添加了一个新的注释。

// 从远程 Web 服务器获取一些示例数据

getSampleData() {

return this.http.get('https://jsonplaceholder.typicode.com/todos/1');

}

这不是我预期的，但它起作用。因此，我决定尝试一个不同的提示。

// 从 API 获取所有帖子

getAllPosts() {

return this.http.get('[`jsonplaceholder.typicode.com/posts'`](https://jsonplaceholder.typicode.com/posts%27));

}

这相当酷，而且事实证明，该 API 是完全可用的。

## 让我们加入一些 RxJS

对 http.get 的调用返回一个 Observable，但目前我们没有处理任何情况。如果出现错误会怎样？我决定在 getAllPosts 中添加提示以支持错误处理。

我将返回值改为 const posts$，得到了这个结果。

const posts$ =

this.http.get('[`jsonplaceholder.typicode.com/posts'`](https://jsonplaceholder.typicode.com/posts%27));

// 记录 API 调用中的任何错误

posts$.subscribe(

posts => console.log(posts),

err => console.log(err)

);

好吧，这根本不是我想要的。我希望它会建议使用 .pipe 和 .catchError 。我决定通过创建一个 logError 函数再次给出提示，这次再次得到了 Copilot 的帮助。

// 将任何错误记录到控制台

handleError(error: any): Promise<any> {

console.error('发生了一个错误', error);

return Promise.reject(error.message || error);

}

这感觉好像它在猜测我的意图时变得更糟了。所以，我尝试了一个不同的提示。

// 在 observable 中记录任何错误到控制台

logError(err) {

console.error('发生了一个错误：' + err);

}

更好。嗯，至少我的计划是这样写的。下一步，我对 Copilot 看到我的文件中的函数并自动调用它感到好奇。

// 在返回给调用者之前检测和处理 observable 流中的错误。

posts$.subscribe(

data => console.log(data),

err => console.error(err),

() => console.log('帖子加载完毕') // 当 observable 完成时调用此函数。

);

返回 posts$;

如果你是一个对于 Angular 或其 HttpClient 或 RxJS 不熟悉的初学者，你可能会认为这是合理的代码。不是，在这种情况下至少不是。代码块创建了一个 RxJS 订阅对象，但从未取消订阅。在这种情况下是可以的，但只因为我知道 HTTP GET 总会完成或出错。然而，这不是处理这个问题的最佳方式。

在完全放弃之前，我决定再试一件事情。

而不是一个注释，我从下一行开始以 posts$.pipe，并让 Copilot 建议其余部分。这就是它给我的。

posts$.pipe(

catchError(this.logError));

这就是我要找的内容！

但是，你们中聪明的人可能已经注意到，我的 logError 函数已经不再有效了。我不得不将其更改为返回一个 Observable，但是 Copilot 并没有真正帮助我完成这个任务。这是我自己做的。现在它看起来像这样。

// 将 Observable 中的任何错误记录到控制台

logError(err): Observable<any> {

console.error('出错了：' + err);

return of();

}

## 在 Angular 模板中使用 Observable

如果我们不能获取 Observable 的值，那 Observable 有什么用呢？这一章的最后一个例子是将该 API 调用返回的文章显示在网页上。我不得不承认，这是非常有趣的。

我从一个空白文件开始，并将以下第一行作为注释。它建议了其他所有内容，只有少数提示，我将在代码块后解释。

// Angular "文章" 组件

import { Component, OnInit } from '[@angular/core](http://twitter.com/angular/core "Twitter profile for @angular/core")';

[@Component](http://twitter.com/Component "Twitter profile for @Component")({

selector: 'app-posts',

template: `

<h1>文章</h1>

<ul>

<li *ngFor="let post of posts">

{{ post.title }}

</li>

</ul>

`,

styles: []

})

export class PostsComponent implements OnInit {

posts: any;

constructor(private apiService: ApiService) { }

ngOnInit() {

this.apiService.getAllPosts().subscribe((data) => {

this.posts = data;

});

}

}

最初，它想要一个单独的文件来放置我的模板和样式。这是完全有效的，但对于我的例子来说有点过头了。我删除了这些行，并手动输入了模板和样式。然后它添加了你在上面看到的内容。

它正确地找到并引用了另一个文件中的 ApiService，虽然我确实不得不修复其导入。我认为这只是一个小麻烦，因为 VS Code 会为我处理这个问题。

## 那什么是异步管道？

我以前提到，如果我不必要订阅 Observable，我更喜欢避免。Angular 提供了自动订阅和取消订阅的异步管道。我能让 Copilot 来帮我处理吗？

遵循使用带有后缀美元符的 Observable 变量的常见做法，我将变量名从 posts 更改为 posts$，并删除了 ngOnInit 的主体。

当我在该函数内添加一个空行时，Copilot 确切地建议了我想要的：

ngOnInit() {

this.posts$ = this.apiService.getAllPosts();

}

唯一剩下的就是看看它是否能修复模板。于是，我回到了`<li *ngFor`，把整个块都擦掉了。Copilot 坚持要把它放回原样，但那根本行不通。甚至都没有一个叫做`posts`的变量，所以它给了我一个字面上的错误。

不想就这样放弃，我在`<ul>`标签内部添加了一个 HTML 注释，希望这样会有所帮助。这招奏效了！

<ul>

<!—遍历`posts$`可观察对象并显示每篇文章—>

<li *ngFor="let post of posts$ | async">

{{ post.title }}

</li>

</ul>

总的来说，一旦我用正确的提示激发它，它的表现让我印象深刻。

## ChatGPT 呢？

也许你会想，ChatGPT 在这一切中都在哪里？嗯，因为我大部分时间都待在代码编辑器里，我觉得 Copilot 更适合这些示例。然而，作为对 ChatGPT 能力的一次测试，我让它为我生成一切，使用我对 Copilot 的提示作为提示。

这是提示及其完整输出。

为我构建一个完整的 Angular 服务，从远程 Web 服务获取一些示例数据（也许是博客文章）。务必记录遇到的任何错误。然后创建一个作为 Angular 组件实现的网页，该组件在无序列表中显示来自服务的博客文章标题。最好在模板中使用 Angular 的异步管道而不是订阅可观察对象。

当然，我很乐意帮助你！这是一个从远程 Web 服务获取博客文章的 Angular 服务和组件的示例实现：

import { Injectable } from '@angular/core';

import { HttpClient } from '@angular/common/http';

import { Observable, throwError } from 'rxjs';

import { catchError } from 'rxjs/operators';

@Injectable({

providedIn: 'root'

})

export class BlogPostService {

private apiUrl = 'https://jsonplaceholder.typicode.com/posts';

constructor(private http: HttpClient) { }

getBlogPosts(): Observable<any[]> {

return this.http.get<any[]>(this.apiUrl).pipe(

catchError(error => {

console.error('获取博客文章时出错：', error);

return throwError(error);

})

);

}

}

该服务使用 Angular 的 HttpClient 模块向指定的 API URL 发送 HTTP GET 请求。如果请求过程中发生错误，服务会将错误记录到控制台并使用 rxjs 库中的 throwError 方法抛出错误。

import { Component, OnInit } from '@angular/core';

import { Observable } from 'rxjs';

import { BlogPostService } from '../blog-post.service';

@Component({

selector: 'app-blog-post-list',

template: `

<h2>博客文章</h2>

<ul>

<li *ngFor="let post of posts$ | async">{{ post.title }}</li>

</ul>

`

})

export class BlogPostListComponent implements OnInit {

posts$: Observable<any[]>;

constructor(private blogPostService: BlogPostService) { }

ngOnInit(): void {

this.posts$ = this.blogPostService.getBlogPosts();

}

}

此组件在模板中使用异步管道来订阅由 BlogPostService 返回的 posts$可观察对象。组件的 ngOnInit 方法将 posts$可观察对象设置为调用服务上的 getBlogPosts 的结果。

最后，您需要将 HttpClientModule 添加到您的应用程序模块的 imports 数组中，以使 HttpClient 可用于服务：

导入 { NgModule } from '@angular/core';

导入 { BrowserModule } from '@angular/platform-browser';

导入 { HttpClientModule } from '@angular/common/http';

导入 { AppComponent } from './app.component';

导入 { BlogPostListComponent } from './blog-post-list/blog-post-list.component';

@NgModule({

declarations: [

AppComponent,

BlogPostListComponent

],

imports: [

BrowserModule,

HttpClientModule

],

providers: [],

启动：[AppComponent]

})

export class AppModule { }

就是这样！有了这段代码，您应该能够使用异步管道在 Angular 组件中显示从远程网络服务检索到的博客文章标题列表。

哇！ChatGPT 几乎完全构建了相同的代码，包括解释。事实上，它生成的内容比我从 Copilot 得到的更完整。

我对它所写的唯一抱怨是，它的信息略显过时。Angular 14.2 引入了“独立组件”的开发者预览，这些组件不需要包含在 NgModule 内。您甚至可以编写完整的应用程序而不需要一个 NgModule。Angular 15 正式将它们纳入了框架。

这只是一个小事，但它可以说明一个重要的观点。ChatGPT 的知识并不了解过去两年的情况。我让 ChatGPT 使用 Angular 15 中的独立组件重写上述应用程序。这是它的回复。

对不起，但 Angular 15 不是一个存在的版本 - 我截止到 2021 年 9 月的知识截止日期的最新版本是 Angular 12。但是，我可以提供一个示例，展示如何使用 Angular 的无组件路由和 ng-container 元素（在 Angular 4 中引入）重写应用程序。

然后它继续给我几乎相同的应用程序，但添加了一些默认路由。当我写这篇文章时，Angular 12 已经过时了 3 个版本，很快就会过时 4 个版本。我甚至认为它已经不再受支持了。

让这成为一个友好的提醒和警告。ChatGPT 在其所做的事情上表现出色，如果你正在寻找那些往往具有长期生存力的信息。这就是为什么它在处理正则表达式、脚本和常见算法时表现出色。据其自己承认，它的知识可能会过时，尤其是在这个行业中，这个行业的发展速度如此之快。
