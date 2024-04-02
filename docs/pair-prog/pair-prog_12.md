



# 其他考虑事项



![包含文本、电子设备、电路的图片  自动生成描述](img/image005.jpg)

图片由[Vicki Hamilton](https://pixabay.com/users/flutie8211-17475707/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=7772914)从[Pixabay](https://pixabay.com/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=7772914)获取

写这样一本书时，很难知道何时停下来。我在 Twitter 上看到一些东西，人们在发布关于他们如何使用 AI 做很酷的事情的帖子。自然地，我也想尝试并将它们添加到书中。然而，这样的态度最终会自我毁灭。有截止日期要满足，还有其他需要我关注的项目。我相信这不会是我最后一次写关于这个主题的文章。我脑海中已经有更多的想法，可能超出了健康范围。我怀疑我永远也无法实现它们。然而，AI 还有一些有趣的用途，不太适合前面的章节。我想花点时间在这里简要谈谈它们。

## 理解新代码

在本书中，我一直在使用 AI 来帮助编程任务。另一个可能性是以相反的方式使用它。ChatGPT 在这方面特别擅长。考虑这样一种情况，你拿到了一些旧代码，不确定它是做什么的（或者确切地说是如何做的）。你可以将代码粘贴到 ChatGPT 中，并要求它解释。

例如，我在一个有段时间没有碰过的项目中有一些旧的 Ionic/Angular/Firebase 代码。所以，我问 ChatGPT 它是做什么的。

updateNames() {

this.db

.list('/hymns')

.snapshotChanges()

.pipe(

first(),

switchMap((list) => list)

)

.subscribe((hymn) => {

hymn.payload.child('/arrangements').forEach((arrangement) => {

const userNameNode = arrangement.child('/user/name');

const names = userNameNode.val().split(' ');

const maskedName = `${names[0]} ${names[names.length - 1][0]}.`;

userNameNode.ref.set(maskedName);

console.log(maskedName);

});

console.log('完成');

});

}

它以这种解释做出了回应：

这段代码更新 Firebase 实时数据库中/hymns 列表中每个赞美诗的 arrangements 子节点中每个用户节点的名称属性。

该代码使用 db 对象（可能是 AngularFire2 的一个实例）访问/hymns 列表，并使用 list()方法将其作为 observable。然后调用 observable 的 snapshotChanges()方法获取数据库中的更改数组，并使用 first()处理第一个更改。

然后使用 switchMap()将数组展平为一个包含各个更改的 observable，然后使用 subscribe()进行订阅。

对于每首赞美诗，该代码使用 forEach()方法循环遍历其 arrangements 子节点中的每个 arrangement 节点。

对于每个排列，代码获取其用户子节点的名称属性，使用 split() 方法将名称拆分为数组，并使用字符串插值创建由名字和姓氏首字母组成的掩盖姓名。然后，使用 set() 方法将掩盖姓名设置为 userNameNode.ref 对象上的名称属性的新值。

最后，代码将掩盖的姓名记录到控制台，并为每首赞美诗重复这个过程。一旦所有赞美诗都被处理完，代码会在控制台记录“完成”。

注意它正确推断了 Firebase（AngularFire2）和 RxJS 的使用。

然后我问 ChatGPT 关于掩盖姓名的意义。它的回答完美无缺。

你认为掩盖姓名的意义是什么？

掩盖姓名的意义很可能是为了保护用户全名的隐私。

通过掩盖姓名，代码只会显示名字和姓氏的首字母，这对于匿名化用户数据或保护用户身份可能很有用。如果应用程序处理敏感信息或用户的全名对应用程序的功能不是必要的，这一点尤为重要。 

使用掩盖的姓名还有助于保持用户数据显示的一致性。例如，如果应用程序显示用户列表或用户生成的内容，掩盖姓名可以使显示更加统一和视觉上更吸引人。

总的来说，使用掩盖姓名是保护用户隐私和确保用户数据显示一致性的常见技术。

这是一个简单、几乎微不足道的例子。我选择它是因为它很容易理解。尽管如此，如果你试图确定陌生代码的作用以及原因，这种技术尤其有用。

## 从数据生成代码

我发现 ChatGPT 的另一个很酷的用途是，你可以粘贴一些来自网络服务（或类似服务）响应的数据，并要求 AI 将其转换为不同的数据格式，甚至是代表该数据形状的代码。

例如，假设你有一些看起来像这样的示例数据：

{

"contacts": [

{

"id": "1",

"firstName": "John",

"lastName": "Doe",

"email": "johndoe@gmail.com",

"address": {

"street": "123 Main St.",

"city": "Anytown",

"state": "CA",

"zip": "12345"

},

"phones": [

{

"type": "home",

"number": "555-555-5555"

},

{

"type": "work",

"number": "555-555-5556"

},

{

"type": "mobile",

"number": "555-555-5557"

}

]

}

]

}

你可以要求 ChatGPT 为你提供所需语言的接口或类。这是它提供的 TypeScript 接口：

接口 Contact {

id: string;

firstName: string;

lastName: string;

email: string;

address: Address;

phones: Phone[];

}

接口 Address {

street: string;

city: string;

state: string;

zip: string;

}

接口 Phone {

type: string;

number: string;

}

我一直在这本书中偏爱 JavaScript 和 TypeScript，但只是为了显示它可以并且会做更多，我要求它从这些数据中生成一个 Python 对象。它给了我这个：

类联系人:

def __init__(self, id, first_name, last_name, email, address, phones):

self.id = id

self.first_name = first_name

self.last_name = last_name

self.email = email

self.address = address

self.phones = phones

类地址：

def __init__(self, street, city, state, zip_code):

self.street = street

self.city = city

self.state = state

self.zip_code = zip_code

类电话:

def __init__(self, type, number):

self.type = type

self.number = number

老实说，我不懂 Python，所以只能猜测其准确性，但看起来很有说服力。

## 编程语言翻译

ChatGPT 擅长的另一个领域是将代码从一种语言翻译成另一种语言。比如我正在尝试在我正在构建的 React 应用程序中重用一些来自 Angular 服务的代码。我想将 TypeScript 类的代码翻译成纯粹的 JavaScript。

这是个不错的类，将作为一个很好的例子。要求 ChatGPT 将其翻译成功能性的 JavaScript 产生以下代码。

我们不会深入讨论 MersenneTwister，只是提一下它是一个用于生成随机数的算法。这是另一个主题。

鉴于以下 TypeScript 类，请为我提供可用于替代的功能性 JavaScript。

export class ShuffleService {

random: MersenneTwister = new MersenneTwister();

seed(slug = 'xyz'): void {

const hash = this.hashCode(slug);

this.random.seed = hash;

}

hashCode(str: string): number {

return Array.from(str)

// eslint-disable-next-line no-bitwise

.reduce((s, c) => Math.imul(31, s) + c.charCodeAt(0) | 0);

}

shuffle(array): any[] {

return this.random.shuffle(array);

}

}

它生成了这些。

function ShuffleService() {

const random = new MersenneTwister();

function seed(slug = 'xyz') {

const hash = hashCode(slug);

random.seed = hash;

}

function hashCode(str) {

return Array.from(str)

.reduce((s, c) => Math.imul(31, s) + c.charCodeAt(0) | 0, 0);

}

function shuffle(array) {

return random.shuffle(array);

}

return {

种子，

shuffle,

};

}

## 框架翻译

它还可以帮助将代码从一个框架重写为另一个框架。继续上面的例子，我有一个小的 Ionic-Angular 组件，我想在我的 Ionic-React 应用程序中重用。我可以简单地复制和粘贴该代码，然后得到新的框架代码。

### 原始的 Ionic-Angular 组件

<ion-card>

<ion-card-content>

<div class="symbols symbols-{{card?.length}}">

<div class="symbol-wrapper"

*ngFor="let cardSymbol of card">

<div class="symbol"

appRandomRotation>

<div appThrottledClick

[class]="cardSymbol"

(throttledClick)="onSymbolClick(cardSymbol)"

[throttleTime]="2000">

{{cardSymbol}}</div>

</div>

</div>

</div>

</ion-card-content>

</ion-card>

### ChatGPT 生成的 Ionic-React 组件

import { IonCard, IonCardContent } from '@ionic/react';

import RandomRotation from './RandomRotation';

import ThrottledClick from './ThrottledClick';

function CardComponent({ card, onSymbolClick }) {

return (

<IonCard>

<IonCardContent>

<div className={`symbols symbols-${card?.length}`}>

{card.map((cardSymbol, index) => (

<div key={index} className="symbol-wrapper">

<div className="symbol" ref={RandomRotation}>

<ThrottledClick throttleTime={2000} onClick={() => onSymbolClick(cardSymbol)}>

<div className={cardSymbol}>{cardSymbol}</div>

</ThrottledClick>

</div>

</div>

))}

</div>

</IonCardContent>

</IonCard>

);

}

export default CardComponent;

在上面的代码中，我们从@ionic/react 导入 IonCard 和 IonCardContent 组件，并将它们用作最外层组件。map 函数用于遍历 card 数组并渲染单个符号。我们在 JSX 中使用 map 函数而不是*ngFor 来循环遍历 card 数组。

对于 RandomRotation 指令，我们需要创建一个自定义的 React 组件，并将其附加为符号元素的 ref。类似地，对于 ThrottledClick 指令，我们正在创建一个自定义的 React 组件，并将 throttleTime 属性和 onClick 处理程序作为 props 传递给它。

最后，我们将 CardComponent 组件作为默认导出。

注意到它识别到需要提取 Angular 指令，并告诉我它们需要单独创建。它没有自动执行，只是因为我没有提供指令的代码。

### GhatGPT 的 Angular Material 组件

或者我根本不想使用 Ionic，而是想坚持使用 Angular 并使用 Angular Material 组件。

<mat-card>

<mat-card-content>

<div [ngClass]="'symbols symbols-' + (card?.length || 0)">

<div class="symbol-wrapper" *ngFor="let cardSymbol of card">

<div class="symbol" appRandomRotation>

<button mat-button appThrottledClick

[ngClass]="cardSymbol"

[节流时间]="2000"

(throttledClick)="onSymbolClick(cardSymbol)">

{{cardSymbol}}

</button>

</div>

</div>

</div>

</mat-card-content>

</mat-card>

ChatGPT 正确识别到我可以继续使用我的 Angular 指令。

希望您能看到通过这种方式能够尝试（甚至学习）多个框架是多么强大。

## 发布说明

ChatGPT 可以帮助您生成软件发布说明。这对我来说是相对新的，我花了一些时间找出最好的方法。我试图从实际的差异开始，但 ChatGPT 不喜欢长篇文字。相反，我决定使用 git 提交消息。这是我一个实际项目的示例：

添加照片 (#23)

* 添加了电容器和电容器存储

* 将学生服务转换为 promises？

* 修复了 DeleteStudent，但不完美

* 从存储服务中删除了 RxJS

* 学生 CRUD 正常工作

* 添加了一些更多功能

* 重构了一些存储代码

* 添加了新学生功能

* 添加了相机功能

* 在学生服务中标准化状态管理 (#22)

* 重构：为服务签名添加显式修饰符

* 重构：简化学生服务中的语法

* 修复：使用存储的数据初始化服务

* 重构：将状态更改移到学生服务中

* 重构：使用 routerLinkActive 来确定链接状态

* 任务：使用 prettier 格式化所有文件

* 任务：对字符串使用单引号

* 添加了相机功能

* 为研讨会做了一些小调整

* 为会议做了一些小调整

我请求 ChatGPT 将此列表分组并按优先级排列成为发布说明。

根据一个拉取请求的提交消息生成一些发布说明，按常见主题分组并按感知重要性排序。<我在这里粘贴了消息>

发布说明

功能

  添加了相机功能（＃23）

  添加了新的学生功能

  添加了电容器和电容器存储

  添加了一些额外的功能

修正

  修复了 DeleteStudent，但并不完美

  从存储服务中删除了 RxJS

改进

  在学生服务中标准化了状态管理（＃22）

  重构了一些存储代码

  重构了学生服务以使用 promises

  重构了学生服务以简化语法

  重构了学生服务以向服务签名显式添加修饰符

  重构学生服务以将状态更改移到学生服务中

  重构了代码以使用 routerLinkActive 来确定链接状态

  使用存储的数据初始化服务

杂项

  为研讨会做了一些小调整

  为会议做了一些小调整

  使用 prettier 格式化了所有文件

  更喜欢对字符串使用单引号

注意：提交信息“添加了相机功能”在原始列表中出现了两次，因此在这些发布说明中只包含一次。

它不是完美的，但它提供了一个很好的起点。

## 生成功能文档

我发现了一个名为“Mintlify Doc Writer”的 VS Code 扩展，它使用人工智能生成函数级文档。它了解多种语言，包括 Python、JavaScript、TypeScript、C++、PHP、Java、C#、Ruby 等等。

安装后，您可以通过突出显示函数或代码块并按下 Ctrl + .（英文句点）或 Cmd + .（英文句点）在 Mac 上来使用它。它将为您的代码创建一个适合您使用的语言的评论块。这里是我项目中一个示例函数和它创建的 JSDoc 注释。

我在编辑器中突出显示整个功能，按下 Cmd + . 然后观察它的神奇。

/**

* 它接受卡片数量和 slug，并返回一个卡组

* @param {number} numberOfCards - number - 卡组中的卡片数量

* @param [slug] - 将用于种子随机数生成器的字符串。如果有需要的话会很有用

* 如果你想要两次生成相同的卡组。

* @returns 一副卡牌

*/

buildDeck(numberOfCards: number, slug = ''): Deck {

this.shuffleService.seed(slug);

this.shuffledSymbols = this.shuffleService.shuffle(SYMBOLS);

const rawCards = this.dobbleService.dobble(numberOfCards);

const deck = rawCards.map(card =>

this.buildCard(card));

return this.shuffleService.shuffle(deck);

}

它在理解你代码的意义并给出基本注释方面做得还过得去。我发现真正有用的是将 Mintlify 与 Copilot 结合起来，帮助更充分地填充你的文档。

我从上面的文档开始，并按 Enter 提示 Copilot 来填充它们。下面是 JSDoc 注释的结果。

/**

* 它接受卡片的数量和 slug，然后返回一副卡片组。

* 随机数发生器使用 slug 作为种子，因此每次生成的是同一副牌。

* 如果不提供 slug，将随机生成牌组。

* @example

* const deck = deckService.buildDeck(5, 'my-slug');

* // 牌组永远都是相同的

* @example

* const deck = deckService.buildDeck(5);

* // 每次牌组都会不同

*



* @param {number} numberOfCards - number - 要生成的卡片数量

* @param [slug] - 一个用于种子随机数生成器的字符串。

* @returns 一副卡片组

*/

它想要走得更远，但我停在那里，觉得已经足够详细了。

你可以在 VS Code 市场上找到这个扩展：[`marketplace.visualstudio.com/items?itemName=mintlify.document`](https://marketplace.visualstudio.com/items?itemName=mintlify.document)

## Codeium

大约当我完成了这本书中 Copilot 部分的一半时，我收到了一个尝试类似 Copilot 的新工具的邀请。它叫 Codeium。像 Copilot 一样，它能集成到多个集成开发环境中，而且比 Copilot 目前的集成更多。最大的吸引点是，个人用户可以免费使用，并且他们声称它永远是免费的。你可以在[`codeium.com`](https://codeium.com)找到它。

Codeium 相信人工智能可以加速软件开发的各种“模式”，但与其让开发者安装多个产品来适应每种模式，他们正在开发一个能在这些模式之间无缝切换的单一产品。他们最新的公告是基于自然语言的仓库范围代码搜索，这与他们的自动完成功能相辅相成。

我不确定他们为什么决定放弃它，也不知道他们是如何决定的，但看起来是一个值得研究的可靠工具。我期待尝试它。
