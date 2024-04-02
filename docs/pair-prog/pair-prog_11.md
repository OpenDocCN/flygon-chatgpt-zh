



# 单元测试



![自动生成描述的夜空图片](img/image013.jpg)

图片由[Gerd Altmann](https://pixabay.com/users/geralt-9301/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=3625406)提供, 来自[Pixabay](https://pixabay.com/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=3625406)

作为开发者，我们知道单元测试在确保软件的质量和可靠性方面的重要性。然而，我们也知道创建有效的单元测试所带来的挑战 —— 所需的时间和精力，测试过程的复杂性，以及确保全面覆盖的挑战。个人而言，我经常为了节省时间而跳过单元测试，只是以后当错误和 bug 不可避免地出现时后悔。

在本章中，我们将探讨 Copilot 和 ChatGPT 如何帮助简化创建有效单元测试的痛点，通过生成一个简单的 Angular 服务的测试用例。通过这个过程，我们将看到这些工具如何帮助增强单元测试过程。

## 该服务

这个服务本身就足够简单。我想建立一种可以在应用程序进行服务调用时设置和检索两个不同的唯一 ID 的方法。第一个是“会话 ID”，它将作为特定用户在给定会话中的所有网络调用的 HTTP 标头进行设置。除非应用用户手动刷新屏幕、关闭浏览器或注销并重新登录，否则它不会改变。

第二个是“相关 ID”。这也会随着每个请求一起发送，但会随着每个请求而改变。我不会展示网络调用，只展示生成这些 ID 的服务。

## 服务 API

服务实现了三个主要要求。

1.  每当我询问时，它将给我相同的会话 ID，除非不存在会话 ID。在这种情况下，它需要给我一个新的并返回。

1.  它将在我每次请求时为我提供一个新的相关 ID。我不应该两次得到相同的 ID。

1.  它将提供一种让我强制获取新会话 ID 的方法。

实现将使用 UUID 分别作为会话 ID 和相关 ID。如果您不了解 UUID 这个术语，我请 ChatGPT 定义它：

什么是 UUID？

UUID，或称为通用唯一标识符，是一种用于在分布式系统中唯一标识信息的标识符类型。UUID 是一个 128 位数字，表示为一系列十六进制数字，通常以连字符分隔的组显示。UUID 旨在在空间和时间上都是唯一的，这意味着即使由不同系统在不同时间生成，它们也不应该发生冲突或重复。UUID 通常用于各种上下文中，包括作为数据库中的键，作为存储系统中文件或对象的标识符，以及作为 Web 应用程序中的会话 ID。使用 UUID 有助于确保在多个系统需要引用相同实体时没有歧义或冲突，并且通过使识别符更难猜测或操纵，还有助于提供额外的安全层。

简而言之，UUID 是用于在各个系统中标识和关联 HTTP 调用的完美标识符。

代码本身简单明了。我将在此处重现整个服务以供参考。

import { Injectable } from '@angular/core';

import { v4 as uuidv4 } from 'uuid';

@Injectable({

providedIn: 'root'

})

export class CorrelationService {

conversationId: string = '';

resetConversationId() {

this.conversationId = uuidv4();

return this.conversationId;

}

getConversationId() {

return this.conversationId || this.resetConversationId();

}

getCorrelationId() {

return uuidv4();

}

}

有三个函数：

+   resetConversationId: 创建一个全新的 UUID 并将其分配给内部 coversationId 变量，并返回该新值。

+   getConversationId: 如果内部 conversationId 有值，则返回该值，否则调用 resetConversationID 并返回其结果。

+   getCorrelationId: 每次调用时都简单地返回一个新的 UUID。

正如我所说，这是一个非常简单的服务。

## 测试框架

我想首先回顾由 Angular CLI 自动生成的测试代码。我并不是指这是一个全面的测试介绍，但我会解释基础知识。这应该足够让您在自己的测试中跟上。

默认情况下，当您使用 Angular CLI 创建服务时，它还会为您创建一个默认的测试文件。在我的情况下，它为我创建了这个。

import { TestBed } from '@angular/core/testing';

import { CorrelationService } from './correlation.service';

describe('CorrelationService', () => {

let service: CorrelationService;

beforeEach(() => {

TestBed.configureTestingModule({});

service = TestBed.inject(CorrelationService);

});

it('should be created', () => {

expect(service).toBeTruthy();

});

});

第一个导入行引入了名为 TestBed 的 Angular 测试类。这个类包含大部分基本的测试框架。

第二个是引入要测试的服务，也被称为“被测试系统”或 SUT。这被分配给变量 service。

### describe

describe('CorrelationService', () => {

使用大多数 JavaScript 测试框架，测试被组织成一个或多个 describe 函数。这些函数封装了相关的测试，并将内部测试与其他不相关的测试隔离开。它们可以被嵌套，你马上就会看到。

调用 describe 函数带有两个参数。

1.  测试标签。在这种情况下，要测试的服务的名称。

1.  包含测试本身的函数。这里是一个箭头函数。它包含一个代表服务的单个变量，但目前尚未分配任何值给它。

### beforeEach

beforeEach(() => {

TestBed.configureTestingModule({});

service = TestBed.inject(CorrelationService);

});

直接在这个函数内部还有另一个函数调用，beforeEach，它本身包含另一个箭头函数。这个函数在每个单元测试执行之前被测试框架调用。

在这个函数内部调用了 TestBed.configureTestingModule({})，你可以看到它被传递了一个空对象作为它唯一的参数。这个对象包含了测试模块的选项。它几乎可以接受正常的 Angular 模块能接受的所有选项。大多数测试使用这个来配置 Angular 的依赖注入系统，以便注入 SUT 所需的测试替身。我的服务没有依赖项，所以没有什么可配置的。

### 其他函数

没有显示的是一些其他函数，它们可以包含设置/拆卸指令：

+   beforeAll：在描述中运行任何测试之前调用一次。这通常用于设置所有测试所需的状态，但这些状态不会从一个测试转到另一个测试。

+   afterEach：在描述中的每个单元测试函数之后调用。这用于拆卸或重置状态，撤消测试可能创建的任何副作用。

+   afterAll：在描述中的所有测试运行完毕后调用一次。同样，这用于重置全局状态，以便来自描述函数的效果不会渗入其他地方。

### it

it('应该被创建', () => {

expect(service).toBeTruthy();

});

这个函数定义了一个单元测试。你可以在描述中创建尽可能多个的 it 函数。生成的测试带有一个单独的 it 函数。它的签名与描述的签名相匹配，它接受一个标签和定义测试的函数。

与其封闭的描述结合起来，这些函数应该这样读：

[描述标签] [测试标签]：通过/失败

因此，当你阅读预生成的测试时，它应该是这样的：

CorrelationService 应该被创建：通过

在创建自己的测试时，请考虑这种措辞。

Angular 测试还有很多内容，但我想确保在开始之前我已经解释了你会看到的内容。

## 测试

解释清楚了，让我们看看 GitHub Copilot 生成的测试。如果你在跟着做，应该很容易为每个要测试的函数创建一个全新的描述。这并非绝对必要。将所有测试放在一个描述中是完全合法的，但我发现这样做可以给 Copilot 提供编写测试所需的上下文。

我输入了下面的第一行作为提示，Copilot 为我生成了测试。

describe('resetConversationId', () => {

it('应该返回 conversationId', () => {

service.resetConversationId();

expect(service.getConversationId()).toBeTruthy();

});

这个测试简单地检查调用 getConversationId()是否返回一个真值或非空值。

it('如果存在应该返回 conversationId', () => {

service.resetConversationId();

const conversationId = service.conversationId;

expect(service.getConversationId()).toEqual(conversationId);

});

这个测试调用 getConversationId()两次，期望两个值相同。如果不是，测试将失败。

it('如果存在应该返回 conversationId', () => {

service.resetConversationId();

const conversationId = service.conversationId;

expect(service.getConversationId()).toEqual(conversationId);

});

});

不，这不是打字错误。它生成了两个相同的测试。我不知道为什么。有时候你会在 Copilot 中看到这种情况。这可能有点烦人，但目的是为了让我少写一些测试。在这种情况下，我对结果感到满意。

它生成了适当运行该函数的测试。我可以进行的一个简单重构是将调用 service.resetConversationId()移动到 beforeEach 函数中，确保在执行每个测试之前都会调用它。

看着它给我的测试，我不确定我是否需要为 resetConversationId 编写单独的测试，但很容易添加它们。

现在让我们看看 getCorrelationId 的测试。根据要求，每次调用它都应该返回一个新的值。对于这个，我没有让 Copilot 完成我的描述，而是使用了一个注释让它写一切。

// 测试 getCorrelationId

it('应该返回 correlationId', () => {

expect(service.getCorrelationId()).toBeTruthy();

});

它为我构建了一个函数，但没有进一步。实际上，这不是一个非常有用的测试，但它确实通过了。就像之前一样，它只是确保函数返回一个真值。

这还远远不够完整，所以我再试一次。这次，我给了它两个更详细的注释。

// 测试 getCorrelationId 每次返回不同的值

it('应该返回 correlationId', () => {

const correlationId = service.getCorrelationId();

expect(service.getCorrelationId()).not.toEqual(correlationId);

});

这有点好一点。这个测试确保调用 getCorrelationId()两次会返回不同的值。如果我们调用它 100 次呢？

// 测试 getCorrelationId 返回不同值多次

it('should return correlationId', () => {

const correlationIds = [];

for (let i = 0; i < 100; i++) {

correlationIds.push(service.getCorrelationId());

}

expect(correlationIds.length).toEqual(100);

expect(new Set(correlationIds).size).toEqual(100);

});

这是一个更好的测试。这个测试调用 getCorrelationId() 100 次，并检查所有 100 个结果是否唯一。

我可能不会想到使用 JavaScript 的 set 对象来确保我永远不会得到相同的值，但这是一个聪明和优雅的解决方案。Set 不能包含重复项。如果在 100 次迭代后集合包含了 100 个值，那么所有生成的值都是唯一的。

这只是表明 Copilot 最擅长处理详细的注释。

## ChatGPT

什么是 ChatGPT？从理论上讲，它应该和编写这些测试一样出色，所以让我们看看它给我们带来了什么。

正如我们在整本书中所看到的，让 ChatGPT 给你合理的代码的窍门在于提供正确的提示。对于这个提示，最好提供完整的服务实现，并要求它使用 Jasmine（或者如果你喜欢的话，Jest）编写测试。

以以下 Angular 服务为例，使用 Jasmine 编写完整的单元测试套件。 <我在这里粘贴了整个类代码>

ChatGPT 如你要求的那样，提供了完整的测试套件。

import { CorrelationService } from './correlation.service';

import { v4 as uuidv4 } from 'uuid';

描述('CorrelationService', () => {

let service: CorrelationService;

beforeEach(() => {

service = new CorrelationService();

});

it('should create the service', () => {

expect(service).toBeTruthy();

});

描述('resetConversationId()', () => {

it('should set conversationId to a UUID', () => {

service.resetConversationId();

expect(uuidv4.test(service.conversationId)).toBe(true);

});

it('should return the new conversationId', () => {

const conversationId = service.resetConversationId();

expect(service.conversationId).toEqual(conversationId);

});

});

describe('getConversationId()', () => {

it('should return conversationId if set', () => {

service.conversationId = 'test-id';

expect(service.getConversationId()).toEqual('test-id');

});

it('should call resetConversationId() and return conversationId if not set', () => {

spyOn(service, 'resetConversationId').and.returnValue('new-id');

expect(service.getConversationId()).toEqual('new-id');

expect(service.resetConversationId).toHaveBeenCalled();

});

});

描述('getCorrelationId()', () => {

it('should return a UUID', () => {

const correlationId = service.getCorrelationId();

expect(uuidv4.test(correlationId)).toBe(true);

});

it('should return a different UUID each time', () => {

const correlationId1 = service.getCorrelationId();

const correlationId2 = service.getCorrelationId();

expect(correlationId1).not.toEqual(correlationId2);

});

});

});

有趣的是，这些测试甚至都无法编译。虽然乍一看似乎合理，但其中两个测试假定 uuidv4 库有一个测试函数。

expect(uuidv4.test(service.conversationId)).toBe(true);

至少我使用的版本，v9，不支持。

我注释掉了那两个测试，其余的都通过了。

这里的要点是什么？使用 Copilot 可能会更加手动，但你对生成的内容有更精细的控制。使用 ChatGPT，你会得到一大堆代码，你要么仔细校对，要么就接受现状。

我不推荐后者。

## 测试 HTTP 调用

测试一个简单的服务是一回事。一旦你做过几次，模式就很简单，也很直接了。我们从 AI 中获得的真正价值在于为那些并不简单和直接的事物编写测试，比如测试 HTTP 调用。

这是我在概念上知道如何做的事情，但我永远无法第一次就正确地使用语法。例如，我知道我必须导入并使用 Angular 的 HttpClientTestingModule。有一定的调用顺序和设置必须完成。每次都是一个试错的过程，直到我做对为止。

不再。

我让 ChatGPT 帮我为一个虚构的天气服务编写测试。我定义的服务本身看起来像这样。

export class WeatherService {

http: HttpClient = inject(HttpClient);

getWeather(zipcode: string) {

return this.http.get(`weather.com/api/forecast/${zipcode}`);

}

}

ChatGPT 为这个提供了一个相当不错的测试套件。

import { TestBed } from '@angular/core/testing';

import { HttpClientTestingModule, HttpTestingController } from '@angular/common/http/testing';

import { WeatherService } from './weather.service';

describe('WeatherService', () => {

let service: WeatherService;

let httpMock: HttpTestingController;

beforeEach(() => {

TestBed.configureTestingModule({

imports: [HttpClientTestingModule],

providers: [WeatherService]

});

service = TestBed.inject(WeatherService);

httpMock = TestBed.inject(HttpTestingController);

});

afterEach(() => {

httpMock.verify();

});

––––––––



it('should be created', () => {

expect(service).toBeTruthy();

});

it('should return the weather for a given zipcode', () => {

const mockResponse = {

temperature: 68,

description: '晴天'

};

const zipcode = '90210';

service.getWeather(zipcode).subscribe(response => {

expect(response).toEqual(mockResponse);

});

const request = httpMock.expectOne(`weather.com/api/forecast/${zipcode}`);

expect(request.request.method).toBe('GET');

request.flush(mockResponse);

});

});

它只处理了“快乐路径”，但给了我我想要的结构。正如我所暗示的，测试 Angular 的 HttpClient 是棘手的，我通常第一次就搞错了。

由于某种原因，我似乎永远记不住在 afterEach 中包含验证，以确保服务只发出了预期的 HTTP 调用，不多不少。我也不记得创建模拟的 expectOne 和 flush 函数的正确顺序。

让 ChatGPT 为我构建这个测试套件节省了很多时间。一旦我有了结构，我就可以填补空白（或让 Copilot 为我完成）。

这次测试一次通过了，顺便说一句。

## 远非完美

毫无疑问，并非一切都是美好的。我们已经看到，ChatGPT 对 2021 年中期之后的任何事情都一无所知。在这方面，Copilot 更好，因为它是在几乎所有的 GitHub 上进行训练的，而且它可以查看你的代码。

我尝试让它们每个人帮我编写一个用于 Angular HttpInterceptor 的单元测试，以与本章开头的 CorrelationService 一起使用。我使用拦截器在每次传出的 HTTP 调用上添加 correlationId 和 coversationId 值作为 HTTP 标头。

ChatGPT 知道基于类的 HttpInterceptor，但对于刚在 Angular 15 中引入的新的 functional HttpInterceptorFn 一无所知。可预见的是，ChatGPT 对此一无所知，坚称不存在这样的东西。

Copilot 尝试了，但没有给我任何可以使用的东西。结果甚至不值得在这里重现。

毫无疑问，事情会变得更好。目前，可以将这视为更多证据，即尽管 AI 变得越来越好，但我们软件开发人员仍然需要了解我们的技艺。我们可以利用这些工具来帮助我们，但我们始终需要意识到它们的局限性。
