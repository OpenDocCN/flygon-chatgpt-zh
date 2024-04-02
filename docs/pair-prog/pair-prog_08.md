



# 数据生成



![带有骰子、卡片和筹码的赌桌](img/image020.jpg)

图片由[Pixabay 的 Thorsten Frenzel](https://pixabay.com/users/thorstenf-7677369/?amp;utm_medium=referral&amp;utm_campaign=image&amp;utm_content=4178462)提供

## 永远不要缺少应用程序的样本数据

生成样本数据是应用程序开发的一个关键方面，因为它允许开发人员在受控环境中测试和完善他们的软件。在本章中，我们将探讨 Copilot 和 ChatGPT 在为应用程序生成样本数据方面的有效性。我们将从简单的示例开始，逐渐转向更复杂的想法，分享沿途的成功和失败。通过本章的结束，您将更好地了解这些工具的能力和局限性，以及如何利用它们来改进您的应用程序开发过程。

与以往一样，我将展示我的简单评论，然后是 AI 建议的内容，必要时附有评论。

## Lorem Ipsum 文本

首先，让我们看看 Copilot 为一般请求“lorem ipsum”文本提供了什么建议。

// 生成一段 lorem ipsum 文本

const text = require('lorem-ipsum').loremIpsum({count: 1, units: 'paragraphs'});

这根本不是我期望的。我希望它可以简单地为我构建一些。老实说，我从来没有听说过[lorem-ipsum npm 包](https://www.npmjs.com/package/lorem-ipsum/v/1.0.5)，所以我决定去找它。我安装了这个包并运行了我的代码，输出如下：

Aliquip qui est officia tempor elit aliquip。Lorem culpa ea exercitation aliqua aliquip et aute。Eiusmod ad sunt labore proident id reprehenderit ullamco dolore laborum excepteur ad eiusmod laboris。Et duis consectetur culpa nulla velit adipisicing minim velit dolore deserunt commodo id occaecat。Mollit aliquip consectetur aliquip duis eu incididunt ut amet deserunt qui。

再次，这不是我期望的，但它做对了。当它给我可用的代码时，我几乎不能抱怨。

ChatGPT 完全按照我的期望做了，没有任何额外提示。它就是有效的。

Lorem ipsum dolor sit amet, consectetur adipiscing elit. Sed auctor, purus non ornare congue, magna magna porta velit, eget malesuada velit velit vel mi. Sed velit velit, suscipit vel dolor eu, malesuada ornare elit. Sed dictum id elit vel dictum. Donec malesuada risus vitae ipsum placerat, eget aliquam velit ullamcorper. Sed in eros vel velit blandit elementum. Sed nec tempor tellus. Sed non eros euismod, feugiat eros ut, gravida dolor. Nam auctor malesuada est, euismod euismod erat tempor id.

## 美国学校列表

对于下一个实验，我想要一个可以在美国找到的学校列表。这个实验采用了与上面相同的模式，但结果不同。

// 美国的学校列表

const schools = require('us-schools').schools;

console.log(schools);

不幸的是，没有这样的 npm 包存在，至少我找不到。我开始对这个过程的信心比开始时更少。

另一方面，ChatGPT 再次成功。

给我一个美国学校的列表作为 JavaScript 数组

const schools = [

{ name: "哈佛大学", state: "马萨诸塞" },

{ name: "斯坦福大学", state: "加利福尼亚" },

{ name: "普林斯顿大学", state: "新泽西" },

{ name: "耶鲁大学", state: "康涅狄格" },

{ name: "哥伦比亚大学", state: "纽约" },

{ name: "布朗大学", state: "罗德岛" },

{ name: "宾夕法尼亚大学", state: "宾夕法尼亚" },

{ name: "康奈尔大学", state: "纽约" },

{ name: "达特茅斯学院", state: "新罕布什尔" }

];

## 伪造带有地址的客户

想知道我是否能从 Copilot 中获得成功，我继续进行我的预定清单。它能为我生成一些虚假客户吗？

// 生成一个随机客户姓名和地址列表

const faker = require('faker');

const customers = [];

for (let i = 0; i < 100; i++) {

customers.push({

name: faker.name.findName(),

address: faker.address.streetAddress(),

city: faker.address.city(),

state: faker.address.state(),

zip: faker.address.zipCode(),

});

}

我过去曾使用[faker](https://www.npmjs.com/package/@faker-js/faker)（[`www.npmjs.com/package/@faker-js/faker`](https://www.npmjs.com/package/@faker-js/faker)），所以我对这个有更高的期望。我安装了 faker npm 包，并添加了一个 console.table(customers) 命令。这会在浏览器控制台中以网格形式打印数组，每个“客户”占据一行。

这给了我错误，因为 require 行不正确。正确的版本是

const { faker } = require('@faker-js/faker');

一旦我修复了那个问题，我被告知 findName 已被弃用，应使用 fullName，但代码仍在运行。我得到了一组虚假客户的输出。

GitHub Copilot 是在多年的现有代码基础上训练的，因此某些代码将基于较旧的模式或已弃用的库。这是不可避免的，但好消息是随着我们继续训练，它只会变得更好。

鉴于您已经看到的内容，您可能更信任 ChatGPT 能够做对这个。如果您打赌的话，您会输掉。

生成一个随机客户姓名和地址列表

const faker = require('faker');

let customers = [];

for(let i = 0; i < 10; i++) {

let customer = {

name: faker.name.findName(),

address: faker.address.streetAddress()

}

customers.push(customer);

}

console.log(customers);

ChatGPT 做出了与 Copilot 完全相同的错误。这并不完全出乎意料，因为 ChatGPT 训练所使用的数据于 2021 年结束。它并不知道在那之后对库和框架进行的任何更新。更意外的是，它写出的代码几乎与 Copilot 完全相同。

稍作修改后，我并不完全感到泄气，于是让 ChatGPT 再次尝试，这次不使用 faker。我想看看它是否能够自己完成。它给出的结果比我预期的要多，但它做到了我的要求。

生成一个不使用 faker 库的随机客户姓名和地址列表

let customers = []

const firstNames = ['John', 'Emily', 'Jessica', 'Michael', 'David',

'Jacob', 'Madison', 'Ethan', 'Elizabeth']

const lastNames = ['Smith', 'Johnson', 'Williams', 'Jones', 'Brown',

'Miller', 'Wilson', 'Moore', 'Taylor']

const streets = ['Main St', 'High St', 'Park Ave', '1st St', '2nd St',

'4th St', '5th St', '6th St', '7th St']

const cities = ['New York', 'Los Angeles', 'Chicago', 'Houston',

'Philadelphia', 'San Antonio', 'San Diego', 'Dallas']

const states = ['NY', 'CA', 'TX', 'AZ', 'PA', 'TX', 'CA', 'TX', 'CA']

const zipCodes = ['10001', '90001', '60601', '77001', '85001', '19019',

'78201', '92201', '75201', '95201']

for(let i = 0; i < 10; i++) {

let customer = {

name: firstNames[Math.floor(Math.random() * firstNames.length)] +

' ' + lastNames[Math.floor(Math.random() * lastNames.length)],

address: streets[Math.floor(Math.random() * streets.length)] + ' ' +

cities[Math.floor(Math.random() * cities.length)] + ' ' +

states[Math.floor(Math.random() * states.length)] + ' ' +

zipCodes[Math.floor(Math.random() * zipCodes.length)]

}

customers.push(customer)

}

这次代码生成的另一个有趣之处：我要求 ChatGPT 将代码包装在 60 个字符处，并使用单引号而不是双引号，它确实做到了。

## 随机颜色生成

你曾经需要一些随机颜色吗？我承认这个有点不那么令人印象深刻，但是我决心继续下去。此刻，我做出的假设是，Copilot 会继续使用 faker。

// 为每个客户添加一个随机颜色

const colors = ['red', 'green', 'blue', 'yellow', 'orange', 'purple'];

for (const customer of customers) {

customer.color = colors[Math.floor(Math.random() * colors.length)];

}

当然，我错了。这更接近在开始使用 faker 之前我期望它能够做到的。我希望得到一些 CSS 颜色而不是名字。

// 为每个客户添加一个喜欢的 CSS 颜色

for (const customer of customers) {

customer.color = faker.commerce.color();

}

什么？它又回到了使用 faker！这没关系，但是 commerce.color()显然也已经被弃用了。Copilot 从未建议使用更新的函数。不过，它奏效了，这可能是我们唯一可以期待的。

ChatGPT 接受了我提出的注释，重新编写了整个代码块，并在适当的位置添加了新功能。以下是它添加的相关行：

为每个客户添加一个随机颜色

const colors = ['红色', '绿色', '蓝色', '橙色', '黄色', '紫色', '粉色', '棕色', '灰色', '黑色']

for(let i = 0; i < 10; i++) {

let customer = {

. . .

color: colors[Math.floor(Math.random() * colors.length)]

}

customers.push(customer)

}

console.log(customers)

如果我让它使用 CSS 颜色，它会做得像那样好吗？它表现得非常完美，将上述颜色数组更改为一个 colorValues 数组。

为每位顾客添加一个喜爱的 CSS 颜色

const colorValues = ['#ff0000', '#00ff00', '#0000ff', '#ffa500',

'#ffc0cb', '#a52a2a', '#808080', '#000000']

注意，ChatGPT 在生成的代码中不使用分号。我不知道该怎么办，但如果你想要包含它们，你可以简单地要求它这样做。

顺便说一下，ChatGPT 很乐意使用假数据库来生成颜色。我不会在这里包含那段代码，因为它还坚持使用一个无法运行的版本。

正如我之前所说的，这些东西并不完美。

## 电影标题

电影标题呢？它们能生成真实的电影还是听起来真实但又是假的电影？

// 为每位顾客添加一个喜爱的电影

for (const customer of customers) {

customer.movie = faker.commerce.productName();

}

显然，假数据库对电影一无所知，而 Copilot 则无法（或不愿意）建议其他任何事情。

我认为这个是失败的，至少对于 Copilot 来说是这样的。

ChatGPT 确实做到了我最初希望它能做到的事情。它为我提供了一系列电影标题。

// 为每位顾客添加一个喜爱的电影

const movies = ['教父', '肖申克的救赎', '黑暗骑士', '黄金三镖客', '指环王:王者归来', '低俗小说', '黑客帝国', '好家伙', '飞越疯人院', '七武士']

然后，它向每位顾客中添加了来自该数组的随机元素（未显示）。

鉴于电影列表，我并不对 Copilot 能否处理其余的列表抱有很高的期望。尽管如此，我对 ChatGPT 的期望仍然很高，我会在这里呈现其余部分，除非结果与我的（现在微薄的）期望差距很大。

## 汽车品牌和型号

### Copilot

// 每位顾客驾驶什么样的汽车？

for (const customer of customers) {

customer.car = faker.vehicle.model();

}

### ChatGPT

它从中为我提供了另一个数组，以供随机分配汽车。

每位顾客驾驶什么样的汽车？

const cars = ['福特', '雪佛兰', '丰田', '本田', '日产', '吉普', '道奇', '克莱斯勒', '宝马', '奔驰']

## 狗的品种

### Copilot

// 每位顾客拥有什么样的狗？

for (const customer of customers) {

customer.dog = faker.animal.dog();

}

### ChatGPT

每位顾客拥有什么样的狗？

const dogs = ['金毛寻回犬', '拉布拉多寻回犬', '德国牧羊犬', '英国斗牛犬', '贵宾犬', '比格犬', '罗威纳犬', '约克郡梗']

## 牌组

### Copilot

// 创建一副随机牌

const deck = [];

const suits = ['红心', '方块', '黑桃', '梅花'];

const ranks = ['A', '2', '3', '4', '5', '6', '7', '8', '9', '10', 'J', 'Q', 'K'];

for (const suit of suits) {

for (const rank of ranks) {

deck.push({ suit, rank });

}

}

这不错，而且准确。接下来，我们可能想要洗牌。

// 洗牌

deck.sort(() => Math.random() - 0.5);

不错。而且它没有使用 faker。

### ChatGPT

ChatGPT 做了类似的工作，并添加了一些解释，正如我们所见，这是它输出的典型特征。

// 创建一个包含所有可能卡牌值的数组

const cardValues = ['A', '2', '3', '4', '5', '6', '7', '8', '9', '10', 'J', 'Q', 'K'];

// 创建一个包含所有可能卡牌花色的数组

const cardSuits = ['红心', '方块', '黑桃', '梅花'];

// 创建一个空数组来存储随机排列的卡牌

const randomDeck = [];

// 遍历每个卡牌值和花色，创建一个新的卡牌对象并将其推送到 randomDeck 数组中

for (let i = 0; i < cardValues.length; i++) {

for (let j = 0; j < cardSuits.length; j++) {

const card = { value: cardValues[i], suit: cardSuits[j] };

randomDeck.push(card);

}

}

console.log(randomDeck);

这段代码将创建一个包含 52 张卡牌的随机牌堆，其中包括 13 种卡牌值（A、2、3 等）和 4 种花色（红心、方块、黑桃、梅花）。生成的 randomDeck 数组将包含 52 个卡牌对象，每个对象都有一个值属性和一个花色属性。

当我要求它洗牌时，我期望它使用内置的数组函数，但它没有。相反，它用了一种费力的方式写了一个洗牌函数。

// 洗牌函数

function shuffleDeck(deck) {

// 遍历牌堆并将每张牌与随机选择的牌交换

for (let i = 0; i < deck.length; i++) {

const randomIndex = Math.floor(Math.random() * deck.length);

const temp = deck[i];

deck[i] = deck[randomIndex];

deck[randomIndex] = temp;

}

return deck;

}

// 洗牌

const shuffledDeck = shuffleDeck(randomDeck);

console.log(shuffledDeck);

鼓励的，我又问了一次，这次指示它使用内置的数组函数。它基本上给了我 Copilot 写的相同函数。

// 使用内置的 Javascript 数组功能洗牌

const shuffledDeck = randomDeck.sort(() => Math.random() - 0.5);

console.log(shuffledDeck);

那应该就可以了。关键在于准确地要求你想要的东西。

## Uno 卡牌堆

他们甚至知道 Uno 卡牌是什么吗？

### Copilot

// 创建一个随机的 Uno 卡牌堆

const unoDeck = [];

const colors = ['红色', '黄色', '绿色', '蓝色'];

const specialCards = ['跳过', '反转', '抽两张', '万能', '万能抽四张'];

for (const color of colors) {

for (const rank of ranks) {

unoDeck.push({ color, rank });

}

for (const specialCard of specialCards) {

unoDeck.push({ color, specialCard });

}

}

很明显它知道一些关于 Uno 卡片的东西，包括颜色和特殊卡片。我有点烦恼它没有创建等级。我推测它使用了上一个代码块中的等级数组，因为我没有删除任何那部分代码。

我决定删除其他卡片的代码，然后再试一次。

// 创建一个随机的 Uno 卡牌牌堆

const { uno } = require('@faker-js/faker');

const deck = [];

for (let i = 0; i < 108; i++) {

deck.push(uno.card());

}

不，这一点都不起作用。毫不奇怪，faker 库没有输出。我尝试的其他方法都没用。第一个代码块实际上更好。

### ChatGPT

ChatGPT 给我的成果让我印象深刻。它生成了功能完备、文档完善的代码，并解释了它生成的内容。

创建一个随机的 Uno 卡牌牌堆

// 创建一个包含所有可能的卡片值的数组

const cardValues = ['0', '1', '2', '3', '4', '5', '6', '7', '8', '9', 'Skip', 'Reverse', 'Draw Two', 'Wild', 'Wild Draw Four'];

// 创建一个包含所有可能的卡片颜色的数组

const cardColors = ['Red', 'Yellow', 'Green', 'Blue'];

// 创建一个空数组来存储 Uno 卡片的随机牌堆

const randomDeck = [];

// 循环遍历每张卡片的值和颜色，创建一个新的卡片对象并将其推入 randomDeck 数组

for (let i = 0; i < cardValues.length; i++) {

for (let j = 0; j < cardColors.length; j++) {

// 跳过'Wild'和'Wild Draw Four'卡片值，因为它们可以是任何颜色

if (cardValues[i] === 'Wild' || cardValues[i] === 'Wild Draw Four') {

continue;

}

const card = { value: cardValues[i], color: cardColors[j] };

randomDeck.push(card);

}

}

// 将'Wild'和'Wild Draw Four'卡片添加到 randomDeck 数组中

for (let i = 0; i < 4; i++) {

const wildCard = { value: 'Wild', color: 'Any' };

randomDeck.push(wildCard);

}

for (let i = 0; i < 4; i++) {

const wildDrawFourCard = { value: 'Wild Draw Four', color: 'Any' };

randomDeck.push(wildDrawFourCard);

}

console.log(randomDeck);

这段代码创建了一个包含 108 张 Uno 卡片的随机牌堆，包括 15 个卡片值（0，1，2，等等）和 4 个卡片颜色（红色，黄色，绿色，蓝色），以及两张特殊卡片'Wild'和'Wild Draw Four'，这些卡片可以是任何颜色，然后它创建一个循环来为每种颜色添加 4 张'Wild'和'Wild Draw Four'卡，并将其推入 randomDeck 数组，最终的 randomDeck 数组将包含 108 个卡片对象，每个对象都有一个值属性和一个颜色属性。

## 食品杂货购物清单

### Copilot

这个也使用了 faker，经过几次失败尝试后，最终给我这个：

// 创建一个随机的食品杂货购物清单

const groceryList = [];

for (let i = 0; i < 10; i++) {

groceryList.push(faker.commerce.productName());

}

这更多证明了 Copilot 意识到了你项目中的其他代码。有时你需要删除它生成的代码，然后再试一次。如果你不喜欢结果，尝试稍微改变一下注释。

### ChatGPT

ChatGPT 采取了稍微不同的方法。它似乎能够理解是否应该考虑先前的指令。在给定这个提示时，它做了我想到的事情。

创建一个可能的杂货项目数组

// 创建一个可能的杂货项目数组

`const groceryItems = ['Apples', 'Bananas', 'Oranges', 'Lemons', 'Lettuce', 'Carrots', 'Potatoes', 'Onions', 'Tomatoes', 'Garlic', 'Ground Beef', 'Chicken Breasts', 'Eggs', 'Milk', 'Cheese', 'Bread', 'Pasta', 'Rice', 'Beans', 'Cereal', 'Yogurt'];`

// 创建一个空数组来存储随机的股票清单

`const randomList = [];`

// 生成随机数量的项目的函数

`function randomNumberOfItems() {`

返回`Math.floor(Math.random() * groceryItems.length);`

}

// 遍历 groceryItems 数组并将随机数量的项目推送到 randomList 数组

`for (let i = 0; i < randomNumberOfItems(); i++) {`

`randomList.push(groceryItems[Math.floor(Math.random() * groceryItems.length)]);`

}

`console.log(randomList);`

这段代码创建了一个可能的杂货项目数组，然后创建一个空数组来存储随机的杂货清单，还创建了一个使用 Math.random()生成随机项目数量的函数 randomNumberOfItems，然后使用这个函数创建一个 for 循环，将随机数量的项目推送到 randomList 数组中。最终的 randomList 数组将包含来自 groceryItems 数组的随机数量的杂货项目。

## 股票市场符号

### Copilot

Copilot 在这方面做出了英勇的尝试，但它想要使用 faker 中的货币符号，显然没有股票代码。

// 创建一个随机股票符号列表

`const symbols = [];`

`for (let i = 0; i < 100; i++) {`

`symbols.push(faker.finance.currencyCode());`

}

它生成了一个包含 100 个 3 个字母代码的列表。对于演示 UI 中的示例代码而言，我想这样做就足够了。

### ChatGPT

我最欣赏 ChatGPT 的地方在于它理解上下文。它知道我所说的“股票符号”的含义。它给了我一个非常详尽的代码块。

创建一个随机股票符号列表

// 创建一个可能的股票符号数组

`const stockSymbols = ['AAPL', 'GOOGL', 'AMZN', 'FB', 'MSFT', 'BABA', 'TATAMOTORS', 'BA', 'INFY', 'WMT', 'GE', 'CVX', 'PG', 'XOM', 'CMCSA', 'C'];`

// 创建一个空数组来存储随机的股票符号

`const randomStockSymbols = [];`

// 生成随机数量的股票符号的函数

`function randomNumberOfSymbols() {`

`return Math.floor(Math.random() * stockSymbols.length);`

}

// 遍历 stockSymbols 数组并将随机数量的符号推送到 randomStockSymbols 数组

`for (let i = 0; i < randomNumberOfSymbols(); i++) {`

`randomStockSymbols.push(stockSymbols[Math.floor(Math.random() * stockSymbols.length)]);`

}

`console.log(randomStockSymbols);`

## 随机股票价格流

它们还能提供来自这些符号之一的随机价格流吗？

### Copilot

// 创建一个随机股票价格列表

`const prices = [];`

`for (let i = 0; i < 100; i++) {`

prices.push(faker.finance.amount());

}

console.table(prices);

然后我想让 Copilot 把这两个列表合在一起。

// 将价格和代码合并为股票列表

const stocks = [];

for (let i = 0; i < 100; i++) {

stocks.push({

symbol: symbols[i],

price: prices[i],

});

}

console.table(stocks);

这并不糟糕，但生成一个我可以订阅的流会很酷。

// 为每支股票生成一个可观察流的价格，每 5 秒变化一次

const { interval } = require('rxjs');

const { map, mergeMap } = require('rxjs/operators');

const { from } = require('rxjs');

const { zip } = require('rxjs');

const { take } = require('rxjs/operators');

const stockStream = from(stocks);

const priceStream = interval(5000).pipe(take(10));

const combinedStream = zip(stockStream, priceStream).pipe(

map(([stock, price]) => {

stock.price = price;

return stock;

}

));

combinedStream.subscribe((stock) => {

console.log(stock);

});

这很酷，而且大部分是正确的。我更希望它从之前创建的列表中获取价格，但它为我做了大部分繁重的工作。当我运行它时，它每 5 秒发出一个股票代码和价格。

### ChatGPT

我从 ChatGPT 得到的代码与 Copilot 给我的类似，但更完整。与过去的提示一样，它坚持为每个问题提供完整的答案。这是它完整给我的内容。

生成一个可观察流的价格，每 5 秒变化一次

const { Observable } = rxjs;

// 创建一个可能的股票代码数组

const stockSymbols = ['AAPL', 'GOOGL', 'AMZN', 'FB', 'MSFT', 'BABA', 'TATAMOTORS', 'BA', 'INFY', 'WMT', 'GE', 'CVX', 'PG', 'XOM', 'CMCSA', 'C'];

// 创建一个空数组来存储随机股票代码

const randomStockSymbols = [];

// 生成随机数量的股票代码的函数

function randomNumberOfSymbols() {

return Math.floor(Math.random() * stockSymbols.length);

}

// 遍历 stockSymbols 数组，并将随机数量的代码推送到 randomStockSymbols 数组中

for (let i = 0; i < randomNumberOfSymbols(); i++) {

randomStockSymbols.push(stockSymbols[Math.floor(Math.random() * stockSymbols.length)]);

}

console.log(randomStockSymbols);

// 创建一个空数组来存储随机股票价格

const randomStockPrices = [];

// 生成一个随机股票价格的函数

function randomStockPrice() {

return (Math.random() * (300 - 50) + 50).toFixed(2);

}

// 遍历 randomStockSymbols 数组，并将随机股票价格推送到 randomStockPrices 数组中

for (let i = 0; i < randomStockSymbols.length; i++) {

const stock = {

symbol: randomStockSymbols[i],

price: randomStockPrice()

};

randomStockPrices.push(stock);

}

console.log(randomStockPrices);

// 为每个股票代码创建一个可观察流

const stockStreams = randomStockSymbols.map(symbol => {

return Observable.create(observer => {

setInterval(() => {

observer.next({

symbol,

price: randomStockPrice()

});

}, 5000);

});

});

// 订阅每个股票流并记录更新后的股票价格

stockStreams.forEach(stream => {

stream.subscribe(stock => {

console.log(`${stock.symbol}: $${stock.price}`);

});

});

此代码使用 rxjs 库和 Observable.create()方法为 randomStockSymbols 数组中的每个股票符号生成一个可观察流。它使用 setInterval()函数每 5 秒发出一个包含符号和随机价格的新股票对象。然后订阅每个股票流，并记录更新后的股票价格。

重要提示：要使此代码工作，您应该首先导入 rxjs 库。

你必须承认这相当完整。

## 结论

总的来说，我认为 Copilot 在成功度量标准上得 5 或 6 分（满分 10 分）。它最终更像是使用 faker 库的助手。我想，即使它没有做我期望它做的事情，真正重要的是如何生成示例数据并不那么重要。Copilot 使用其可用的工具，这是一件好事。我认为这不应该算在 Copilot 的账上。考虑到其设计目的，它做得很好。 

另一方面，ChatGPT 得分为 8 或 9。它会使用或不使用现有的库，这使得它更加灵活。它还会记住过去的请求，因此您可以给出如“再次使用单引号而不是双引号”或“使用内置 JavaScript 数组函数重写该函数”等指示。我没有展示 ChatGPT 的一个缺点是，每次您要求它重新编写或重构之前的答案时，它都会缓慢地重新生成整个代码块。经过五六次这样的操作后，它生成答案的时间感觉越来越长。

我后来发现，ChatGPT Plus，即付费订阅版，生成代码的速度要快得多。我想那就是你每月付 20 美元的原因（截至 2023 年 3 月的价格）。

当我们继续探索使用这些工具的各种方式时，我想你会同意每种方法都有其优点，这取决于在何处以及如何使用。
