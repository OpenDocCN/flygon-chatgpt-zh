# 前言

在发布仅仅五天后，ChatGPT 就吸引了惊人的一百万用户，这在科技行业及其他领域引起了轰动。作为一个副作用，OpenAI API 用于人工智能文本生成的接口突然曝光，尽管它已经可用了三年。ChatGPT 界面展示了这种语言模型的潜力，突然之间，开发人员和发明家开始意识到他们手边可利用的令人难以置信的可能性。

自然语言处理领域在多年来取得了令人难以置信的技术进步，但直到最近，这项技术的使用仅限于少数精英。OpenAI API 及其附属库为寻求构建人工智能应用程序的任何人提供了一个即插即用的解决方案。无需拥有强大的硬件或深入的人工智能知识；只需几行代码，开发人员就可以以合理的成本将令人难以置信的功能集成到他们的项目中。

我们结合了我们的知识和经验，Olivier 作为数据科学家，Marie-Alice 作为软件工程师，为您提供了如何使用 GPT-4 和 ChatGPT 开发应用程序的广泛理解。在这些页面中，您将找到人工智能概念的清晰和详细的解释，以及如何有效、安全和节约成本地集成 OpenAI 服务的用户友好指南。

本书旨在让所有人都能理解，但最好具备一些基本的 Python 知识。通过清晰的解释、示例项目和逐步说明，我们邀请您与我们一起发现 GPT-4 和 ChatGPT 如何改变我们与机器互动的方式。

# 本书中使用的约定

本书中使用了以下排版约定：

*斜体*

表示新术语、URL、电子邮件地址、文件名和文件扩展名。

`等宽`

用于程序清单，以及在段萂中引用程序元素，如变量或函数名称、数据库、数据类型、环境变量、语句和关键字。

**`等宽粗体`**

显示用户应该按照字面意思输入的命令或其他文本。

*`等宽斜体`*

显示应该用用户提供的值或上下文确定的值替换的文本。

###### 提示

这个元素表示提示或建议。

###### 注意

这个元素表示一般说明。

###### 警告

这个元素表示警告或注意。

# 使用代码示例

可下载补充材料（代码示例、练习等）[*https://oreil.ly/DevAppsGPT_GitHub*](https://oreil.ly/DevAppsGPT_GitHub)。

如果您有技术问题或在使用代码示例时遇到问题，请发送电子邮件至[*support@oreilly.com*](mailto:support@oreilly.com)。

本书旨在帮助您完成工作。一般来说，如果本书提供了示例代码，您可以在您的程序和文档中使用它。除非您复制了代码的大部分内容，否则无需征得我们的许可。例如，编写一个使用本书中几个代码块的程序不需要许可。出售或分发 O'Reilly 图书中的示例需要许可。引用本书并引用示例代码来回答问题不需要许可。将本书中大量的示例代码整合到产品文档中需要许可。

我们感谢，但通常不要求署名。署名通常包括标题、作者、出版商和 ISBN。例如：“*使用 GPT-4 和 ChatGPT 开发应用程序*，作者 Olivier Caelen 和 Marie-Alice Blete（O'Reilly）。版权所有 2023 年 Olivier Caelen 和 Marie-Alice Blete，978-1-098-15248-2。”

如果您觉得您使用的代码示例超出了合理使用范围或上述给出的许可，请随时与我们联系[*permissions@oreilly.com*](mailto:permissions@oreilly.com)。

# O'Reilly 在线学习

###### 注意

[*O’Reilly Media*](https://oreilly.com)已经提供技术和商业培训、知识和见解，帮助公司取得成功超过 40 年。

我们独特的专家和创新者网络通过书籍、文章和我们的在线学习平台分享他们的知识和专长。O'Reilly 的在线学习平台让您随需应变地访问现场培训课程、深入学习路径、交互式编码环境，以及来自 O'Reilly 和其他 200 多家出版商的大量文本和视频。有关更多信息，请访问[*https://oreilly.com*](https://oreilly.com)。

# 如何联系我们

请就本书的评论和问题与出版商联系：

+   O’Reilly Media, Inc.

+   1005 Gravenstein Highway North

+   Sebastopol, CA 95472

+   800-889-8969（在美国或加拿大）

+   707-829-7019（国际或本地）

+   707-829-0104（传真）

+   [*support@oreilly.com*](mailto:support@oreilly.com)

+   [*https://www.oreilly.com/about/contact.html*](https://www.oreilly.com/about/contact.html)

我们为这本书建立了一个网页，列出勘误、示例和任何额外信息。您可以在[*https://oreil.ly/devAppsGPT*](https://oreil.ly/devAppsGPT)上访问这个页面。

有关我们的书籍和课程的新闻和信息，请访问[*https://oreilly.com*](https://oreilly.com)。

在 LinkedIn 上找到我们：[*https://linkedin.com/company/oreilly-media*](https://linkedin.com/company/oreilly-media)

在 Twitter 上关注我们：[*https://twitter.com/oreillymedia*](https://twitter.com/oreillymedia)

在 YouTube 上观看我们：[*https://youtube.com/oreillymedia*](https://youtube.com/oreillymedia)

# 致谢

要写一本关于最快发展的人工智能主题之一的书，没有许多人的帮助是不可能的。我们要感谢不可思议的 O'Reilly 团队对我们的支持、建议和中肯的评论；特别是 Corbin Collins，Nicole Butterfield，Clare Laylock，Suzanne Huston 和 Audrey Doyle。

这本书还受益于那些花了很多时间提供宝贵反馈的杰出审阅者的帮助。非常感谢 Tom Taulli，Lucas Soares 和 Leonie Monigatti。

非常感谢我们 Worldline Labs 同事对 ChatGPT 和 OpenAI 服务的见解和永无止境的讨论；特别是 Liyun He Guelton，Guillaume Coter，Luxin Zhang 和 Patrik De Boe。同样非常感谢 Worldline 的开发者倡导团队从一开始就提供的支持和鼓励；特别是 Jean-Francois James 和 Fanilo Andrianasolo。

最后，我们感谢我们的朋友和家人在我们疯狂迷恋 ChatGPT 期间的支持，使我们能够在如此短的时间内发布这本书。
