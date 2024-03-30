# Wolfram|Alpha 作为将计算知识超能力带入 ChatGPT 的途径

![Wolfram|Alpha 作为将计算知识超能力带入 ChatGPT 的途径](img/Image00094.jpg "Wolfram|Alpha 作为将计算知识超能力带入 ChatGPT 的途径")

## ChatGPT 和 Wolfram|Alpha

当事情突然“奏效”时总是令人惊讶。2009 年我们与[Wolfram|Alpha](https://www.wolframalpha.com/)合作时发生了这种情况。2020 年我们的[物理项目](https://www.wolframphysics.org/)也是如此。现在，[OpenAI](https://openai.com/)的[ChatGPT](https://chat.openai.com/chat)也是如此。

我已经追踪[神经网络技术](https://www.wolfram.com/language/core-areas/machine-learning/)很长时间了（实际上大约 43 年）。即使在过去几年里观察到的发展，我发现 ChatGPT 的表现非常出色。最终，突然间，这是一个可以成功生成几乎任何内容的系统，非常类似于人类可能写的内容。这令人印象深刻，也很有用。而且，正如我在[其他地方讨论的](https://writings.stephenwolfram.com/2023/02/what-is-chatgpt-doing-and-why-does-it-work/)，我认为它的成功可能告诉我们一些关于人类思维本质的非常基本的事情。

但是，虽然 ChatGPT 在自动执行类似人类的重要任务方面取得了显著成就，但并非所有有用的任务都是如此“类似人类”。其中一些更加正式和结构化。事实上，我们文明在过去几个世纪中取得的伟大成就之一就是建立数学、精确科学——最重要的是现在的计算——的范式，并创造了一个与纯人类思维所能实现的完全不同的能力之塔。

我自己多年来一直深度参与计算范式，致力于构建一种[计算语言](https://writings.stephenwolfram.com/2019/05/what-weve-built-is-a-computational-language-and-thats-very-important/)，以尽可能多地以形式符号方式表示世界上的事物。在这样做的过程中，我的目标是构建一个可以“计算辅助”——并增强——我和其他人想要做的事情的系统。我像一个人类一样思考事物。但我也可以立即调用[Wolfram 语言](https://www.wolfram.com/language/)和 Wolfram|Alpha，利用一种独特的“计算超能力”，让我做各种超越人类能力的事情。

这是一种非常强大的工作方式。重点是，这不仅对我们人类重要。对于类似人类的人工智能来说同样重要，甚至更重要——立即赋予它们我们可以称之为计算知识超能力，利用结构化计算和结构化知识的非人类力量。

我们刚刚开始探索这对 ChatGPT 意味着什么。但很明显，可能会发生一些奇妙的事情。Wolfram|Alpha 与 ChatGPT 做的事情非常不同，方式也截然不同。但它们有一个共同的接口：自然语言。这意味着 ChatGPT 可以像人类一样“与”Wolfram|Alpha 交流——Wolfram|Alpha 将从 ChatGPT 获取的自然语言转化为精确的符号计算语言，以便应用其计算知识能力。

数十年来，人们在思考人工智能方面存在着一种“统计方法”（像 ChatGPT 使用的那种）和“符号方法”（实际上是 Wolfram|Alpha 的起点）之间的二分法。但现在——多亏了 ChatGPT 的成功，以及我们在让 Wolfram|Alpha 理解自然语言方面所做的所有工作——终于有机会将这两者结合起来，创造出比任何一种方法都更强大的东西。

## 一个基本示例

在其核心，ChatGPT 是一个生成语言输出的系统，其“遵循”了网络上和书籍以及其他训练中使用的材料中存在的模式。值得注意的是，输出的人类化程度是多么惊人，不仅仅是在小规模上，而且在整篇文章中都是如此。它有连贯的论点，引入了它学到的概念，往往以有趣和意想不到的方式。它产生的内容在语言层面上总是“统计上可信的”。但是——尽管最终结果令人印象深刻——这当然并不意味着它自信地提出的所有事实和计算都一定是正确的。这里有一个我刚刚注意到的例子（是的，ChatGPT 具有固有的内置随机性，所以如果你尝试这个，你可能不会得到相同的结果）：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img1.png)

这听起来相当令人信服。但事实证明这是错误的，因为 Wolfram|Alpha 可以告诉我们：

![从芝加哥到东京有多远？](https://www.wolframalpha.com/input?i=How+far+is+it+from+Chicago+to+Tokyo%3F)

当然，公平地说，这正是 Wolfram|Alpha 擅长的事情：可以将其转化为可以基于其结构化、策划知识进行的精确计算。但有趣的是，人们可以考虑 Wolfram|Alpha 自动帮助 ChatGPT 完成这项任务。人们可以[通过编程方式](https://reference.wolfram.com/language/ref/WolframAlpha.html)向 Wolfram|Alpha 提问（也可以使用[web API](https://products.wolframalpha.com/api)，等等）：

| ![](img/Image00097.gif) |
| --- |

现在再次向 ChatGPT 提问这个问题，并附上这个结果：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img4.png)

ChatGPT 非常礼貌地接受了更正，如果你再次提出问题，它会给出正确的答案。显然，处理与 Wolfram|Alpha 的来回可能有更简洁的方式，但很高兴看到即使这种非常直接的纯自然语言方法基本上已经起作用。

但是 ChatGPT 为什么会在第一次就犯这个特定的错误呢？如果它在训练中的某个地方（例如来自网络）看到了芝加哥和东京之间的具体距离，它当然可以做对。但这是一个神经网络可以轻松做到的泛化的情况——比如从许多城市之间的距离的例子中——这是不够的；这里需要一个实际的计算算法。Wolfram|Alpha 处理事情的方式完全不同。它接受自然语言，然后——假设可能的话——将其转换为精确的计算语言（即 Wolfram 语言），在这种情况下：

| ![](img/Image00099.jpg) |
| --- |

[城市](https://reference.wolfram.com/language/ref/entity/City.html)的坐标和[计算它们之间距离的算法](https://reference.wolfram.com/language/ref/GeoDistance.html)随后成为 Wolfram 语言中内置的计算知识的一部分。是的，Wolfram 语言拥有[大量内置的计算知识](https://www.wolfram.com/knowledgebase/)——这是我们数十年工作的结果，精心策划了现在一个庞大的持续更新的数据量，实施（并经常发明）方法和模型和算法——并系统地建立了一个涵盖一切的计算语言。

## 还有一些例子

ChatGPT 和 Wolfram|Alpha 的工作方式非常不同，具有非常不同的优势。但为了了解 ChatGPT 如何利用 Wolfram|Alpha 的优势，让我们讨论一些情况，在这些情况下，单独 ChatGPT 并不能完全做对。ChatGPT 和人类一样，经常在数学方面遇到困难。

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img6.png)

这是一个有趣的、散文风格的回答。但实际结果是错误的：

![3 的 73 次方是多少？](https://www.wolframalpha.com/input?i=What+is+3+to+the+power+73%3F)

但如果 ChatGPT“咨询”Wolfram|Alpha，它当然能够做对。让我们尝试一些稍微复杂的东西：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img8a.png)

乍一看，这个结果看起来很棒，我会倾向于相信它。然而，事实证明，这是错误的，因为 Wolfram|Alpha 可以告诉我们：

![半轴为 3 和 12 的椭圆周长](https://www.wolframalpha.com/input?i=circumference+of+an+ellipse+with+half+axes+3+and+12)

而且，使用 ChatGPT 做数学作业（而不能请教 Wolfram|Alpha）可能是一个坏主意。它可以给出一个非常合理的答案：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img10.png)

但是，如果 ChatGPT 没有“真正理解数学”，它基本上不可能可靠地得到正确答案。在这种情况下，答案再次是错误的：

![x² cos(2x)的积分是多少？的积分是多少？")](https://www.wolframalpha.com/input?i=What+is+the+integral+of+x%5E2+cos%282x%29)

尽管如此，ChatGPT 甚至可以编造一个看起来非常合理的“得出答案的方式”（并不是它真正“做到的方式”）。而且，相当迷人（也很有趣）的是，它给出的解释与一个不理解数学的人可能犯的错误非常相似：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img12.png)

有各种各样的情况会导致“不真正理解事物含义”带来麻烦：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img13.png)

听起来很有说服力。但是这是不正确的：

![中美洲最大的国家是哪些？](https://www.wolframalpha.com/input?i=What+are+the+largest+countries+in+Central+America%3F)

ChatGPT 似乎在某处正确地学到了这些基础数据，但���并不“理解其含义”足以正确排列这些数字：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img15.png)

而且，可以想象找到一种方法来“修复这个特定的错误”。但关键是，像 ChatGPT 这样基于生成语言的人工智能系统在需要进行结构化计算时并不适用。换句话说，要“修复”几乎无限数量的“错误”才能弥补即使是 Wolfram|Alpha 的几乎无限小的一部分所能实现的结构化方式。

而且“计算链”越复杂，你越可能需要借助 Wolfram|Alpha 来正确解决问题。在这里，ChatGPT 给出了一个相当混乱的答案：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img16.png)

而且，正如 Wolfram|Alpha 告诉我们的那样，它的结论是不正确的（因为它在某种程度上已经“知道”）：

![哪些行星卫星比水星大？](https://www.wolframalpha.com/input?i=What+planetary+moons+are+larger+than+Mercury%3F)

每当涉及具体（例如数量化）数据，即使是相当原始的形式，很多时候往往更像是“Wolfram|Alpha 的故事”。以下是一个例子，灵感来自长期以来备受喜爱的 Wolfram|Alpha 测试查询“土耳其有多少只火鸡？”：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img18.png)

再次，这似乎（起初）完全合理，并且甚至引用了相关来源。然而，事实证明，这些数据基本上只是“凭空捏造”的：

![土耳其的家畜数量](https://www.wolframalpha.com/input?i=Livestock+populations+in+Turkey)

不过，非常好的一点是，ChatGPT 可以轻松地“要求核实事实”：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img20.png)

现在将这些通过 Wolfram|Alpha API 进行处理：

| ![](img/Image00115.gif) |
| --- |

现在我们可以要求 ChatGPT 修正其原始回答，注入这些数据（甚至以粗体显示注入的位置）：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img22.png)

当涉及实时（或位置等相关）数据或计算时，“注入事实”的能力尤为重要。ChatGPT 不会立即回答这个问题：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img23.png)

但这里有一些相关的 Wolfram|Alpha API 输出：

| ![](img/Image00118.gif) |
| --- |

如果我们将这些输入到 ChatGPT 中，它将生成一个漂亮的“论文风格”结果：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img25a.png)

有时，计算机和人类之间会有一些有趣的互动。以下是一个相当异想天开的问题，向 Wolfram|Alpha 提出的（甚至还会询问您是否想要“软冰淇淋”）：

![一立方光年的冰淇淋有多少卡路里？](https://www.wolframalpha.com/input?i=How+many+calories+are+there+in+a+cubic+light+year+of+ice+cream%3F)

ChatGPT 起初对体积的概念有点困惑：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img27.png)

但后来似乎“意识到”那么多冰淇淋相当荒谬：

![点击放大](https://content.wolfram.com/uploads/sites/43/2023/01/swchattech1923img28.png)

## 未来之路

机器学习是一种强大的方法，特别是在过去的十年中，它取得了一些显著的成功——其中 ChatGPT 是最新的例子。[图像识别](https://reference.wolfram.com/language/ref/ImageIdentify.html)。[语音转文本](https://reference.wolfram.com/language/ref/SpeechRecognize.html)。[语言翻译](https://reference.wolfram.com/language/ref/TextTranslation.html)。在每一个案例中，以及许多其他案例中，都突破了一个门槛——通常是相当突然的。并且某些任务从“基本上不可能”变为“基本上可行”。

但结果基本上永远不会是“完美的”。也许有些事情有 95%的成功率。但无论如何努力，另外的 5%仍然难以捉摸。对于某些目的，人们可能认为这是一个失败。但关键点在于，通常有各种重要的用例，对于这些用例，95%已经“足够好”。也许是因为输出是某种情况下根本没有“正确答案”的东西。也许是因为人们只是试图呈现一些可能性，然后由人类或系统算法选择或完善。

完全值得注意的是，一个数百亿参数的神经网络，一次生成一个标记的文本，可以做 ChatGPT 可以做的事情。鉴于这种戏剧性的——以及意想不到的——成功，人们可能会认为，如果只是“训练一个足够大的网络”，就能做任何事情。但事实并非如此。关于计算的基本事实——尤其是[计算不可简化](https://www.wolframscience.com/nks/chap-12--the-principle-of-computational-equivalence#sect-12-6--computational-irreducibility)的概念——清楚地表明最终是不可能的。但更重要的是我们在机器学习的实际历史中看到的。会有一个重大突破（就像 ChatGPT）。改进不会停止。但更重要的是，会发现一些成功的用例，这些用例可以成功完成可以做的事情，而不会被不能做的事情所阻碍。

是的，会有很多情况下，“原始的 ChatGPT”可以帮助人们写作，提供建议，或生成对各种文档或互动有用的文本。但当涉及到必须完美的事情时，机器学习并不是解决问题的方法——就像人类也不是一样。

正是我们在上面的例子中看到的。ChatGPT 在“类似人类的部分”表现出色，在那里没有确切的“正确答案”。但当它被“置于困境”需要精确的东西时，它经常失败。但这里的重点是有一个很好的方法来解决这个问题——将 ChatGPT 连接到 Wolfram|Alpha 及其所有计算知识“超能力”。

在 Wolfram|Alpha 内部，一切都被转化为计算语言，并转化为精确的 Wolfram 语言代码，这在某种程度上必须是“完美的”才能可靠地发挥作用。但关键点在于 ChatGPT 不必生成这些。它可以生成其通常的自然语言，然后 Wolfram|Alpha 可以利用其自然语言理解能力将该自然语言翻译为精确的 Wolfram 语言。

在许多方面，有人可能会说 ChatGPT 从未“真正理解”事物；它只是“知道如何生成有用的东西”。但对于 Wolfram|Alpha 来说情况就不同了。因为一旦 Wolfram|Alpha 将某事转换为 Wolfram 语言，它所得到的是一个完整、精确、正式的表示，从中可以可靠地计算事物。不用说，有许多“人类感兴趣的”事物，我们没有[正式的计算表示](https://writings.stephenwolfram.com/2016/10/computational-law-symbolic-discourse-and-the-ai-constitution/) —尽管我们仍然可以用自然语言谈论它们，尽管可能不够精确。对于这些事物，ChatGPT 就只能靠自己，凭借其非常出色的能力。

但就像我们人类一样，有时候 ChatGPT 需要更正式和精确的“动力辅助”。但关键是它不必在表达自己想要的内容时“正式和精确”。因为 Wolfram|Alpha 可以用类似于 ChatGPT 的母语——自然语言与其交流。当它转换为其母语——Wolfram 语言时，Wolfram|Alpha 会负责“添加形式和精确性”。我认为这是一个非常好的情况，具有巨大的实际潜力。

这种潜力不仅仅局限于典型的聊天机器人或文本生成应用程序。它延伸到诸如进行数据科学或其他形式的计算工作（或编程）等事物。在某种意义上，这是一种立即获得两全其美的方式：ChatGPT 的人类化世界和 Wolfram 语言的计算精确世界。

那么 ChatGPT 直接学习 Wolfram 语言呢？是的，它可以这样做，事实上它已经开始了。最终，我完全期待类似 ChatGPT 的东西将能够[直接在 Wolfram 语言中运行](https://writings.stephenwolfram.com/2015/11/how-should-we-talk-to-ais/)，并且在这样做时非常强大。这是一个有趣且独特的情况，这是由于 Wolfram 语言的[计算语言特性](https://writings.stephenwolfram.com/2019/05/what-weve-built-is-a-computational-language-and-thats-very-important/)，它可以广泛地用计算术语讨论世界和其他地方的事物。

沃尔夫拉姆语言的整个概念是将我们人类所思考的事物，能够以计算方式表示和处理。普通的编程语言旨在提供告诉计算机具体要做什么的方法。沃尔夫拉姆语言——作为一种全面的计算语言——涉及的范围远远超出了这个。实际上，它旨在成为一种语言，人类和计算机都可以在其中“以计算方式思考”。

许多世纪以前，当数学符号被发明时，它首次提供了一个简化的媒介，用于“数学思考”事物。它的发明很快导致了代数、微积分，最终导致了各种数学科学的产生。沃尔夫拉姆语言的目标是为计算思维做类似的事情，尽管现在不仅仅是为了人类，还为了启用计算范式所能开启的所有“计算 X”领域。

我自己从拥有沃尔夫拉姆语言作为“思考语言”中受益匪浅，过去几十年来，通过人们通过沃尔夫拉姆语言“以计算方式思考”，取得了许多进展，这是令人欣喜的。那么，ChatGPT 呢？嗯，它也可以做到这一点。至于它将如何运作，我还不太确定。但这不是关于 ChatGPT 学习如何进行沃尔夫拉姆语言已经知道如何做的计算。这是关于 ChatGPT 学习如何像人类一样使用沃尔夫拉姆语言。这是关于 ChatGPT 提出“创造性论文”的类比，但现在不是用自然语言而是用计算语言写成。

我长期以来一直讨论人类撰写的[计算性文章的概念](https://writings.stephenwolfram.com/2017/11/what-is-a-computational-essay/)——这些文章以自然语言和计算语言的混合形式进行交流。现在的问题是 ChatGPT 能否写出这些文章，并能够使用沃尔夫拉姆语言作为传递“有意义沟通”的方式，不仅仅是对人类，还包括对计算机。是的，这里涉及到一个潜在有趣的反馈循环，涉及到沃尔夫拉姆语言代码的实际执行。但关键点在于，沃尔夫拉姆语言代码所代表的“思想”的丰富性和流畅性——与普通编程语言不同——更接近于 ChatGPT 在自然语言中“神奇地”成功处理的内容。

或者换个说法，沃尔夫拉姆语言——就像自然语言一样——是足够表达的，人们可以想象用它为 ChatGPT 编写一个有意义的“提示”。是的，沃尔夫拉姆语言可以直接在计算机上执行。但作为 ChatGPT 的提示，它可以用来“表达一个想法”，其“故事”可以继续。它可能描述一些计算结构，让 ChatGPT 来“即兴创作”关于该结构的[计算性描述](https://writings.stephenwolfram.com/2021/11/the-concept-of-the-ruliad/)，这将根据它通过阅读人类写的许多东西所学到的东西，对人类来说会是“有趣的”。

由于 ChatGPT 意外成功，突然打开了各种令人兴奋的可能性。但目前有一个即时的机会，通过 Wolfram|Alpha 为 ChatGPT 赋予计算知识超能力。这样它不仅可以产生“似乎合理的类人输出”，而且可以利用 Wolfram|Alpha 和沃尔夫拉姆语言中封装的整个计算和知识体系来输出。
