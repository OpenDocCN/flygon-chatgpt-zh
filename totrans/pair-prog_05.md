| ![image](img/chapter_title_corner_decoration_left.png) |  | ![image](img/chapter_title_corner_decoration_right.png) |
| --- | --- | --- |

![image](img/chapter_title_above.png)

# 学习 RxJS

![image](img/chapter_title_below.png)

![人体的抽象图像，二进制数和行星](img/image015.jpg)

由 [Gerd Altmann from Pixabay](https://pixabay.com/users/geralt-9301/?amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=3175073) 的图像

与 Copilot 和 ChatGPT 一起处理常见算法让我想到它们可能会是学习 JavaScript 中的 React 扩展（RxJS）或者至少帮助我记住一些它的非显而易见的语法的非常有用的工具。

很多人不喜欢使用 RxJS，认为它太复杂了。他们倾向于避开它，但我认为这很遗憾。是的，RxJS 可能有一个陡峭的学习曲线，但学会以“反应式”的方式思考并有效地使用 RxJS 是值得努力的。我想知道 Copilot 在帮助其他人学习 RxJS 方面能有多大帮助。

对于本章，我将继续使用之前的那组谜题数组。如果你需要回顾，它看起来是这样的：

// 用于此示例的“谜题”部分数组

private demoPuzzles: Puzzle[] = [

{ id:88, size: 4, solution: ['abetbabeebontent'] },

{ id:89, size: 4, solution: ['icedcaveevendent'] },

{ id:90, size: 8, solution: ['abetracemirestun', 'armsbaitecruteen'] },

{ id:91, size: 8, solution: ['cageheaturicmyth', 'chumaerygaitetch'] }

];

## from 和 of

保持上面的谜题数组，让我们假设这些谜题是游戏的一部分，并且它们存在为一个 Observable 流。此外，假设游戏从外部来源获取它们。现在，我们不需要担心它们来自哪里。每当出现一个新的谜题时，游戏将对其进行“某些”处理。

因此，我要求 Copilot 就是这样做的。这是我写的注释以及它为我写的代码：

// 从示例谜题数组创建一个新的 Observable

const puzzles$ = from(this.demoPuzzles);

完美！RxJS 的 from 函数从一个数组创建了一个新的 Observable，在数组的每个元素上都会发出一个新值。这正是我想要的。还请注意，它使用了一个常见的命名约定，即在标识符后面添加 $，表示它是一个 Observable。

还有另一个 RxJS 操作符，即 of，也可以从数组创建一个 Observable。虽然使用它也是有效的，但 of 只会创建一个 Observable 并发出一次，包含整个数组。这不是我想要的，但不知何故 Copilot 知道（或者猜到）了。

## filter

现在我们有了一个 Observable，让我们对它做点什么。让我们从一些更简单和更常见的 RxJS 操作符开始：map 和 filter。

RxJS 的 filter 操作符用于实现其名字的含义：过滤现有的流，只包括与某些提供的条件匹配的项目。

如果游戏玩家只想看到尺寸为 4 的谜题怎么办？我们能让 Copilot 为我们做到这点吗？这是我输入的评论以及 Copilot 根据评论生成的代码的回应：

// 仅将谜题筛选为尺寸为 4 的谜题

const size4$ = puzzles$.pipe(filter(puzzle => puzzle.size === 4));

它给了我们什么？它创建了一个新的 Observable，使用了之前的一贯命名惯例称为 size4$。

它还正确理解了使用 filter 操作符，我们首先必须使用 RxJS 的 pipe 函数。每当你使用 RxJS Observable 并且想要在订阅值流之前对其进行操作时，你需要将操作符列表传入 pipe 函数中。

然后，为了选择尺寸为 4 的谜题，它正确地推断出我需要 filter 操作符，它接受一个回调函数来定义流中每个项目应该如何匹配。如果它看起来很熟悉，那是因为它的工作方式与 Array.filter 完全相同。

你可能会认为我在评论中有点耍花招，使用了“Filter”这个词。如果我使用不同的短语会发生什么？好吧，我决定找出答案。我删掉了上面的代码及其评论，然后输入了完全新的东西。我想避免暗示“选择”或“过滤”之类的词语。这是它给我的。

// 给我尺寸为 4 的谜题

const size4$ = puzzles$.pipe(filter(puzzle => puzzle.size === 4));

它仍然正确地决定我需要在 pipe 中添加 filter 操作符，它将“four”转换为 4 。相当令人印象深刻。

## map

让我们看看如果我们只想要每个上述谜题的一部分会发生什么。也许我们只会显示每个谜题的第一个解决方案。

每当你想要将一个对象强制转换为另一个对象时，你首先会使用 map 操作符，它的工作方式与 JavaScript 数组函数 map 非常相似。

就像以前的例子一样，这里是我的评论和生成的代码：

// 仅显示每个谜题的第一个解决方案

const firstSolution$ = size4$.pipe(map(puzzle => puzzle.solution[0]));

你看到它的操作了吗？它正确地假设我将使用先前命令的输出，所以它给了我之前的 size4$value。就像我以前指出的那样，这表明 Copilot 意识到你源代码的上下文。

我认为我唯一不同意的是 firstSolution$ 的名字，但我现在想不出更好的名字。

此时，我有一个经过过滤和映射的 Observable，它只会在产生时给我尺寸为 4 的谜题的第一个解决方案。

## 能为我合并它们吗？

如果我构造我的评论尝试让 Copilot 为我编写整个管道会怎么样？让我们看看它的样子。

// 给我每个尺寸为 4 的谜题的第一个解决方案

puzzles$.pipe(

filter(puzzle => puzzle.size === 4),

map(puzzle => puzzle.solution[0]),

first()

).subscribe(solution => console.log(solution));

老实说，这很接近，但这不是我想要的。我觉得注释中的“of”这个词可能会让它困惑。另外，它坚持要添加 subscribe，而我并不想要它这样做。在构建 RxJS 解决方案时，我尽量不订阅，因为这要求我记住何时必须取消订阅。我稍后会谈到这一点。

我决定给它一些更多的提示，看看我是否能帮助它。在这种情况下，我在下一行键入了注释和 const，暗示 Copilot 我想要一个常量而不是订阅。

// 给我每个大小为 4 的谜题的第一个解

const

firstSolution$ = puzzles$.pipe(

filter(puzzle => puzzle.size === 4),

map(puzzle => puzzle.solution[0]),

first()

);

更好了，但它添加了 first()，而这绝对不是我想要的。它被注释中的“first”这个词所迷惑。

为什么我不想使用 first()？这个操作符只会给我 Observable 流中的第一个值，而这不是我想要的。相反，我想要来自流中每个值的第一个谜题。这是微妙但重要的区别。

让我们看看我是否可以做出最后一次调整以更接近。 

// 给我每一个大小为四的谜题中的第一个解

const firstSolution$ = puzzles$.pipe(

filter(puzzle => puzzle.size === 4),

map(puzzle => puzzle.solution[0])

);

这正是我想让它做的。对我来说，关键是你需要非常明确地表达你的意图。不要害怕拒绝它的第一次尝试。你总是可以再试一次。

## take

take 操作符用于从 Observable 中选择（或取出）一定数量的值，然后自动断开连接。Copilot 完全知道如何为我构建这个结构。

// 仅取出前两个大小为 8 的谜题

const firstTwoSize8Puzzles$ = this.demoPuzzles$.pipe(

filter(puzzle => puzzle.size === 8),

take(2)

);

我觉得我可能会给它一个曲球，所以我要求它只记录上一个示例中的谜题。它做得很对，建立在它刚刚创建的代码上。

// 将上一个示例中的前两个大小为 8 的谜题记录到控制台中

firstTwoSize8Puzzles$.subscribe(puzzle => console.log(puzzle));

## tap

有时你希望在不影响流或任何下游操作符的情况下查看 Observable 流中的值。tap 操作符就是为这种情况设计的。我能让 Copilot 重新编写我的上面的记录语句以使用 tap 吗？

// 取出前两个大小为 8 的谜题，但将所有的谜题记录到控制台

const demoPuzzles2$ = demoPuzzles$.pipe(

tap(puzzles => console.log(puzzles)),

filter(puzzles => puzzles.size === 8),

take(2)

);

这看起来差不多，尽管我对它的命名并不满意。事实上，Copilot 似乎记得我不喜欢订阅我的 Observables，所以我会忽略这个奇怪的名称。

## subscribe

尽管我不愿意过早使用 subscribe，但我能否让 Copilot 订阅 Observable？毫无疑问，只要有正确的提示。事实证明，一旦我按下回车键，Copilot 立即提供了以下代码，而我并没有采取进一步的行动。

demoPuzzles2$.subscribe(puzzles => console.log(puzzles));

这正是我希望它做的。我想它读懂了我的想法。

## 那么 ChatGPT 对 RxJS 怎么样呢？

ChatGPT 对此的帮助较少，但并非因为你可能期望的原因。起初，我以为它会更好，特别是因为它倾向于解释它产生的代码。但我对 ChatGPT 对 RxJS 不满意的原因是，它似乎对我的话过于字面。

例如，当我询问它使用 take 来获取前两个元素时，它实际上将一切都写成了一个完整的函数。Copilot 倾向于在你需要时为你提供所需的代码。

ChatGPT 擅长解释 Copilot 写的代码。让我们在进行下一步之前看看这将如何运行。我询问 ChatGPT 这段代码的作用。它给出了以下分析，我确信你会认为这很令人印象深刻。

以下代码块的作用是什么？

const firstSolution$ = puzzles$.pipe(

filter(puzzle => puzzle.size === 4),

map(puzzle => puzzle.solution[0])

);

当然，你提供的代码确实完成了以下工作：

创建一个 observable puzzles$，它发出一个更大的 Puzzle 对象数组的每个元素，类似于我们之前看到的 demoPuzzles 数组。

使用管道方法创建一系列操作符，这些操作符将应用于 puzzles$ observable 的每个发射。

链中的第一个操作符是 filter，它过滤掉没有大小属性为 4 的拼图。这意味着只有大小为 4 的拼图将被允许继续传递。

链中的第二个操作符是 map，它将每个剩余的拼图映射到它的第一个解决方案。因为每个 Puzzle 对象的 solution 属性是一个字符串数组，所以我们使用数组索引操作符[0]来选择数组的第一个元素作为解决方案。

生成的 observable firstSolution$ 发出每个拼图有 4 个大小的第一个解决方案。

总结一下，该代码通过大小过滤 Puzzle 对象的流，然后将剩余的拼图映射到它们的第一个解决方案，从而产生一个表示每个有 4 个拼图大小的第一个解决方案的字符串流。

## 总结一下？

诚然，在这里我使用的操作符远不止我使用的几个。RxJS 非常庞大，拥有 100 多个操作符，尽管大多数开发者通常只使用其中不到十几个。本章的目标不是对 RxJS 进行彻底的测试。

我的目的是看看 Copilot 是否可以帮助新手开发者了解 RxJS，并且只知道它的一点点功能。稍后在更合适的情境下会使用更多 RxJS。

Copilot 能帮助某人学习 RxJS 或更好地使用它吗？我持怀疑态度，因为它并不总是给我想要的代码。一个刚开始接触 RxJS 的新手可能没有足够的经验来知道什么时候接受，什么时候再试一次。

Copilot 可能是有经验的 JavaScript 开发人员的更好选择，他们了解 RxJS 的基础知识。他们可以合理地期望它会选择正确的操作符来满足他们的需求。

最终，虽然我发现 Copilot 是一个有用且[大多数时候]无害的工具，但它经常需要被迫做正确的事情。

我并不认为它是 RxJS 初学者的工具，他们可能会被错误的代码误导。

ChatGPT，另一方面，在帮助新手理解代码方面表现出色。只需将其粘贴到文本框中并请求解释。这是强大的，不应忽视。
