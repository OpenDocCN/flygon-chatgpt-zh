# 7

ChatGPT 网页开发提示

如果您的职责包括创建网页内容、网页或甚至整个网站，ChatGPT 可以成为一个有价值的助手。您可以让 ChatGPT 承担各种职责——从分析竞争性网站到起草网页内容，再到为您创建 HTML、CSS 和脚本。本章指导您朝着您可能立即发现最有帮助的行动方向。

对于本章中需要完全访问网络的提示，比如分析一个网站，您需要使用 ChatGPT 的 Web 浏览模型。对于其他提示，您可以使用 Web 浏览模型或其他模型。例如，您可以让 ChatGPT 通过将网页内容粘贴到“发送消息”字段中来分析网页，而不是直接在其网站上访问网页。  ## 分析竞争性网站

如果您想改进您的网站，您可能想知道竞争对手的网站提供了什么。了解的一个快速方法是让 ChatGPT 分析它们。以下是您可能使用的三个提示，包括网站的 URL，其中包含*URL*占位符：

+   ![Prompticon](img/prompticon.png) **分析以下网站并给我一个内容概述：*URL***

+   ![Prompticon](img/prompticon.png) **从设计角度分析以下网站。告诉我这个网站做得好的地方和做得不太好的地方。*URL***

+   ![Prompticon](img/prompticon.png) **分析*URL*的可用性，并创建一个 200 字的报告向我解释。**  ## 总结网页

在第四章中，您看到了如何使用“summarize”命令告诉 ChatGPT 给您一个书面文档的要点。您也可以对网页进行这样的操作。例如，启用 Web 浏览模型后，您可以给出类似以下的提示：

+   ![Prompticon](img/prompticon.png) **总结*URL*。**

或者：

+   ![Prompticon](img/prompticon.png) **总结*URL*，用 100 个字。**

没有启用 Web 浏览模型，您需要复制网页内容并将其粘贴到 ChatGPT 中。通常情况下，您受 ChatGPT 对文本输入的 4096 标记限制，因此总结长页面可能会有问题。  ## 分析网��关键词

启用 Web 浏览模型后，您可以要求 ChatGPT 分析网页的关键词。例如：

+   ![Prompticon](img/prompticon.png) **请分析这个网页并告诉我关键词：*URL***

ChatGPT 返回了一个“突出显示的关键术语和短语”的列表。

没有启用 Web 浏览模型，您可以复制网页并将其粘贴到 ChatGPT 中，使用类似以下的提示：

+   ![Prompticon](img/prompticon.png) **分析以下文本，并告诉我前 10 个关键词：**

然后您可以选择按 Shift+Enter 创建一个换行，并强制按 Ctrl+V 粘贴文本。与上述相同，ChatGPT 可以接受长达 4096 个标记的文本输入，这可能会截断较长的网页。  ## 确定您的网站需要什么

ChatGPT 可以帮助你确定你的网站需要什么。例如，如果你刚开始建立你的网站，你可以开始提示 ChatGPT 为你创建一个站点地图：

+   ![Prompticon](img/prompticon.png) **为一个以烹饪洋葱为重点的静态网站提出一个站点地图。**

+   ![Chatgpticon](img/chatgpticon.png) *当然！这是一个针对以烹饪洋葱为重点的静态网站的建议站点地图：*

+   *1\. 主页*

    +   *网站及其目的的介绍*

    +   *精选与洋葱烹饪相关的食谱或文章*

+   *…*

+   *10\. 联系方式*

    +   *网站或其创建者的联系信息*

    +   *反馈表格或电子邮件地址以供查询或建议*

    +   *社交媒体资料链接以进行更多互动*

站点地图看起来不错，但联系表单存在暴露联系方式给抓取攻击的风险，即在线恶意分子收集联系信息用于垃圾邮件或钓鱼。所以：

+   ![Prompticon](img/prompticon.png) **如何在静态网站上实现一个不容易受到基于抓取的垃圾邮件攻击的联系表单？**

ChatGPT 提出了六种减轻基于抓取的垃圾邮件攻击风险的策略，从使用 CAPTCHA（例如，“点击包含汽车的每个方块”）到添加一个隐藏的“蜜罐字段”，机器人会填写但人类不会。

+   ![Prompticon](img/prompticon.png) **我可以使用专门领域的嵌入式元素吗？**

ChatGPT 表示“是的”，并建议几家具有垃圾邮件保护功能的表单服务提供商，包括 Google reCAPTCHA 和 Formspree。## 创建网页

一旦确定了需要创建的网页，让 ChatGPT 帮助你创建它们。首先给 ChatGPT 一个明确说明你想要的提示。这里有一个例子：

+   ![Prompticon](img/prompticon.png) **创建一个 500 字的网页，解释洋葱的作用及其在烹饪和人类饮食中的重要性。将网页编码为 HTML。**

即使提示指定了一个网页，你也需要告诉 ChatGPT 将其编码为 HTML。否则，ChatGPT 会给你网页的文本内容，让你自己处理编码。

你可能更喜欢获得文本内容，这样你可以在文字处理软件中重新编写和增强页面，而不是在 HTML 编辑器中工作。如果是这样，当文本准备好时，你可以提示 ChatGPT 为你将其转换为 HTML，例如：

+   ![Prompticon](img/prompticon.png) **将以下文本转换为 HTML 网页：**

通常情况下，粘贴文本，可选择在前面加上一个换行符（按 Shift+Enter）。

你可以提示 ChatGPT 为特定类型的网页创建模板，比如博客文章。这里有一个例子：

+   ![Prompticon](img/prompticon.png) **你能为博客文章页面编写 HTML 结构吗？**

ChatGPT 为博客文章创建了一个简单直接的 HTML 页面，包括导航链接和页脚。ChatGPT 将文章的主要部分制作成了 HTML 文章元素。  ## 审查和改进网页内容

无论是从头开始创建网页还是寻求 ChatGPT 的帮助创建网页，你都可以要求 ChatGPT 提出改进页面的建议，然后进行这些改进。以下是一些示例：

+   ![Prompticon](img/prompticon.png) **审查以下网页内容，检查语法错误和语言清晰度。建议我可以进行关键词优化。**

如往常一样，你会粘贴网页内容，可选择按 Shift+Enter 键创建新行。

对于示例网页，ChatGPT 回应道：

+   ![Chatgpticon](img/chatgpticon.png) *当然，让我们为语��、清晰度和关键词优化进行审查*。

+   *内容通常清晰而引人入胜，融合了讲故事和信息性写作。语调轻松友好，很可能会引起许多读者的共鸣*。

+   *然而，有一些地方语言可以更清晰或简化以提高可读性。此外，我已经确定了一些潜在的关键词优化…*

具体建议得到了采纳。大多数都很中肯和有帮助。

+   ![Prompticon](img/prompticon.png) **提出改进博客网站首页的方法。**

+   ![Chatgpticon](img/chatgpticon.png) *为示例博客网站提供的首页是一个不错的起点，但可以通过几种方式进行改进。以下是一些建议：*

    1.  *添加一个网站图标：在网站的根目录中包含一个 favicon.ico 文件。这个小图标将出现在浏览器的标签中，提高你网站的视觉识别度*。

ChatGPT 的 10 条建议中有很多听起来不错。所以：

+   ![Prompticon](img/prompticon.png) **请实施一个网站图标链接，一个吸引人的 CSS 标题，一个导航菜单，一些语义化的 HTML 元素，一个视觉上独特的页脚，以及更好的 CSS 文件链接方式。另外，添加 meta 标签。**

+   ![Chatgpticon](img/chatgpticon.png) *当然！这是首页的更新版本，包含了请求的改进：…*  ## 创建外部 CSS 文件

你可以让 ChatGPT 为你创建 CSS 文件。例如，你可以让 ChatGPT 指向一个网页，并给出如下提示：

+   ![Prompticon](img/prompticon.png) **为我编写一个源自这个网页的外部 CSS 文件。**

如往常一样，如果你使用 Web 浏览模型，你会提供 URL。如果不是，你会粘贴网页的文本。

如果你有使用内联样式的 HTML 页面，你可以让 ChatGPT 将这些样式转换为内部样式表，以便更容易维护和更新页面。以下是一个示例：

+   ![Prompticon](img/prompticon.png) **在下面的 HTML 文件中，将每个内联样式的实例更改为使用内部样式表的样式。**

+   ![Chatgpt 图标](img/chatgpticon.png) *要用内部样式表替换内联样式，您需要在 HTML 文档的<head>部分中添加一个<style>块，并创建适当的 CSS 选择器。我们将创建两个类：.table1 和.table2，分别分配给您的表。这是更新后的 HTML：*

正如你所看到的，ChatGPT 很好地处理了这个任务。同样，ChatGPT 很好地将 HTML 文档从内部样式切换到它创建的外部 CSS 文件。这是我使用的提示：

+   ![提示图标](img/prompticon.png) **在下面的 HTML 文件中，请将每个内部样式实例更改为外部 CSS 文件中的样式。创建 CSS 文件并将其命名为 styles42.css。**  ## 为网页编写脚本

除了擅长创建和操作 HTML 和 CSS 之外，ChatGPT 还可以处理各种编程语言。我们将在第八章更详细地讨论这种能力，但在谈论网页工作时，您可能希望让 ChatGPT 为您的网站编写脚本。

你只需要一个合适的提示。这里有一个例子：

+   ![提示图标](img/prompticon.png) **编写一个 Python 脚本，生成一个摘要页面，其中包含/blog-posts/目录中每个文件的标题和前几行，并链接到它们，就像 WordPress 以逆时间顺序总结帖子一样。**

+   ![Chatgpt 图标](img/chatgpticon.png) *当然！这是一个示例 Python 脚本，生成一个摘要页面，其中包含/blog-posts/目录中每个 HTML 文件的标题和前几行，并以逆时间顺序链接到它们：*

这个脚本需要安装 BeautifulSoup 库，但当我提示时，ChatGPT 很乐意改用另一个库：

+   ![提示图标](img/prompticon.png) **你能修改脚本以使用 LXML 吗？**

+   ![Chatgpt 图标](img/chatgpticon.png) *当然！这是修改后的脚本版本，使用 lxml 而不是 BeautifulSoup 来解析 HTML 文件：*

这个脚本的版本运行良好，但运行时间有点长。但只需一个快速提示，就足以说服 ChatGPT 将脚本改写为 Rust，运行速度更快：

+   ![提示图标](img/prompticon.png) **请使用 Rust 编写类似的实现。**
