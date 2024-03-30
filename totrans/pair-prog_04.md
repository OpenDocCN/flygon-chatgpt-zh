| ![图片](img/chapter_title_corner_decoration_left.png) |  | ![图片](img/chapter_title_corner_decoration_right.png) |
| --- | --- | --- |

![图片](img/chapter_title_above.png)

# 常见算法

![图片](img/chapter_title_below.png)

![一个屏幕的特写 由低置信度自动生成的描述](img/image003.jpg)

图片由[Pixabay](https://pixabay.com/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1486361)的[Markus Spiske](https://pixabay.com/users/markusspiske-670330/?utm_source=link-attribution&utm_medium=referral&utm_campaign=image&utm_content=1486361)提供

我最喜欢 AI 的用途之一是让它为常见算法生成代码。在本章中，我将重点介绍一些我用它解决常见问题的真实场景。

## IIFE

您知道 JavaScript 中的 IIFE 是什么吗？好吧，只需问 ChatGPT！

JavaScript 中的 IIFE 是什么，我为什么需要它，以及如何创建一个？

IIFE 代表立即调用的函数表达式。这是 JavaScript 中常用的设计模式，用于为您的代码创建一个私有作用域，并避免用变量和函数污染全局命名空间。

在需要封装一些代码并防止其影响页面上其他代码的情况下，您可能会使用 IIFE。例如，您可以使用 IIFE 来定义应用程序中的一个模块，其中模块的代码包含在 IIFE 的私有作用域内。

要创建一个 IIFE，您只需定义一个函数表达式并将其包装在括号中使其成为表达式。然后，您可以通过在其后附加一对括号立即调用该函数，就像这样：

(function() {

// 在这里放置您的代码

})();

在这个例子中，定义了一个匿名函数并立即调用。该函数为其中的代码创建了一个私有作用域，防止其中声明的任何变量或函数泄漏到全局作用域中。

请注意，围绕函数表达式的括号是必需的，因为它们使函数被解释为表达式而不是声明。没有这些括号，JavaScript 解析器会将函数解释为函数声明，这只能在某些上下文中使用。

这是一个相当令人印象深刻的解释。实际上，它给了我一个更长的解释，但我为您精简了一下。

实际上，使用 TypeScript，我们几乎不再需要使用 IIFE。事实上，如果我们让 ChatGPT 将其最后一个 IIFE 转换为等效的 TypeScript 类，会怎么样？

如果我们在 TypeScript 中使用类，那么该代码的等价物会是什么？

如果您要在 TypeScript 中使用类来实现与 IIFE 示例类似的结果，您可以定义一个类并使用构造函数方法来执行您的代码。

这里是一个例子：

class MyClass {

构造函数() {

// 在这里放置您的代码

}

}

new MyClass();

在这个例子中，当使用 new 关键字创建类的实例时，MyClass 构造函数会立即执行。

你也可以向构造方法传递参数，就像这样：

class MyClass {

constructor(arg1, arg2) {

// 你的代码在这里

}

}

new MyClass(val1, val2);

在这种情况下，参数 val1 和 val2 作为 arg1 和 arg2 传递给构造方法。

在 TypeScript 中使用类提供了额外的好处，如更好的类型检查和封装，以及定义公共和私有成员的能力。然而，IIFE 和类示例的总体目标是相同的：封装您的代码，防止其影响页面上的其他代码。

注意我不必重复我的请求，只需要求它重写“那段代码”。这是 ChatGPT 记住对话上下文的第一个例子。

## 数组函数

Copilot 和 ChatGPT 在帮助操作数组方面非常擅长。你只需要提出请求。

### Reduce

由于某种原因，我总是记不住如何使用 JavaScript 的 reduce 函数来计算数组中项目的总和。然而，GitHub Copilot 知道。我只需提供我想要实现的注释，让 Copilot 完成剩下的工作。

考虑以下“拼图”数组。这是我游戏 Foreword 中的一个片段，一个单词方块游戏。

// 这个例子的“拼图”部分数组

private demoPuzzles: Puzzle[] = [

{ id:88, size: 4, solution: ['abetbabeebontent'] },

{ id:89, size: 4, solution: ['icedcaveevendent'] },

{ id:90, size: 8, solution: ['abetracemirestun', 'armsbaitecruteen'] },

{ id:91, size: 8, solution: ['cageheaturicmyth', 'chumaerygaitetch'] }

];

注意一些拼图有一个解，一些有两个解。我的实际拼图数组有成千上万个元素。

现在假设我想计算我的拼图数组中的总解数。我提供了一个简单的注释给 Copilot，让它生成代码。

// 计算 demo Puzzle 数组中的总解数

const total = this.demoPuzzles.reduce((acc, puzzle) => acc + puzzle.solution.length, 0);

是的，我本可以使用 for 循环，或查找 Array.reduce 的语法，但 Copilot 为我完成了这项工作，只需一个注释。对我来说，这很高效！

### 过滤

接下来，假设我想找到数组中大小为 4 的所有拼图。我给 Copilot 第一个注释。然后它继续写第二个注释。

//  查找所有大小为 4 的拼图

//  查找所有大小为 8 的拼图

它能够做到这一点，因为它了解应用程序的上下文，并且可以看到我在做什么。通过识别一些拼图大小为 4，一些大小为 8，它提供了第二个注释。接下来发生的事情让我感到惊讶。它没有给我期望的数组过滤函数，而是给了我这个。

public findPuzzlesBySize(size: number): Puzzle[] {

return this.demoPuzzles.filter(puzzle => puzzle.size === size);

}

没错。它给了我一个通用函数，可以按任何大小查找谜题。

当我给 ChatGPT 相同提示时，它走了稍微不同的方向。

给定一个看起来像以下数组的数组，找到所有大小为 4 或 8 的谜题。（然后我粘贴了谜题数组）。

要查找所有大小为 4 或 8 的谜题，您可以在 demoPuzzles 数组上使用 filter 方法，并提供一个检查每个谜题大小的回调函数：

const filteredPuzzles = demoPuzzles.filter(puzzle => puzzle.size === 4 || puzzle.size === 8);

这将返回一个新数组，其中仅包含大小为 4 或 8 的谜题。

您还可以使用 forEach 方法检查每个谜题的大小，然后将匹配的谜题推入新数组：

const filteredPuzzles = [];

demoPuzzles.forEach(puzzle => {

if (puzzle.size === 4 || puzzle.size === 8) {

filteredPuzzles.push(puzzle);

}

});

这与 filter 方法实现了相同的结果。

无论哪种情况，结果过滤后的谜题数组将仅包含大小为 4 或 8 的谜题。

在这种情况下，ChatGPT 字面上带我，给了我一种找到大小为 4 或大小为 8 的谜题的方法。奇怪的是，它给我的代码将产生一个与原始内容相同的数组，这一点一点也不有用。

另一方面，Copilot 给了我更接近我所需的代码。可以认为这是 Copilot 的胜利。

### 排序

如果我想对数组进行排序怎么办？我知道 JavaScript 有一个 sort 函数，它接受一个描述排序方式的回调函数。但也许我不太记得语法。

要求 Copilot 对我的谜题数组进行排序，将较大（大小为 8）的谜题放在前面，给了我这个：

// 按大小排序谜题，最大的在前

puzzles = this.demoPuzzles.sort((a, b) => b.size - a.size);

注意，这次 Copilot 只给了我一行代码，而不是完整的函数。根据我的经验，这更符合 Copilot 通常的回应方式。

ChatGPT 给了我这个回应。

const sortedPuzzles = demoPuzzles.sort((a, b) => b.size - a.size);

这将返回一个新数组，其中包含按大小排序的谜题，最大的在前。

在这个例子中，sort 方法接受一个回调函数，比较 a 和 b 对象的 size 属性。通过从 b.size 减去 a.size，我们确保谜题根据大小按降序排序。

这两个函数是相同的，这是一个好迹象。我仍然喜欢 ChatGPT 为其建议提供解释，而 Copilot 则假定您只需要它来编写代码。

### 数组作为堆栈或队列

有时我们想要使用数组实现堆栈或队列。Copilot 和 ChatGPT 也可以帮助处理这个问题。

当我要求 ChatGPT 完成一组强类型的 TypeScript 函数时，它给了我这个：

生成一组强类型的 TypeScript 函数，以将数组视为堆栈或队列。

type Puzzle = { id: number; size: number; solution: string[] };

function pushToStack(stack: Puzzle[], puzzle: Puzzle): Puzzle[] {

return [...stack, puzzle];

}

function popFromStack(stack: Puzzle[]): [Puzzle | undefined, Puzzle[]] {

const poppedPuzzle = stack[stack.length - 1];

const newStack = stack.slice(0, stack.length - 1);

return [poppedPuzzle, newStack];

}

function enqueue(queue: Puzzle[], puzzle: Puzzle): Puzzle[] {

return [...queue, puzzle];

}

function dequeue(queue: Puzzle[]): [Puzzle | undefined, Puzzle[]] {

const dequeuedPuzzle = queue[0];

const newQueue = queue.slice(1);

return [dequeuedPuzzle, newQueue];

}

通常，它为每个函数提供了完整的解释。

Copilot 更加简洁，尽管它在我的第一个注释之后写了每一行（包括新注释）。

// 添加一个新拼图到拼图列表中的队列的函数

addPuzzle() {

this.demoPuzzles.push({ id: 92, size: 4, solution: ['cageheaturicmyth', 'chumaerygaitetch'] });

}

// 从拼图列表中移除一个拼图的函数

removePuzzle() {

this.demoPuzzles.pop();

}

// 添加一个新拼图到拼图列表中的队列的函数

pushPuzzle() {

this.demoPuzzles.unshift({ id: 92, size: 4, solution: ['cageheaturicmyth', 'chumaerygaitetch'] });

}

// 从拼图列表中移除一个拼图的函数

popPuzzle() {

this.demoPuzzles.shift();

}

注意它没有尝试为我创建一个新的拼图类型。它知道我已经有了数据，只给我提供了我在应用程序上下文中需要的内容。

然而，它完全错误地假设我想要一个硬编码的拼图文字（而且是无效的），而不是给函数一个拼图参数。

幸运的是，Copilot 只需要重新表述的注释来纠正那个错误的假设。

// 添加一个新拼图到拼图列表中的队列的函数，

// 以强类型的拼图对象作为参数

addPuzzle(puzzle: Puzzle) {

this.demoPuzzles.push(puzzle);

}

它对其他函数的处理都正确，但对于这个例子，我认为不需要再显示所有的代码。

### 数组转哈希

在我的一个项目中，我查询了一个远程网络服务以检索客户和销售信息，返回的数据结构看起来类似于以下内容。

"订单": [

{

"id": "订单 1",

"customerName": "约翰·史密斯",

"productName": "衬衫",

"数量": 2,

"价格": 25

},

{

"id": "订单 2",

"customerName": "简·多",

"productName": "裤子",

"数量": 1,

"价格": 40

},

{

"id": "订单 3",

"customerName": "鲍勃·约翰逊",

"productName": "袜子",

"数量": 3,

"价格": 10

}

]

注意，订单是一个数组，每个订单都是数组中一个独立的对象。现在想象一下，有数百或数千个这样的订单。如果我只想获取订单 72，我将不得不遍历整个数组。如果数据结构是哈希而不是数组，每个订单都有其 id 作为键，那么获取任意元素将更简单（也更快）。

我很快就能编写循环遍历整个数组并生成一个新的哈希对象的代码，但这是 ChatGPT 擅长的枯燥任务。这是我给它的提示，随后是它生成的代码。

ChatGPT 建议使用 reduce 函数，这实在是我从未想到的。就像我之前告诉过你的，这不是我擅长的函数之一。这是我的（许多？）盲点之一。

我在 TypeScript 中有一个具有以下结构的数组。（我将上面的 JSON 粘贴到这里）。我想将它从数组转换为哈希数组，以便可以通过其 "id" 地址访问每个对象。

你可以通过使用 reduce 方法将数组转换为哈希数组，并创建一个新对象，其中 "id" 属性作为键。这里是一个例子：

const hashArray = orders.reduce((acc, config) => {

acc[config.id] = config;

return acc;

}, {});

现在你可以通过像这样的"id"访问每个对象：hashArray["order2"]。

然后我进一步完善它，要求一个独立的函数，它为我创建了一个（未显示）。

## 字符串操作

你经常发现自己经常操作文本吗？我知道我会。从长输入中提取较小的文本片段，确定一个字符串是否存在于另一个字符串中，处理填充等。这些事情相当简单，但如果不必要的话，我宁愿不输入这些东西。

### 字符串搜索

考虑在长字符串中查找单词的每个出现的问题。ChatGPT 会如何处理？

const text = "The quick brown fox jumps over the lazy dog.";

// 查找所有出现的子字符串"the"（不区分大小写）

const substring = /the/gi;

const matches = text.match(substring);

// 打印匹配项

console.log(matches);

ChatGPT 直接使用了正则表达式。我将在本书后面更深入地讨论正则表达式。

Copilot 也使用了正则表达式，但它走了完全不同的方向。

const regex = /the/gi;

let m;

while ((m = regex.exec(text)) !== null) {

// 这是为了避免与零宽匹配无限循环

if (m.index === regex.lastIndex) {

regex.lastIndex++;

}

// 结果可以通过 `m` 变量访问。

m.forEach((match, groupIndex) => {

console.log(`找到匹配项，组 ${groupIndex}：${match}`);

});

}

老实说，我并不完全确定 Copilot 给我的东西。为了好玩，我将 Copilot 的代码示例粘贴到 ChatGPT 中，并要求它解释给我听。这就是它说的。

这段 JavaScript 代码使用正则表达式在给定文本中找到子字符串 "the" 的所有出现，并将匹配项记录到控制台。以下是它的工作原理：

const regex = /the/gi; - 这一行创建了一个正则表达式 regex，用 /the/ 语法匹配子字符串 "the"。g 和 i 标志分别用于执行全局搜索和不区分大小写搜索。

let m; - 这一行声明了一个未初始化的变量 m。

while ((m = regex.exec(text)) !== null) { - This line sets m to the result of calling the regex.exec(text) method, which returns an array of information about the next match of the regular expression in the text string. The while loop continues as long as m is not null.

if (m.index === regex.lastIndex) { regex.lastIndex++; } - This line checks whether the match is a zero-width match (i.e., an empty string), and if so, increments the lastIndex property of the regex object to avoid an infinite loop.

m.forEach((match, groupIndex) => { console.log(Found match, group ${groupIndex}: ${match}); }); - This line loops through each match in the m array using the forEach() method, and logs each match and its group index to the console using a template literal.

总的来说，这段代码是前面代码示例的更高级版本，使用 regex.exec()方法迭代每个匹配并访问其属性。使用 forEach()允许更细粒度控制输出，并提供访问匹配的组索引，这在处理更复杂的正则表达式时会很有用。

Do you see what it did? Read that final paragraph carefully. ChatGPT recognized that the code I pasted from Copilot was related to my original question, and then explained that it was a more advanced example of the same concept. Truly amazing!

### 移除空格

有时，你可能面对一大段过多空白的文本。在给定这样的字符串的情况下，你会如何去除其中多余的空白，同时保留重要的文本呢？

对于这个例子，我要求 ChatGPT 生成一些带有大量额外空白的“lorem ipsum”文本示例。

const loremIpsumWithWhitespace = `

Lorem ipsum  dolor sit amet, consectetur adipiscing elit.  Fusce molestie turpis  nec  felis malesuada accumsan. Vestibulum  tincidunt lacus nec nulla dignissim blandit. Morbi tristique, enim eu imperdiet luctus, nisl turpis aliquam nunc,  eu interdum purus  velit  quis velit.  Curabitur vel semper tellus,  at iaculis lectus.  Morbi sed lectus  ac nibh eleifend tristique.  Praesent sagittis elit vel dui consequat,  eu maximus purus molestie. Integer varius  pharetra odio, non vestibulum urna lobortis et.  Sed et eleifend lorem, quis mollis ipsum.

Pellentesque  consectetur  mauris sed risus laoreet,  vel malesuada augue convallis.  Nullam vestibulum commodo metus, id tristique est suscipit id. Etiam pretium sagittis malesuada.  Vivamus sit amet mi lorem.  Etiam hendrerit euismod libero, nec  accumsan massa laoreet vel.  Donec  viverra felis et urna fringilla, non convallis tellus egestas. Suspendisse faucibus quam in erat sagittis  dignissim. Duis maximus risus sit amet eros bibendum feugiat.

接下来，我要求一个通用函数，它将接受这种类型的输入并返回移除所有不重要空白的字符串。

function removeInsignificantWhitespace(text) {

// Replace all whitespace characters with a single space

const stripped = text.replace(/\s+/g, " ");

// 移除前导/尾随空格和换行符

return stripped.trim();

}

这个函数首先使用正则表达式（/\s+/g）匹配所有出现的一个或多个空白字符（空格、制表符、换行符等），然后使用 replace()方法将它们替换为一个空格字符。

最终的字符串然后传递给 trim()方法，该方法会移除任何前导或尾随空格或换行符。

这确保最终输出只包含必要的空格字符（例如单词之间的空格），而不包含不必要的空格字符。

对于 Copilot 的测试，我从前面的长 JavaScript 常量开始，并给了一个类似的提示。它的结果有点简洁。

// 从字符串中移除所有空格的函数

function removeWhitespace(text: string) {

return text.replace(/\s/g, '');

}

Copilot 结果有趣的地方在于，当我粘贴了冗长的文本后，它建议了自己的注释。永远记住，Copilot 的强项在于它对整个应用程序的意识。

### 空格填充

现在，让我们考虑一下谜题数组。如果我想要使用只有文本的固定宽度字体生成一些漂亮的格式，我该如何做？ChatGPT 给了我以下函数，以及输出看起来像的示例：

const printTable = (puzzles: Puzzle[]): void => {

console.log('ID  Size  Solution');

console.log('——————————-');

puzzles.forEach(puzzle => {

console.log(`${puzzle.id.toString().padEnd(4, ' ')}${puzzle.size.toString().padEnd(6, ' ')}${puzzle.solution[0]}`);

});

};

printTable(demoPuzzles);

这段代码将以固定宽度字体的形式输出 demoPuzzles 数组，如下所示：

––––––––

![image](img/scene_break.png)

ID  Size  Solution

——————————-

![image](img/scene_break.png)

88  4  abetbabeebontent

89  4  icedcaveevendent

90  8  abetracemirestun

91  8  cageheaturicmyth

Copilot 给了我一些不同的东西，但我认为在这种情况下它作弊了。

// 以只使用文本的方式将谜题数组打印为表格，适用于使用固定宽度字体。

printPuzzles() {

let puzzleTable = this.demoPuzzles.map(p => {

return { id: p.id, size: p.size, solution: p.solution.join(' ') };

});

console.table(puzzleTable);

}

从技术上讲，console.table 确实做到了我要求的，所以在这方面是正确的。我决定再给它一个提示，看看能否让它写出更接近 ChatGPT 的东西。

// 以只使用文本的方式将谜题数组打印为表格，适用于使用固定宽度字体的输出，使用 console.log。

printPuzzles() {

// 获取最长的谜题 id，以便填充 id 列以对齐谜题数据。

const longestId = this.demoPuzzles.reduce((longest, puzzle) => Math.max(longest, puzzle.id.toString().length), 0);

// 打印标题行。

console.log(`id${' '.repeat(longestId - 2)} | size | solution`);

console.log('-'.repeat(longestId + 2) + '-+-' + '-'.repeat(5) + '-+-' + '-'.repeat(16));

// 打印谜题行。

this.demoPuzzles.forEach(puzzle => {

console.log(`${puzzle.id}${' '.repeat(longestId - puzzle.id.toString().length)} | ${puzzle.size} | ${puzzle.solution.join(' ')}`);

});

}

第二次运行效果更好。你觉得呢？我喜欢它寻找最长 ID 的功能，这样我就可以正确填充列。这是一个很好的点子。

### 生成 CSV 文件

如果我想要将数组输出为逗号分隔的文件呢？Copilot 给了我几乎与上面相同的代码，但带有一些额外的逻辑。

// 生成包含谜题数组的 CSV 文件

generateCsv() {

// 创建一个带有标题行和每个谜题行的 CSV 文件。

const csv = 'id,size,solution\r\n' + this.demoPuzzles.map(puzzle => `${puzzle.id},${puzzle.size},"${puzzle.solution.join(' ')}"`).join('\r\n');

// 将 CSV 文件写入磁盘。

require('fs').writeFileSync('puzzles.csv', csv);

}

依赖人工智能来为你工作的一个危险是它可能会创建看起来合理但存在错误的代码。在这种情况下，如果我的任何字段包含逗号，这个函数生成的输出很可能会导致 CSV 文件无法阅读。

ChatGPT 给了我几乎相同的代码，只是它考虑了谜题字段中可能存在的逗号。

import * as fs from 'fs';

const generateCSV = (puzzles: Puzzle[]): void => {

const header = 'id,size,solution\n';

const rows = puzzles.map(puzzle => `${puzzle.id},${puzzle.size},"${puzzle.solution.join(';')}"\n`);

const csv = header + rows.join('');

fs.writeFileSync('puzzles.csv', csv);

};

generateCSV(demoPuzzles);

请注意，这两个解决方案都假设我在使用 Node，因为每个解决方案都使用了 fs 库。ChatGPT 特别注意告诉我我需要来自 NodeJS 的 fs 模块。

请注意，为了运行此代码，您需要安装 fs 模块和 Node.js 运行时。

### 生成 HTML

我也可以要求它为我生成 HTML。ChatGPT 确实按照我要求的方式做了，再次记住了我的谜题数组和对象的形状。

创建一个 JavaScript 函数，将谜题数组输出为 HTML 表格

function printTable(puzzles) {

const table = document.createElement('table');

const headerRow = document.createElement('tr');

const idHeader = document.createElement('th');

const sizeHeader = document.createElement('th');

const solutionHeader = document.createElement('th');

idHeader.textContent = 'ID';

sizeHeader.textContent = '大小';

solutionHeader.textContent = '解决方案';

headerRow.appendChild(idHeader);

headerRow.appendChild(sizeHeader);

headerRow.appendChild(solutionHeader);

table.appendChild(headerRow);

puzzles.forEach(puzzle => {

const row = document.createElement('tr');

const idCell = document.createElement('td');

const sizeCell = document.createElement('td');

const solutionCell = document.createElement('td');

idCell.textContent = puzzle.id;

sizeCell.textContent = puzzle.size;

solutionCell.textContent = puzzle.solution.join(';');

row.appendChild(idCell);

row.appendChild(sizeCell);

row.appendChild(solutionCell);

table.appendChild(row);

});

document.body.appendChild(table);

}

printTable(demoPuzzles);

在这里，我认为它可能已经超越了自己。我原本期望看到一堆硬编码的带有 HTML 字符的字符串。我没想到它会使用 DOM 操作，但当然，在许多情况下这可能是更好的解决方案。

Copilot 会做得一样好吗？实际上，它做了我最初期望的事情。

// 将谜题数组输出为 HTML 表格的函数

printPuzzlesAsHtml() {

// 获取最长的谜题 ID，以便我们可以填充 ID 列以对齐谜题数据。

const longestId = this.demoPuzzles.reduce((longest, puzzle) => Math.max(longest, puzzle.id.toString().length), 0);

// 打印标题行。

console.log('<table>');

console.log('<tr><th>id</th><th>size</th><th>solution</th></tr>');

// 打印谜题行。

this.demoPuzzles.forEach(puzzle => {

console.log(`<tr><td>${puzzle.id}</td><td>${puzzle.size}</td><td>${puzzle.solution.join(' ')}</td></tr>`);

});

console.log('</table>');

}

这并不意味着它无法使用 DOM API。我所要做的就是稍微改变我的提示。

// 使用 DOM API 输出谜题数组为 HTML 表格的函数

private outputPuzzles(puzzles: Puzzle[]): void {

const table = document.createElement('table');

const header = document.createElement('tr');

header.innerHTML = '<th>ID</th><th>Size</th><th>Solution</th>';

table.appendChild(header);

puzzles.forEach(puzzle => {

const row = document.createElement('tr');

row.innerHTML = `<td>${puzzle.id}</td><td>${puzzle.size}</td><td>${puzzle.solution}</td>`;

table.appendChild(row);

});

document.body.appendChild(table);

}

我不确定这样做是否更好。最终它为我构建了一个 DOM 调用和 HTML 字符串文本的混合体。这就是这些 AI 的问题；通常您必须尝试多次相同的方法才能得到您要找的代码。

### 结论

本章主要关注数组和字符串操作，这是我日常工作中的大部分内容。您可能经常使用不同的算法。请放心，这两个工具都将为您节省大量输入时间。要记住的重要事情是提示与您要求它们使用的语言一样重要。

此外，正如你所看到的，有时你必须尝试多个提示才能得到正确的代码。最后，请确保验证代码的正确性。任何工具都可以创建看起来很棒但不考虑边缘情况的代码。

记住，归根结底，你是程序员，而不是 AI。
