![Cover.png](img/Cover.png)

超级增强的编码与 GenAI

从 vibe 编码到使用 GitHub Copilot、ChatGPT 和 OpenAI 的最佳实践

Hila Paz Herszfang

Peter V. Henstock

![](img/Packt_Logo_New.png)

超级增强的编码与 GenAI

版权所有 © 2025 Packt 出版公司

*版权所有*。未经出版者事先书面许可，本书的任何部分不得以任何形式或任何方式复制、存储在检索系统中或通过任何手段传输，除非在评论或评论中嵌入的简短引用。 

在准备本书的过程中，已尽一切努力确保所提供信息的准确性。然而，本书中的信息销售不附带任何明示或暗示的保证。作者、Packt 出版公司或其经销商和分销商不对由此书直接或间接造成的任何损害承担责任。 

Packt 出版公司已尽力通过适当使用大写字母提供本书中提到的所有公司和产品的商标信息。然而，Packt 出版公司不能保证此信息的准确性。

**投资组合总监：** Gebin George

**关系负责人：** Sonia Chauhan

**项目经理：** Prajakta Naik

**内容工程师：** Aditi Chatterjee

**技术编辑：** Irfa Ansari

**编辑：** Safis Editing

**索引者：** Pratik Shirodkar

**校对：** Aditi Chatterjee

**设计总监：** Vijay Kamble

**增长负责人：** Nimisha Dua

首次出版：2025 年 8 月

生产参考：2220825

由 Packt 出版公司有限公司出版

格罗夫纳大厦

11 St Paul’s Square

伯明翰

B3 1RB, 英国。

ISBN 978-1-83664-529-0

[www.packtpub.com](http://www.packtpub.com)

*献给我的丈夫，Dvir，我的母亲，Yifat，我的父亲，Amos，我的兄弟，Roy，以及我的狗，Panda——感谢你们在这段旅程中的支持和鼓励。*

*– Hila*

*献给我的父亲，特别感谢我的母亲、兄弟，以及尤其是我的妻子对他们的支持。*

*– Peter*

# 前言

当 Hila 告诉我她正在编写一本关于 GenAI 驱动的软件开发的书时，我笑了。当然，她会。我们在人工智能与网络安全相遇的论文中合作过，所以我亲眼看到了她的思考——严谨、好奇，从不满足于表面的洞察。如果有人要绘制人工智能编码的未来，那一定是 Hila。

这本书不仅仅是对 ChatGPT 或 Copilot 的一次巡游。它是 AI 增强工程时代的建造者手册。它部分是工作流程，部分是剧本，部分是对当机器成为你的合作伙伴时编码意味着什么的哲学反思。它从提示工程到系统设计，从小型重构到架构指导，从 GitHub Copilot 到 OpenAI API，没有失去主线或迎合炒作。我最欣赏的是它的脚踏实地。希拉和彼得既不浪漫化通用人工智能，也不害怕它。他们以工程师的态度对待它：好奇、怀疑和实用。你如何评估通用人工智能的输出？你如何保持它的可靠性？何时应该覆盖它，或者更好的是，教导它？这些问题不是抽象的。它们是日常挑战，而这本书以清晰和坚韧的态度应对了它们。对于我们这些生活在 AI、代码和安全交汇处的人来说，这本书就像家一样。它针对开发者在将工具集成到生产环境中时面临的真实问题进行了讨论，在这些环境中，正确性至关重要，幻觉可能是危险的，而生产力意味着的不仅仅是自动完成。如果你在寻找一本教你如何更快地编码的书，当然，你会得到。但如果你在寻找一本教你如何在机器也编写代码的世界中更清晰地思考编码的书，那么这本书就是你的书。

恭喜希拉和彼得。你们创造了一些及时、真诚且真正有用的东西。

*迈克·埃尔利松，博士*

*AI 部门负责人，隐形网络安全初创公司*

# 贡献者

# 关于作者

希拉·帕兹·赫茨方格，拥有七年构建机器学习（ML）服务和领导团队的经验，拥有哈佛大学扩展学院的信息管理系统硕士学位，并正在完成第二个数据科学硕士学位。她开发了一门*Python for MLOps*的 Udemy 课程，并运营一个拥有 15K 粉丝和 300K+点赞的数学和科技 TikTok 频道。

彼得·V·亨斯特克是一位拥有 25 年以上在辉瑞公司、Incyte 公司和麻省理工学院 LL 实验室经验的 AI 专家。他在哈佛大学扩展学院教授研究生软件工程和 AI/ML 课程。他拥有普渡大学的 AI 博士学位和七个硕士学位。被 DKA 评为顶级 AI 领导者，彼得在 AI/ML、软件、可视化和统计学领域指导专业人士。

# 关于审稿人

迈克·埃尔利松是一位经验丰富的 AI 专业人士，利用他在数学方面的博士学位和深度学习与数据科学方面的广泛专业知识。作为一名多产的科学内容创作者和讲师，他已经审阅了大约 500 篇深度学习论文，并主持了 50 多场记录在案的播客，在 LinkedIn 上建立了超过 60,000 人的庞大追随者群体。除了他的专业工作外，迈克致力于在 AI 社区中进行教育和知识分享，通过他的各种内容平台使复杂主题易于理解。

Alice Fridberg 是一位拥有特拉维夫大学应用统计学硕士学位的数据科学团队负责人。她专长于创新的机器学习和深度学习方法，用于营销优化、预测和用户建模。她的工作使她获得了 *媒体和广告技术杰出女性 - 数据揭秘者* 奖项。Alice 是一位活跃的公众演讲者，在 *Women on Stage* 社区发表过 *数据科学简史* 等演讲。她还通过 DataHack、数据科学女性和特拉维夫大学的计划指导学生和早期职业人士。

# 免费获取电子书

新框架、演进的架构、研究突破、生产故障——AI_Distilled 将噪音过滤成每周简报，供实际操作 LLM 和 GenAI 系统的工程师和研究人员阅读。现在订阅，即可获得免费电子书，以及每周的洞察力，帮助您保持专注并获取信息。

订阅请访问 [`packt.link/TRO5B`](https://packt.link/TRO5B) 或扫描下方的二维码：

![一个带有橙色方块的二维码，AI 生成的内容可能不正确。](img/B31534_Newsletter_NEW.png)

# 前言

*Supercharged Coding with GenAI* 旨在培训软件开发人员在整个 **软件开发生命周期**（**SDLC**）中提高生产力。它不仅涵盖了编程方面，还包括如何使用 GenAI 方法编写测试、文档以及其他将软件投入生产所需的方面。本书介绍了 *五个 S 框架*，这是一种标准化的方法，旨在持续产生高质量的输出，许多 GenAI 用户都会遇到。

它指导您如何以及何时使用目前市场上占主导地位的三个最常见 GenAI 软件工具：ChatGPT、OpenAI API 和 GitHub Copilot。每个工具都提供不同的代码生成界面，各有不同的优势和劣势。学习如何有效地使用这些工具是软件工程快速发展的领域中一种赋权技能集。

本书采用实践方法，在不同章节中介绍了许多实验室，因为 GenAI 编码工具需要练习。这些实验室提供了必要的练习，以挑战知识并探索引入的关键技能。本书还深入探讨了如何使用指令背后的概念，确保您不仅学习 *如何* 做某事，而且理解 *为什么* GenAI 会产生特定的输出。

本书分为三个部分：

+   *第一部分*，*使用 GenAI 进行编码的基础*，提供了三个不同 GenAI 工具的快速入门教程，这些工具可用于代码补全和相关任务。我们将从 OpenAI API 框架开始，利用**大型语言模型**（**LLMs**）作为软件开发者。我们构建了一个代码补全程序，以便更好地理解 GenAI 工具的设计。接下来，我们将使用 GitHub Copilot 和 ChatGPT 开始，采用三种不同的交互模式：聊天、补全和分析。到那时，我们也将了解不同交互模式之间的设计差异。最后，我们将介绍五个 S 框架，这是一种构建精确提示的结构化方法，可以引导出可预测且更理想的输出。

+   *第二部分*，*GenAI 编码的 LLM 提示从基础到高级*，是成为超级编码者的下一步。我们将更深入地研究 LLMs 的基础。目标是更好地理解为什么这些模型比之前的许多工具表现得更好。然后，我们将通过学习哪些任务是模型的原生任务，哪些任务需要高级提示技术，以及哪些任务最好不依赖 GenAI 的帮助来培养超级编码者的心态。我们还将学习如何将高级提示技术应用于与编码相关的任务，如何使用评估技术评估我们输出的质量，以及如何微调模型以使其针对特定任务进行专业化。

+   *第三部分*，*使用 GenAI 从代码到生产的实践*，致力于高级 SDLC 方法，我们将能够使用新获得的能力和心态与 GenAI 工具一起工作。我们将讨论使用 GenAI 工具高效快速地进行日志记录、监控、调试、单元测试和文档编写。我们还将应用提示工程技术进行空间和内存优化。我们将以关于设计、架构和未来的讨论结束这一章节。

# 本书面向对象

如果你是一名对 GenAI 感兴趣的 Python 开发者，并希望提高你的软件工程生产力，这本书将改变你对软件的方法。我们包括了许多不同问题复杂性的结构化示例，这些示例将展示高级提示技术的应用，适用于初级到高级的开发者。

为了最大限度地利用这本书，你应该至少有一年的 Python 开发实践经验，并对 SDLC 有一定了解。

# 本书涵盖内容

*第一章*，*从自动化到全软件生命周期开发：GenAI 的当前机遇*，描述了软件开发工具与基于 LLM 的 AI 转型的最新融合。它提出现在是提高 GenAI 技能以更快地生成高质量代码的最佳时机。

*第二章*, *OpenAI API 快速入门指南*，介绍了开始使用 OpenAI 所需了解的一切。到本章结束时，你将能够开始用它来编写代码。

*第三章*, *GitHub Copilot 在 PyCharm、VS Code 和 Jupyter Notebook 中的指南*，提供了 GitHub Copilot（一种配对编程 GenAI 工具）的设置说明。然后展示了如何将 GitHub Copilot 与两个最受欢迎的 IDE 集成。有了这个背景，你将能够使用 GenAI 进行提示。

*第四章*, *使用 ChatGPT 进行提示的最佳实践*，深入探讨了提示，这是 GenAI 编码的核心技能。本章介绍了用于一致输出的五个 S 框架。

*第五章*, *使用 OpenAI API 和 GitHub Copilot 进行提示的最佳实践*，通过将提示方法扩展到函数、类和方法，完成了本书的*第一部分*。这些方法不仅应用于编写代码，还用于修复错误和提供文档。

*第六章*, *幕后揭秘：ChatGPT、GitHub Copilot 和其他 LLMs 是如何工作的*，揭示了 LLMs 底层的工作原理，因为这种理解有助于了解其优势和局限性。本章从一个统计示例开始，然后继续讨论通用的 LLMs。本章以扩展到 GitHub Copilot 核心的代码特定 LLMs 结束。

*第七章*, *使用 GenAI 阅读和理解代码库*，展示了不同 GenAI 工具在处理完整代码库中的有效性。本章展示了 GenAI 如何解释代码的工作原理，并使用代码和支持文档帮助调试问题。

*第八章*, *提示工程导论*，将这一新兴领域应用于代码开发，并介绍了少样本学习。提示工程方法通过 OpenAI API 和 GitHub Copilot 用于代码重构，以支持一致的编码风格。

*第九章*, *与编码相关任务的进阶提示工程*，将第八章中介绍的少样本方法扩展到推理模型。迭代提示、思维链提示和链式提示可以有效地生成高度可预测的代码，实现关键功能，包括代码和注释。

*第十章*, *使用 GenAI 重构代码*，回顾并扩展了思维链提示技术以提高代码质量。本章涵盖了重构代码以提高质量和性能的示例。

*第十一章*，*使用 OpenAI 微调模型*，比较和对比了少样本学习方法和微调，这是定制 LLMs 的标准方法。本章使用 OpenAI 游乐场来比较两种方法的有效性和成本。

*第十二章*，*使用 GenAI 编写代码文档*，开始*第三部分*，该部分专注于 SDLC 组件之外的编码。本章是编写 Python 标准文档的指南，即 docstrings，同时也提供了解决代码中过时注释问题的解决方案。

*第十三章*，*编写和维护单元测试*，展示了利用 GenAI 加速测试创建的多种方法。本章还涵盖了测试驱动开发（TDD）过程，即先编写测试用例，然后自动生成功能代码以通过测试。

*第十四章*，*GenAI 用于运行时和内存管理*，深入探讨了性能优化，这在 GenAI 代码文献中很少讨论。其示例展示了如何评估性能权衡，以及如何通过提示链结合提示来估计运行时容量并优化代码以大规模运行。

*第十五章*，*使用 GenAI 上线：日志记录、监控和错误处理*，提供了使用 GenAI 进行关键后期组件（将代码投入生产）的指导。本章将过去的概念，如强制风格、少样本学习和微调，应用于监控和日志记录方法。

*第十六章*，*架构、设计和未来*，讨论了 GenAI 的兴起、软件经济学以及软件工程领域的变革。它从 vibe 编码到长期预期，包括风险和治理，提供了对软件工程未来的观点。

# 为了最大限度地利用这本书

如果记住以下几点，跟随起来会更容易：

+   **示例**：从每一章提供的动手示例开始，确保你能够有效地使用所有工具，而不仅仅是关注其中一个

+   **实验室**：使用实验室来测试你如何应对挑战的知识，并使用每一章末尾的问题来确保你掌握了基础知识

+   **GenAI 方法**：在自己的代码和示例中尝试每一章的不同技术，看看 GenAI 如何改变你对软件工程的方法

+   **超越思考**：思考所介绍的 GenAI 工具的实用知识如何与 LLMs 工作的基本原理相关，以及它们如何增强你组织软件开发实践的多个方面

这里是一份你需要拥有的清单：

| **本书涵盖的软件/硬件** | **系统要求** |
| --- | --- |
| Python 3.11 或更高版本 | Windows、macOS 或 Linux。 |
| LLM 聊天和嵌入模型 | Windows、macOS 或 Linux。您可以选择利用您选择的 LLM。在整个书中，我们将使用来自 ChatGPT、OpenAI API 和 GitHub Copilot 的各种 GPT 模型。 |

## 下载示例代码文件

本书代码包托管在 GitHub 上，网址为[`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)。我们还有其他来自我们丰富图书和视频目录的代码包，可在[`github.com/PacktPublishing`](https://github.com/PacktPublishing)找到。查看它们吧！

## 下载彩色图像

我们还提供了一份包含本书中使用的截图/图表彩色图像的 PDF 文件。您可以从这里下载：[`packt.link/gbp/9781836645290`](https://packt.link/gbp/9781836645290)。

## 约定用法

本书使用了多种文本约定。

`CodeInText`: 表示文本中的代码词汇、数据库表名、文件夹名、文件名、文件扩展名、路径名、虚拟 URL、用户输入和 X 处理。例如：“编辑窗口支持如`/fix`、`/explain`和`/test`等斜杠命令，以及定制指令来修改您的代码。”

代码块应如下设置：

```py
def get_geometric_mean_of_two_numbers(
 a: float,
 b: float, ) -> float: return pow(a * b, 1 / 2)
num1: float = 5.0 num2: float = 20.0
print(get_geometric_mean_of_two_numbers(num1, num2)) 
```

任何命令行输入或输出都应如下所示：

```py
(.venv) $ pip install openai 
```

**粗体**: 表示新术语、重要词汇或您在屏幕上看到的词汇，例如在菜单或对话框中。例如：“在本章中，我们将介绍**提示工程**的实践，这是一个始于 2020 年的研究领域，它提供了用于改进提示的高级技术，以在**大型语言模型**（**LLM**）应用中实现更可靠、可预测和理想的结果。”

警告或重要注意事项如下所示。

技巧和窍门如下所示。

## 关于 AI 使用的免责声明

作者承认使用了尖端 AI，如 ChatGPT、OpenAI API 和 GitHub Copilot，其唯一目的是增强书中的语言和清晰度，从而确保读者有一个顺畅的阅读体验。重要的是要注意，内容本身是由作者创作的，并由专业出版团队编辑。

# 联系我们

我们读者的反馈总是受欢迎的！

**一般反馈**: 请通过电子邮件`feedback@packtpub.com`发送反馈，并在邮件主题中提及本书的标题。如果您对本书的任何方面有疑问，请通过电子邮件`questions@packtpub.com`联系我们。

**勘误**: 尽管我们已经尽最大努力确保内容的准确性，但错误仍然可能发生。如果您在这本书中发现了错误，如果您能向我们报告，我们将不胜感激。请访问[`www.packtpub.com/submit-errata`](http://www.packtpub.com/submit-errata)，点击**提交勘误**，并填写表格。

**盗版**：如果您在互联网上以任何形式发现我们作品的非法副本，如果您能提供位置地址或网站名称，我们将不胜感激。请通过 `copyright@packtpub.com` 联系我们，并提供材料的链接。

**如果您有兴趣成为作者**：如果您在某个主题上具有专业知识，并且您有兴趣撰写或为书籍做出贡献，请访问 [`authors.packtpub.com/`](http://authors.packtpub.com/)。

# 加入我们的 Discord 和 Reddit 空间

您不是唯一一个在导航碎片化工具、不断更新和不确定的最佳实践的人。加入一个不断壮大的专业社区，交流那些没有进入文档的见解。

| 通过我们的作者提供更新、讨论和幕后洞察，保持信息畅通。加入我们的 Discord 空间 [`packt.link/z8ivB`](https://packt.link/z8ivB) 或扫描下面的二维码：![白色背景上的二维码  AI 生成的可能内容可能不正确。](img/B31534_Discord_NEW.png) | 与同行建立联系，分享想法，并讨论现实世界的 GenAI 挑战。在 Reddit 上关注我们 [`packt.link/0rExL`](https://packt.link/0rExL) 或扫描下面的二维码：![白色背景上的二维码  AI 生成的可能内容可能不正确。](img/B31534_Reddit_NEW.png) |
| --- | --- |

# 分享您的想法

读完 *Supercharged Coding with GenAI* 后，我们非常希望听到您的想法！请 [点击此处直接进入此书的亚马逊评论页面](https://packt.link/r/1836645295) 并分享您的反馈。

您的评论对我们和科技社区非常重要，并将帮助我们确保我们提供高质量的内容。

# 您的书籍附带独家优惠 – 这是如何解锁它们

|

#### 现在解锁这本书的独家优惠

扫描此二维码或访问 [packtpub.com/unlock](http://packtpub.com/unlock)，然后按名称搜索此书。确保是正确的版本。 | ![](img/Unlock-01.png)![](img/Split-B-PEN-Unlock-QR.png) |

| *注意：在开始之前，请准备好您的购买发票。* |
| --- |

![](img/nextgen.png)

使用我们的下一代阅读器增强阅读体验：

![黑色背景上的黑色方块  AI 生成的可能内容可能不正确。](img/cloud-computing.png) **多设备进度同步**：在任何设备上无缝同步进度。

![黑色背景上的黑色方块  AI 生成的可能内容可能不正确。](img/highlighter.png) **高亮和笔记**：将您的阅读转化为持久的知识。

![黑色背景上的黑色方块  AI 生成的可能内容可能不正确。](img/bookmark-white.png) **书签**：随时回顾您最重要的学习内容。

![黑色背景上的黑色方块  AI 生成的可能内容可能不正确。](img/brightness-and-contrast.png) **暗黑模式**：通过切换到暗色或棕褐色模式，以最小的眼部疲劳来集中注意力。

使用我们的 AI 助手（Beta）更智能地学习：

![黑色背景上的黑色方块  AI 生成的内容可能不正确。](img/sparkler.png) **总结**: 总结关键部分或整章内容。

![黑色背景上的黑色方块  AI 生成的内容可能不正确。](img/sparkler.png) **AI 代码解释器**: 在下一代 Packt Reader 中，点击每个代码块上方的**解释**按钮以获取 AI 驱动的代码解释。

注意：AI 助手是下一代 Packt Reader 的一部分，目前处于测试阶段。

任何时间、任何地点学习：

![PDF 图片](img/pdf.png)![EPUB 图片](img/epub_%281%29.png) 使用无 DRM 的 PDF 和 ePub 版本离线访问您的内容——与您喜欢的电子阅读器兼容。

# 解锁您书籍的专属权益

您的这本书附带以下专属权益：

![黑色背景上的黑色方块  AI 生成的内容可能不正确。](img/cloud-computing.png) 下一代 Packt Reader

![黑色背景上的黑色方块  AI 生成的内容可能不正确。](img/sparkler.png) AI 助手（测试版）

![PDF 图片](img/pdf.png) 无 DRM PDF/ePub 下载

如果您尚未解锁，请使用以下指南进行解锁。此过程只需几分钟，并且只需完成一次。

# 如何通过三个简单步骤解锁这些权益

## Step 1

准备好这本书的购买发票，因为您在*步骤 3*中需要它。如果您收到的是实物发票，请用手机扫描，并准备好作为 PDF、JPG 或 PNG 格式。

想要了解更多关于查找发票的帮助，请访问[`www.packtpub.com/unlock-benefits/help`](https://www.packtpub.com/unlock-benefits/help)。

**注意**: 您是否直接从 Packt 购买此书？您不需要发票。完成第二步后，您可以直接跳转到您的专属内容。

|

## Step 2

扫描此二维码或访问[packtpub.com/unlock](http://packtpub.com/unlock)。| ![二维码图片](img/Split-B-PEN-Unlock-QR.png) |

| 在打开的页面（如果您在桌面，将类似于*图 0.1*），通过名称搜索此书。请确保您选择了正确的版本。网页截图  AI 生成的内容可能不正确。图 0.1：桌面上的 Packt 解锁登录页面 |
| --- |

## Step 3

登录您的 Packt 账户或免费创建一个新账户。登录后，上传您的发票。可以是 PDF、PNG 或 JPG 格式，且大小不得超过 10 MB。按照屏幕上的其余说明完成此过程。

|

## 需要帮助？

如果遇到困难需要帮助，请访问[`www.packtpub.com/unlock-benefits/help`](https://www.packtpub.com/unlock-benefits/help)获取如何查找发票等详细 FAQ。以下二维码将直接带您到帮助页面：| ![二维码图片](img/help_qr.jpg) |

**注意**: 如果您仍然遇到问题，请联系`customercare@packtpub.com`

# Part 1

# 使用 GenAI 进行编码的基础

在本书的第一部分，我们介绍了 GenAI 在编码方面的基础知识，并帮助您开始使用 OpenAI API 和 GitHub Copilot。本部分从讨论 GenAI 在编码领域是如何从软件开发工具的长期演变和 AI 领域最近出现的**大型语言模型（LLMs**）的交汇点中出现的开始。这种技术的最新融合已经彻底改变了编程的格局。现在开始这段旅程是完美的，因为将它们应用于软件开发任务需要培训和练习。

*第一部分*的剩余部分提供了使用 OpenAI API 和 GitHub Copilot 的实战指导。在设置这些工具之后，本部分介绍了使用 OpenAI API 和 GitHub Copilot 的最佳实践。

本部分包含以下章节：

+   *第一章*，*从自动化到完整的软件开发生命周期：GenAI 的当前机遇*

+   *第二章*，*OpenAI API 快速入门指南*

+   *第三章*，*GitHub Copilot 使用 PyCharm、VS Code 和 Jupyter Notebook 的指南*

+   *第四章*，*使用 ChatGPT 的最佳实践*

+   *第五章*，*使用 OpenAI API 和 GitHub Copilot 的最佳实践*

# 1

# 从自动化到完整的软件开发生命周期：GenAI 的当前机遇

如果您正在阅读这本书，您可能已经听到了一些关于**生成式人工智能（GenAI**）在编码方面的兴奋、炒作、担忧和现实。您可能已经在线查看了一些教程，甚至可能探索过使用这项技术进行自己的编码。

学习将 GenAI 应用于软件编码需要实践和时间。虽然有很多在线演示其功能，但还没有一种系统的方法可以始终如一地实现功能齐全、高质量的代码。此外，也没有很多资源指导开发者使用 GenAI 进行简单的代码补全或测试之外的应用。GenAI 在加速诸如标准化编码风格以提高可读性、调试、优化性能以及软件工程师执行的其他许多任务等方面特别有用。

在本章中，我们将探讨以下主题：

+   改变软件工程领域

+   介绍大型语言模型的兴起

+   探索软件开发生命周期

+   接受 GenAI 工具包

+   GenAI 对软件工程来说值得学习吗？

+   您将从这本书中获得什么

# 改变软件工程领域

计算机编程和软件工程，总的来说，不仅对技术产业做出了贡献，还促进了经济许多不同领域的繁荣，包括商业、金融、健康、交通和能源。软件推动了众多新产品的创造。它通过流程的自动化和优化提高了公司的生产力，并实现了成本降低。

随着软件持续创造经济价值，新的范例和工具增加了软件开发者编写高质量软件的速度。在过去的几年里，通用人工智能（GenAI）已经成为这些工具之一。

在软件工程中，通用人工智能突然发展到达到拐点，并从根本上改变了该领域。这项最近的技术使从新手到专家级软件开发者都能在编码以及更广泛的**软件开发生命周期**（**SDLC**）中大幅提高生产力。

包括人工智能在内的高级技术似乎最近每天都会出现在新闻中。尽管如此，许多软件工程师似乎对人工智能已经发展到能够支持他们的领域和特定的软件开发工作这一点感到有些惊讶。当前软件工程工具的状态是两个独立趋势汇聚的结果。首先，软件开发工具并非新事物，但它们在过去的几十年里一直在持续进步。其次，通用人工智能技术已经从**大型语言模型**（**LLMs**）的快速出现中跨越，这些模型可以追溯到神经网络和人工智能的起源。

## 软件开发工具的演变

通用人工智能在软件工程中的应用是一个相当新的发展。尽管多年来人们一直在讨论人工智能作为增强代码开发的潜在工具集，但通用人工智能的出现引领了一个新时代的能力。

在过去的几十年中，软件开发经历了许多新工具，这些工具改变了该领域。很容易论证，软件开发一直在不断演变，新的工具简化了流程并提高了生产力。本节概述了一些主要的技术革命，这些革命有助于软件开发者。

在 20 世纪 70 年代和 80 年代，*Maestro I*作为第一个**集成开发环境**（**IDE**）被开发出来，尽管按照今天的标准，它几乎不会被认作是这样一个环境。其继任者，如*Borland 的 Turbo Pascal*和*Visual Studio*，提供了编码、文件管理、调试、编译和执行的简单集成。今天的 Python IDE，如*Visual Studio Code*、*PyCharm*和*Spyder*，促进了变量的全局更改、代码高亮、语法检查以及访问多个工具。

**版本控制系统**是软件工程中的一个关键步骤，使得许多开发者能够在一个单一的项目上协同工作。拥有单一代码库，可以跟踪和管理代码的不同版本。20 世纪 60 年代的 IBM 的*IEBUPDTE*是这个技术的先驱，随后在 1982 年出现了*修订控制系统*，1986 年出现了*并发版本系统（CVS）*。直到 2005 年，现在无处不在的*Git*才被开发出来，它实现了一个分布式版本控制系统。

构建工具和**持续集成和持续部署**（**CI/CD**）系统加速了软件的交付过程。如 Jenkins 和 Maven 之类的构建工具将源代码转换为可执行代码。CI/CD 工具通常由构建触发，但会进一步自动化测试、执行**代码检查器**或其他代码工具，并经常将更新版本部署给用户。完整的部署管道让开发者从许多手动步骤中解放出来，并能够以快速和一致的方式向用户提供最新的功能。

在**软件测试**方面投入了大量的研究。除了针对不同测试形式的各种专用工具外，测试框架现在几乎成为所有软件开发套件的标准部分。IDE 通过使用方法签名和标准测试命名约定，已经通过这些方式加快了从现有代码创建骨架测试的过程。"unittest"框架运行所有测试并报告失败，显著加快了过程。

**代码分析**和**重构**工具可以识别代码中的问题，并可以提升整体质量。"SonarQube"是一个执行静态代码分析的代码分析工具的例子。它识别代码中潜在的问题，通常被称为**代码异味**，但也可以检查一系列潜在的问题，例如代码风格的偏差和安全性处理不当。

一些更高级的工具不仅能识别编码问题，还能修复它们。例如，*ReSharper*实际上重构代码以提升其质量。这些工具节省了开发者的时间，并通过**模式匹配**和人工智能的组合来实现这一结果。

随着编码源和包的不断变化，软件开发似乎总是需要新的包、平台，甚至语言。因此，软件开发者需要访问最新的手册或其他文档。有些人会参考在*Stack Overflow*或*Reddit*上搜索代码示例。这个领域的创新包括*Kite*，这是一款由人工智能驱动的软件，提供自动代码补全和即时代码文档。Kite 证明了它可以减少键盘点击并提高代码开发速度，拥有大约 50 万程序员的用户群。不幸的是，该公司在 2021 年停止运营，并将其多语言代码工具捐赠给了开源社区。

接下来，我们将介绍人工智能研究中的一个转折点，该转折点推动了包括软件工程在内的多个领域的重大采用。

# 介绍 LLMs 的崛起

在过去的短短几年里，大型语言模型（LLMs）已经崛起，成为写作、研究和推理的主要人工智能资源。它们目前正在改变科技行业，并在所有领域产生了深远的影响。本节简要概述了它们前所未有的崛起。

人工智能于 1956 年在著名的达特茅斯学院计算机科学专家研讨会上正式开始。他们提出了**人工智能**（**AI**）这一术语，并设定了从自动化推理到**自然语言处理**（**NLP**）等雄心勃勃的目标。尽管参与者预期会迅速实现这些目标，但计算和技术的限制阻碍了他们的成功。1969 年的一篇出版物谴责了关键技术，并据称引发了第一次有详细记录的**人工智能冬天**，一个长期没有资金或研究活动的时期。

在 20 世纪 80 年代，**专家系统**作为一种可行的解决方案出现，其中技术专家可以制定规则来在有限的领域内复制人类推理，以解决特定问题。尽管这种方法在早期取得了一些成功，但制定和管理规则集的顺序证明是困难的。这阻碍了其采用，并最终导致了第二次人工智能冬天。

**机器学习**（**ML**），作为人工智能的一个子领域，成为唯一的可行解决方案。与专家系统的手工规则不同，ML 系统可以直接从数据中学习做出预测或决策。研究导致了该子领域内数十种技术的出现，但**神经网络**在过去十年中已成为主导方法。受到生物神经元的轻微启发，神经网络已被证明是学习和建模数据的有力系统。研究人员已经表明，神经网络可以很好地泛化并近似任何函数。**深度学习**，任何具有多层**神经元**的神经网络，克服了更传统机器学习技术的局限性。具体来说，它可以在提供越来越大的训练集时继续学习。

**自然语言处理**（**NLP**）是将机器学习应用于人类语言数据的应用。它适用于任何文本，如文章、博客、电子邮件或书籍。该领域借鉴了计算机科学、人工智能和语言学。早期方法大量借鉴了统计方法，后来又借鉴了传统的 ML 技术。近年来，深度学习方法通过引入**语言模型**（**LMs**），基于现有语言数据预测和生成文本，彻底改变了 NLP 领域。LLMs 是 LMs 的扩展版本，在庞大的数据集和数十亿参数上训练，这些内部权重被调整以反映训练数据中的模式。本书的后续章节将广泛讨论 LLMs。

在过去几年中，深度学习模型在不断增加的文本量上进行了训练，并且随着新技术的出现，可以理解每个句子中的单词是如何相互关联的。这类 LLMs 包括 OpenAI 的*GPT*、Meta 的*Llama*、Google 的*Gemini*、Anthropic 的*Claude*，以及不断开发的新模型。这些 LLMs 最初被设计为准确预测短语中的下一个单词。在规模和最近的技术下，它们已经实现了**自然语言生成**（**NLG**）解决方案，可以编写完整的文本以实现报告编写、问答、聊天机器人等更多功能。

大型语言模型（LLMs）通常在可用的在线文本源上训练，但相同的模型也可以在软件代码上训练。这些 LLMs 使用来自 GitHub 存储库的公开可用的 Python、Java 和其他编程语言的代码。结果是，LLMs 可以预测下一块代码，可以生成注释，编写测试，甚至重构代码。这些都是我们在下一节中将描述的整体 SDLC 的组成部分。

# 探索软件开发生命周期

为了交付高质量的软件，大多数软件团队会经历一系列被称为**软件开发生命周期**（**SDLC**）的阶段。如图*图 1.1*所示，这些步骤旨在采取一种高效的方法，以最大限度地减少失败的风险。该过程通常从识别未满足的业务需求开始，并通过许多阶段来满足需求，以软件系统来实现。项目从分析现有状态到收集需求、设计系统、实现和测试代码、交付解决方案，以及通常维护软件。

尽管大多数人将软件开发与编码联系起来，但实际上编程只占整体工作的 25-35%，具体取决于软件类型及其需求。其余步骤包括收集需求、测试和记录代码、部署软件以及支持其持续功能，如*图 1.1*所示。

![图 1.1：软件开发生命周期 – 从需求到维护的持续软件开发或改进过程](img/B31534_01_1.png)

图 1.1：软件开发生命周期 – 从需求到维护的持续软件开发或改进过程

SDLC 过程始于收集需求，然后是规划、可行性分析和风险评估。成功分析导致创建高级系统设计，工程师只有在这一步之后才会继续进行软件编码。在部署之前，该形式将进行正式测试，从而产生一个实时或**生产**系统。随着环境或业务需求的变化，支持和维护总是需要的，这可能会触发下一个开发周期。

**重要提示**

虽然软件开发生命周期（SDLC）是行业标准的方法，但各个组织通常会引入变化以适应其软件开发流程。例如，一些组织可能会选择在编写代码之前实施测试，这种做法被称为**测试驱动开发**（**TDD**）。其他组织可能在可行性分析之前创建原型系统或引入**概念验证**（**POC**），这一步骤在 LLM 的帮助下变得更容易执行。

描述使用通用人工智能（GenAI）进行编码的书籍和视频越来越多，但这项技术可以极大地提升整个流程，而不仅仅是实际的编码实现。本书将探讨这些方面的几个方面，包括测试、文档编制和软件监控。这些对于软件项目的成功至关重要。

接下来，我们将看到作为软件开发者，我们如何在我们技术栈中接受一个全面的通用人工智能工具包。

# 接受通用人工智能工具包

本书专注于软件开发中的三个独立工具：ChatGPT、OpenAI API 和 GitHub Copilot。到 2024 年，这三个工具在软件工程应用中的市场规模约为 3500 万美元。根据*Research and Markets*的报告，预计整个十年内市场年增长率为 25%。本书的后续章节将提供如何订阅这些服务以及如何开始的指导。这些工具提供不同类型的功能，了解何时使用哪个工具是学习曲线的一部分。后续章节将突出介绍每个工具的功能和用例。

## ChatGPT

OpenAI 自 2015 年以来一直是 LLM 的领导者。在 CEO Sam Altman 的领导下，公司推出了其**生成式预训练变换器**（**GPT**）LLM 的多个版本。虽然这些版本受到了好评，但 2022 年 12 月 ChatGPT 的发布改变了全球对 AI 的看法。

ChatGPT 是一个由 AI 驱动的聊天机器人，是一种设计用于使用自然语言进行文本对话的应用程序。它的发布引发了广泛的使用，在下一个月达到了 1 亿用户。它继续成为全球最受欢迎的网站之一。

尽管与 ChatGPT 进行自然语言对话通常能够成功引发问题的答案，但**提示工程**已被证明是一种更稳健的技术。这是一种制作指令以产生更理想输出的艺术。提示通常包括上下文、指令、对话历史，有时还包括期望输出的示例。本书将提供结构化的格式，引导读者有效地进行提示工程，以生成代码、注释、测试和其他输出。

## OpenAI API

ChatGPT 是最受欢迎的与 LLM 交互的工具之一。然而，在许多情况下，提示工程缺乏软件中常见的简单结构，如循环和条件。OpenAI 提供了一个开发者平台，可以直接针对 ChatGPT 使用的相同 OpenAI LLM 进行编码。通过其**应用程序编程接口**（**API**），OpenAI 使开发者能够结合软件和提示工程。该 API 还提供了特定附加功能，这对于解决软件工程问题非常有用。

## GitHub Copilot

虽然 GitHub 是使用 Git 分布式版本控制共享代码最受欢迎的平台之一，但该公司于 2021 年发布了 GitHub Copilot。最初由 OpenAI 的 LLM 提供动力，它利用生成式 AI 的编程能力提供智能代码补全。该功能已集成到许多 IDE 中，包括 Visual Studio Code 和 PyCharm——这两个都是 Python 最受欢迎的 IDE。

与其他 OpenAI 模型不同，Copilot 充当一个**配对程序员**。这个概念源于**极限编程**（**XP**）敏捷方法，其中两位开发者使用一个键盘共同编写代码。尽管 Copilot 还不是完全功能的配对程序员，但它可以快速找到并显示代码语法的引用，甚至根据用户的要求提供注释示例或完整的代码。它从函数和变量名中解读意图。结合周围的代码作为上下文，它可以预测并建议下一块代码。

接下来，我们将回顾最近的研究，评估使用生成式 AI 进行软件开发的情况。

## 使用生成式 AI 提升软件开发

许多研究评估了生成式 AI 在编码任务中是否提高了生产力。*麦肯锡*报告了从最小到 50%的增长，具体取决于任务的复杂程度。对于代码文档和生成，收益远高于困难任务。他们发现，对于常规任务和重复性工作，以及新代码项目的初步探索特别有效。通过生成式 AI 技术重构代码以进行更改和应对新挑战也得到了改善。也许更重要的是，他们的研究表明，使用生成式 AI 进行软件开发的用户感到更快乐，能够更多地专注于有意义的工作，并且更频繁地达到*心流*状态。研究详情可以在[`www.mckinsey.com/capabilities/mckinsey-digital/our-insights/unleashing-developer-productivity-with-generative-ai`](https://www.mckinsey.com/capabilities/mckinsey-digital/our-insights/unleashing-developer-productivity-with-generative-ai)找到。

*Exadel* 进行的一项类似研究报告称，他们研究中的一半开发者至少 50% 的时间使用 GitHub Copilot。其中三分之二的开发者完成任务更快，节省了 10-30% 的开发时间。Copilot 使他们更加高效和满足。更多关于该研究的详细信息，请参阅 [`exadel.com/news/measuring-generative-ai-software-development/`](https://exadel.com/news/measuring-generative-ai-software-development/).

*Colombatto 和 Rivadulla* 的研究 ([`aws.amazon.com/blogs/apn/transforming-the-software-development-lifecycle-sdlc-with-generative-ai/`](https://aws.amazon.com/blogs/apn/transforming-the-software-development-lifecycle-sdlc-with-generative-ai/)) 发现，在软件开发全生命周期 (SDLC) 中应用 GenAI 具有诸多益处。通过分析 AWS 和 IBM 的数据，他们发现益处始于需求工程阶段。即使在 SDLC 的早期阶段，研究人员观察到使用 GenAI 的时间减少了高达 60%。他们发现开发时间减少了 30%，生成单元测试和测试计划的时间减少了 25%。尽管花费的时间较少，但代码质量提高了 25%，这有助于减少错误和降低软件维护成本。

由 *BlueOptima* 从 2022 年至 2024 年进行的一项研究，利用代码仓库分析了 77,338 名开发者的生产力、质量和成本。与其他报告显著节省的研究相比，这些发现要谦虚得多。他们发现，对于能够访问 GenAI 的人来说，生产力仅提高了 3.99%，而没有访问的人则下降了 5.12%。质量仍然略有提高，这很重要，因为它证明生产力提升并没有损害质量，但提升幅度并不显著。然而，该研究将这些工具的访问权限作为输入变量，而没有描述 GenAI 在其工作流程中的培训、熟悉度或集成。此外，随着 GenAI 工具的预测准确性和整体性能的持续快速提高，生产力很可能会增加。该研究的详细信息可以通过此链接找到：[`www.blueoptima.com/resource/llm-paper-1/`](https://www.blueoptima.com/resource/llm-paper-1/).

接下来，我们将讨论我们对在软件开发中使用 GenAI 的利弊的看法。

# 对于软件工程来说，学习 GenAI 是否值得？

我们已经使用代码补全工具超过十年，但当前的 GenAI 工具有所不同。我们使用了所有工具，例如键盘快捷键、Stack Overflow 搜索帮助、代码 API 搜索工具，以及 IDE 中可用的所有最新重构工具和模板。所有这些策略都有助于我们提高工作效率，但总有大量枯燥、重复的工作限制了我们的编码速度和乐趣。

## 使用 GenAI 编码的好处

GenAI 工具已经改变了我们的输出。在使用 GitHub Copilot 早期版本的三个月内，我们的编码速度提高了 15%。现在，经过两年，GitHub Copilot、ChatGPT 和 OpenAI API 的组合比我们使用过的任何其他东西都极大地提升了我们的编码输出。我们完成的工作量是之前使用多个工具时的两倍。生产力的提升是工具本身的进步以及如何使用它们的熟悉度的结合，这两者都在本书的各个部分进行了介绍。

除了仅仅编写代码的生产力之外，GenAI 还对软件开发的其他方面做出了贡献。GenAI 可以帮助自动重构代码，这有助于使其更易于阅读和维护。正如后续章节所示，代码还可以通过选择执行速度更快的更好算法来改进。GenAI 还可以帮助编写代码文档并自动化测试的创建。使用 GitHub Copilot，高效的编码配对方法包括提供帮助，这对资深开发者很有用，但对于学习新语言或框架的开发者来说则价值连城。

## 使用 GenAI 编码的缺点

软件开发背后的 GenAI 技术仍然相当新颖。2022 年早期的研究表明，GitHub Copilot 在生成正确代码的准确性低于 50%。尽管底层模型每几个月就会发布新的版本和改进，但它们当然并不完美。

事实上，GenAI 已经产生了一些我们见过的最糟糕的致命开发错误。为了更清楚地说明这一点，我们看到了一位数据科学家将他们的整个环境文件推送到公司仓库，这暴露了需要更换的秘密令牌。一位软件开发者在将文件重命名为 `pandas` 后导致了一个微服务崩溃。一位数据工程师花了两周时间学习 *Cython* 来处理 Python `DataFrame` 的内存问题，而不是简单地切换到 `Dask` 或 `PySpark`。GenAI 可能不仅会放大你的优势，还可能放大你的弱点。毕竟，它仍然是一个发展中的技术，但它的改进速度可能比任何人预期的都要快。

AI 编码成为了头条新闻，但可能并不清楚为什么会失败。底层编码模型是在可用的 GitHub 仓库数据和各种语言中公开可用的其他代码上训练的。对于广泛记录的问题，例如斐波那契数列计算或用于通过 *LeetCode* 面试问题的许多代码片段，答案几乎是完美的。因此，YouTube 上充满了展示 GitHub Copilot 如何在 3 分钟内编写 React 网页的视频。

GenAI 在解决更不为人知的编码任务时遇到了更大的困难，因为这些任务中的训练数据要少得多。即使是最著名的 *LeetCode 的两数之和问题* 稍微改变以包括 Python `Threads`，例如，解决方案也是不可预测的。

对于 LLM 生成文本的一个常见问题是，当答案不明显时，它们往往会虚构或编造信息。针对这个不太为人所知的问题正在进行重大研究。然而，当 GenAI 应用于软件工程时，幻觉和其他 LLM 问题确实会发生。

一些开发人员担心 GenAI 编码工具会将他们变成能力较弱的开发者。他们害怕依赖自动代码补全、建议和示例会导致他们失去编程优势或对函数的熟悉度。

迈克尔·格尔利克（Michael Gerlick）的最新研究（[`doi.org/10.3390/soc15010006`](https://doi.org/10.3390/soc15010006)）表明，AI 工具可能通过认知卸载的过程降低我们的批判性思维能力。然而，类似的论点也曾经被用来讨论自动拼写检查器，它们能产生更好的文档，但也许会加强我们的拼写错误。确实，当网络断开时，可能需要更长的时间来记住在`matplotlib`图中添加标记的确切语法。然而，如果你可以用更少的按键来加倍你的输出，你就可以专注于 GenAI 尚未解决的更重要的问题。

## 吸收要点

近期博客描述了一种名为**氛围编码**的新趋势，其中开发人员甚至非开发人员可以在周末利用 GenAI 广泛设计和构建完整的应用程序，这通常可能需要几个月的时间。令人印象深刻的是，技术已经发展到快速原型设计有效的程度。然而，原型并非生产代码。

在许多 GenAI 失败的教程中，常见的观点是“你应该验证你得到的结果”，然而没有人提供一种实用方法，甚至没有提供一种指导性的心态，来说明如何有效地评估输出并改进代码。

被认为是一种良好的实践，为所有代码应用单元测试和其他测试方法。然而，使用 GenAI 既不是盲目信任，也不是事实核查一切。GenAI 的失败并不意味着我们必须对它产生的每一块代码进行过度的事实核查。同样，GenAI 成功的证据并不意味着你应该将每个内存优化建议都推入生产。

利用 GenAI 是关于开发一套新的技能，以形式化从 LLM 获得的输入和输出。这将使你能够在整个 SDLC 中真正加速你的编码任务。它使你能够拥有代码，无论你是从头开始自己编写的，还是利用了 LLM。当你能够评估这些工具生成的输出质量和风险时，你将能够改变你对软件工程的方法。

# 摘要

本章强调了编码领域的生成式人工智能（GenAI）是从软件工具的进步与大型语言模型（LLMs）的结合中产生的。这项新兴技术不仅适用于编码，还可以增强软件开发生命周期的许多方面。ChatGPT、OpenAI API 和 GitHub Copilot 的结合提供了一套互补的工具，这些工具已被证明不仅能提高生产力并提升代码质量，甚至能给程序员带来快乐。

尽管这项技术尚新且仍在发展中，但生成式人工智能（GenAI）已经改变了软件工程领域。本书旨在提供一个结构化的方法，以有效地利用工具并在软件开发生命周期（SDLC）的许多方面取得最佳结果。

在下一章中，我们将介绍 OpenAI API 的快速入门指南，并使用 **聊天服务** 进行编码任务。我们将构建自己的代码补全程序，该程序以函数签名作为输入，并返回其实施作为输出。

# 进一步阅读

要了解更多关于本章所涉及的主题，请查看以下资源：

+   VS Code 插件：[`github.com/kiteco/vscode-plugin`](https://github.com/kiteco/vscode-plugin)

+   Begum Karaci Deniz, Chandra Gnanasambandam, Martin Harrysson, Alharith Hussin, Shivam Srivastava. *利用生成式人工智能（Generative AI）释放开发者生产力*：[`www.mckinsey.com/capabilities/mckinsey-digital/our-insights/unleashing-developer-productivity-with-generative-ai`](https://www.mckinsey.com/capabilities/mckinsey-digital/our-insights/unleashing-developer-productivity-with-generative-ai).

+   Alexey Girzhadovich. *科学测量生成式人工智能软件开发的真实影响*：[`exadel.com/news/measuring-generative-ai-software-development/`](https://exadel.com/news/measuring-generative-ai-software-development/).

+   Diego Colombatto 和 Jose Manual Pose Rivadulla. *使用生成式人工智能（Generative AI）改造软件开发生命周期（SDLC）*：[`aws.amazon.com/blogs/apn/transforming-the-software-development-lifecycle-sdlc-with-generative-ai/`](https://aws.amazon.com/blogs/apn/transforming-the-software-development-lifecycle-sdlc-with-generative-ai/)

+   研究和市场报告：2024 年至 2029 年编码市场中的生成式人工智能（AI）预测：[`www.researchandmarkets.com/reports/6014321/generative-artificial-intelligence-ai-in?utm_source=GNE&utm_medium=PressRelease&utm_code=8xz7cm&utm_campaign=2014387+-+Generative+Artificial+Intelligence+(AI)+in+Coding+Market+Research+2024-2029%2c+Profil`](https://www.researchandmarkets.com/reports/6014321/generative-artificial-intelligence-ai-in?utm_source=GNE&utm_medium=PressRelease&utm_code=8xz7cm&utm_campaign=2014387+-+Generative+Artificial+Intelligence+(AI)+in+Coding+Market+Research+2024-2029%2c+Profil)

+   Michael Gerlick. *AI Tools in Society: Impacts on Cognitive Offloading and the Future of Critical Thinking:* [`doi.org/10.3390/soc15010006`](https://doi.org/10.3390/soc15010006)

|

#### 现在解锁本书的独家优惠

扫描此二维码或访问 [packtpub.com/unlock](http://packtpub.com/unlock)，然后通过名称搜索此书。 | ![白色背景上的二维码 AI 生成的内容可能不正确](img/Split-B-PEN-Unlock-QR.png) |

| *注意：在开始之前，请准备好您的购买发票。* |
| --- |

# 2

# 您的 OpenAI API 快速入门指南

**生成式人工智能**（**GenAI**）平台，如 OpenAI，通过赋予普通用户生成针对问题、报告和图像的定制答案的能力，正在改变整个行业。您不必成为 AI 专家就可以利用 OpenAI 来加速您的软件开发。本章重点介绍设置 OpenAI 以及使用其 **应用程序编程接口**（**API**）调用生成高质量代码。

OpenAI 提供了众多服务，如聊天、图像生成和文本到语音。这些服务可以通过 **RESTful HTTP** 请求获得，这是应用程序在网络上通信的标准方式，或者通过 `openai` Python 包的程序化接口。

在本书的第一篇快速入门指南中，我们将通过三个交互式实验室和三组请求，使用 OpenAI Chat 服务进行操作。我们将深入了解通过 OpenAI API 可用的不同模型，以及如何影响 AI 生成的输出。

我们将获取我们的项目 API 密钥，分析服务的限制，并学习如何计算每个请求的成本。成本是根据模型输入和输出的 **tokens** 或子词片段的数量来计算的。

我们将通过创建一个基本的代码补全程序来结束本章，该程序可以根据函数签名生成 Python 代码实现。

在本章中，我们将探讨以下主题：

+   介绍 OpenAI API

+   从 OpenAI 获取您的项目 API 密钥

+   使用 `openai` Python 包发送您的第一个 OpenAI API 请求

+   学习如何计算请求成本

+   理解免费和付费 OpenAI 账户的速率限制和使用限制

+   分析请求参数

+   使用 OpenAI API 生成代码

# 技术要求

为了充分利用本章内容，请确保您具备以下条件：

+   您的个人 OpenAI 账户凭据

+   访问本书的 GitHub 仓库，网址为 [`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)

+   在您的 **集成开发环境**（**IDE**）中设置虚拟环境，无论是 VS Code 还是 PyCharm

如果您在设置 OpenAI 账户或 IDE 中的虚拟环境方面需要额外帮助，请参阅 *附录* 以获取详细说明。

# 介绍 OpenAI API

OpenAI 平台提供各种 **自然语言处理**（**NLP**）服务，为许多 AI 应用程序提供动力。在其核心，平台利用在大量数据上训练的 **大型语言模型**（**LLMs**），具有复杂的架构和数十亿可学习的参数，以生成 AI 生成的响应。开发者可以通过其 API 通过基于文本的请求与平台交互，这些请求通常被称为 **提示**。提示在经过处理、丰富和转换后，被传递到 LLM 模型。模型的输出进一步细化并作为对 API 请求的响应交付。

OpenAI 的 Chat 服务旨在与 LLM 进行对话交互，其中对话使用三种类型的提示角色 - 用户、系统和助手：

+   **用户提示**代表系统的一个最终用户，例如 ChatGPT 用户，类似于我们输入到 ChatGPT 中的提示，例如 `告诉我关于斐波那契数列的事情。`

+   **助手提示**通过对话表示模型输出，类似于我们从 ChatGPT 收到的答案，例如 `斐波那契数列是一系列数字，其中每个数字都是前两个数字的和。`

+   **系统提示**通过对话定义助手行为的指南，例如 `你是一位有用的编程讲师。`

与行业中的许多其他 GenAI 工具一样，OpenAI API 调用主要是付费服务。它确实提供了一些有限的免费使用，例如每分钟对受限制的模型选择进行三次请求，不包括 *GPT-4o*。只需 $5 的 OpenAI 信用额度，您就可以完全参与本书中展示的示例和实验室。我们将在最初的 *Lab 2.1* 实验之后指导您如何做到这一点。

## 通过 RESTful HTTP 请求使用 OpenAI API

OpenAI API 服务通过 **RESTful HTTP 请求** 访问，这是一种基于 **表示状态转移**（**REST**）架构原则的通信协议，并使用 **超文本传输协议**（**HTTP**）。RESTful HTTP 提供了一种标准化的方式，通过互联网从服务器发送和检索数据。对 OpenAI API 的请求包括四个关键组件：

+   **端点**：指定您要访问的服务 URL，例如用于 Chat 服务的 [`api.openai.com/v1/chat/completions`](https://api.openai.com/v1/chat/completions)

+   **HTTP 方法**：要执行的操作，例如 OpenAI Chat 服务请求的 `POST`，它将数据发送到服务器

+   **头部**：关于请求的元数据，包括您的 API 令牌，用于身份验证和提供请求的上下文

+   **正文**：包含使用 LLM 和输入提示等详细信息的请求数据负载

下面是一个使用 Python 中的 `requests` 包向 OpenAI API Chat 服务发送请求的示例。它演示了如何向服务发送 `POST` 请求，包括一个包含您的 API 密钥进行身份验证的头部和一个包含数据负载的正文，例如模型和提示：

```py
import requests import json
api_key = "your-key-here" headers = { "Authorization": f"Bearer {api_key}", 
 "Content-Type": "application/json" }
payload = { "model": "your model's name here", 
 "messages": "your message here"}
response = requests.post("https://api.openai.com/v1/chat/completions", 
    headers=headers, 
    data=json.dumps(payload))
chat_response = response.json()["choices"][0]["message"]["content"] 
```

![](img/3.png) **快速提示**：使用**AI 代码解释器**和**快速复制**功能增强您的编码体验。在下一代 Packt 阅读器中打开本书。点击**复制**按钮

（**1**）快速将代码复制到您的编码环境，或点击**解释**按钮

（**2**）让 AI 助手为您解释代码块。

![白色背景上的黑色文字  AI 生成的内容可能不正确。](img/image_%282%29.png)

**![](img/4.png)** **新一代 Packt 阅读器**随本书免费赠送。扫描二维码或访问 packtpub.com/unlock，然后使用搜索栏通过书名查找此书。请仔细核对显示的版本，以确保您获得正确的版本。

![白色背景上的二维码  AI 生成的内容可能不正确。](img/Split-B-PEN-Unlock-QR.png)

注意，此代码示例也可以在本书的存储库路径中找到，*ch2/code_samples/openai_request.py*。

在此示例中，有效负载以 JSON 格式提交。如果请求成功接受并且服务器响应，可以从`response.json()["choices"][0]["message"]["content"]`检索 OpenAI API 聊天服务的输出。

对于 Python 开发者来说，有一种更有效的方法可以访问 OpenAI 聊天服务。我们不必处理构建和发送 RESTful HTTP 请求的复杂性，例如构造正确的端点 URL、在头中设置身份验证令牌、格式化 JSON 有效负载以及处理潜在的响应错误，我们可以利用专门的`openai`包。

## OpenAI API Python 包安装

`openai` Python 包通过抽象诸如 URL 路径、重试、错误处理和身份验证等复杂性，简化了安装过程。这使得我们能够直接与 Python 对象交互，而不是手动构建 RESTful HTTP 请求。

要安装`openai`包，请在您的虚拟环境中运行以下命令：

```py
(.venv) $ pip install openai 
```

要验证`openai`包是否正确安装在您的虚拟环境中，请运行以下指定包信息的命令：

```py
(.venv) $ pip show openai 
```

您的控制台将输出有关包版本、作者和支持电子邮件的信息。

安装了`openai`包后，我们可以使用程序性框架简化与 OpenAI 平台的交互。我们不会直接发送 RESTful HTTP 请求，而是将利用 Python 类。这减少了样板代码，例如处理身份验证和错误管理，并使代码更易于维护。

重要提示

如果您已经在处理本书的存储库，则无需单独安装`openai`包。它已在`requirements.txt`文件中指定，并应在您的虚拟环境中安装。如果您需要设置虚拟环境的额外帮助，请参阅*附录*以获取详细说明。

## 从 OpenAI 获取您的项目 API 密钥

所有对 OpenAI API 的请求都需要一个认证令牌，我们必须在提交任何请求之前获取一个。

导航到 [`platform.openai.com`](https://platform.openai.com) 并使用与你在 [`chat.openai.com/`](https://chat.openai.com/) 上使用的相同凭据登录。

登录后，点击右上角的 **仪表板**，然后在左侧菜单中选择 **API 密钥**。

最近，OpenAI 用创建项目 API 密钥的选项替换了个人 API 密钥。这个新密钥有两个用途。首先，它允许个人使用，正如本书中的工作所要求的那样。其次，它支持服务 API 密钥，这些密钥用于非人类身份，例如在生产中运行的微服务。

![图 2.1：项目 API 密钥仪表板](img/B31534_02_1.png)

图 2.1：项目 API 密钥仪表板

要生成你的第一个 API 密钥，点击右上角账户图标下的 **创建新密钥**。选择一个属于 **你** 的 API 密钥，因为我们将会使用这个密钥而不是将其分配给服务账户。你可以为它指定一个名称以便将来参考，并且它应该与一个项目相关联（如果你还没有更改项目名称，则命名为 *默认项目*）。

![图 2.2：为个人使用创建新的密钥](img/B31534_02_2.png)

图 2.2：为个人使用创建新的密钥

点击 **创建密钥** 后，平台将为你生成一个新的密钥。

返回你的 IDE，无论是 VS Code 还是 PyCharm，然后在终端运行以下命令以将环境变量导出：

```py
$ export OPENAI_API_KEY="your-key-here" 
```

或者，为了创建一个可重复的环境，你可以使用本书仓库提供的 *.env* 文件模板：

![图 2.3：.env 文件模板，位于仓库根目录](img/B31534_02_3.png)

图 2.3：.env 文件模板，位于仓库根目录

如果你选择使用 *.env* 来管理环境变量，你应该验证你的运行配置是否设置为与该文件一起工作。如需额外帮助，请参阅 *附录*。

接下来，我们将学习如何使用 `openai` Python 包提交我们的第一个 OpenAI API 请求，我们将遵循一个将在整本书中使用的模板。

# 实验 2.1 – 使用 openai Python 包发送你的第一个 OpenAI API 请求

安装了 Python 包和 API 密钥后，我们就准备好执行第一个 OpenAI API 请求了。请注意，完成这个实验不需要 OpenAI 平台的信用额度，我们将在本章后面指导你如何将信用额度加载到你的账户中。如果你之前已经将信用额度加载到 OpenAI 平台，这个示例的执行成本不会超过几分之一美分。

在这个实验中，我们将从一个简单的模板开始，用于执行对 Chat 服务的 OpenAI API 请求并打印响应输出。我们将有三个步骤：

1.  创建一个 `openai.OpenAI` 类实例。

1.  使用单个用户提示和一个模型选择（如 *GPT-4o-mini* 或 *GPT-3.5-turbo*）向聊天服务提交请求。

1.  打印响应输出。

这些步骤已包含在我们的起始代码中，我们将引导您完成它、运行它并分析我们得到的结果：

```py
import openai from openai import OpenAI if __name__ == "__main__": 
    client: OpenAI = OpenAI()
    completion: openai.ChatCompletion = ( 
        client.chat.completions.create( 
            model="", # Your model's name here messages=[] # Your messages here )) print("your print here") 
```

在这个实验室演示中，我们将在此基础上完成 `model` 和 `messages` 参数，使我们能够从 OpenAI 平台接收对请求的 AI 生成的响应。

## 实验室 2.1 指导性演示

在位于 *ch2/labs/lab21.py* 的书籍仓库中打开 *Lab 2.1*。首先，我们将创建 `openai.OpenAI` 类的新实例：

```py
client: OpenAI = OpenAI() 
```

我们在代码中不直接指定任何认证参数。`OpenAI` 客户端会自动从 `OPENAI_API_KEY` 环境变量中检索 API 密钥。虽然您可以在实例化时使用 `api_key` 参数传递 API 密钥，但我们强烈建议出于安全原因不要在脚本中硬编码凭证。

下一步是使用 OpenAI 客户端发送请求。我们将通过访问 `chat.completion` 来发起对聊天服务的调用，在那里我们将定义必要的 RESTful HTTP 请求参数。这至少包括两个部分：`model` 和 `messages` 关键字参数。`model` 参数代表您查询的 LLM 名称，而 `messages` 参数代表发送给模型的输入提示：

```py
completion = client.chat.completions.create( 
    model="", # Your model's name here messages=[] # Your messages here ) 
```

如果您已在您的 OpenAI 平台账户中充值了积分，请在双引号内输入 `model` 值：

```py
gpt-4o-mini 
```

否则，请使用以下模型：

```py
gpt-3.5-turbo 
```

接下来，将单个用户提示添加到 `messages` 参数中：

```py
messages = [{"role": "user", "content": "What is the FizzBuzz problem?"}] 
```

最后一步是打印聊天服务的响应输出。在最后一行，将 `print` 语句替换为以下内容：

```py
print(completion.choices[0].message.content) 
```

到目前为止，您的 *Lab 2.1* 代码应该如下所示：

```py
import openai from openai import OpenAI if __name__ == "__main__": 
    client: OpenAI = OpenAI() 
    completion: openai.ChatCompletion = client.chat.completions.create( 
        model="gpt-4o-mini", 
        messages=[{"role": "user", "content": "What is the FizzBuzz problem?"}] 
    ) print(completion.choices[0].message.content) 
```

*Lab 2.1* 现在已准备好运行，并将打印出对以下用户提示的聊天完成：`What is the FizzBuzz problem?`。

注意

在编写实验室代码时，您始终可以在 `ch2/solutions` 文件夹中找到完整的实验室解决方案。

## Lab 2.1 分析

如果您使用 VS Code，请在终端中运行脚本并检查输出；如果您使用 PyCharm，请在 `run` 控制台中检查输出。程序的输出应该是聊天服务对用户提示 `What is the FizzBuzz problem?` 的响应，这是我们将在后续章节中再次讨论的问题。

根据您选择的模型（无论是 *GPT-3.5-turbo* 还是更高级的 *GPT-4o-mini*），您可能从聊天服务中获得相当不同的输出。为了您的参考，这里是一个来自 *GPT-3.5-turbo* 模型的响应，其中包含上下文和问题描述：

```py
FizzBuzz is a common programming problem often used in job interviews to test a candidate's ability to write simple code. The problem is as follows:
Write a program that prints the numbers from 1 to 100\. But for multiples of three, print "Fizz" instead of the number, and for the multiples of five, print "Buzz For numbers which are multiples of both three and five, print "FizzBuzz" 
```

这里是来自 *GPT-4o-mini* 模型的响应，除了上下文和描述外，还包括了编码任务阶段的详细说明、示例输出以及任务的挑战：

```py
The FizzBuzz problem is a classic programming task often used in coding interviews and educational settings to test a developer's basic understanding of control structures, loops, and conditional statements. The problem is simple:
1\. Write a program that prints the numbers from 1 to a specified number, typically 100. 2\. For multiples of three, print "Fizz" instead of the number. 3\. For multiples of five, print "Buzz" instead of the number. 4\. For numbers that are multiples of both three and five, print "FizzBuzz." The output would look something like this:
```

1, 2, Fizz, 4, Buzz, Fizz, 7, 8, Fizz, Buzz, 11, Fizz, 13, 14, FizzBuzz, ... ```py
This task helps demonstrate an understanding of loops and conditionals, often revealing both logical reasoning and code clarity. 
```

在*第六章*中，我们将更详细地探讨*GPT-4o*和*GPT-3.5*之间的底层差异。

重要提示

如*第一章*中所述，建立在 LLM 之上的应用程序很少输出确定性的结果，并且由于提示构造、用户定制和随机性，相似提示的响应可能不同。在本书接下来的内容中，我们将进一步讨论如何控制这三个方面以实现模型所需的结果。

接下来，我们将探讨如何预测每个 API 调用相关的成本，并了解作为单词片段的标记是如何用来计算请求费用的。

# 学习如何计算请求成本

由于 OpenAI API 主要是一项付费服务，因此理解并预测每个请求相关的成本至关重要。

在进行实验室练习之前，强烈建议您向您的 OpenAI 平台账户充值。初始的 5 美元信用额度应该足以完成本书中的所有实验室。充值信用也将使您的账户从免费层使用（无先前信用额度）升级到一级账户，显著提高您的速率和限制，我们将在本章后面讨论。

要充值信用，请打开 OpenAI 的**账单概览**页面[`platform.openai.com/settings/organization/billing/overview`](https://platform.openai.com/settings/organization/billing/overview)，并添加一个最低收费为 5 美元的支付方式。

![图 2.4：剩余信用余额](img/B31534_02_4.png)

图 2.4：剩余信用余额

您也可以通过访问相同的链接在任何时候检查您的剩余余额。

## 理解标记

OpenAI 平台根据**标记**计算请求成本，这些标记是文本的小段（通常是子词、单词或字符），平均每个约为 0.75 个单词或 4 个字符。文本通过标点符号、词根和词尾等元素被划分为标记。我们将在*第六章*中详细讨论标记。

每个 API 请求都包含输入和输出标记，OpenAI 对两者都收费。例如，在*实验 2.1*中，消息`{"role": "user", "content": "What is the FizzBuzz problem?"}`包含 15 个标记。您可以从以下代码中的`prompt_token`属性访问确切的计数：

```py
>> completion.usage.prompt_tokens
>> 15 
```

或者，我们可以使用 OpenAI 标记器等工具来估计我们的总输入标记消耗，这些工具可在[`platform.openai.com/tokenizer`](https://platform.openai.com/tokenizer)找到。标记器还会对文本中的不同标记进行着色编码，将如`role`和`user`这样的单词识别为单个标记，将如逗号和问号这样的标点符号识别为单个标记，将 FizzBuzz 识别为三个标记。

![图 2.5：OpenAI 标记器模拟](img/B31534_02_5.png)

图 2.5：OpenAI 标记器模拟

输出令牌也会收费。例如，在*Lab 2.1*中，*GPT-4o-mini*模型的输出响应包含 292 个令牌。您可以通过调用以下代码来访问`completion_tokens`属性：

```py
>> completion.usage.completion_tokens
>> 292 
```

这使得应计令牌总数达到 307 个。您可以通过调用以下代码来访问`total_tokens`属性：

```py
>> completion.usage.total_tokens
>> 307 
```

## 账单是如何计算的

OpenAI 对输入和输出令牌都收费，费用因模型而异。较新、更先进的模型通常费用更高，而优化版本，例如带有*-mini*或*-turbo*后缀的模型，则更经济实惠。您可以在[`openai.com/api/pricing/`](https://openai.com/api/pricing/)找到完整的定价详情。

截至 2025 年 1 月，*GPT-4o*模型的输入令牌每百万个令牌定价为 2.50 美元（或每 40 万个输入令牌收费 1 美元），输出令牌每百万个令牌定价为 10 美元（或每 10 万个输出令牌收费 1 美元）。

在*Lab 2.1*中，我们使用了更经济的*GPT-4o-mini*模型。该模型的输入令牌每百万个令牌收费 0.15 美元（或每 660 万个输入令牌收费 1 美元），输出令牌每百万个令牌收费 0.60 美元（或每 160 万个输出令牌收费 1 美元）。这些成本大约是*GPT-4o*模型定价的 1/16。

![图 2.6：GPT-4o 输入和输出令牌的成本](img/B31534_02_6.png)

图 2.6：GPT-4o 输入和输出令牌的成本

例如，我们可以计算运行*Lab 2.1*的成本，该实验使用了 15 个输入令牌和 292 个输出令牌。根据*GPT-4o-mini*模型的定价，成本如下：

```py
>> (15 * 0.15 + 292 * 0.6) / 1000000
>> 0.00018 
```

这大约是 1/55 分。

如果我们使用更大的*GPT-4o*模型来运行*Lab 2.1*，成本如下：

```py
>> (15 * 2.5 + 292 * 10) / 1000000
>> 0.002 
```

这相当于 1/5 分。

在设计自己的应用程序时，请记住这些成本差异，尤其是在决定使用更先进的模型及其较小、更经济实惠的版本之间时。随着新模型的推出，模型价格历史上一直在下降，因此定期查看[`openai.com/api/pricing/`](https://openai.com/api/pricing/)上的**定价**页面是个好主意。

在清楚了解成本计算之后，我们现在可以继续讨论与 OpenAI 账户不同层级相关的限制和限制。

# 理解免费和付费 OpenAI 账户的速率限制和使用限制

OpenAI 的使用受到三个因素的限制：**每分钟请求数**（**RPM**）、**每天请求数**（**RPD**）和**每分钟令牌数**（**TPM**）。每个限制的值根据模型和您拥有的账户类型而有所不同。对于未添加信用额的免费层账户，限制为每分钟三个 RPM，并且只有某些模型可用，不包括*GPT-4o*。对于像*GPT-4o*这样的高级模型，令牌限制通常更为严格，适用于所有账户层级，而较老或迷你模型，如*GPT-4o-mini*，则有更宽松的限制。

仅供参考，以下是截至 2025 年 1 月的免费层账户的速率限制：

![图 2.7：免费层账户的速率限制示例](img/B31534_02_7.png)

图 2.7：免费层账户的速率限制示例

以下是截至 2025 年 1 月层 1 账户的速率限制：

![图 2.8：层 1 账户的速率限制示例](img/B31534_02_8.png)

图 2.8：层 1 账户的速率限制示例

我们鼓励您通过导航到组织右上角的 **设置** 部分来了解您账户的 API 限制：[`platform.openai.com/settings/organization/limits`](https://platform.openai.com/settings/organization/limits)。

在层 1 的 RPM 和 TPM 限制增加后，我们现在可以继续前进到下一个实验室，我们将探索 OpenAI API 的其他参数。

# Lab 2.2 – 分析请求参数

在 *Lab 2.2* 中，我们将通过添加额外的参数来扩展我们对 Chat 服务的 OpenAI API 基本请求，以自定义模型的响应。这次，我们将要求 Chat 服务解释 *两数之和问题*，我们将在后续章节中进一步探讨这个话题。

我们将使用与 *Lab 2.1* 类似的起始代码，其中包括设置 `OpenAI` 客户端和 `print` 语句：

```py
client: OpenAI = OpenAI()
completion: openai.ChatCompletion = ( 
    client.chat.completions.create()) print("Completion Tokens: ") print("Output: ") 
```

在本实验室的指导性说明中，我们将添加以下有效负载参数：

`n`：指定响应变体的数量

`temperature`：控制模型输出的随机程度，范围从 `0` 到 `2`

`max_tokens`：限制每个响应中的标记数

诸如代码补全服务之类的应用程序通常从语言模型为用户提供多个建议，因此我们可能希望检索多个响应。此外，在某些情况下，例如生成创意提示（例如，`给我一个关于 GenAI 编码的书的营销标语`），我们可能更喜欢输出中更高的随机度，这可以通过将 `temperature` 参数设置得更接近其最大值 2 来实现。

`max_tokens` 参数限制了响应中的标记数，但这并不保证输出将在该限制内完全完整。当使用 `max_tokens` 时，OpenAI 按指定的标记限制而不是实际使用的标记数收费，因此最好将其设置得接近预期响应长度。

## Lab 2.2 指导性说明

这个说明包括两个步骤：更新带有额外参数的有效负载以及添加一个 `print` 语句以显示额外的响应。

在书籍仓库的 *ch2/labs/lab22.py* 中打开 *Lab 2.2*，并确保您已设置 `OPENAI_API_KEY` 环境变量或配置了您的 `run` 设置以指向 *.env* 文件。

作为第一步，更新第 7 行 `.create` 方法的参数如下：

1.  将模型设置为 `gpt-4o-mini`：

    ```py
    model = "gpt-4o-mini" 
    ```

如果您尚未向您的 OpenAI 平台账户添加信用，您的访问可能仅限于某些模型，不包括 `gpt-4o-mini`。在这种情况下，请使用 `gpt-3.5-turbo` 模型。

1.  设置一个低的`temperature`参数以减少输出的随机性：

    ```py
    temperature=0.2 
    ```

1.  将`max_tokens`参数设置为限制模型的输出最多为 100 个令牌：

    ```py
    max_tokens=100 
    ```

1.  将`n`参数设置为指示模型为请求返回单个响应：

    ```py
    n=1 
    ```

1.  将系统提示添加到`messages`参数中，以给代理商一个科技公司招聘经理的语气：

    ```py
    {"role": "system", "content": "You are a hiring manager at a tech company."} 
    ```

1.  将额外的用户提示添加到`messages`参数中，询问关于两数之和问题：

    ```py
    `{`"role"`:` "user"`,` "content"`:` "What is the Two Sum problem?"`}` 
    ```

1.  对于第二步，更新`print`语句以显示输出令牌计数和模型输出。

1.  将第一个`print`语句修改为指示输出计数：

    ```py
    print("Completion Tokens: ", completion.usage.completion_tokens) 
    ```

1.  要显示输出响应，更新第二个`print`语句如下：

    ```py
    print("Output: ", completion.choices[0].message.content) 
    ```

如果你正确地遵循了所有步骤，你的代码应该看起来像这样：

```py
import openai from openai import OpenAI if __name__ == "__main__": 
    client: OpenAI = OpenAI() 
    completion: openai.ChatCompletion = ( 
        client.chat.completions.create( 
            model="gpt-4o-mini",
            temperature=0.2,
            max_tokens=100,
            n=1,
            messages=[{"role": "system", "content": "You are a hiring manager at a tech company."},
            {"role": "user", "content": "What is the Two Sum problem?"}],
        )) print("Completion Tokens: ", completion.usage.completion_tokens) print("Output: ", completion.choices[0].message.content) 
```

*Lab 2.2*现在可以运行，并将打印输出令牌计数以及用户提示`什么是两数之和问题？`的响应。

## Lab 2.2 分析

运行脚本并检查输出。如果你使用 VS Code，请查看终端，如果你使用 PyCharm，请检查`run`控制台。确保输出令牌计数不超过 100，并且聊天服务开始解释两数之和问题，这是我们将在未来章节中再次讨论的主题。

请记住，设置`max_tokens`限制并不能保证完整的解释，并且可能会截断响应。

以下是从运行实验室获得的样本输出，限制为 100 个令牌，相当于 84 个单词：

```py
"The Two Sum problem is a classic algorithmic problem often encountered in coding interviews and competitive programming. The problem can be stated as follows:
Given an array of integers `nums` and an integer `target`, you need to determine if there are two distinct indices `i` and `j` in the array such that the sum of the elements at these indices equals the target value. In other words, you need to find two numbers in the array that add up to the specified target. ### Problem Statement" 
```

虽然这个输出被截断，但它可能仍然提供足够的信息来理解两数之和问题。

注意

问题：你能计算*lab22.py*请求的成本吗？

答案：

`>> (28 * 0.15 + 100 * 0.6) / 1000000>> 0.000064`

这大约是 1/150 美分。

## 使用 Lab 2.2 的多个服务响应

反思*Lab 2.2*，我们现在可以更好地理解有效载荷请求参数对聊天服务初始输出的影响。

在那个实验室中，我们将`n`参数设置为`1`，这也是默认值。然而，在某些 GenAI 应用中，生成多个响应可能是有益的。例如，在 GitHub Copilot 或其他代码补全服务中，显示多个建议可以增强用户体验。在这种情况下，通过增加`n`参数的响应数量，可以让模型提供多个输出。请注意，计费将包括所有生成的输出以及输入令牌。

在*Lab 2.2*中，将`n`参数修改为请求三个不同的响应，并增加`temperature`参数以鼓励输出更多的随机性和多样性：

```py
n=3 temperature = 2 
```

现在，更新`print`语句以包括聊天服务的附加输出：

```py
print("Output 1: ", completion.choices[0].message.content) print("Output 2: ", completion.choices[1].message.content) print("Output 3: ", completion.choices[2].message.content) 
```

再次运行实验室以查看聊天服务解释两数之和问题的三个不同响应。你可以自由地进一步实验参数，看看它们如何影响输出。

接下来，我们将探讨如何利用 OpenAI API 进行与编码相关的任务，例如根据函数签名生成 Python 代码实现。

# 实验 2.3 – 使用 OpenAI API 生成代码

现在我们已经学会了如何执行 OpenAI API 调用并配置各种参数，我们可以使用它们来创建我们自己的基本代码补全程序。以前，开发者可以选择像 `code-davinci-002` 这样的模型，这些模型专门用于代码补全。这些模型现在已经弃用，现在聊天服务可以有效地处理代码补全任务。

## 将聊天功能路由到代码补全

在本实验中，我们将通过五个步骤创建一个代码补全程序：

1.  仅定义函数签名输入。

1.  添加系统提示以引导模型生成完整的代码。

1.  使用特定指令包装函数签名以让模型完成代码。

1.  获取我们请求的聊天服务响应。

1.  仅从模型的输出中提取代码以呈现给最终用户。

这些步骤展示了基于 LLM 模型的应用程序需要采用定制方法，例如使用包装设计和特定提示，以使模型的输出与当前的业务问题相匹配。我们将在本书的后面深入探讨这一点。

我们的开源代码包含所有五个步骤，我们将在引导演示中完成它们：

```py
import openai from openai import OpenAI
USER_PROMPT = """
user prompt here
""" SYSTEM_PROMPT = "system prompt here"
def get_code_with_instructions(code: str) -> str: """ 
 Add a comment to the code for specific code completion instruction 
 :param code: Python code as string 
 :return: The code with additional instruction - "Complete this code" 
 """ 
    return code + "your wrapping instructions here"
if __name__ == "__main__": 
    client: OpenAI = OpenAI() 
    completion: openai.ChatCompletion = (
        client.chat.completions.create()) for i in range(2): 
        output = completion.choices[i].message.content print(f"Output {i + 1}:") try: 
            suggested_code = output.split("```")[1] print(suggested_code) except IndexError: print(output)

```py

In this lab walk-through, we will learn how to complete the system prompt, wrapping instructions for the `get_code_with_instructions` function, and payload arguments for `client.chat.completions.create`. Combined with a function signature as the user prompt, these elements will channel OpenAI’s Chat service capabilities toward a targeted code completion program.

## Lab 2.3 guided walk-through

Open *Lab 2.3* in the book repository at *ch2/labs/lab23.py* and ensure that you have either set the `OPENAI_API_KEY` environment variable or configured your `run` settings to point to the *.env* file.

First, set the user prompt to be a function signature for printing the Fibonacci sequence:

```

USER_PROMPT="""

def print_fibonacci_sequence(n: int) -> None:

"""

```py

Next, include a system prompt to set guidelines for the assistant to act as an AI pair programmer:

```

SYSTEM_PROMPT = "您将获得一个 Python 函数签名。您的任务是实现该函数。仅返回代码。"

```py

We will also wrap the function signature to include a specific instruction for code completion. Update the `get_code_with_instructions` function to wrap the given code with an extended comment that instructs the model to complete the function signature:

```

return code + "\n# 完成此代码"

```py

Next, configure the payload arguments by specifying the appropriate model, the desired number of responses, and the level of randomness:

1.  Set the model to `gpt-4o-mini`:

    ```

    model = "gpt-4o-mini"

    ```py

If you have not loaded credits to your OpenAI platform account yet, your access may be limited to certain models, excluding `gpt-4o-mini`. In that case, use the `gpt-3.5-turbo` model instead.

1.  Set a medium `temperature` argument to increase the randomness of the outputs:

    ```

    temperature=1

    ```py

2.  Set the `n` argument to instruct the model to return two different coding suggestions:

    ```

    n=2

    ```py

3.  Finally, set up the request arguments to include the wrapped function signature as the user prompt, along with a system prompt:

    ```

    model = "gpt-4o-mini" temperature=1 n=2 messages = [

        {"role": "system", "content": SYSTEM_PROMPT},

        {"role": "user", "content": get_code_with_instructions(USER_PROMPT)}

    ]

    ```py

If you followed all the steps correctly, your lab’s code should be implemented as follows:

```

import openai from openai import OpenAI

USER_PROMPT = """

def print_fibonacci_sequence(n: int) -> None:

""" SYSTEM_PROMPT = "您将获得一个 Python 函数签名。您的任务是实现该函数。仅返回代码。"

def get_code_with_instructions(code: str) -> str: """

在代码中添加注释以提供特定的代码补全指令

:param code: 字符串形式的 Python 代码

:return: 带有附加指令 "完成此代码" 的代码

"""

    return code + "\n# 完成此代码"

if __name__ == "__main__":

    client: OpenAI = OpenAI()

    completion: openai.ChatCompletion = (

        client.chat.completions.create(

            model="gpt-4o-mini",

            temperature=1,

            n=2,

            messages=[

                {"role": "system", "content": SYSTEM_PROMPT},

                {"role": "user", "content": get_code_with_instructions(USER_PROMPT)}

            ],

        )

    )

    ...

```py

*Lab 2.3* is now ready to run and will print two coding suggestions for the Fibonacci sequence.

## Lab 2.3 analysis

In this lab, we wrapped the user prompt and added a supporting system prompt to explicitly define the task for the Chat service: to complete a function that prints the Fibonacci sequence based solely on its signature. The following is a sample output generated when running this lab with two outputs. The first response provides a shorter solution without type checking, printing the Fibonacci numbers one by one. The second response includes input validation, creates the sequence up to the `n` limit, and then prints the entire sequence:

```

输出 1:

def print_fibonacci_sequence(n: int) -> None:

    a, b = 0, 1

    for _ in range(n):

        print(a, end=' ')

        a, b = b, a + b

    print()   # 在序列后换行

输出 2:

def print_fibonacci_sequence(n: int) -> None:

    if n <= 0:

        print("请输入一个正整数。")

        return

    sequence = []

    a, b = 0, 1

    count = 0

    while count < n:

        sequence.append(a)

        a, b = b, a + b

        count += 1

    print(sequence)

```py

To further explore code completion, try adding additional system prompts such as `add a docstring` or `add type hints` and observe the results. You can also increase the number of returned outputs or modify the instructions in the wrapped user prompt to see how these changes affect the generated code.

Important note

In this lab, the system prompt includes specific instructions for the desired output: `Return code only`. In later chapters, we will explore how to craft more effective instructions to guide the model toward the desired output structure using best practices and prompt engineering techniques.

# Summary

In the first quickstart guide, we used the `openai` Python package to build three different programs based on AI-generated output. We experimented with various models, including *GPT-4o* and *GPT-3.5*, explored different request parameters, and combined user prompts with system prompts.

We also loaded credits to the OpenAI platform, which increased our rate limits and allowed us to use a broader range of models. We learned how request costs are calculated based on the number of input and output tokens.

Finally, we developed a basic code completion program that wrapped a function signature, guiding the model to generate the rest of the function’s implementation.

With these foundations in place, we can progress to the next chapter, *Quickstart Guide to GitHub Copilot*, and better understand how Copilot generates coding suggestions and how to tailor them to fit our unique preferences when necessary.

# Quiz time

Before you proceed to the next chapter, make sure that you can confidently answer the following questions:

**Question 1**: What is the difference between a system prompt and a user prompt in a Chat service request?

**Answer**: User prompts are the inputs provided by the end user, such as the questions or commands given to ChatGPT. They represent the direct interaction with the AI-generated content, such as the following:

```

解释两数之和问题

```py

Here is another example:

```

def print_fibonacci_sequence(n): # complete this code

```py

System prompts, however, define the guidelines and tone for the Chat interaction. They instruct the assistant on how to behave during the conversation with the end user, as in this example:

```

您是软件工程实习生的技术面试官

```py

Here is another example:

```

您将获得一个 Python 函数签名。您的任务是实现该函数。仅返回代码。

```py

**Question 2**: What are tokens, and how do they impact the cost of an OpenAI API request?

**Answer**: Tokens are small segments of text, typically averaging around 0.75 words or 4 characters each when the text is split into tokens based on elements such as punctuation, root words, and word endings. The cost of an OpenAI API request is calculated based on the number of input tokens, output tokens, and the `max_tokens` argument, with different models having varying token costs.

# Further reading

To learn more about the topics that were covered in this chapter, take a look at the following resources:

*   OpenAI Platform home page: [`platform.openai.com`](https://platform.openai.com)
*   OpenAI API official documentation: [`platform.openai.com/docs/overview`](https://platform.openai.com/docs/overview)
*   OpenAI Pricing: [`openai.com/api/pricing/`](https://openai.com/api/pricing/)
*   OpenAI Rate Limits (General): [`platform.openai.com/docs/guides/rate-limits`](https://platform.openai.com/docs/guides/rate-limits)
*   OpenAI available models: [`platform.openai.com/docs/models/model-endpoint-compatibility`](https://platform.openai.com/docs/models/model-endpoint-compatibility)
*   OpenAI individual rate limits: [`platform.openai.com/settings/organization/limits`](https://platform.openai.com/settings/organization/limits)
*   The FizzBuzz wiki page: [`en.wikipedia.org/wiki/Fizz_buzz`](https://en.wikipedia.org/wiki/Fizz_buzz)
*   The Two Sum Leet Code page: [`leetcode.com/problems/two-sum/description/`](https://leetcode.com/problems/two-sum/description/)

# Subscribe for a free eBook

New frameworks, evolving architectures, research drops, production breakdowns—AI_Distilled filters the noise into a weekly briefing for engineers and researchers working hands-on with LLMs and GenAI systems. Subscribe now and receive a free eBook, along with weekly insights that help you stay focused and informed.

Subscribe at [`packt.link/TRO5B`](https://packt.link/TRO5B) or scan the QR code below.

![A qr code on a white background  AI-generated content may be incorrect.](img/B31534_Newsletter_NEW.png)

# 3

# A Guide to GitHub Copilot with PyCharm, VS Code, and Jupyter Notebook

GitHub Copilot, an **AI pair programmer**, is enabling developers to supercharge their coding abilities and write code more efficiently. The application uses an underlying **large language model (LLM)** designed specifically for code completion tasks, code analysis, and chat for coding-related tasks.

Since we built our own code completion program capable of completing a Python function based on its signature alone in *Chapter 2*, we can better understand the role of LLMs in Copilot’s implementation, as well as what other preprocessing and postprocessing work is required.

This chapter is dedicated to working with GitHub Copilot in our **integrated development environment** (**IDE**). First, we will set up a GitHub Copilot account and determine who is eligible for a free account. Then, we will connect our account to our IDE (either VS Code or PyCharm) and explore the three interaction modes of the tool: chat, completion, and analysis. We will also work with Copilot in a Jupyter Notebook using VS Code. PyCharm cannot run Jupyter notebooks yet with Copilot.

Through three interactive labs, we will implement a geometric mean calculator using all three GitHub Copilot interaction modes: chat, completion, and analysis. Additionally, we will experiment with keyboard shortcuts for core Copilot functionality to help streamline our workflow and boost productivity.

In this chapter, we will cover the following key topics:

*   Introducing GitHub Copilot – our AI pair programmer
*   Understanding GitHub Copilot’s free account limits, costs, and policies
*   Setting up Copilot in PyCharm and VS Code
*   Using Copilot chat
*   Introducing completion and keyboard shortcuts for geometric mean calculations
*   Analyzing code with Copilot
*   Working with Copilot in VS Code’s Jupyter Notebook for code analysis

# Technical requirements

To get the most out of this chapter, ensure you have the following:

*   GitHub account
*   Access to IDE – either VS Code or PyCharm
*   Access to the book’s repository, which is available at [`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)
*   Virtual environment set up in your preferred IDE, VS Code or PyCharm

If you require additional assistance in setting up your OpenAI account or a virtual environment in your IDE, refer to the *Appendix* for detailed instructions.

# Introducing GitHub Copilot – our AI pair programmer

**GitHub Copilot** is an AI-powered tool that uses LLMs trained on vast and diverse datasets containing a significant amount of open source code from public repositories across various programming languages, including Python. By combining the model’s extensive knowledge with your code’s context, GitHub Copilot provides tailored coding suggestions, as well as chat and code analysis features, to assist in your development process.

## Code completion design overview

To provide meaningful code completions, Copilot processes the input and output of the LLM, like the code completion program developed in *Lab 2.3*. For the input, Copilot structures a prompt based on the lines surrounding the cursor, function signatures, and additional context, such as recent edits, Git details, file names and open files. The LLM’s output is further processed, including validation to ensure it compiles successfully.

We can visualize Copilot’s code completion process as a flowchart, as shown in *Figure 3.1.*

![Figure 3.1: An overview of GitHub Copilot’s suggestion process](img/B31534_03_01.png)

Figure 3.1: An overview of GitHub Copilot’s suggestion process

In addition to code completion, GitHub Copilot offers two other modes of interaction: chat (available inline or through the chat window) and code analysis. Both modes are based on the underlying code and comments but differ in their final output and the postprocessing steps involved. We will discuss these extensively later in this chapter.

**Important note**

Some developers may think that GitHub Copilot sends the entire Git repository code they are working on to the LLM. This is very unlikely given two reasons: the cost of input tokens and the relevance of the entire code to the specific code completion task. It is far more likely that only relevant code is preprocessed by Copilot first. Then, only the necessary information including coding style preferences or relevant classes, code, and variables, is added to the prompt in addition to the cursor’s surrounding context.

# Understanding GitHub Copilot’s free account limits, costs, and policies

To enable GitHub Copilot in your IDE, you first need to subscribe to the service through GitHub’s platform. Like many other GenAI services, GitHub Copilot is primarily a paid service, though some exceptions allow free access.

## Who is eligible for a free account?

There are three ways to qualify for GitHub Copilot at no cost:

*   Free account available to anyone, which includes up to 2,000 code completions and 50 chat requests per month.
*   Free pro account for students and educators with a valid university email
*   Free pro account for maintainers of popular open source repositories

If you are a student or educator with a university email and the required documentation, you can apply for GitHub’s Student Pack at [`education.github.com/pack`](https://education.github.com/pack).

If you are a leading maintainer of a popular open source repository, you may have free access to Copilot. GitHub determines eligibility based on internal criteria, without requiring an application process. If eligible, upon clicking your profile icon and selecting **Your Copilot,** you will be directed to a page titled *GitHub Copilot Individual* instead of a payment page, as detailed later in this chapter.

Some organizations and enterprises cover the cost of GitHub Copilot access for their users. If you belong to such an organization or enterprise, you will find a **request access** button next to the organization’s name at [`github.com/settings/copilot`](https://github.com/settings/copilot). In these cases, you will not be charged for using Copilot, as the organization or enterprise will handle the licensing fees on your behalf.

Compared to individual accounts, GitHub Copilot for business and enterprises offers additional features, such as pull request summaries, a knowledge base, and the ability to fine-tune a custom LLM for enterprise versions. These options come at a higher cost than individual memberships.

## Pricing

For individual users, the service is priced at $10 per month or $100 annually. For Copilot business, the rate is $19 per user per month, while the enterprise version increases to $39 per user per month.

## Code completion policies

All GitHub Copilot users are governed by specific policies that define the scope of code suggestions, privacy, and access points, including your IDE and [github.com](https://github.com/).

A notable policy is *suggestions matching public code*. Since the GitHub Copilot model is primarily trained on open source and publicly available code repositories, some of its suggestions may be subject to copyright protection. To mitigate potential issues, GitHub provides users with an option to exclude coding suggestions that replicate such code.

![Figure 3.2: Privacy and ownership options in Copilot](img/B31534_03_02.jpg)

Figure 3.2: Privacy and ownership options in Copilot

![](img/1.png) **Quick tip**: Need to see a high-resolution version of this image? Open this book in the next-gen Packt Reader or view it in the PDF/ePub copy.

![](img/2.png) **The next-gen Packt Reader** is included for free with the purchase of this book. Scan the QR code OR go to packtpub.com/unlock, then use the search bar to find this book by name. Double-check the edition shown to make sure you get the right one.

![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png)

Here, suggestions that match public code are allowed. We also recommend enabling additional underlying models such as Anthropic Claude and Google Gemini alongside to support further experimentation.

For business or enterprise accounts, the policies are pre-determined by the administrator of the organization or enterprise. Individual account users, however, can set their own policies during account setup or through the Copilot settings page: [`github.com/settings/copilot`](https://github.com/settings/copilot).

## Activating your GitHub Copilot account

To participate in the labs and hands-on exercises in this book, you will need either a free, pro, business, or enterprise GitHub Copilot account. If you wish to set up an individual account, go to [`www.github.com`](https://www.github.com), click on your profile icon, and select **Your Copilot**.

![Figure 3.3: Copilot access in the GitHub account](img/B31534_03_03.jpg)

Figure 3.3: Copilot access in the GitHub account

If you are a leading maintainer of a popular open source repository and qualify for free access to Copilot, you will be directed to a page titled *GitHub Copilot Individual* page. Otherwise, you will be directed to the payment page, where you can select a free trial option or a paid plan.

Select the plan that suits you, adjust settings to align with your individual or company policies (e.g., enable or disable public code matches), and enter your payment details.

Once completed, you will have access to Copilot services at [`github.com/settings/copilot`](https://github.com/settings/copilot ) as shown in *Figure 3.4*:

![Figure 3.4: GitHub Copilot settings header](img/B31534_03_04.jpg)

Figure 3.4: GitHub Copilot settings header

This page shows your access level, provides links to resources for setting up Copilot in your IDE, and outlines Copilot’s privacy and ownership policies.

With our account now activated, we are ready to proceed and connect Copilot to our IDE.

# Setting up Copilot in PyCharm and VS Code

GitHub Copilot is available via a PyCharm plugin or a VS Code extension. The core features of GitHub Copilot in both IDEs are similar, offering the three interaction modes we will cover in this book: chat, completion, and analysis.

However, Copilot is more tightly integrated with VS Code, meaning new features, such as Jupyter Notebook support or switching to newer LLMs, are often released in VS Code before they are available in the PyCharm extension.

Since your GitHub Copilot subscription can be used across multiple IDEs, we encourage PyCharm users to try VS Code to explore Jupyter Notebook support. However, the labs in this book are tailored for both PyCharm and VS Code.

## GitHub Copilot plugin for PyCharm

To install the GitHub Copilot plugin in PyCharm, go to **PyCharm** | **Settings** | **Plugins**, then search `GitHub Copilot` in the marketplace. After installation, you will be prompted to restart your IDE.

![Figure 3.5: GitHub Copilot Plugin in PyCharm](img/B31534_03_05.jpg)

Figure 3.5: GitHub Copilot Plugin in PyCharm

When your IDE restarts, you will be prompted to log in to your GitHub account.

To check whether the service is available, look for the Copilot icon at the bottom of the IDE. Hovering over it should display **Ready**.

![Figure 3.6: GitHub Copilot plugin icon health check in PyCharm](img/B31534_03_06.jpg)

Figure 3.6: GitHub Copilot plugin icon health check in PyCharm

This confirms that the plugin is set up correctly, allowing us to start using Copilot.

## GitHub Copilot extension for VS Code

To install the Copilot extension, navigate to **Code** | **Extensions**, search `GitHub Copilot`, and install it. When you do this, the GitHub Copilot Chat extension will also be automatically installed.

![Figure 3.7: GitHub Copilot and Copilot Chat extension in VS Code](img/B31534_03_07.png)

Figure 3.7: GitHub Copilot and Copilot Chat extension in VS Code

After the installation, the GitHub Copilot extension window will open, prompting you to authenticate or sign up for a GitHub Copilot account.

To check whether the extension is working properly after authentication, click on the GitHub Copilot icon in the bottom-right corner to open **GitHub Copilot Menu**.

![Figure 3.8: GitHub Copilot icon in the bottom right window](img/B31534_03_08.png)

Figure 3.8: GitHub Copilot icon in the bottom right window

A drop-down list will appear, and if you are logged into your GitHub account with a stable internet connection, the status should display **Ready**.

![Figure 3.9: Verifying GitHub Copilot extension status in VS Code](img/B31534_03_09.png)

Figure 3.9: Verifying GitHub Copilot extension status in VS Code

This confirms that the extension is set up correctly, allowing us to start using Copilot.

## The three interaction modes – chat, completion, and analysis

Originally designed to provide tailored code completion suggestions, GitHub Copilot now offers three key interaction modes powered by LLMs: chat, completion, and analysis:

1.  **Chat** is accessible via a chat window resembling the ChatGPT interface or through an inline compact view. We will use this mode when we want contextual assistance with coding-related questions.
2.  **Completion** is available automatically in our files. As we type, Copilot will suggest code completions based on the code we write. We will use this mode when implementing new code.
3.  **Analysis** includes features such as *explain*, *fix*, and *tests*, which are available through the chat window, the inline chat, and the edits window in VS Code. We will use this mode when interacting with existing code.

In the next three labs, we will experiment with each of these interaction modes.

# Using Copilot chat

The chat feature complements GitHub Copilot’s code completion capabilities. The chat window can assist with questions related to your code, external topics, terminal commands, and even the VS Code IDE itself.

In VS Code, you can open the Copilot chat window using *Ctrl + Alt + I* (or *cmd + control + I* on Mac). Alternatively, click on the Copilot icon next to the top search bar of the screen.

![Figure 3.10: GitHub Copilot chat window in VS Code](img/B31534_03_10.jpg)

Figure 3.10: GitHub Copilot chat window in VS Code

In PyCharm, you can open the Copilot chat window using *Ctrl* + *Shift* + *C* or by selecting the **GitHub Copilot Chat** tab in the left-hand menu.

![Figure 3.11: GitHub Copilot chat window in PyCharm](img/B31534_03_11.jpg)

Figure 3.11: GitHub Copilot chat window in PyCharm

Let us look at an example. Open a new chat window and enter this prompt:

```

您能做什么？

```py

Copilot will respond with examples of use cases across the three interaction modes, such as refactoring existing code (analysis), generating unit tests (completion), providing version control assistance (chat), and more. In addition to the response itself, GitHub Copilot chat will also display the pre-processed context in addition to the prompt itself, and the steps taken to prepare the input for the LLMs such as the following:

*   Collecting recent files
*   Retrieving Git information
*   Analyzing problems and errors

This aligns with the GitHub Copilot process flow we discussed earlier in this chapter.

Here is an example of the prompt, `What can you do?`, output in PyCharm:

```

我可以帮助您处理各种编程任务，例如：

- 编写和调试代码

- 解释代码片段和概念

- 提供代码示例和模板

- 协助版本控制（例如，Git）

- 帮助配置和设置开发环境

- 提供最佳实践和优化技巧

如果您有具体问题或需要帮助解决特定的代码片段，请随时提问！

```py

Here is an example of the prompt, `What can you do?`, output in VS Code:

```

我可以帮助处理各种编程任务，包括：

* 回答一般编程问题

* 解释您活动编辑器中的代码如何工作

* 审查您活动编辑器中的选定代码

* 为选定的代码生成单元测试

* 为选定的代码中的问题提出修复方案

* 为您的工作区中的新文件或项目搭建代码框架

* 创建一个新的 Jupyter Notebook

* 找到与您的查询相关的代码

* 提出测试失败的修复方案

* 回答关于 VS Code 的问题

* 生成工作区搜索的查询参数

运行命令

* 解释终端输出

* 为终端任务提供逐步指导

今天我能帮您做什么？

```py

The PyCharm plugin and the VS Code extension may produce different outputs for the same prompt. This occurs because the GitHub Copilot application handles files in PyCharm and VS Code slightly differently, offers distinct features in each, and incorporates an element of randomness. Keep in mind that, like any GenAI output, suggestions may not always be accurate or complete, as we will observe later in this chapter.

Next, we will explore how the chat window can enhance code completion tasks within our IDE, even when further exploration of a topic is needed (such as an explanation of the geometric mean).

# Lab 3.1 – calculating geometric mean with chat completion

In *Lab 3.1*, we will explore the geometric mean through the chat interaction mode. The geometric mean is a way of averaging numbers that are multiplicative in nature, such as financial portfolio growth rates, population growth rates, or drug concentrations that vary exponentially over time. Unlike the arithmetic mean, which calculates the sum of a sequence of numbers divided by its length, the geometric mean is the *n*-th root of the product of the numbers:

![@holatex \begin{document} $$ \text{Arithmetic Mean} = \dfrac{1}{n} \sum_{i=1}^n x_i $$ \end{document}](img/B31534_03_001.png)![@holatex \begin{document} $$ \text{Geometric Mean} = \left( \prod_{i=1}^n x_i \right ) ^{\frac{1}{n}} $$ \end{document}](img/B31534_03_002.png)

For example, the geometric mean of 5 and 20 is 10, because of the following:

![@holatex \begin{document} $$ (20 \cdot 5)^{\frac{1}{2}} = (100)^{\frac{1}{2}} = \sqrt{100} = 10 $$ \end{document}](img/B31534_03_003.png)

Similarly, the geometric mean of 5, 20, and 10 is also 10, because of the following:

![@holatex \begin{document} $$ (20 \cdot 5 \cdot 10)^{\frac{1}{3}} = (1000)^{\frac{1}{3}} = \sqrt[3]{1000} = 10 $$ \end{document}](../Images/B31534_03_004.png)

In this lab, we will use the chat window along with code completion. First, we will obtain an explanation of the geometric mean using the chat window. Next, we will utilize Copilot to complete an implementation based on a function signature, including the name, parameters, type hints, and return values. Finally, we will print the function’s output by defining sample call parameters.

## Lab 3.1 guided walk-through

Open *Lab 3.1* in the book’s repository at *ch3/labs/lab31.py* and ensure that you have a stable internet connection, and that GitHub Copilot is ready.

The starter code consists of three parts:

```

# 第一部分：打开聊天窗口并要求解释几何平均数。

# 第二部分：实现两个浮点数的几何平均数函数。

# 第三部分：调用

```py

`Part 1` is for practice only, `Part 2` requires specifying the function signature for code completion, and `Part 3` involves adding sample parameters and printing their response.

For `Part 1`, delete the comment, open the Copilot chat window and enter the following prompt:

```

解释几何平均数。

```py

This prompt will provide an explanation of the geometric mean. Note that the explanation may be truncated due to the `max_tokens` limit of Copilot, which we have no control over, or contain raw mathematical formatting, such as LaTeX code instead of compiled equations. Despite this, it should still provide enough information for us to understand the topic.

For `Part 2`, delete the comment and type the function signature to calculate the geometric mean of two floating-point numbers:

```

def get_geometric_mean_of_two_numbers(

a: float,

b: float, ) -> float:

```py

This function signature, with its name, parameters, type hints, and return type, is considered a complete prompt to Copilot that should yield a desirable implementation.

In `Part 3`, delete the comment and add a sample call that tests the implementation. Enter the following prompt:

```

num1: float = 5.0 num2: float = 20.0

print

```py

The `print` statement acts as the cue for Copilot, which will likely suggest a call to the `get_geometric_mean` function using `num1` and `num2` as arguments.

If you followed all the steps correctly, your code should look like this:

```

def get_geometric_mean_of_two_numbers(

a: float,

b: float, ) -> float: return pow(a * b, 1 / 2)

num1: float = 5.0 num2: float = 20.0

print(get_geometric_mean_of_two_numbers(num1, num2))

```py

*Lab 3.1* is now ready to run and will print the geometric mean of 5 and 20, which is as follows:

```

10.0

```py

## Lab 3.1 analysis

In this lab, we used Copilot chat to learn about the geometric mean. We also leveraged code completion based on either a function signature as a starter code or a print call as a cue.

For your reference, here is the Copilot chat response to the prompt, `Explain the geometric mean`. We generated it using the VS Code chat window with the *GPT-4o* model. The response includes raw LaTeX code and is truncated before the full output:

```

>> 几何平均数是一种中心趋势度量，特别适用于那些数值需要相乘或具有指数性质的数字集合。它定义为 n 个数的乘积的 n 次方根。公式

对于一组（n）正数（x_1, x_2, ..., x_n），几何平均数（G）由以下公式给出：

[ G = \left( \prod_{i=1}^{n} x_i \right)^{\frac{1}{n}} ]

计算步骤

将所有数字相乘以得到乘积。取乘积的 n 次方根，其中（n）是值的总数。示例

考虑数字 2, 8 和 4：

将数字相乘：（2 × 8 × 4 = 64）

由于有 3 个数字，取立方根：（√[3]{64} =）

```py

Choosing the underlying models to power the chat is available in the bottom-right corner of the chat window.

![Figure 3.12: Model selection for the Copilot chat window](img/B31534_03_12.jpg)

Figure 3.12: Model selection for the Copilot chat window

We found this response lacking due to the truncation of the example, as Copilot imposes a `max_tokens` limit on model outputs, and the formatting of mathematics as raw LaTeX code. However, for topics we are already familiar with, the chat window saves considerable time and eliminates the need to use external tools, such as Google or ChatGPT.

Next, we will further explore GitHub Copilot’s code completion capabilities using a variety of keyboard shortcuts to make our experience even smoother.

# Lab 3.2 – introducing completion and keyboard shortcuts for geometric mean calculations

Keyboard shortcuts are vital for enhancing a programmer’s efficiency, especially when working with Copilot, which provides a wide range of options to accept or reject suggestions partially or fully. This lab will focus on implementing the geometric mean using code completion, incorporating keyboard shortcuts to do the following:

*   Reject a suggestion
*   Regenerate a rejected suggestion
*   Accept a full suggestion or parts of it
*   Switch between different code options.

In this lab, we will implement the geometric mean for a sequence of floating-point numbers using a function signature and an instructive prompt to validate the input arguments. We will explore various implementation suggestions, selectively accepting or rejecting parts of them.

**Important note**

This lab includes standard keyboard shortcuts for working with Copilot. If any of these are missing or you would prefer different shortcuts, you can customize them by editing your keymap. In PyCharm, navigate to **Settings** | **Keymap**, and in VS Code, go to **Settings** | **Keyboard Shortcuts**. For further assistance with keyboard shortcuts, refer to the *Appendix*.

## Lab 3.2 guided walk-through

Open *Lab 3.2* in the book repository at *ch3/labs/lab32.py* and ensure that you have a stable internet connection, and that GitHub Copilot is ready.

There is no starter code for this lab. Our task is to begin by typing an instructive function signature to calculate the geometric mean of a sequence of floating-point numbers.

Add the following code to the file. If you type it rather than copy and paste it, Copilot may offer early completion suggestions. Ignore these until you complete the prompt:

```

def get_geometric_mean(*nums):

```py

At this point, you should already see completion suggestions by Copilot. Use the following instructions for both PyCharm and VS Code to explore these suggestions:

![Figure 3.13: Copilot code completion example in VS Code](img/B31534_03_13.png)

Figure 3.13: Copilot code completion example in VS Code

To experiment with Copilot’s keyboard shortcuts, follow these steps. If any of the keyboard shortcuts are different or missing in your interface, make sure to find the alternate shortcuts:

1.  Accept the entire code completion by pressing *Tab*.
2.  Then, undo it by *Ctrl* + *Z* / *cmd* + *Z*.
3.  In PyCharm, accept a single line from the suggestion by pressing *Ctrl* + *Alt* + the right arrow (*cmd* + *control* + right if you are a Mac user).
4.  In VS Code, there is no default keyboard shortcut for this. Instead, hover over the suggested text, click on the ellipsis (**...**), and select **Accept Line**.
5.  Then, undo it by pressing *Ctrl* + *Z* / *cmd* + *Z*.
6.  Accept a single word from the suggestion by pressing *Ctrl* + the right arrow (*cmd* + the right arrow if you are a Mac user).
7.  Then, undo it by pressing *Ctrl* + *Z* / *cmd* + *Z*.
8.  Hide the suggestion by pressing *Esc*.
9.  Retrigger the Copilot suggestion by pressing *Alt* + *\* (*option* + *\* if you are a Mac user).
10.  Toggle to the next suggestion by pressing *Alt* + *]* (*option* + *]* if you are a Mac user). Go back to previous suggestions by pressing *Alt* + ** (*option* + *[* if you are a Mac user).
11.  In PyCharm, access the code completion pane by right-clicking on Copilot’s suggestions and selecting **Copilot: Open Completion**.
12.  In VS Code, access it by pressing *Ctrl* + *Enter*.

Next, we encourage you to modify the prompt by adjusting the function name, arguments, type hints, or return type. Keep practicing with the keyboard shortcuts and observe how the completions evolve with each change.

## Lab 3.2 analysis

In this lab, we practiced keyboard shortcuts in PyCharm and VS Code to streamline pairing with Copilot, making it easier to accept, reject, or switch between completion suggestions smoothly.

For your reference, a sample completion for the `get_geometric_mean` implementation in PyCharm is shown in *Figure 3.14*.

![Figure 3.14: Copilot inline menu in PyCharmFigure 3.14: Copilot inline menu in PyCharmWhen right-clicking on the completion and selecting **Copilot: Open Completion**, the completion pane displays various suggestions provided by Copilot.![Figure 3.15: Copilot code completion pane in PyCharm](img/B31534_03_15.jpg)

Figure 3.15: Copilot code completion pane in PyCharm

We can then choose to accept any of these suggested solutions.

Similarly, VS Code will also display a variety of different completion suggestions.

![Figure 3.16: VS Code Copilot code completion pane](img/B31534_03_16.jpg)

Figure 3.16: VS Code Copilot code completion pane

Here too, we can then choose to accept any of these suggested solutions.

**Important Note**

In later chapters, we will explore best practices for prompt precision and prompt engineering techniques. These will help us better structure a function’s content by covering aspects like input validation, formatting with type hints, and handling side effects such as monitoring and logging.

Next, we will explore Copilot’s code analysis options, demonstrating how they complement code completion when working with existing code.

# Analyzing code with Copilot

The recently introduced code analysis features in both PyCharm and VS Code complement GitHub Copilot’s code completion capabilities. It can be accessed via the Copilot menu or the inline chat window using commands such as `/fix` `/explain` and `/test`

To use these features, right-click on your code, select **Copilot**, and you will see the available options. This menu is accessible in both PyCharm and VS Code.

Here is how the menu appears in PyCharm:

![Figure 3.17: Copilot code analysis in PyCharm](img/B31534_03_17.jpg)

Figure 3.17: Copilot code analysis in PyCharm

Here is how the menu appears in VS Code:

![Figure 3.18: Copilot code analysis in VS Code](img/B31534_03_18.jpg)

Figure 3.18: Copilot code analysis in VS Code

For quicker access, you can use Copilot inline chat commands. In VS Code, press *Ctrl* + *I* (*cmd* + *I* for Mac).

![Figure 3.19: Copilot editor inline chat in VS Code](img/B31534_03_19.jpg)

Figure 3.19: Copilot editor inline chat in VS Code

In PyCharm, press *Ctrl* + *Shift* + *I* (*cmd* + *shift* + *I* for older Mac versions of PyCharm).

![Figure 3.20: Copilot inline chat in PyCharm](img/B31534_03_20.jpg)

Figure 3.20: Copilot inline chat in PyCharm

In the inline chat window, type your code analysis command, such as `/fix` or `/explain`.

## Analyzing code with Copilot editor window in VS Code

GitHub Copilot has recently introduced a dedicated editor window to enhance editing tasks and streamline working across multiple files simultaneously. To access the window, open the chat window and select **Edit**, as shown in *Figure 3.21*:

![Figure 3.21: Accessing Copilot’s edits window](img/B31534_03_21.png)

Figure 3.21: Accessing Copilot’s edits window

In this editor window, you can add files you want to work on or target specific sections using the annotation `#selection`, as shown in *Figure 3.22*:

![Figure 3.22: Working with #selection in Copilot edits window](img/B31534_03_22.jpg)

Figure 3.22: Working with #selection in Copilot edits window

The edits window supports the slash commands such as `/fix`, `/explain`, and `/test`, as well as tailored instructions to modify your code. For instance, to add input validation for `float` inputs to the following function:

```

def get_geometric_mean_for_three_numbers(a, b, c):

```py

We can type the prompt:

```

#selection add input validation for float inputs.

```py

Copilot will generate suggestions to include input validation for float types, as shown in *Figure 3.23*:

![Figure 3.23: Adding input validation with the edits window](img/B31534_03_23.jpg)

Figure 3.23: Adding input validation with the edits window

With this prompt, Copilot presents suggestions in a version control format within the working set file, allowing us to approve or revert each change individually. We can also click **Accept** to apply all changes at once.

In the next chapters, we will explore best practices for crafting precise prompts to achieve more desirable results with Copilot, including its edits window. Later in the book, we will delve deeper into using the edits window for prompt engineering techniques and refactoring code.

Now that we have explored how to analyze and edit code with Copilot, we can practice addressing and fixing a faulty implementation of the geometric mean, using both VS Code and PyCharm.

# Lab 3.3 – working with Copilot in VS Code’s Jupyter Notebook for Code Analysis

The following lab focuses on code analysis. We will use the `/fix` command to fix an incorrect implementation of the geometric mean for three floating-point numbers. We will then use the `/explain` command to get a brief explanation of an implementation for the geometric mean of a sequence of numbers.

The lab is available in two formats: a Jupyter Notebook or a Python script. If you are using VS Code, choose the Jupyter Notebook version to explore Copilot’s features for notebooks. Since Jupyter Notebook support is not yet available in PyCharm, a Python script version is also provided. In *Lab 3.3 guided walk-through*, we will cover both formats and use Copilot’s code analysis features to fix and understand code more efficiently.

## Lab 3.3 guided walk-through

Open *Lab 3.3* from the book repository: If you are using VS Code, go to *ch3/labs/lab33.ipynb*, and if you are using PyCharm, go to *ch3/labs/lab33.py*. Make sure you have a stable internet connection, and that GitHub Copilot is ready.

Our starter code includes two functions that we will apply code analysis to. The first function, `get_geometric_mean_for_three_numbers`, incorrectly implements the geometric mean for three floating-point numbers, as it takes the square root of their product instead of the cube root.

The second function, `get_geometric_mean`, calculates the geometric mean for a sequence of numbers of any length. It first validates that there is at least one item in the sequence. Then, it computes the product of all the numbers using a `reduce` operation. It also checks that the root results in a real number, which occurs if either the product is positive, or the required root is odd. Finally, after validation, it returns the *n*-th root of the product for a sequence of length *n*:

```

from functools import reduce def get_geometric_mean_for_three_numbers(a, b, c): return (a*b*c)**(1/2) def get_geometric_mean(*nums: float) -> float: """

计算一系列数字的几何平均值

"""

    if not len(nums): raise ValueError("Cannot calculate the geometric mean of an empty sequence")

    product = reduce(lambda a, b: a * b, nums) if product < 0 and len(nums) % 2 == 0: raise ValueError("Cannot calculate the geometric mean") return pow(product, 1 / len(nums))

```py

The calculation in `get_geometric_mean_for_three_numbers` is incorrect, as it takes the square root of the product of the numbers instead of the cube root.

To fix this code, choose the fix option or type `/fix` in the inline chat.

Copilot should suggest replacing the incorrect square root with the cube root:

```

return (a*b*c)**(1/3)

```py

For your reference, here is a sample output in VS Code with the proposed fix (note that this fix could be implemented in your code using the **Accept** button):

![Figure 3.24: Copilot fix suggestion in VS Code](img/B31534_03_24.jpg)

Figure 3.24: Copilot fix suggestion in VS Code

In PyCharm, here is a sample output with the proposed fix. To accept it, click the **Preview** button and then **Accept**.

![Figure 3.25: Copilot fix suggestion in PyCharm](img/B31534_03_25.jpg)

Figure 3.25: Copilot fix suggestion in PyCharm

In the top-left corner, the preview icon is the first on the left. Click it to open the preview mode:

![Figure 3.26: The Preview button for accepting Copilot changes in PyCharm](img/B31534_03_26.jpg)

Figure 3.26: The Preview button for accepting Copilot changes in PyCharm

The preview window displays the original code on the left and the proposed fix on the right, with an **Accept** button to confirm the changes.

![Figure 3.27: Accepting Copilot fix suggestions in PyCharm](img/B31534_03_27.jpg)

Figure 3.27: Accepting Copilot fix suggestions in PyCharm

Accept this proposed implementation.

Next, move your cursor to the `get_geometric_mean` function and examine how Copilot explains its four parts: validating the input length, computing the product, verifying that the geometric mean is real, and returning the *n*-th root of the product.

Right-click on the code, select **Copilot** | **explain**, or use the keyboard shortcuts to open the inline chat and type `/explain`. Copilot should cover all four steps of the function.

## Lab 3.3 analysis

In this lab, we used the code analysis mode to efficiently review existing code. Since a sizable portion of our work as software developers involves maintaining code rather than generating new code, these extended capabilities are invaluable for enhancing our productivity.

For reference, here is the code explanation we obtained in VS Code, covering the four steps of the function:

```

提供的代码定义了一个名为 get_geometric_mean 的函数，该函数用于计算一系列数字的几何平均值。该函数接受可变数量的浮点数参数 (*nums) 并返回一个浮点数结果。函数首先使用 if not len(nums) 检查数字序列是否为空。如果序列为空，则抛出一个包含消息 "Cannot calculate the geometric mean of an empty sequence" 的 ValueError。这确保了函数不会对无效输入进行操作。接下来，函数使用 reduce 函数和 lambda 函数（lambda a, b: a * b）结合计算序列中所有数字的乘积。reduce 函数将 lambda 函数累积应用于序列的项，从而将所有数字相乘。在计算乘积后，函数检查乘积是否为负数以及序列中的元素数量是否为偶数（if product < 0 and len(nums) % 2 == 0）。如果这两个条件都成立，则抛出一个包含消息 "Cannot calculate the geometric mean" 的 ValueError。这个检查是必要的，因为包含偶数个负值的数字集的几何平均值在实数系统中是未定义的。最后，函数通过取乘积的 n 次方根来返回几何平均值，其中 n 是序列中的元素数量（pow(product, 1 / len(nums))）。pow 函数用于计算 n 次方根，相当于将乘积提升到元素数量的倒数次幂。总的来说，该函数旨在处理各种边缘情况并确保对有效输入正确计算几何平均值。

```py

Overall, Copilot explains all four steps of the function well and addresses its input. However, the interpretation of the real geometric mean output is missing from Copilot’s explanation, as shown in the highlighted part of the output:

```

在计算乘积后，函数检查乘积是否为负数以及序列中的元素数量是否为偶数...

```py

Rather than being a limitation of the tool, this suggests that our implementation could be improved. We will explore this further in *Chapter 4*.

# Summary

In this chapter, we took our first steps with the GitHub Copilot by setting up subscriptions and enabling Copilot in our IDE. Through three labs, we explored its three interaction modes: chat, completion, and analysis.

After implementing a basic code completion program in *Chapter 2*, we were able to better understand how GitHub Copilot is designed. Copilot enhances the code to be completed with contextual information, such as recent edits, coding preferences, and Git logs. This information is processed into user and system prompts, which are then fed to an LLM. The model’s output is further processed before being presented to the user.

Throughout the three labs, we utilized the three interaction modes to implement and refine several calculators of the geometric mean. We saw how a function signatures can be used as a prompt to Copilot. We also experimented with various completion options using keyboard shortcuts. While mastering these techniques requires some practice, they can significantly boost productivity when working with Copilot.

In the next chapter, we will discuss the three pillars of good model output: model mastery, evaluation metrics, and precise prompts. We will also learn about the best practices in making our prompt precise with the five S’s: having a structured prompt, providing surrounding context, focusing on a single task, and having specific and short instructions.

# Quiz time

Before you proceed to the next chapter, make sure that you can confidently answer the following questions.

**Question 1**: Is Copilot a paid service?

**Answer**: Copilot is primarily a paid service, with a few exceptions including free limited access. Students, educators, and maintainers of leading open-source repositories are also eligible for a free subscription.

**Question 2**: What are the three interaction modes for GitHub Copilot?

**Answer**: Copilot’s original task of code completion is complemented by two additional features: chat, which is available inline or through the chat window, and code analysis, which is accessible via the Copilot right-click menu, using slash commands, such as `/fix` and `/explain`, or in the edits window within VS Code.

# Further reading

To learn more about the topics that were covered in this chapter, look at the following resources:

*   GitHub Copilot documentation: [`docs.github.com/en/copilot/quickstart`](https://docs.github.com/en/copilot/quickstart)
*   Copilot subscription plans: [`docs.github.com/en/copilot/about-github-copilot/subscription-plans-for-github-copilot`](https://docs.github.com/en/copilot/about-github-copilot/subscription-plans-for-github-copilot)
*   Copilot setup in your IDE: [`docs.github.com/en/copilot/setting-up-github-copilot/setting-up-github-copilot-for-yourself`](https://docs.github.com/en/copilot/setting-up-github-copilot/setting-up-github-copilot-for-yourself)
*   Copilot best practices: [`docs.github.com/en/copilot/using-github-copilot/best-practices-for-using-github-copilot`](https://docs.github.com/en/copilot/using-github-copilot/best-practices-for-using-github-copilot)

|  
#### Unlock this book’s exclusive benefits now

Scan this QR code or go to [packtpub.com/unlock](http://packtpub.com/unlock), then search for this book by name. | ![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png) |
| *Note: Keep your purchase invoice ready before you start.* |

# 4

# Best Practices for Prompting with ChatGPT

GenAI applications excel in certain aspects of coding and often achieve high scores in coding assignment tests. Ongoing improvements to these models continue to push the boundaries, as they begin to master a wide range of coding-related tasks and supercharge the way we develop and refine code.

To achieve good results from GenAI applications, we will focus on three pillars: **model mastery** of the specific task at hand, **evaluation metrics** to critically assess the output, and crafting **precise prompts** to clearly achieve the desired outcome.

This chapter focuses on best practices for crafting prompts in coding-related tasks, guided by the **five S’s**: **structured** prompt, including **surrounding** context, focusing on a **single** task, providing **specific** instructions, and keeping the prompt as **short** as possible. Later in the book, we will delve into advanced prompt engineering techniques, methods to construct manual and automatic evaluation metrics, and strategies for improving the model’s mastery of specific tasks.

Through two interactive labs, we will explore how following best practices for crafting prompts for coding-related tasks leads to reusable prompt structures. We will apply these principles to refine a prompt for translating **Graphical User Interface** (**GUI**) actions into **Command-Line Interface** (**CLI**) commands. We will also review a sample prompt published by OpenAI and analyze it through the lens of the five S’s for crafting prompts. This analysis will help us understand how these examples yield desirable outcomes and highlight potential improvements, which we will explore further in later chapters of the book.

In this chapter, we will cover the following topics:

*   Can we trust GenAI for coding tasks?
*   Best practices for crafting prompts for coding tasks
*   Crafting prompts for ChatGPT
*   Prompt samples by OpenAI

# Technical requirements

To get the most out of this chapter, ensure you have the following:

*   OpenAI account with access to ChatGPT
*   Access to the book’s repository available at [`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)

If you need help creating an OpenAI account, refer to the *Appendix* for detailed guidance.

# Can we trust GenAI for coding tasks?

**Large language models** (**LLMs**) are continuously improving their capabilities in mathematics and coding, achieving impressive results in both areas. For instance, internal research by OpenAI showed that the *GPT-o1* model scored correctly on 11 out of 15 questions in the **American Invitational Mathematics Examination** (**AIME**). This performance not only exceeds the threshold required to qualify for the **USA Mathematical Olympiad** (**USAMO**) or the **USA Junior Mathematical Olympiad** (**USAJMO**) but also places the model in the top percentile of participants. Similarly, when evaluated on coding problems from the *Codeforces* competition website, the internal research showed that the model performed at the 89th percentile, highlighting its proficiency in tackling challenging coding tasks.

Yet, the web is filled with screenshots, videos, and examples of highly undesirable outputs from certain prompts. Not long ago, the author encountered a **pull request** (**PR**) containing a file named `new.env` that exposed seven secret keys. A post-mortem meeting dedicated to that issue revealed that the data scientist who committed the file had used the following prompt:

```

如何从 PyCharm 终端提交我的文件到 GitHub？

```py

The output included the following instruction:

```

git add .

```py

The data scientist, who typically utilized PyCharm’s **Git tool window** and was used to choosing the files to commit manually, failed to notice that the file named `new.env` with the secret keys had been included in the commit. This incident highlights that following GenAI-generated instructions can sometimes lead to risky outcomes.

This example does not imply that we should distrust all GenAI output or validate every detail. The fault did not occur because of the model’s hindsight about exposing secret keys through a `.env` file. Instead, it stemmed from a poorly crafted prompt combined with the model’s bias toward suggesting CLI commands such as `git add .`, which frequently appear in online manuals.

We argue that crafting a better prompt, such as the following, would lead to a more desirable model output:

```

CONTEXT: 你将获得包含在 {{{ STEPS }}} 中的 PyCharm GUI 步骤，以执行包含在 {{{ PROCESS }}} 中的过程。TASK: 将步骤转换为 CLI 命令。PROCESS: {{{ 提交并推送文件到远程 git 分支 }}}

STEPS: {{{

1\. 审查更改后的文件

2\. 阶段化所需文件

3\. 添加提交信息

4\. 提交文件

5\. 验证分支名称

6\. 将更改推送到远程分支

}}}

CLI COMMANDS:

```py

This prompt, which follows the best practices for crafting effective prompts, is structured, provides surrounding context for the problem, focuses on a single task, is specific, and is short enough. In this chapter, we will explore how to create such prompts and understand why following these practices leads to better GenAI outputs.

## The three pillars of good outputs

To achieve good results from GenAI applications, we will focus on the three pillars: model mastery, evaluation metrics, and crafting precise prompts.

**Model mastery** refers to an LLM’s ability to handle a specific task described in a prompt. For instance, GPT models are extensively trained in Python code and problems such as those found on *LeetCode*, a platform for coding interview preparation. However, when the task deviates from mainstream topics, such as integrating Python **threading** to parallelize code execution across cores and virtual cores, there is significantly less training material available online, leading to outputs that may not match the quality of those for well-covered topics. Keep in mind that for such topics, LLM outputs may be suboptimal. However, we can enhance model mastery using techniques such as fine-tuning to achieve more desirable outputs. This will be covered in greater detail later in the book.

**Evaluation metrics** refer to the manual and automatic methods we use to assess the quality of GenAI outputs. Effective prompting always involves evaluating the GenAI output, as it is not guaranteed that good results will be achieved on the first attempt. Manual evaluations involve tasks we can personally verify, such as the following:

*   Reading code in a language we recognize, such as Python
*   Asking for CLI commands we can identify as incorrect
*   Evaluating visual outputs such as plots to see whether they align with our expectations
*   Verifying straightforward outputs, such as ensuring a requested CSS color matches light pink

Automatic evaluations rely on computational checks, such as:

*   Compiling suggested code to ensure it runs without errors.
*   Running unit tests to validate functional correctness.
*   Using frameworks such as *OpenAI Evals* to systematically assess outputs.

These evaluations help detect faulty outputs and guide iterative improvements toward better suggestions.

OpenAI Evals in brief

*Evals* is a system designed to assess the performance of LLM applications by using a collection of prompts and expected outputs. These can include prompts and outputs provided by the system itself or custom examples that we create. Accessible via both Python package installers and a CLI, it compares the application’s outputs against the expected results and assigns a performance score to the full set. In later chapters, we will delve into strategies for improving evaluation metrics and explore how to effectively leverage the OpenAI Evals system for evaluating GenAI outputs.

**Precise prompts** refer to how closely the instructions given to the model align with the actual task we want it to perform. When prompts are ambiguous, the model is likely to fill in gaps with assumptions based on its training data, which may not always align with the task at hand.

For example, the prompt `How can I commit my files to GitHub from the PyCharm terminal?` is less precise than a prompt providing specific steps performed in the PyCharm GUI and a request to convert these steps to CLI commands.

Next, we will explore best practices for designing prompts for coding tasks and learn how to refine these prompts into precise inputs that produce high-quality outputs.

# Best practices for crafting prompts for coding tasks

When working with GenAI applications for coding-related tasks, the best practices for crafting precise prompts can be summarized by the five S’s:

*   **Structured** prompts with a clear separation between the instructions and provided data
*   **Surrounding** information that provides context for the problem, such as the code language for the provided code and whether it compiles
*   **Single-task** focus to ensure each prompt addresses only one objective
*   **Specific** instructions detailing how the coding task should be performed, rather than using generic requests
*   **Short** and minimal prompts that avoid fluff, redundant, or overly verbose instructions

Let us dive into each of these practices.

## Structured

Just as well-written, functional Python code separates logic from data, a good prompt should also distinguish instructions from provided data. When including elements such as steps, code snippets, or code drafts, ensure they are separated from the main instructions and aliased appropriately for clarity and reusability.

Replace unstructured prompts that mix supporting data with instructions, such as the following:

```

转换 COBOL 代码

IDENTIFICATION DIVISION. PROGRAM-ID. ... 转换为 Python。

```py

Use a structured approach that separates the instructions from the data:

```

CONTEXT: 你将获得包含在 {{{ COBOL CODE }}} 中的 COBOL 代码。TASK: 你的任务是将其转换为 Python，以下是一些指导原则：

... COBOL CODE: {{{

}}}

Python 代码：

```py

This structured prompt is simple to reuse with other COBOL snippets.

## Surrounding information

When specifying the surrounding context, include information about the data relevant to the problem. Here are three examples of three different prompt pieces that could be used for different tasks:

*   `You are provided with Python code / a function / a function signature.`
*   `You are provided with a Python function that contains a bug.`
*   `You are provided with GUI steps.`

These instructions are general and avoid specific details, making them reusable:

*   The first and second examples do not specify any function
*   The third example does not describe specific GUI steps

As a result, these prompt pieces are reusable across various tasks.

## Single task per prompt

Always aim for a single task in your prompts. This approach not only improves your ability to evaluate the model’s output by focusing on a single task but also increases the likelihood that the model has encountered similar tasks during its training, enhancing its mastery of the topic.

For example, in refactoring tasks, refrain from combining multiple objectives, as follows:

```

解释以下函数并修复编译错误。

```py

While LLMs are well trained on both individual tasks, combining them into a single prompt may be less common, reducing the model’s mastery of the topic. Instead, focus on either explaining the function or fixing its compilation bugs.

## Specific instructions

As software developers, it is tempting to use keywords such as *optimize*, *improve*, *refactor*, or *scale*. However, these are broad and ambiguous, often leaving room for interpretation by the model.

To achieve better results, use specific instructions, such as the following:

*   `Use list comprehensions instead of for loops.`
*   `Use np.array to vectorize for loop computations.`
*   `Convert hard-coded integers to global constants.`
*   `Cache function results using lru_cache.`

Specific instructions eliminate ambiguity, ensuring the model understands exactly what changes or actions are expected, and increase the likelihood of producing the desired outcome.

## Short prompts

Focus on including only relevant information, leaving fluff out, and avoiding ambiguity in your language. Note that this does not mean that you should avoid valuable and relevant information. With the GPT-o1 model supporting over 65,000 tokens (about 164 pages), it can handle longer prompts if its content is minimal and relevant.

For example, avoid phrases such as the following:

```

我认为以下函数存在错误 [...]

```py

Prefer instructions such as the following:

```

在 [...] 中找到编译错误

```py

Additionally, avoid vague phrases such as the following:

```

这个 for 循环看起来可以被转换为一个列表推导式。

```py

Prefer instead the following instruction:

```

将 for 循环转换为列表推导式。

```py

Keeping your prompts minimal and relevant and avoiding fluff and ambiguity allows the model to focus on the specific instructions at hand.

Next, we will see how to adapt these best practices to crafting prompts for ChatGPT.

# Crafting prompts for ChatGPT

When crafting prompts for ChatGPT, we can apply the structured approach suggested earlier:

```

CONTEXT: ... TASK: ... SUPPORTING_DATA: {{{

}}}

COMPLETION:

```py

Replace `SUPPORTING_DATA` with terms such as `CODE`, `STEPS`, `OLD_CODE`, or any other appropriate label for the provided data. Replace `COMPLETION` with terms such as `SOLUTION`, `CLI COMMANDS`, `NEW_CODE`, or another label that matches the desired model output.

When working with the *GPT-4o* model with the integrated *canvas editor*, apply the following structure:

```

CONTEXT: ... TASK: ... SUPPORTING_DATA: {{{ }}}

```py

To access it, start a new GPT-4o chat and type the following to launch the canvas editor:

```

打开 Python 编辑器

```py

Then, add your supporting code to the Python editor as you would in any IDE, as shown in *Figure 4.1*:

![Figure 4.1: GPT-4o with canvas editor for Python](img/B31534_04_01.png)

Figure 4.1: GPT-4o with canvas editor for Python

ChatGPT will edit your code based on your request and provide additional output in the chat window, as shown in *Figure 4.2*:

![Figure 4.2: Sample edited code from canvas editor](img/B31534_04_02.png)

Figure 4.2: Sample edited code from canvas editor

Later in this chapter, we will use the canvas editor in ChatGPT to fix errors in a function.

In the upcoming lab, we will follow these practices to refine a ChatGPT prompt for converting PyCharm GUI steps into Git CLI commands. We will also evaluate how these improvements improve the model output.

## Lab 4.1 – converting PyCharm GUI steps to CLI

When transitioning from GUI steps to working directly with the CLI for Git operations, we can use ChatGPT to construct the steps required for committing and pushing staged files to a remote repository. A critical part of this process involves manually reviewing the staged files to ensure that only the desired ones are committed to our remote branch.

By applying the best practices for prompt precision, we will refine the following initial prompt into a prompt that produces a more reliable output:

```

我如何在 PyCharm 终端将文件提交到 GitHub？

```py

For reference, using this initial prompt alone may result in a response such as the one shown in the following figure when entering it into the GitHub Copilot chat window:

![Figure 4.3: Copilot chat suggestion](img/B31534_04_03.png)

Figure 4.3: Copilot chat suggestion

![](img/1.png) **Quick tip**: Need to see a high-resolution version of this image? Open this book in the next-gen Packt Reader or view it in the PDF/ePub copy.

![](img/2.png) **The next-gen Packt Reader** is included for free with the purchase of this book. Scan the QR code OR go to packtpub.com/unlock, then use the search bar to find this book by name. Double-check the edition shown to make sure you get the right one.

![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png)

In our guided walk-through, we will apply the following best practices to craft a more effective prompt:

*   **Structured format**: Separate the logic of the task from the actual steps to be converted and the desired GUI process
*   **Surrounding context**: Provide the context of the data and structure
*   **Single-task focus**: Narrow the task to converting GUI steps into CLI commands
*   **Specific instructions**: Clearly indicate all steps previously executed from the GUI, avoiding a generic request
*   **Short prompt**: Eliminate redundant details such as `PyCharm terminal`

We will then feed this refined prompt to ChatGPT and observe how applying these best practices enhances the trustworthiness and reliability of the model’s output.

### Lab 4.1 guided walk-through

Navigate to [`chatgpt.com/`](https://chatgpt.com/) and start a new chat with the *GPT-o1-mini* model. This model has high proficiency in **science, technology, engineering, and mathematics** (**STEM**) tasks, particularly coding and mathematics. As of November 2024, it achieves the highest performance among available GPT models on the *Codeforces* coding exam.

![Figure 4.4: ChatGPT model menu](img/B31534_04_04.png)

Figure 4.4: ChatGPT model menu

Our starter information consists of the following:

*   **Scenario**: A data scientist aims to work with the terminal instead of the PyCharm GUI to push changes into a desired branch
*   **Initial prompt**:

    ```

    我如何在 PyCharm 终端将文件提交到 GitHub？

    终端？

    ```py

We will now address each of the five S’s best practices for coding-related prompts following these four guidelines:

*   Structure the prompt
*   Add surrounding context
*   Focus on a specific task
*   Include specific instructions

Throughout the steps, we will follow the fifth best practice of keeping prompts short, ensuring they remain minimal and free of unnecessary details and fluff.

**Step 1 – structure the prompt**

A well-structured prompt separates the instructions from the data, ensuring clarity and allowing for simple adjustments. In this case, the instructions outline the task, while the data contains the specific steps required to push the files to the remote branch. For ChatGPT, one strategy is to alias the data by enclosing it within delimiters such as `{{{ DATA }}}` for easy reference:

```

指令中包含对数据的引用，用 {{{ DATA }}} 包围

... DATA: {{{

... }}}

解决方案：

```py

Important note

We recommend using `{{{ DATA }}}` as an alias because the `{{{ }}}` delimiter is rare in both code and other types of data. However, choosing alternative separators is also acceptable if they do not commonly appear in your code. For example, enclosers such as `""" """` are used in Python for multi-line strings and could cause confusion for the model if used as delimiters.

**Step 2 – add surrounding context**

A precise prompt should include information about the surrounding context of the problem and the provided data. When converting GUI commands into terminal commands, a clear and relevant surrounding context might look like this:

```

CONTEXT: 你将获得 PyCharm GUI 步骤，用 {{{ STEPS }}} 包围，以执行用 {{{ PROCESS }}} 包围的过程。

```py

By avoiding references to specific processes, such as committing and pushing files to a remote Git branch, this context remains flexible and can be reused for similar tasks in the future.

Add this context at the beginning of your ChatGPT prompt to establish the context of the task.

**Step 3 – single task**

Our single task in this lab is to translate GUI steps into CLI commands. A clear phrasing of this task could be as follows:

```

TASK: 将步骤转换为 CLI 命令。

```py

This prompt piece specifies that the GUI step needs to be converted into corresponding CLI commands.

Add this prompt piece directly below the surrounding context information. Then, complete the structured prompt with the following line at the end:

```

CLI COMMANDS:

```py

This signals to the model that the output should be the list of CLI commands to execute.

**Step 4 – specific instructions**

In this lab, we aim to provide detailed and accurate instructions reflecting what is typically done when pushing changed files to a remote branch. In PyCharm, the first step of reviewing changed files can be performed by navigating to the Git tool window icon in the left menu:

![Figure 4.5: Git tool window](img/B31534_04_05.png)

Figure 4.5: Git tool window

It is good practice to manually review your staged files in the working directory, ensuring that files such as `new.env`, which should be ignored by Git, are not included in the commit.

After adding a commit message and clicking on **Commit and Push**, PyCharm pops up the push window, indicating that the selected files are about to be pushed to the remote branch.

![Figure 4.6: Pushing a commit to a remote branch from PyCharm](img/B31534_04_06.png)

Figure 4.6: Pushing a commit to a remote branch from PyCharm

In this figure, we can see that a single file, the solution to *Lab 4.1*, is being pushed to a new remote branch called `ch4-labs`.

Describing these steps may look like this:

```

STEPS: {{{

1. 审查已更改的文件

2. 阶段所需的文件

3. 添加提交信息

4. 提交文件

5. 验证分支名称

6. 将更改推送到远程分支

}}}

```py

Include these steps in the prompt, placing them directly beneath the `TASK` line.

If you have followed all the steps correctly, your final prompt should look like this:

```

CONTEXT: 你将获得 PyCharm GUI 步骤，用 {{{ STEPS }}} 包围，以执行用 {{{ PROCESS }}} 包围的过程。TASK: 将步骤转换为 CLI 命令。PROCESS: {{{ 提交并推送文件到远程 Git 分支 }}}

STEPS: {{{

1. 审查已更改的文件

2. 阶段所需的文件

3. 添加提交信息

4. 提交文件

5. 验证分支名称

6. 将更改推送到远程分支

}}}

CLI COMMANDS:

```py

Your prompt is now ready to use in ChatGPT. Execute it and refer to the lab analysis for a sample output generated by the model.

### Lab 4.1 analysis

In this lab, we crafted a precise prompt by applying the five S’s best practices. When we ran the prompt in ChatGPT using the *GPT-o1-mini* model, the output provided a set of CLI commands for committing and pushing the desired files to a remote branch. The generated commands were as follows:

![Figure 4.7: ChatGPT’s response to the Lab 4.1 prompt](img/B31534_04_07.png)

Figure 4.7: ChatGPT’s response to the Lab 4.1 prompt

This output is more desirable than the initial prompt because it directly references each of the six steps we would perform using the GUI, providing explanations for each corresponding command. Additionally, the output aligns with the prompt’s specificity, offering only the CLI commands with minimal surrounding explanation.

**Important note**

Refining prompts using the five S’s best practices may seem like a lot of work initially. However, over time, seasoned prompters develop their own reusable prompt templates, making the process more efficient. Well-structured prompts are reproducible across different tasks and adapting them with varied data can often be done at scale. In the next chapters, we will reuse prompts crafted with these best practices for a variety of tasks.

Having introduced and implemented the best practices for crafting precise prompts, we can now observe how applying the five S’s can further enhance outputs, even from prompts already considered strong. Next, we will delve into OpenAI’s examples of good prompts, analyze them through the lens of the five S’s, and refine a prompt further to achieve a more desirable output.

# Prompt samples by OpenAI

OpenAI occasionally updates a collection of sample prompts tailored to various tasks, including coding, content generation, translations, and grammar corrections. These prompts display the core capabilities where the underlying models exhibit strong mastery. They have been carefully crafted and have demonstrated consistent success across these use cases.

You can explore the full list of prompts and filter the samples by category at [`platform.openai.com/docs/examples`](https://platform.openai.com/docs/examples).

![Figure 4.8: OpenAI sample prompts](img/B31534_04_08.png)

Figure 4.8: OpenAI sample prompts

When clicking on a prompt sample from this page, we can observe the prompt itself, divided into a system prompt and a user prompt, a sample response, and a code snippet demonstrating how to implement the prompt using OpenAI API.

![Figure 4.9: Improve code efficiency prompt example](img/B31534_04_09.png)

Figure 4.9: Improve code efficiency prompt example

In this example, the system prompt contains general instructions describing the task to be performed, while the user prompt includes the import statement and a function that could benefit from efficiency improvements.

Next, we will critically analyze a sample prompt to assess how well it aligns with the five S’s.

## Lab 4.2 – code debugging

In this lab, we will examine a Python bug fixer use case through the lens of our best practices.

Navigate to [`platform.openai.com/docs/examples`](https://platform.openai.com/docs/examples) and search for *Python bug fixer*. This should yield the following prompt example to instruct the model to find a bug in a Python program that quizzes a user on multiplication problems:

![Figure 4.10: Sample prompt for Python bug fixer](img/B31534_04_10.png)

Figure 4.10: Sample prompt for Python bug fixer

This prompt, like the code efficiency improvement prompt example by OpenAI, separates the system and user prompts while providing a sample response. Scrolling further down the window reveals the code necessary to implement this prompt with OpenAI API.

In the guided walk-through, we will identify the errors in the provided code, so we can better evaluate the output of the model. In the analysis, we will analyze the usage of the five S’s and see how we can improve the prompt even further.

### Lab 4.2 guided walk-through

Before we can analyze the output of the model, here are the errors in the user-provided functions:

*   **Compilation errors**:
    *   **Typo in import statement**: `import Random` should be corrected to `import random`.
    *   **Type error**: The `question` variable cannot concatenate integers `a` and `b` with strings directly. This needs to be resolved by converting integers to strings.
    *   **Missing colon**: The `if` statement is missing a `:` character at the end, leading to `SyntaxError`.
    *   **Invalid assignment**: The `answer = a*b` statement attempts to assign a value within the `if` condition. Modern Python compilers will raise `SyntaxError` as this is an invalid syntax.
    *   **Invalid print statement**: The string `Well done!` is not enclosed with quotes and therefore is an invalid syntax.
*   **Logical errors**:
    *   The `a` and `b` variables are generated once before the loop and remain constant through all 10 iterations. This is not desirable.
    *   The output from the user is a string, while the comparison is made against integers. As a result, `answer` of type `str` can never be equal to `a * b`, which is of type `int`.
*   **Reproducibility issue**:
    *   The code with random numbers is not reproducible across runs due to the absence of a `random seed` set. Without this, the output will vary unpredictably between executions.

Considering the output published on the OpenAI website, here is a summary of identified and fixed code errors and issues:

| **Error type** | **Problem** | **Error** | **Found** | **Fixed** |
| --- | --- | --- | --- | --- |
| Compilation | Invalid case | import `R`andom | Yes | Yes |
| Compilation | Concatenate `int` and `str` | a + " x " + b | Yes | Yes |
| Compilation | Missing colon in `if` statement | if statement... | **No** | Yes |
| Compilation | Assignment in `if`statement | if answer `=` a * b | Yes | Yes |
| Compilation | Missing quotes for `str` | print(Well done!) | Yes | Yes |
| Logic | Random numbers generated once | `a, b` outside the `for` loop | **No** | **No** |
| Logic | `str` compared to `int` | answer = a * b | Yes | Yes |
| Reproduce | No seed set | Missing `random.seed(...)`, or equivalent initialization | **No** | **No** |

Table 4.1: OpenAI API’s performance in detecting and fixing errors

The proposed solution also introduced a new issue related to casting the input to an integer; there is no proper error handling if an input such as `hello` cannot be cast.

The following is the full model response, as published on the OpenAI website:

```

提供的代码中存在几个错误：

1. 导入语句不正确。Python 区分大小写，所以 "Random" 应该是 "random"。2. 变量 `a` 和 `b` 在循环外部定义，因此它们在每次迭代中都不会改变。如果你想生成不同的问题，它们应该位于循环内部。3. 在问题字符串中，`a` 和 `b` 是整数，所以你需要使用 `str()` 函数将它们转换为字符串以进行连接。4. 在 if 语句中，你使用单个等号 `=`，这是一个赋值运算符。你应该使用双等号 `==` 进行比较。5. 打印语句 "Well done!" 没有被引号包围。在 Python 中，字符串必须被引号包围。6. 用户输入是一个字符串，所以在将其与 `a` 和 `b` 的乘积进行比较之前，你需要使用 `int()` 函数将其转换为整数。以下是修正后的代码：

```pypython
import random
for i in range(10):
    a = random.randint(1,12)
    b = random.randint(1,12)
    question = "What is "+ str(a) +" x "+ str(b) +"? "
    answer = int(input(question))
    if answer == a*b:
        print ("Well done!")
    else:
        print("No.")
```

```py

Next, we will analyze the prompt through the lens of the five S’s, evaluate the quality of the output based on the errors identified, fixed, and introduced, and propose improvements to achieve a better outcome.

### Lab 4.2 analysis

The prompt introduced in this example mostly aligns with the five S’s guidelines:

*   **Good structure**: The instructions are clearly separated from the code, making the prompt reusable and adaptable for other tasks.
*   **Sufficient surrounding context**: The prompt provides context by mentioning Python code as the supporting data.
*   **No single task**: The prompt combines two related tasks, identifying and fixing errors in the code. While these tasks are interconnected, focusing solely on fixing the errors could improve the model’s response and responsibility.
*   **Specific**: The task specifies that the model should identify and fix the errors in the code. However, the instructions could be improved by explicitly stating the types of errors to address, such as compilation, logical scoping, reproducibility, or error handling.
*   **Short**: The prompt is concise and avoids unnecessary or irrelevant details.

Overall, following most of the guidelines resulted in a decent output. Since we have strong evaluation capabilities and are aware of all the errors the model should address, we can continue iterating to resolve all remaining issues in the code.

Alternatively, we could better align the best practices with the following prompt:

```

CONTEXT: 你将获得 Python 编辑器中的 Python 代码，其中包含用

{{{ CODE_EXPLANATION }}} 可能包含错误，用 {{{ ERRORS }}} 包围。TASK: 修复代码中的错误。CODE_EXPLANATION: {{{

运行 10 次随机的乘法测验，并对每个测验向用户提供反馈

}}}

ERRORS: {{{

1. 编译

2. 随机数生成的可重复性

3. 变量赋值的逻辑作用域

4. 输入类型转换的错误处理

}}}

```py

Using this prompt with *GPT-4o with canvas* resulted in an output that addressed all the required fixes.

![Figure 4.11: Better output](img/B31534_04_11.png)

Figure 4.11: Better output

All compilation, logic, reproducibility, and error handling are addressed in the fixes.

#### Even better prompts

In the next chapters, we will explore advanced prompt engineering techniques such as **iterative prompting** for creating a feedback loop with LLMs and **chain-of-thought prompting** for guiding model reasoning. These techniques will enable us to refine prompts that yield decent results for manual use and scale them effectively for broader applications.

# Summary

In this chapter, we explored how to achieve high-quality GenAI outputs by focusing on the three pillars: model mastery for handling a specific topic, evaluation metrics, and precise prompts. We examined how imprecise prompts can lead to risky outcomes, such as CLI commands exposing secret keys, and demonstrated how following best practices can produce far better and more reliable model outputs.

We also learned about the five S’s of prompt precision best practices for coding-related tasks: keeping a structured prompt, providing surrounding context, maintaining a single task per prompt to best leverage model mastery and evaluation capabilities, ensuring that prompts are specific rather than general and vague, and keeping the input as short as possible by removing irrelevant information and fluff.

With two interactive labs, we explored how to implement those best practices in ChatGPT. With an OpenAI example of a good prompt to a bug fix, we saw that even good prompts can be improved to achieve more desirable results.

In the next chapter, we will explore how to apply the five S’s using OpenAI API and GitHub Copilot. In later chapters, we will delve into advanced prompt engineering techniques to further refine prompts and meet specific engineering needs in the **Software Development Life Cycle** (**SDLC**).

# Quiz time

Before you proceed to the next chapter, make sure that you can confidently answer the following questions:

**Question 1**: What are the three factors that determine the quality of output of an LLM?

**Answer**: Model mastery, evaluation capabilities, and prompt precision. Model mastery means how much the LLM trained on this specific task, evaluation capabilities means how much we can assess the desirability of the outcome, and prompt precision means to what extent the prompt is crafted to tell the model what exactly we need.

**Question 2**: What are the best practices for a coding-related task prompt?

**Answer**: The best practices are the five S’s, structuring the prompt to accommodate supporting data such as code and steps, including surrounding context on the task, focusing on a single task per prompt, and keeping specific and short instructions.

**Question 3**: Which parts of a prompt can be reproducible?

**Answer**: When following the best practices of precise prompts, we can reuse the surrounding context and the single task. These can be leveraged to many prompts and reused with a change of the details, such as the function attached, steps to be converted to CLI commands, or improvements required to a given function. This is highly efficient for large-scope refactoring tasks, repetitive tasks, and many more examples we will see in the book.

# Further reading

To learn more about the topics that were covered in this chapter, look at the following resources:

*   OpenAI on GPT-o1 performances: [`openai.com/index/openai-o1-mini-advancing-cost-efficient-reasoning/`](https://openai.com/index/openai-o1-mini-advancing-cost-efficient-reasoning/)
*   American Invitational Mathematics Examination: [`en.wikipedia.org/wiki/American_Invitational_Mathematics_Examination`](https://en.wikipedia.org/wiki/American_Invitational_Mathematics_Examination)
*   Codeforces: [`codeforces.com/`](https://codeforces.com/)
*   Prompt best practices in OpenAI: [`help.openai.com/en/articles/6654000-best-practices-for-prompt-engineering-with-the-openai-api`](https://help.openai.com/en/articles/6654000-best-practices-for-prompt-engineering-with-the-openai-api)
*   Prompt examples in OpenAI: [`platform.openai.com/docs/examples`](https://platform.openai.com/docs/examples)

# Subscribe for a free eBook

New frameworks, evolving architectures, research drops, production breakdowns—AI_Distilled filters the noise into a weekly briefing for engineers and researchers working hands-on with LLMs and GenAI systems. Subscribe now and receive a free eBook, along with weekly insights that help you stay focused and informed.

Subscribe at [`packt.link/TRO5B`](https://packt.link/TRO5B) or scan the QR code below.

![A qr code on a white background  AI-generated content may be incorrect.](img/B31534_Newsletter_NEW.png)

# 5

# Best Practices for Prompting with OpenAI API and GitHub Copilot

In the concluding chapter of *Part 1*, we will explore how to apply best practices for crafting prompts tailored to OpenAI API and GitHub Copilot. These practices are encapsulated in the **five S’s**: **structuring** the prompt, providing **surrounding**context, focusing on a **single** task, including **specific** instructions, and keeping prompts **short** and fluff-free. While the core principles remain consistent, their application varies slightly across different GenAI tools.

We will delve into working with Python objects such as functions, classes, and methods for coding-related tasks. We will leverage the built-in `inspect` package to extract key details about objects, such as their source code, docstrings, and filenames. We will also learn how to integrate this information into the system and user prompts offered by OpenAI API, combining context, task focus, and concise, structured instructions.

Additionally, we will examine how GitHub Copilot inherently provides structure, context, and single-task focus while generating short, specific prompts for us. We will learn techniques to extend Copilot’s capabilities by incorporating additional structure and precision, ensuring minimal fluff and redundant comments.

Through two interactive labs, we will implement these practices using a real-world example: a **Singleton design pattern** to enforce single-instance creation per class. Using OpenAI API, we will craft a docstring for the Singleton `__call__` method, which controls the instantiation process of a new class instance. Then, with Copilot, we will generate a unit test to validate the functionality and fix a faulty implementation.

In this chapter, we will cover the following topics:

*   Extracting properties from Python objects for OpenAI API
*   Crafting precise prompts for OpenAI API
*   Generating docstrings with OpenAI API
*   Crafting precise prompts for GitHub Copilot
*   Fixing faulty implementation with GitHub Copilot

# Technical requirements

To get the most out of this chapter, ensure you have the following:

*   GitHub Copilot account
*   I**ntegrated development environment** (**IDE**) – either VS Code or PyCharm
*   OpenAI account with access to OpenAI API
*   Access to the book’s repository, which is available at [`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)
*   Virtual environment set up in VS Code or PyCharm
*   OpenAI API token

For assistance setting up a GitHub Copilot account, refer to *Chapter 2*. For instructions on setting up OpenAI API access and token generation, see *Chapter 3*. If you need help creating an OpenAI account or setting up a virtual environment in your IDE, refer to the *Appendix* for detailed guidance.

# Extracting properties from Python objects for OpenAI API

When using OpenAI for coding tasks, we often include details about Python objects such as variables, functions, and classes in our prompts. This helps with various tasks such as debugging, generating docstrings, creating unit test suites, or improving code. The information provided may include the object name, arguments, return type, filename, docstring, and source code.

Throughout this book, we frequently use the built-in `inspect` package to extract relevant details from Python objects. Additionally, we leverage some special attributes, identified by a **double underscore** (**dunder**), such as `obj.__attribute__`, which store metadata about the object or class. Here are some more examples:

*   `obj.__name__` retrieves the name of the object
*   `obj.__class__.__name__` retrieves the class name of an instance or function or the metaclass name of a class
*   `obj.__doc__` retrieves the docstring of the object

To extract the source code and filename of an object, we typically use Python’s built-in `inspect` library:

*   `inspect.getsource(obj)` retrieves the source code of the object
*   `inspect.getfile(obj)` retrieves the file name of the object

For example, we can use `inspect.getsource(obj)` to retrieve the source code for the faulty implementation of the `multiplication_quiz` function discussed in *Lab 4.2* in *Chapter 4*. This function is intended to execute 10 different multiplication quizzes, as outlined in its docstring, but contains implementation bugs that we need to address:

```

def multiplication_quiz() -> None: """

此函数生成一个包含 1 到 12 之间十种不同随机乘法问题的乘法测验。

The user is prompted to answer each question. If the user answers correctly, the function prints "Well done!".

If the user answers incorrectly, the function prints "No.".

""" a = random.randint(1, 12)

    b = random.randint(1, 12)

    score = 0

    for _ in range(10):

        question = "What is " + a + " x " + b + "? " answer = input(question) if answer == a * b: print("Well done!")

            score += 1

        else: print("No.") print(f"Your score is {score} out of 10.")

```py

![](img/3.png)**Quick tip**: Enhance your coding experience with the **AI Code Explainer** and **Quick Copy** features. Open this book in the next-gen Packt Reader. Click the **Copy** button

(**1**) to quickly copy code into your coding environment, or click the **Explain** button

(**2**) to get the AI assistant to explain a block of code to you.

![A white background with a black text  AI-generated content may be incorrect.](img/image_%282%29.png)

**![](img/4.png)** **The next-gen Packt Reader** is included for free with the purchase of this book. Scan the QR code OR visit packtpub.com/unlock, then use the search bar to find this book by name. Double-check the edition shown to make sure you get the right one.

![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png)

The code for the function can be extracted using the `getsource` function:

```

inspect.getsource(multiplication_quiz)

```py

The returned value will be a string containing the function’s code as text, as shown here:

```

'def multiplication_quiz() -> None:\n    """\n    This function generates a multiplication quiz of ten different random multiplication questions between 1 and 12\. ... the rest of the code is omitted for brevity ...'

```py

This format is easily interpreted by GenAI applications and **large language models** (**LLMs**), and we will use it to include Python objects and code blocks in our prompts, enclosed within `{{{ }}}`.

Next, we will explore how these objects are integrated into OpenAI prompts using the five S’s best practices for crafting precise and effective prompts.

# Crafting precise prompts for OpenAI API

Applying best practices for building a precise prompt with OpenAI API enables us to automate and scale the prompting process while ensuring quality outputs from the underlying LLMs.

We will revisit the five S’s best practices, beginning with structuring OpenAI API prompts. We will craft system prompts that incorporate the surrounding context and focus on a single task, enabling the development of reproducible and adaptable templates. Additionally, we will explore how incorporating specific and short instructions helps transform diverse inputs into concise user prompts.

## Structured prompts

To structure prompts for OpenAI API, we use **system prompts** and **user prompts** to separate the surrounding context and single task objective from specific details such as steps, source code, and data. System prompts define the context and task, allowing for reuse across varying details such as different source codes. In later chapters of the book, we will also explore how to integrate **assistant prompts** to achieve even more refined results from our prompts.

In Python, this prompt structure usually includes a variable called `SURROUND` to provide the surrounding context and a variable called `SINGLE_TASK` to specify the task for the model. It may be structured as follows:

```

SURROUND = " Your surrounding context here " SINGLE_TASK = " Your task here "

def get_user_prompt(*args, **kwargs) -> str: return """"

# your code here

COMPLETION:

""" system_prompt = f"{SURROUND}  {SINGLE_TASK}" user_prompt = get_user_prompt(...)

messages = [

    {"role": "system", "content": "system_prompt"

{"role": "user", "content": user_prompt},

]

```py

In this structure, the `messages` parameter combines both `system_prompt` and `user_prompt` to form a precise prompt for OpenAI API. `system_prompt` integrates `SURROUND` and `SINGLE_TASK`, while the `get_user_prompt` function provides details such as steps, source code, and object information, concluding with a lead-in cue such as `COMPLETION` to align with `SINGLE_TASK`, as we will discuss in depth throughout this chapter.

Now that we have examined the structure that combines both system prompts and user prompts, let us dive deeper into each, starting with system prompts.

## System prompts with the surrounding context and single task

In OpenAI API, system prompts are used to define the surrounding context and specify a single task. These prompts are designed to be reproducible, accommodating varying supporting data.

For instance, a system prompt might state that the model is provided with a code snippet and tasked with identifying the programming language:

```

SURROUND = "You will be provided with a code snippet enclosed with {{{ CODE }}}."

SINGLE_TASK = "Your task is to identify the programming language of the provided code snippet."

system_prompt = f"{SURROUND} {SINGLE_TASK}"

```py

The `SURROUND` context specifies that the provided data is a code snippet in an unidentified language, while `SINGLE_TASK` clarifies that the expected output should identify the programming language of the code.

In another scenario, the task might involve generating documentation for a Python function where the programming language (Python) and object type (function) are already known. In such cases, this information should be included in the surrounding context to help the model focus on generating the docstring rather than determining the language or object type:

```

SURROUND = "You will be provided with a Python function enclosed with {{{ FUNCTION }}}."

SINGLE_TASK = "Your task is to generate a Google Style docstring for it."

system_prompt = f"{SURROUND} {SINGLE_TASK}"

```py

In this case, `SURROUND` provides context about the Python function, enabling the model to concentrate on the task of generating docstrings, as specified in `SINGLE_TASK`.

## User prompts with specific instructions

To create an effective user prompt for OpenAI API call, we typically define a `get_user_prompt` function that encapsulates the necessary task details along with a lead-in cue to align with the system prompt.

For example, if the task is to identify the programming language from the source code, the function implementation might look like this:

```

def get_user_prompt(code_source: str) -> str: return f"""

CODE: {{{{{{ {code_source} }}}}}}

PROGRAMMING LANGUAGE:

"""

```py

In the preceding implementation, {{ in f-strings are used to represent a literal {. As a result, `{{{{{{` is required to represent `{{{`. Also, the source code is retrieved as a string, requiring no further conversion.

In a different scenario involving Python objects, such as extracting the docstring for a class method, the source code can be directly obtained from the object. The implementation of `get_user_prompt` in this case might look like this:

```

def get_user_prompt(func: callable) -> str: return f"""

FUNCTION: {{{{{{ {inspect.getsource(func)} }}}}}}

    DOCSTRING:

    """

```py

In this implementation, the `inspect.getsource` function is used to extract the source code from the function.

Next, we will combine system prompts and user prompts to observe how they work together to produce high-quality outputs.

# Lab 5.1 – Generating docstrings with OpenAI API

In this lab, we will utilize OpenAI API to generate a docstring for the `__call__` method in a Singleton design pattern, as outlined in the following steps. The `__call__` method defines the **instantiation process**, which involves creating or managing a new instance of the class.

## Singleton design pattern

As Python developers, we often use design patterns to define and control the behavior of Python objects, such as functions and classes. One such pattern is the **Singleton pattern**, which ensures that only one instance of a class is created and used throughout the program’s execution.

Regular classes create a new instance from scratch with each instantiation, using either provided arguments or default parameters. For example, consider the following program with an `Environment` class that defaults to the name `Production`:

```

class Environment: def __init__(self, name: str = "Production"): self.name = name

env1 = Environment("Development")

env2 = Environment() print("env1 name: ", env1.name) print("env2 name: ", env2.name)

```py

In this case, `env1` and `env2` are two separate instances of the `Environment` class. For instance, the `name` attribute of `env1` is set to `Development`, while the name of `env2` is set to `Production` based on the provided default argument.

The output of this program is as follows:

```

env1 name:  Development

env2 name:  Production

```py

The Singleton design pattern ensures that only one instance of a class is created and maintained throughout the program’s runtime. It is typically implemented using a **metaclass**, which acts as a **class of classes**, defining how other classes are structured and behave.

A typical Singleton implementation maintains a **registry** dictionary of instantiated classes. For each class defined with `metaclass=Singleton`, whenever a new instance is requested, the Singleton checks its registry for an existing instance of that class. If an instance is found, it is returned; otherwise, a new instance is created and added to the registry. Here is an example of such an implementation:

```

class Singleton(type):

    _instances = {} def __call__(cls, *args, **kwargs): if cls not in cls._instances:

            cls._instances[cls] = super(Singleton, cls).__call__(*args, **kwargs) return cls._instances[cls]

```py

In this implementation, the `__call__` method is invoked whenever a class of the `Singleton` type, referred to as `cls` (a common name for a class argument), attempts to instantiate a new instance. If an instance of the class already exists, it is stored in the `_instances` attribute with the class’s hash as the key, and the existing instance is returned. Otherwise, a new instance of `cls` is created as usual and added to the `_instances` registry for future use.

To use classes of the `Singleton` type, such as `Environment`, we specify that the metaclass for the class is `Singleton`, as shown here:

```

class Environment(metaclass=Singleton): def __init__(self, name: str = "Production"): self.name = name

```py

Assigning the `Singleton` metaclass ensures that all instances of the class refer to the same object. When two instances are created, one with the `Development` name and the other without any parameters, both `Environment` instances will share the name `Development`:

```

env1 = Environment("Development")

env2 = Environment() print("env1 name: ", env1.name)

print("env2 name: ", env2.name)

```py

In this case, `env1` and `env2` are the same instance and `env2.name` is also expected to be `Development`. The program output confirms this, as shown here:

```

env1 name:  Development

env2 name:  Development

```py

Next, we will see how to leverage OpenAI API to generate a docstring for the Singleton `__call__` method.

## Generating a docstring

A **docstring** is a special string literal in Python that provides a clear description of an object’s purpose, behavior, arguments, and return values, typically for functions or classes, and would be followed by the code implementation. For instance, here is a **Google-style docstring** for a function that calculates the *n*th Fibonacci number:

```

def fibonacci(n): """

Calculate the n-th Fibonacci number.

The Fibonacci sequence is a series of numbers where each number is the sum

of the two preceding ones, starting from 0 and 1\. This implementation uses

an iterative approach for better performance with large values of n.

Args:

n (int): The position in the Fibonacci sequence (0-indexed).

Returns:

int: The n-th Fibonacci number.

Raises:

ValueError: If n is a negative integer.

Examples:

>>> fibonacci(0)

0

>>> fibonacci(1)

1

>>> fibonacci(5)

5

""" ...

```py

We will explore how to effectively create and utilize high-quality docstrings for Python objects in greater detail in *Chapter 18*.

In this lab, we will focus on crafting a simple Google-style docstring for the `__call__` method of the `Singleton` class, incorporating information about the source code of the Python object.

## Lab 5.1 guided walk-through

Open *Lab 5.1* in the book repository at `ch5/labs/lab51.py` and ensure that you have either set the `OPENAI_API_KEY` environment variable or configured your run settings to point to the `.env` file.

The starter code includes the implementation of the `Singleton` metaclass, along with placeholders for the `SURROUND` and `SINGLE_TASK` strings, the `get_user_prompt` function, and the `messages` parameter for OpenAI API:

```

import inspect from openai import OpenAI from openai.types.chat import ChatCompletion

SURROUND = "" SINGLE_TASK = ""

class Singleton(type):

    _instances = {} def __call__(cls, *args, **kwargs): if cls not in cls._instances:

            cls._instances[cls] = super(Singleton, cls).__call__(*args, **kwargs) return cls._instances[cls] def get_user_prompt(func: callable) -> str:

    ... if __name__ == "__main__":

    client: OpenAI = OpenAI()

    completion: ChatCompletion = client.chat.completions.create(

        model="gpt-4o-mini",

        messages=[],

    ) 打印("文档字符串:", completion.choices[0].message.content)

```py

In the guided walk-through, we will complete the `SURROUND` and `SINGLE_TASK` strings, the `get_user_prompt` function, and the `messages` parameter.

First, we will define the surrounding context and single task for the reusable system prompt. Update the `SURROUND` and `SINGLE_TASK` strings as follows:

```

SURROUND = "您将获得一个包含在{{{ Function }}}中的 Python 函数。" SINGLE_TASK = "您的任务是为其生成 Google 风格的文档字符串。"

```py

These strings inform the model that the provided source code is a Python function and specify that the generated docstring should follow Google-style conventions.

Next, we will integrate specific and short instructions into the user prompt. Implement the `get_user_prompt` function to encapsulate the source code of a provided function, along with a lead-in cue to generate a Google-style docstring:

```

def get_user_prompt(func: callable) -> str: return f"""

FUNCTION: {{{{{{ {inspect.getsource(func)} }}}}}}

GOOGLE STYLE DOCSTRING:

"""

```py

Finally, complete the `messages` argument for OpenAI API call by including the system prompt with the `SURROUND` and `SINGLE_TASK` strings, along with the output of `get_user_prompt` encapsulating the `__call__` method of the `Singleton` class:

```

messages=[

    {"role": "system", "content": f"{SURROUND}  {SINGLE_TASK}"},

    {"role": "user", "content": get_user_prompt(Singleton.__call__)},

],

```py

If you have completed all the steps correctly, your lab code should appear as follows:

```

import inspect from openai import OpenAI from openai.types.chat import ChatCompletion

SURROUND = "您将提供包含在{{{ Function }}}中的 Python 函数。" SINGLE_TASK = "您的任务是为其生成 Google 风格的文档字符串。"

class Singleton(type):

    _instances = {} def __call__(cls, *args, **kwargs): if cls not in cls._instances:

            cls._instances[cls] = super(Singleton, cls).__call__(*args, **kwargs) return cls._instances[cls] def get_user_prompt(func: callable) -> str: return f"""

函数: {{{{{{ {inspect.getsource(func)} }}}}}}

GOOGLE STYLE DOCSTRING:

"""

if __name__ == "__main__":

    client: OpenAI = OpenAI()

    completion: ChatCompletion = client.chat.completions.create(

        model="gpt-4o-mini",

        messages=[

            {"role": "system", "content": f"{SURROUND}  {SINGLE_TASK}"},

            {"role": "user", "content": get_user_prompt(Singleton.__call__)},

        ],

    ) 打印("文档字符串:", completion.choices[0].message.content)

```py

Your lab is now ready to execute and generate a Google-style docstring. Stay tuned for the lab analysis, where we will review a sample output from the run.

## Lab 5.1 analysis

In this lab, we demonstrated how applying the five S’s best practices for precise prompts can yield good results with just a few lines of code. Using OpenAI API, we successfully generated a Google-style docstring for the `__call__` method of the `Singleton` class.

For reference, here is a sample output from the lab, which produced a Google-style docstring that clearly explains the method’s general purpose, its arguments, and its return value, ensuring that the same single instance of the class is returned for every instantiation:

```

文档字符串: ```pypython
def __call__(cls, *args, **kwargs):
    """Overrides the default behavior of instance creation to ensure that only one instance of
    the class is created (Singleton Pattern). This method checks if the class has already been instantiated. If not, it creates a new instance
    and stores it in the class's `_instances` dictionary. Subsequent calls will return the existing
    instance. Args:
        cls: The class that is being instantiated. *args: Variable length argument list for the class constructor. **kwargs: Arbitrary keyword arguments for the class constructor. Returns:
        The single instance of the class. """
```

```py

This docstring accurately describes the `_instances` attribute of the `Singleton` metaclass, which stores the single instances of the class, as well as the arguments of the `__call__` method and its return value.

Having explored how to craft prompts for OpenAI API using the five S’s, including system and user prompts that integrate information about Python objects for coding tasks, identifying the programming language of a code snippet, and generating a Google-style docstring, we will now turn to implementing the five S’s best practices for prompt precision when crafting prompts for GitHub Copilot.

# Crafting precise prompts for GitHub Copilot

When working with GitHub Copilot’s three interaction modes, code completion, chat, and code analysis, many best practices are already built in. Copilot structures the prompt automatically, providing surrounding context for these modes, each with a clearly defined single task, whether it is completing code, engaging in a chat, or analyzing code. The prompts are also designed to be specific and short.

However, we can use the five S’s more precisely and achieve even better results. In this section, we will use the Singleton design pattern as an example to explore how Copilot supports code completion, code analysis, and chat.

With an understanding of this pattern and its applications, let us examine how the five S’s are implemented and can be extended within Copilot’s three interaction modes.

## Structuring with a lead-in cue

Copilot automatically structures prompts for its three interaction modes while considering surrounding context such as the filename, open files, code before and after the cursor, and Git history to generate a prompt on your behalf.

To improve Copilot’s structured prompts, you can provide lead-in cues such as `def func_name`, the start of a variable declaration, `env1 =`, or the beginning of a return statement for an f-string, such as `return """`. These lead-ins, like the closing cues used in ChatGPT and OpenAI prompts, help clarify the starting point for Copilot’s generation and ensure it proceeds as intended.

For example, consider a prompt such as the following:

```

class Singleton

```py

This is more effective than a comment such as the following:

```

# 实现一个 Singleton 元类，确保一个类只有一个实例被创建。

```py

The first option provides a clear lead-in cue indicating the class to be implemented, while the latter is likely to result in another comment instead of initiating the actual implementation.

For reference, here is a sample completion generated by Copilot, which includes an additional comment on the next line:

![Figure 5.1: Comment completion with a code comment instead of an implementation](img/B31534_05_01.png)

Figure 5.1: Comment completion with a code comment instead of an implementation

Copilot interprets the request as an opportunity to elaborate further on the Singleton implementation as a comment rather than starting the actual implementation.

Here is a sample completion based on the lead-in cue, `class Singleton`:

![Figure 5.2: Lead-in code for Copilot to implement the Singleton metaclass](img/B31534_05_02.png)

Figure 5.2: Lead-in code for Copilot to implement the Singleton metaclass

In this case, Copilot correctly inferred that it should generate the metaclass implementation even before the `Singleton` class name was fully specified.

## Surrounding with imports and hashtags

GitHub Copilot already supplies the underlying LLM with extensive context across its three interaction modes. This includes information such as the filename, analysis of open files for coding preferences and customization, `import` statements, code before and after the cursor, the programming language being used, and preferred styling guidelines.

When writing new code, we can enhance the surrounding context by explicitly including cues about the `import` statements we plan to use. For instance, if we plan to use the built-in `@dataclass` decorator, which simplifies data-focused classes by automatically generating boilerplate code such as the `__init__` method, adding an `import` statement such as `from dataclasses import dataclass` helps Copilot understand the decorators we want to work with:

![Figure 5.3: Import cues for dataclass decorators](img/B31534_05_03.png)

Figure 5.3: Import cues for dataclass decorators

In this example, Copilot autocompletes the `@` cue with the appropriate `@dataclass` decorator. See the *Further reading* section for additional resources on data classes.

When using Copilot in VS Code, you can enhance the surrounding context in the chat by referencing elements such as `@workspace` or `@terminal`. These annotations, while beginning with `@`, do not refer to decorators but rather specify the environment the chat should consider.

Additionally, specific files or code selections can be referenced using the hashtag, `#`.

For example, to request an explanation of the `__call__` method in the `Singleton` metaclass, you can select the method, type `#selection` in the chat, and then use the `/explain` command, as shown in *Figure 5.4*.

![ Figure 5.4: Using #selection /explain in VS Code/Copilot Chat](img/B31534_05_04.png)

Figure 5.4: Using #selection /explain in VS Code/Copilot Chat

![](img/1.png) **Quick tip**: Need to see a high-resolution version of this image? Open this book in the next-gen Packt Reader or view it in the PDF/ePub copy.

![](img/2.png) **The next-gen Packt Reader** is included for free with the purchase of this book. Scan the QR code OR go to packtpub.com/unlock, then use the search bar to find this book by name. Double-check the edition shown to make sure you get the right one.

![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png)

This gives the chat context about the specific code snippet you want explained. For reference, here is the explanation we received for the selected code:

```

此代码定义了一个 Python 中的 Singleton 元类。Singleton 是一种设计模式，确保一个类只有一个实例，并提供一个全局访问点。以下是代码的分解：

1. 类定义: class Singleton(type):

这定义了一个名为 Singleton 的元类。在 Python 中，元类是类的类，它定义了类如何行为。使用此元类的类将遵循 Singleton 模式。2. 类属性: _instances = {}

此字典将存储使用此元类的类的单个实例。3. __call__ 方法: def __call__(cls, *args, **kwargs):

此方法被重写以控制类的实例化。cls 指的是正在实例化的类。*args 和 **kwargs 用于将任何参数传递给类构造函数。4. 实例检查: if cls not in cls._instances:

这检查类的一个实例是否已经存在于 _instances 字典中。 5. 实例创建：cls._instances[cls] = super(Singleton, cls).__call__(*args, **kwargs)

如果类不在 _instances 中，它将使用 super() 创建一个新的实例并将其存储在 _instances 字典中。 6. 返回实例：return cls._instances[cls]

这返回类的实例，确保只有一个实例存在。总之，这个元类确保使用它的任何类都只有一个实例，实现了单例模式。

```py

Copilot identified the purpose of the `Singleton` metaclass and provided a clear explanation of its key components.

**Note**

As of January 2025, adding additional surrounding context to Copilot Chat is not yet supported in PyCharm.

## Further narrowing the single task

While Copilot is already tailored to the three interaction modes, each aligned with a specific task, there are cases where the task scope can be further refined.

For example, extracting hardcoded strings with arguments or global variables requires providing more specific guidance instead of relying solely on the straightforward `/fix` command. Without additional context, the `/fix` command might generate broader suggestions.

For reference, here is an example of a `/fix` suggestion that unnecessarily proposes adding a `__post_init__` method to the `Environment` class (see *Figure 5.5*).

![Figure 5.5: Copilot offers irrelevant fix](img/B31534_05_05.png)

Figure 5.5: Copilot offers irrelevant fix

Always aim to include single-task instructions, even when using `/` commands. For instance, if the goal is to extract hardcoded values, you can specify that the desired fix, `extract the hard-coded default values to global constants`, alongside the `/fix` command. Narrowing down the single task in this way helps Copilot better understand your intent and produces more accurate recommendations:

![Figure 5.6: Single task narrowed to extracting hardcoded values](img/B31534_05_06.png)

Figure 5.6: Single task narrowed to extracting hardcoded values

In this example, Copilot effectively understands the task and successfully extracts the hardcoded values, proposing to extract `DEFAULT_ENV_NAME` and `DEFAULT_ENV_VERSION`:

![Figure 5.7: Successful extraction of hardcoded values](img/B31534_05_07.png)

Figure 5.7: Successful extraction of hardcoded values

In the green highlighted text in *Figure 5.7*, we can see that Copilot suggested extracting the hardcoded default values into global constants named `DEFAULT_ENV_NAME` and `DEFAULT_ENV_VERSION`.

This demonstrates how applying the single task principle and narrowing it further, even when using backslash commands such as `\fix`, helps us achieve more effective results when working with Copilot.

## Specific instructions with type hints, docstrings, descriptive names, and unit tests

Copilot already preprocesses your files and surrounding context to include specific instructions, ensuring tailored code completions, analyses, and chat responses.

To follow the specificity practice more precisely in our prompts, we can incorporate type hints, docstrings, descriptive names, and unit tests into our code. These practices not only improve the quality and readability of the code but also help Copilot generate better implementations.

For instance, if our code involves handling environment versioning as integers, adding clear type hints and a meaningful name enables Copilot to better suggest appropriate default values:

![Figure 5.8: Using type hints to specify desired completions](img/B31534_05_08.png)

Figure 5.8: Using type hints to specify desired completions

In *Lab 5.2*, we will explore how adding a failing unit test can assist Copilot in identifying and addressing issues in our code.

## Short prompts without comment fluff

When working with Copilot, the goal is to supercharge our work without cluttering the code base we work on. To follow the short principle, we should avoid adding comment fluff, which we define as comments we would not include if not using Copilot and would likely remove after code generation, as they add no value to the implementation.

A better approach is to use meaningful names, type hints, docstrings, and unit tests when generating code, along with a lead-in cue to hint to Copilot that it should start its implementation.

For example, to instruct Copilot for code completion, it is better to provide a meaningful class signature that aligns with the intended implementation:

```

class TestSingleton(TestCase):

```py

That is better than adding unnecessary comments such as the following:

```

# 实现一个测试用例以验证 Environment 类的单例行为

```py

Similarly, prefer a docstring instead of comments:

```

def recursive_fibonacci(n): """

使用递归方法计算第 n 个斐波那契数。

参数：

n (int): 斐波那契序列中的位置（0 索引）。

返回值：

int：第 n 个斐波那契数。

Raises：

ValueError：如果 n 是负整数。

示例：

>>> recursive_fibonacci(0)

0

>>> recursive_fibonacci(1)

1

>>> recursive_fibonacci(5)

5

"""

```py

That is better than using comments such as the following:

```

# 在此处实现 recursive_fibonacci 函数

# 函数应该使用递归方法计算第 n 个斐波那契数

# 如果 n 是负整数，函数应该引发 ValueError

# 参数是 n，返回类型是整数

# 示例：

# recursive_fibonacci(0) => 0

# recursive_fibonacci(1) => 1

# recursive_fibonacci(5) => 5

```py

The former approach is not only more predictable for Copilot but also helps avoid clutter in the code base if the comment is kept after the class generation, or confusion about the code’s origin if the comment is removed.

Also, prefer variable names with type hints instead of inline comments:

```

product: float =

```py

Use the preceding code instead of the following:

```

# 初始化一个 product 变量为 1

```py

Here, too, the former approach is more predictable to Copilot and avoids clutter in the code base.

Next, we will explore how to implement the five S’s best practices with Copilot and apply them in the upcoming lab to fix a faulty implementation of a `Singleton` metaclass.

# Lab 5.2 – Fixing faulty implementation with GitHub Copilot

In this lab, we will address a faulty `Singleton` implementation by adding a unit test to verify its Singleton behavior, then use Copilot to analyze the error and suggest a fix. This lab is inspired by a bug fix the author encountered earlier in her career, where an `Environment` class, intended to function as a Singleton, failed to preserve attribute changes across instances.

The initial faulty implementation of the `Singleton` metaclass was as follows:

```

class Singleton(type):

    _instances = {} def __call__(cls, *args, **kwargs): if cls not in cls._instances:

            cls._instances[cls.__name__] = super(Singleton, cls).__call__(*args, **kwargs) return cls._instances[cls.__name__]

```py

This implementation is close to the correct implementation of a Singleton `__call__` function:

```

class Singleton(type):

    _instances = {} def __call__(cls, *args, **kwargs): if cls not in cls._instances:

            cls._instances[cls] = super(Singleton, cls).__call__(*args, **kwargs) return cls._instances[cls]

```py

However, the faulty implementation searches for an instantiated class instance using the `cls` hash key but stores it under the `cls.__name__` key. This inconsistency causes a bug that prevents the Singleton from maintaining its intended behavior.

In this lab, we will address this logical error by first using Copilot to implement a unit test that evaluates the behavior of the metaclass and then asking Copilot to fix the bug.

## Lab 5.2 guided walk-through

Open *Lab 5.2* in the book repository at `ch5/labs/lab52.py` and ensure that you have a stable internet connection and that GitHub Copilot is ready.

The starter code includes the faulty `Singleton` implementation along with an `import` statement for the `TestCase` class and the `main` runner from Python’s `unittest` package:

```

from dataclasses import dataclass from unittest import TestCase, main class Singleton(type):

    _instances = {} def __call__(cls, *args, **kwargs): if cls not in cls._instances:

            cls._instances[cls.__name__] = super(Singleton, cls).__call__(*args, **kwargs) return cls._instances[cls.__name__] @dataclass

class Environment(metaclass=Singleton):

    name: str = 'Production' version: int = 1

if __name__ == "__main__":

    main()

```py

In the next steps, we will create a unit test to debug the faulty behavior of the `Singleton` metaclass, analyze why it fails, and correct the implementation accordingly.

To test a metaclass’s behavior, we might want to include a class implementation that utilizes the Singleton and compare different instances of it, as follows:

```

def test_something(self):

    @dataclass

    Class A(metaclass=Singleton):

        a: int = 0

self.assertEqual(A(2), A())

```py

To ensure Copilot follows this guideline, we will provide a lead-in cue to start the test case implementation by beginning with the class name. Type the following lead-in:

```

class TestSingleton

```py

As you type, Copilot should recognize that you are attempting to test the `Singleton` metaclass. It may suggest a complete test case, but to tailor it more specifically to our requirements, accept only the first line, which should be as follows:

```

class TestSingleton(TestCase):

```py

Continue by adding a descriptive name for the test case:

```

def test_singleton_should_return_same_instance(self):

```py

Using descriptive names for unit tests is good practice, as it clearly conveys the purpose of the test and serves as a documentation tool.

At this point, Copilot may suggest an implementation involving the `Environment` class. However, the preferred approach is to test a designated class that uses the `Singleton` metaclass, as our goal is to validate the metaclass itself rather than the `Environment` class. Begin the implementation with the following:

```

@dataclass

class A(

```py

At this point, Copilot should detect that we are testing an implementation of the metaclass. By combining the test name and the lead-in cue, it may suggest a unit test such as the following:

```

@dataclass

class A(metaclass=Singleton):

    a: int = 0

self.assertEqual(A(2), A())

```py

This unit test verifies that an instance of `A` initialized with a non-default value of `2` should be equal to a new instantiation of the class without additional parameters, ensuring the Singleton behavior is maintained.

We will delve deeper into writing unit tests with GenAI applications in *Chapter 16*. For now, accept the suggested test case if it resembles the preceding one or tests similar functionality.

If you have completed all the steps correctly, your test class should look like this:

```

class TestSingleton(TestCase): def test_singleton_should_return_same_instance(self):

@dataclass

        class A(metaclass=Singleton):

            a: int = 0

        self.assertEqual(A(2), A())

```py

Please note that this test will fail because the `Singleton` implementation has not yet been corrected.

Next, execute the lab using the following shell command:

```

python -m unittest ch5/labs/lab52.py

```py

This should result in a failing unit test:

![Figure 5.9: Failing unit test for Singleton behavior](img/B31534_05_09.png)

Figure 5.9: Failing unit test for Singleton behavior

Failure is expected because the `__call__` method of the Singleton is not properly implemented. When a new instance of `A` is created, its attribute, `a`, is set to the default value of `0` instead of retaining the value from the previous instantiation of `a=2`.

If you are using VS Code, you can get an explanation of the terminal error by typing the following in the **Chat** window:

```

@terminal /解释失败的单元测试

```py

This prompt specifies that the context is the terminal, instructing Copilot to explain the test failure as shown in the terminal trace. Here is an example explanation generated by Copilot Chat using the *GPT-4o* model:

![Figure 5.10: VS Code explanation for the failing unit test](img/B31534_05_10.png)

Figure 5.10: VS Code explanation for the failing unit test

Note that the objects in the explanation are clickable for added convenience. Clicking on objects such as `A` will direct you to their location in the code:

![Figure 5.11: Clicking on A would highlight the objects in the file](img/B31534_05_11.png)

Figure 5.11: Clicking on A would highlight the objects in the file

The explanation correctly identifies that the incorrect implementation of the `Singleton` metaclass results in two different instances of the `A` class, causing the test to fail.

If you are using PyCharm, copy the failing traceback and paste it into the chat as follows, following the five S’s:

```

CONTEXT：您将获得一个包含在 {{{ TRACEBACK }}} 中的失败的 Python 单元测试跟踪。任务：解释为什么单元测试会失败。跟踪：{{{

python -m unittest ch5/labs/lab52_singleton.py

F

======================================================================

失败：test_singleton_behavior_should_return_same_instance (ch5.labs.lab52_singleton.TestSingleton.test_singleton_behavior_should_return_same_instance)

----------------------------------------------------------------------

Traceback (most recent call last):

    文件 "supercharge/ch5/labs/lab52.py"，第 26 行，在 test_singleton_behavior_should_return_same_instance 中

    self.assertEqual(A(2), A())

AssertionError: TestS[13 chars]_singleton_behavior_should_return_same_instance.<locals>.A(a=2) != TestS[13 chars]_singleton_behavior_should_return_same_instance.<locals>.A(a=0)

----------------------------------------------------------------------

运行 1 个测试用例耗时 0.001 秒

失败 (失败用例数=1)

}}}

EXPLANATION:

```py

This structured prompt, which includes surrounding context, a specific task to explain the failing unit test, the traceback with an enclosed alias, and a lead-in explanation cue, will help us understand why our test is failing.

For reference, here is a sample output from Copilot Chat in PyCharm that correctly identifies the cause of the failing test, specifically, the error in the singleton `__call__` method implementation:

![Figure 5.12: Copilot Chat explanation for the failing unit test](img/B31534_05_12.png)

Figure 5.12: Copilot Chat explanation for the failing unit test

Although this chat does not contain clickable elements, it accurately identifies the problem in the `__call__` method that is not implemented correctly.

Now that we have identified the issue with the `Singleton` metaclass, we can adjust the `__call__` method to properly maintain the single class instance design pattern.

To fix the issue, navigate to the `__call__` method, highlight it, and prompt Copilot to fix the `cls` instantiation, as follows:

```

/修复类实例化

```py

This prompt will suggest the correct fix for the `cls._instances` registry. For your reference, here is a sample output we received when using the Copilot extension in VS Code with the *GPT-4o* model:

![Figure 5.13: Suggested fix for the cls instantiation](img/B31534_05_13.png)

Figure 5.13: Suggested fix for the cls instantiation

Copilot provided the correct implementation of the `Singleton` metaclass using `cls._instances[cls]` instead of `cls._instances[cls.__name__]`.

Accept this solution. At this point, your code should appear as follows:

```

from dataclasses import dataclass from unittest import TestCase, main class Singleton(type):

    _instances = {} def __call__(cls, *args, **kwargs): if cls not in cls._instances:

            cls._instances[cls] = super(Singleton, cls).__call__(*args, **kwargs) return cls._instances[cls]

```py

Rerun the lab using the following shell command:

```

python -m unittest ch5/labs/lab52.py

```py

The unit test should pass, confirming that the singleton is correctly implemented:

![Figure 5.14: Test ran with no errors](img/B31534_05_14.png)

Figure 5.14: Test ran with no errors

The unit test verifies that a new instantiation of the `A` class retrieves the previously created instance with the argument of `a=2`, and the `main()` runner completes without errors.

## Lab 5.2 analysis

In this lab, we debugged the `Singleton` implementation by creating a unit test that failed. Based on the failure explanation, we used Copilot to fix the error. To accomplish this, we applied the five S’s best practices across five different prompts. Let us examine how each prompt emphasizes different practices of the five S’s, helping us achieve more desirable results.

### Prompt 1 – following the structured prompt principle with a lead-in cue

To create a test for the `Singleton` metaclass, we began with a code lead-in cue for Copilot:

```

class TestSingleton

```py

We also followed the *short* best practice, by avoiding unnecessary comments. This was enough for Copilot to suggest the name `class TestSingleton(TestCase)` for the test class.

### Prompt 2– providing specific and short prompt principles

To generate a unit test that utilizes the singleton as a metaclass, we used a descriptive test name, `test_singleton_should_return_same_instance`, along with a lead-in `@dataclass` decorator and class implementation:

```

@dataclass

class A(metaclass=Singleton):

```py

This was sufficient for Copilot to understand that the test should validate the correct instantiation of the Singleton:

```

class TestSingleton(TestCase): def test_singleton_should_return_same_instance(self):

@dataclass

        class A(metaclass=Singleton):

            a: int = 0

        self.assertEqual(A(2), A())

```py

This test case compares two instances of the `A` class: one created with the default parameter and another with a specified parameter. If the Singleton is implemented correctly, the two instances should be equal.

### Prompt 3 – adding surrounding context and focusing on a single task with VS Code

After running the failing unit test, we enhanced the prompt with the additional surrounding context and a single task by using the following:

```

@terminal /解释失败的单元测试

```py

This provided detailed information about the incorrect implementation of the `__call__` method.

### Prompt 4 – applying the five S’s with PyCharm chat

When using PyCharm chat, we applied the same prompt techniques that work with ChatGPT. We used a *structured* prompt with the *surrounding* context, focusing on a *single* task, and created a *specific* and *short* prompt that led to an explanation of the traceback for the failing unit test.

### Prompt 5 – narrowing down the single task to fix a method implementation

Once Copilot identified that the issue was with the `__call__` method’s `cls` instantiation, we provided the following `/fix` command with a narrowed-down single task:

```

/修复类实例化

```py

This allowed Copilot to focus on the correct fix required from this method.

In summary, the five S’s for crafting precise prompts are essential when interacting with any of GitHub Copilot’s three interaction modes. They help refine the structure by incorporating lead-in cues, adding surrounding context to both chats and input statements, and narrowing the focus to the specific task. This approach makes instructions more precise while avoiding unnecessary comments and keeping prompts short and minimal.

In the upcoming chapters, we will explore advanced prompt engineering techniques to further enhance our ability to achieve even better results from the GenAI applications.

# Summary

In this chapter, we explored how to apply the five S’s best practices for crafting precise prompts using both OpenAI API and GitHub Copilot. With OpenAI API, we learned how to extract valuable information from Python objects, including attributes such as source code, docstrings, filenames, object types, and more. When working with Copilot, we examined which aspects of the five S’s are already implemented and identified how we can use those more precisely to improve outputs from the GenAI application.

Through two interactive labs, we utilized the Singleton design pattern, commonly employed by Python developers to enforce a single class instance with a designated metaclass. Using OpenAI API, we generated documentation for the `__call__` method of the Singleton. With GitHub Copilot, we constructed a unit test that failed due to an undesirable behavior caused by faulty implementation, analyzed the test failure, and assisted Copilot in fixing the implementation.

With this, we conclude *Part 1* of this book, in which we explored the best practices for crafting precise prompts in ChatGPT, OpenAI API, and GitHub Copilot.

By now, we have learned how to use OpenAI API, ChatGPT, and GitHub Copilot for a variety of use cases. We examined the costs associated with each tool and observed the OpenAI rate limits. We also explored Copilot’s architecture, built on the foundation of OpenAI API, and gained insights into using ChatGPT’s canvas editor effectively.

We discussed the three pillars of achieving quality outcomes from a GenAI application: model mastery, evaluation metrics, and precise prompts. We emphasized the role of precise prompts by implementing the five S’s: structured prompts, surrounding context, single-task focus, specific instructions, and short prompts without unnecessary fluff.

Next, we move on to *Part 2*, where we will delve deeper into understanding the underlying LLMs, analyzing their risks and limitations, and learning how to take ownership of GenAI-generated code, including critically reviewing code created from colleagues’ prompts.

# Quiz time

Before you proceed to the next chapter, make sure that you can confidently answer the following questions:

**Question 1**: How can we incorporate information from Python objects when working with OpenAI API?

**Answer**: When working with OpenAI API, we often include data about Python objects such as functions, methods, classes, and variables. To extract details such as source code, docstrings, filenames, and object types, we can use special attributes (dunder) methods, or the built-in `inspect` package.

**Question 2**: Which of the five S’s for precise prompts are implemented in OpenAI API system prompts?

**Answer**: OpenAI API system prompts incorporate surrounding context and single-task specifications, separated by a space. These prompts are reusable across different user prompts that are typically handled by a function such as `get_user_prompt`.

**Question 3**: How can we extend the structured prompt practice with GitHub Copilot?

**Answer**: GitHub Copilot handles much of the structuring automatically. Adding a lead-in cue, such as a function name (`def func_name`), variable type hint (`product: float =`), or a class name (`class ClassName`), serves as an effective cue for Copilot to begin the desired implementation.

**Question 4**: Are code comments such as `# implement the following function` effective when working with Copilot?

**Answer**: Such comments are considered fluff and do not enhance the code’s readability or Copilot’s output. Always prefer using lead-in cues instead of trivial comments.

# Further reading

To learn more about the topics that were covered in this chapter, look at the following resources:

*   Singleton design pattern, by Geeks for Geeks: [`www.geeksforgeeks.org/singleton-method-python-design-patterns/`](https://www.geeksforgeeks.org/singleton-method-python-design-patterns/)
*   Metaclasses, by Real Python: [`realpython.com/python-metaclasses/`](https://realpython.com/python-metaclasses/)
*   Python dataclass documentation: [`docs.python.org/3/library/dataclasses.html`](https://docs.python.org/3/library/dataclasses.html)
*   The 3S’s best practices for GitHub Copilot for VS Code: [`techcommunity.microsoft.com/blog/azuredevcommunityblog/single-short-specific---prompting-github-copilot-for-visual-studio/4117226`](https://techcommunity.microsoft.com/blog/azuredevcommunityblog/single-short-specific---prompting-github-copilot-for-visual-studio/4117226)

|  
#### Unlock this book’s exclusive benefits now

Scan this QR code or go to [packtpub.com/unlock](http://packtpub.com/unlock), then search for this book by name. | ![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png) |
| *Note: Keep your purchase invoice ready before you start.* |

# Part 2

# Basics to Advanced LLM Prompting for GenAI Coding

In *Part 2* of this book, we explore how LLMs can be applied to consistently generate quality code. It begins with a high-level guide on how LLMs work and then applies them to different tasks. By the end of this part, you will understand which tools (ChatGPT, OpenAI API, and GitHub Copilot) can be best applied for a given task.

This part expands into prompt engineering, including advanced topics such as few-shot learning, Chain-of-Thought reasoning, iterative prompting, and chaining to better understand and refactor code. It concludes with an exploration of fine-tuning methods.

This part contains the following chapters:

*   *Chapter 6*, *Behind the Scenes: How ChatGPT, GitHub Copilot, and Other LLMs Work*
*   *Chapter 7*, *Reading and Understanding Code Bases with GenAI*
*   *Chapter 8*, *An Introduction to Prompt Engineering*
*   *Chapter 9*, *Advanced Prompt Engineering for Coding-Related Tasks*
*   *Chapter 10*, *Refactoring Code with GenAI*
*   *Chapter 11*, *Fine-Tuning Models with OpenAI*

# 6

# Behind the Scenes: How ChatGPT, GitHub Copilot, and Other LLMs Work

While most of the chapters in this book provide hands-on guides to using GenAI models for coding, it is also useful to understand how they work under the hood. ChatGPT, OpenAI API, and GitHub Copilot are based around **large language models** (**LLMs**) that have been responsible for the sudden rise of GenAI not only in the technology space but across industries. By understanding how LLMs work, you will understand when they can be most effective, know their limitations, and appreciate their role in prompting. This will maximize your overall success with GenAI.

This chapter will introduce the following concepts:

*   Statistical approach to finding similar letters
*   Small and large language models for words
*   Improving LLM output performance
*   What are the limitations of LLMs?
*   ChatGPT
*   GitHub Copilot

# Technical requirements

To get the most out of this chapter, ensure you have the following:

*   GitHub Copilot account
*   IDE – either VS Code or PyCharm
*   OpenAI account with access to OpenAI API
*   Access to the book’s repository, available at [`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)
*   Virtual environment set up in VS Code or PyCharm
*   OpenAI API token

For assistance setting up a GitHub Copilot account, refer to *Chapter 3*. For instructions on setting up OpenAI API access and token generation, see *Chapter 2*. If you need help creating an OpenAI account or setting up a virtual environment in your IDE, refer to the *Appendix* for detailed guidance.

# Statistical approach to LLMs

Many users of ChatGPT and other LLMs often have an incorrect impression of how LLMs work. They ask questions such as *What fraction of the internet do they understand?*. To introduce the underlying concepts, this section focuses on a simpler problem using just statistics. This will allow us to provide a foundation for discussing how models work before we shift into AI and deep learning. The question we will address is whether we can use probabilities to predict the next letter given a set of preceding letters. If we can, then we should be able to create true English from data without any understanding of linguistic orthography, phonology, morphology, or even general language.

For this sample problem, we will use a medium-sized dataset called the *Reuters-21578* dataset. It is available at the **UCI Machine Learning Repository** ([`archive.ics.uci.edu/`](https://archive.ics.uci.edu/)) and consists of 21,578 different news wire articles, which are just text stories across different topics. While the main use of this dataset is to train and assess text classification algorithms, we are using this as a large corpus of text that has over 15 million letters. The rest of this section describes the process of using this corpus to predict the next letter using a statistical approach. A curious reader can experiment further with the provided code available in the GitHub repository for *Chapter 6*.

Our first analysis step is to look at the frequencies of individual letters. Although the dataset has not only letters but also numbers, punctuation, and other symbols, we will focus on just the letters and the spaces between words. We will also ignore the case and convert everything to lowercase. The frequencies of the individual letters are shown in *Figure 6.1*. The frequency of words typically follows **Zipf’s law**, but not for letters. However, we do see the expected tapering of frequencies when sorted by letter, although the distribution is not as smooth due to the limited size of the dataset.

![Figure 6.1: Letter frequencies for the Reuters-21578 dataset](img/B31534_06_1.png)

Figure 6.1: Letter frequencies for the Reuters-21578 dataset

With the frequencies or probabilities of the individual letters from *Figure 6.1*, we can produce words by sampling from this distribution. We can sample proportional to the frequency of the letters in the dataset and try to craft English words. We can do this by generating a random number with a uniform distribution between 0 and 100%. If it’s < 12%, it would be an `e`. If it’s in the 12 to *(12+9)*% range, then it would be `t`. If it’s in the 19 to *(19+8.5)*% range, it would be `a`, and so on. The results of this approach are shown in *Figure 6.2*. Each row represents a different example to show some variation. As you can see, we have not replicated anything that looks vaguely like English:

![ Figure 6.2: Creating “words” from using just the individual word frequencies](img/B31534_06_2.png)

Figure 6.2: Creating “words” from using just the individual word frequencies

Using the individual frequencies of words doesn’t use any context, and so it produces words that do not resemble English. Context in this case refers to the order of the letters that come before it. For instance, in the first line, no English words start with *wwu* or *tte* or *dn*. Similarly, the letter *q* is usually followed by *u* in English.

To augment this with the context of preceding letters, we can use conditional probabilities. In statistical terms, *p(x|y)* is read as the probability of *x* given *y*, and it means the probability of *x* occurring given that *y* occurs. Mathematically, the formal definition is as follows:

![](img/B31534_06_001.png)

If we think of playing cards, the probability of the queen of diamonds is 1/52, but the probability of the queen of diamonds given it is a queen is 1/4\. The probability of a queen of diamonds given it is a diamond is 1/13.

In our context, we are going to use these conditional probabilities to compute the probability of the next letter. So, given the current letter is a *q*, the next letter is usually a *u*. In fact, we can build a table of all the possibilities written as percentages for each combination of letters. *Figure 6.3* shows the first letter as the column, and the conditional probability of the next letter as a row. For instance, *p(u|q)* is 90.3%.

![Figure 6.3: Percentage of conditional probabilities for next letters (rows) given letters (columns)](img/B31534_06_3.png)

Figure 6.3: Percentage of conditional probabilities for next letters (rows) given letters (columns)

The sampling is more complicated in the conditional probability case, so let’s use an example. To create text, we might assume that our last letter is a *q*. To choose the next letter, we randomly sample from the possibilities across all rows of the `q` column. We then generate a random value from 0 to 100% representing a random probability drawn from a uniform distribution for the next letter. We then consider which bucket the random number fell in. The letter *a* is `0.7`%, *b* through *h* are all `0.0`%. The letter *I* has a `1.1`% chance. The letter *t* has a *7.6*% chance, and the letter *u* has the largest probability of *90.3*%. While it appears that these numbers do not sum to 100%, this is due to round-off errors only. If we select based on these probabilities, the most likely letter is *u*. We repeat the process with the `u` column, where the most likely letters are *t*, *r*, *n*, and *s*, and the least likely letters are *q* and *u*. You are likely wondering which words have these strange letters, but remember that there may be acronyms, email addresses, and foreign names included in the articles.

Now that we can generate words for conditional probabilities, does this approach work? *Figure 6.4* shows the results. The word lengths are much closer, and there are a couple of real words, such as `it`, `as`, and `mag`, but otherwise, they do not look like English words:

![Figure 6.4: Conditional probabilities fo﻿r p(next_letter | current letter)](img/B31534_06_4.png)

Figure 6.4: Conditional probabilities for p(next_letter | current letter)

We can extend the model so that instead of just looking at a letter given its preceding single letter, we can consider a wider context. Specifically, we can consider the next letter given the preceding *j* letters using the probability *p(next_letter | preceding j letters)*. This makes the table much larger since the number of columns would increase from 26 to combinations of 2 letters, 3 letters, or more. For the next letter, based on all combinations of the 2 previous letters, the table would be 26 by 26² = 676\. For the next letter based on the previous 3 letters, the table would be 26 by 26³ = 17,576\. However, with a longer context, we would expect better results. We will not show these larger tables of percentages or probabilities, but show the results instead.

The result for the preceding two letters is shown here:

![Figure 6.5: Conditional probabilities for﻿ p(next_letter | preceding 2 letters)](img/B31534_06_5.png)

Figure 6.5: Conditional probabilities for p(next_letter | preceding 2 letters)

For the preceding three letters, the result is as follows:

![Figure 6.6: Conditional probabilities for﻿ p(next_letter | preceding 3 letters)](img/B31534_06_6.png)

Figure 6.6: Conditional probabilities for p(next_letter | preceding 3 letters)

For the preceding four letters, this is the result:

![Figure 6.7: Conditional probabilities for ﻿p(next_letter | preceding 4 letters)](img/B31534_06_7.png)

Figure 6.7: Conditional probabilities for p(next_letter | preceding 4 letters)

For the preceding five letters, the result is as follows:

![Figure 6.8: Conditional probabilities for p﻿(next_letter | preceding 5 letters)](img/B31534_06_8.png)

Figure 6.8: Conditional probabilities for p(next_letter | preceding 5 letters)

Finally, the result for the preceding six letters is the following:

![Figure 6.9: Conditional probabilities for p﻿(next_letter | preceding 6 letters)](img/B31534_06_9.png)

Figure 6.9: Conditional probabilities for p(next_letter | preceding 6 letters)

As we can see, the results improve substantially as we increase the context window. In fact, most of the output has real English words once we use the four preceding letters. With six preceding letters, the sentence flow starts to make some sense, which may be surprising since we are only looking at single letters.

It is important to understand what the model is learning. Although the statistics appear to be producing English words and even some meaningful sentences in *Figure 6.9*, it does not understand the concept of an English word or sentence structure. Furthermore, the model is not storing knowledge or facts of the English language or words. It is only storing the probabilities of the next letter from the preceding context. Our model focuses only on letters at this point, and the next section describes the extension to word-level models. If we had training data that was a thousand or a million times larger, it would be merely doing a better job of estimating the same frequencies.

## Extending the model to words

Our English model, which builds language from letters, is quite limited. To produce meaningful language, we would need a much longer context of preceding words to understand the relationships between words spaced throughout a sentence. Furthermore, we don’t think of language in terms of letters—we think in terms of words. With our 26 letters in English and a space, each of the preceding *j* positions can only have 27 possibilities, which means our model is relatively small.

Note

If we consider all combinations of the preceding 3 letters, there are 27 x 27 x 27, or about 20,000 possibilities of letters. With 15 million letters in the dataset and 20,000 combinations, we have a 750:1 ratio of training to combinations, which provides excellent training. The average person knows 42,000 words, so if we use all combinations of the preceding 3 words, it would be 42,000 x 42,000 x 42,000 ~ 7.4E13, or 74 trillion 3-word combinations possible, which is about 10x more than any PC hard disk can handle today. However, if we have 15 million letters and the average word plus a space character is 6 letters, then there would be 2.5 million words. The ratio of training to combinations drops to a 2.5 million:74 trillion ratio, or 1 in 30 million.

Based on the preceding information, we would need billions of times more data for similar accuracy using the statistical model.

As a model becomes more complex, it requires more training data. We can think of a model as a general function where we try to approximate a *y* value from different *x* values. This approximation process determines the best function parameters from a set of training data *(x, y)* pairs representing the input, *x*, and the output, *y*. In the case of a linear model, the model must learn the best slope and *y*-intercept to represent the data. The training data is collected and designed to be representative of future data so that when the model fits well, it can be useful to predict future *y* values.

Of course, most models are not simple linear models or functions. There may be multivariate inputs with billions of parameters and large output dimensionality. Learning from such large datasets requires significantly larger training data. Consider fitting a linear or a higher-order linear model to a set of data points, as shown in *Figure 6.10*:

![Figure 6.10: The number of training data points increases as the model becomes more complex](img/B31534_06_10.jpg)

Figure 6.10: The number of training data points increases as the model becomes more complex

We can fit a line with just two points, perhaps, but the seventh-order model on the right needs far more data points to accurately fit. AI models often require data for trillions of parameters, which introduces a problem where the model may suffer from insufficient training data available. The accuracy of the model depends on the number of parameters in the model and the size of its training dataset.

To summarize, the example with letters showed that a statistical model could approximate English language words with a moderate training dataset since the number of combinations is reasonably small. However, we need to store the probabilities of each letter given all preceding letter contexts, which can be quite large. For even the context of just three preceding words, the frequencies are prohibitive to store. In addition to the storage challenge, we would need vast quantities of data to fill a word frequency table to achieve modest prediction accuracy, which is not readily available. The next section uses AI rather than statistics to overcome these challenges for words.

# Small and large language models for words

The statistical model clearly worked well for a medium-sized dataset with a small model based on letters. Since grammar and meaning function at the word level, we need to be able to accurately predict the next word rather than the next letter. Since the number of possible next words is far larger than the number of next letters, the model will need to be many orders of magnitude larger. If we think about code or even text, there are no datasets that are billions of times larger. AI methods, and specifically LLMs, provide solutions that enable predictions more efficiently than just probabilities. We describe two methods in this section: word2vec and the Transformer deep learning model.

## Word2vec

The **word2vec model** is arguably a small language model that uses a simple neural network. Inspired by biology, neural networks are a particular type of machine learning algorithm that learn from data. Although there are a variety of neural network models, this type learns a mathematical function. Each output neuron is a nonlinear function of the weighted sum of the input values. In the training step, the weights are adjusted so that the input values will predict the output values.

As an example, a neural network could learn to predict whether today is a good day to play tennis based on the inputs of temperature, wind, precipitation, and humidity. The training data would use past decisions to play tennis (`output=1`) or not play (`output=0`), and the corresponding weather conditions. With only this data, a neural network could learn to classify future good days for tennis based on the weather. The learned weights for wind and precipitation might be large negative values since high wind speeds and precipitation make tennis unplayable.

Developed by Google in 2013, the word2vec algorithm ([`en.wikipedia.org/wiki/Word2vec`](https://en.wikipedia.org/wiki/Word2vec)) trained a model to predict the target word from the context of two words before and after that word. They also developed the opposite problem of predicting the surrounding context from a single word. Essentially, this is equivalent to the next word prediction using the presence of adjacent words rather than only preceding words. Backed with an efficient training algorithm, the results proved reasonably predictive. Of greater importance, *the word2vec weights formed an embedding of the word or numeric vector representation that quantified the semantic and syntax function of words*. In other words, the word2vec model learns to associate every trained word with a numeric vector of numbers. These vectors can be compared, which is useful for comparing the similarity of word meanings.

## Deep learning

Deep learning is a subset of neural networks that involves learning functions of functions, essentially. That is, the outputs of one layer form the inputs to a second layer, creating a deep stack of functions. The **Universal Approximation Theorem** proved that neural networks could learn to approximate any mathematical function, given a two-layer network under certain conditions. Research has found that creating deep neural networks with tens, hundreds, or thousands of layers is an efficient way of achieving accurate results. In each layer, the model adjusts its weights based on the training data to learn functions with the results passed as input to subsequent layers.

In 2017, a new deep learning architecture called the Transformer was published in a famous paper called *Attention is All You Need* from Google, the link to which can be found in the *Further reading* section. Rather than relying on the context of adjacent words, the Transformer architecture efficiently learns the relationship between all words in a sentence. The training process learns the relationship between words using a masking process, through which it hides each word separately and learns to predict it from all the other words in each sentence.

A deep learning network describes an architecture in machine learning with a specific number of inputs, outputs, layers, nodes per layer, inter-node connections, and weights throughout. Like the previously described linear model, the architecture describes the solution and is trained to solve a specific problem. LLMs are the result of training a deep learning network on large volumes of text. They learn to correctly predict the next word much better than statistical and word2vec models. Similar to the statistical next-letter prediction models, they can iteratively predict the next word to generate sentences, paragraphs, and full texts. Researchers have found that by training on ever larger volumes of text (or code), the accuracy continues to improve, so many LLMs have been developed that use increasingly larger network sizes and more training data.

LLMs by themselves offer significant capabilities in next-word prediction, but they are continuing to expand into new areas of intelligence. Many of the breakthroughs are now coming from various techniques that improve the performance of their respective LLMs. The next section describes some steps that users can take with an LLM to improve the outputs of LLMs.

# Improving LLM output performance

If the LLM does not answer questions well, there are four general courses of action: improving prompt engineering, adding more data through the context window, providing examples (few-shot learning), fine-tuning, and **retrieval-augmented generation** (**RAG**). These will be discussed in this section.

## Prompt engineering

The discipline of prompt engineering has recently emerged as a human interface to the LLM. Users or programs can send commands to, ask questions of, and apply research reasoning through the LLM. The discipline involves applying specific wording to maximize the chance of correct outputs without producing erroneous or biased outputs, including hallucinations. The process of writing prompts is often an iterative process where it may require multiple rounds to achieve the desired output. Most of the prompts discussed in this book focus on a single task with specific and clear wording, which is considered good practice. The *five S’s* framework outlined in this book provides a useful general-purpose structured approach to writing the prompts. We’ll cover more on prompt engineering techniques in later chapters.

## Adding context

As discussed in this chapter, LLMs are not databases that store data, nor are they an oracle of all knowledge (yet). They can perform a limited number of tasks and answer a finite number of questions without further enhancements. To enable question-answering, interactive chats, or other tasks such as code generation, the user can send the LLM both the question as well as additional information within a **context window**.

Note

The context window is somewhat analogous to a human’s short-term memory in that it has a limited size and may forget older information. However, the context window is generally large enough to include documents, earlier inputs, and returned outputs. A document can be provided as context, and the prompt engineer can ask questions of the document.

Depending on the size of the context window, all or part of earlier outputs from the system and past inputs are automatically included in the next prompts associated with that user, so an entire dialog or thought process is included in every interaction with the LLM. A short context window might only allow a few papers to be uploaded and summarized together, while a longer context window could enable a book to be uploaded with multiple interactive sessions kept as context. This approach has several advantages over an LLM system, which will be discussed next as ways of improving results.

### Providing examples

The context window allows for documents and other data to be included along with the prompt or question, but it also allows for examples. A prompt may ask the LLM to return a particular nugget of information in a specific format. In many cases, this will be successful, and this is called **zero-shot learning**. That is, there are no examples of how the LLM should form a response—it just uses its baseline approach. However, the prompts can include one example of an input and an output as part of the prompt. This is called **one-shot learning**. If multiple examples are provided, this is called **few-shot learning**. While many examples can be used depending on the context window length, there is a law of diminishing returns. However, it is an effective approach to instruct the LLM to tailor its outputs to meet a specific need. We will discuss few-shot learning in depth in *Chapter 8*.

## Fine-tuning

Training an LLM from scratch may cost $100 million to learn the trillions of weights that are trained on prose, poetry, drama, literature, and science. Due to the prohibitive cost, it will not be trained often. In fact, it is typically two years out of date, which means it does not have any recent events or information. It also likely doesn’t have personal or corporate documents included in its training. One solution discussed is to provide these in a context window. As discussed in *Chapter 2*, for pay-for-service LLMs such as OpenAI, every transaction has two costs: a cost to send information to the LLM and a cost for the output produced, both based on the length of the information. As the amount of input information and the number of calls with the same information increase, it may become a costly solution.

**Fine-tuning** offers an alternative to repeatedly sending a large context to the LLM. It essentially adds a limited supplemental dataset to the LLM training in the form of documents or examples. The training *fine-tunes* the weights of the neural network by making minor adjustments that are sufficient to produce improved outputs. Fine-tuning provides a cost-efficient way of improving outputs without repeatedly sending large contexts of data to the LLM. We will dive deeper into fine-tuning in *Chapter 11*.

## Retrieval-augmented generation

RAG solves two major problems with the LLMs. First, OpenAI and ChatGPT are not databases of information, so they cannot retrieve information like a web search. Second, their training data is typically two years old and does not include personal or corporate documents. The RAG architecture integrates the LLM with external information from a web search, database, or set of documents. RAG uses the LLM to interpret the input from a user and then retrieves blocks of text from various sources that it finds to be closely related to the input. The LLM then processes the combination of the input and retrieved data to form an answer or response using the standard LLM processing. Essentially, RAG fills the context window with candidate answers relevant to the question based on a search and then instructs the LLM to perform its usual summary or question-answering on that context window. This enables a full system with an LLM to perform web searches on current information or focus on specific documents when generating output.

Each of the approaches described in this section is widely used to improve LLM results. While research continues to advance LLM capabilities, it is important to understand their limitations, which are discussed in the next section.

# What are the limitations of LLMs?

With both the statistical approach for the letters and the LLM approach for words, there is no formal knowledge that many expect, given its ability to answer many questions. There is no extensive knowledge base of topics, common sense, or anything except the word patterns it has learned. What is surprising to researchers is the fact that the learned patterns and their relationships somehow enable LLMs to perform new tasks for which they have never been trained. For instance, LLMs have even shown some capability in some foreign languages that are not part of their training set, through a process called **zero-shot cross-linguistic transfer**. Even if the output has been trained, one may get slightly different results each time from a prompt due to the randomness in the system. Much of the research in the prompt engineering area focuses on how to receive consistent and correct outputs from LLMs by crafting the prompts with specific phrases, commands, and context.

The deep learning approach will almost always produce syntactically correct and plausible-looking output, but some of the output may be prone to **hallucinations**. There have been some famous cases where the output was completely incorrect, technically wrong, and sometimes just made up. A professor was accused of assault on a school trip that never happened. Many students have been caught using ChatGPT since none of their references existed. Even a US government health report was caught citing facts of a made-up reference. These incidents can be found in the *Further reading* section. Hallucinations often occur when there is insufficient training to support a particular output. The statistical methods do not have such an issue since they only sample from the previously seen patterns.

It is currently nearly impossible to know in which areas exactly the LLM has expertise, and in which areas they have limited training. A few years ago, the training of LLMs was generally released as part of its research publication. In the past couple of years, much of the LLM training has become more secretive, so we do not know exactly which sources were used and cannot exactly predict their domains of capability. However, OpenAI has been trained extensively on both texts and code in multiple languages. OpenAI’s philosophy is to provide safe and beneficial general AI across many domains. ChatGPT is a specialization using an OpenAI LLM and is discussed in the next section.

# ChatGPT

Launched by OpenAI in November 2022, ChatGPT was developed on the **GPT-3.5** model. It became a focal point of the AI growth since it worked through a conversational interface, unlike the programming interface of other LLMs. The dialog-driven interface requires it to track the history of the conversation, even across sessions. ChatGPT is a specialization of the LLM with improved conversational capability.

One of the key technology improvements was the use of **reinforcement learning from human feedback** (**RLHF**), which improved the dialog capability through training and feedback to give better responses. As discussed earlier, fine-tuning can improve the LLM’s performance for specific tasks. RLHF goes one step further and incorporates feedback from users to adjust the weights. As a result, it delivers results that incorporate human preferences and even reasoning capabilities in terms of responses and answers to questions.

ChatGPT continues to be a leader in the growth of AI, in part due to its easy web interface that makes it widely accessible with minimal training. It has led to greater research in **natural language processing** (**NLP**) and multiple use cases. Although it can write code, its capabilities are limited as compared to GitHub Copilot, which extends the GPT model for generative coding, as described in the next section.

# GitHub Copilot

GitHub Copilot was officially announced as a collaboration between GitHub, Microsoft, and OpenAI, specifically for writing code, in 2021, and opened for technical review. At the time, it started with the GPT-3 instance from OpenAI, and the three companies collaboratively trained it to focus on code development, resulting in the OpenAI Codex. After GPT-4 was released, GitHub Copilot adopted it and released GitHub Copilot X. Its optimization focuses on code completion, fixing bugs, code comments, and tests based on billions of lines of code training beyond the GPT models. The combination of the underlying GPT model with the code-training focus enables the two-way natural language and computer language code writing and explanation.

GitHub Copilot uses a combination of technologies to provide its coding experience. When writing code from a single file, it sends at least part of the current file through the internet to the Copilot server. It will also use the prompt and other open files that are open within their respective VS Code or PyCharm IDE for context. It uses this context to search for similar code using the RAG approach, and then sequentially generates code one token at a time. The amount of code sent to the Copilot server is based on the context length and certainly costs.

If part of your open code and possibly data is being sent to Copilot, it is natural to be concerned about security. The information is encrypted when sent to and from Copilot. The exchange context resides in memory but is deleted without being stored or used for training. The **GitHub Copilot Trust Center** page, available at [`copilot.github.trust.page/`](https://copilot.github.trust.page/), provides more information about their data security, privacy, and related issues. It includes suggestions, feedback, prompts, and user engagement data. None of the code exchanged while using GitHub Copilot is used for training their system.

# Summary

Statistical and AI approaches can learn patterns from sequential data such as text or code, which can efficiently predict the next symbol. Due to the range of possible words, deep learning methods scale well to efficiently predict the next words much better than statistical techniques and have become the standard. Even so, they require vast training sets of text and code and an expensive computational process to be effective.

While LLMs are highly effective, they are not perfect and are limited by their training set of data and perhaps the time it was trained. The output can be limited for various domains and time periods, which can result in hallucinations. While research continues in these areas, some solutions to improve results include effective prompt engineering, providing contextual information such as documents or examples, fine-tuning, and the RAG approach.

OpenAI and ChatGPT are trained on general data and code, and are quite effective at generating code. GitHub Copilot is built upon OpenAI and, with significant additional training on code, is more efficient at generating code, tests, comments, and more.

# Quiz time

Before you proceed to the next chapter, make sure that you can confidently answer the following questions:

**Question 1**: How is the deep learning approach for words similar to and different from the statistical approach described for letters in this chapter?

**Answer**: Both the deep learning approaches and statistical approaches generate new text or code using a combination of their trained model and randomness. Even though they are both trained on data, they rely on randomness to select from the probable next words, which means their outputs can be different each time. In both cases, if they are trained with insufficient data, they may not produce satisfactory results. Neither has a conceptual understanding of the inputs or outputs, so both are relying on patterns of inputs to predict patterns of outputs.

The deep learning approach is orders of magnitude more efficient in predicting the range of possible next words or code using complex, less interpretable models. While both could easily predict the next letters with a large training set, the conditional probabilities would not be able to scale to predict next words as the deep learning approach can.

**Question 2**: How is GitHub Copilot different from OpenAI in terms of code development?

**Answer**: OpenAI was optimized for general knowledge, and GitHub Copilot was optimized for code generation. GitHub Copilot took the human language capabilities of GPT-4 from OpenAI and further trained it on billions of lines of code, comments, and documentation. In this way, it serves as a pair programmer with the ability to generate code from text, explain code as text, write tests from code, and write comments from code.

# Further reading

To learn more about the topics that were covered in this chapter, take a look at the following resources:

*   *Zipf’s law*: [`en.wikipedia.org/wiki/Zipf’s_law`](https://en.wikipedia.org/wiki/Zipf’s_law)
*   Mikolov, Tomas; Chen, Kai; Corrado, Greg; Dean, Jeffrey (16 January 2013). *Efficient Estimation of Word Representations in Vector Space*: [`en.wikipedia.org/wiki/Word2vec`](https://en.wikipedia.org/wiki/Word2vec )
*   Vaswani, Ashish; Shazeer, Noam; Parmar, Niki; Uszkoreit, Jakob; Jones, Llion; Gomez, Aidan N; Kaiser, Łukasz; Polosukhin, Illia (December 2017). *Attention is All You Need*. In I. Guyon, U. Von Luxburg, S. Bengio, H. Wallach, R. Fergus, S. Vishwanathan, and R. Garnett (ed.). 31st Conference on **Neural Information Processing Systems** (**NIPS**). Advances in Neural Information Processing Systems. Vol. 30\. Curran Associates, Inc.: [`arxiv.org/abs/1706.03762`](https://arxiv.org/abs/1706.03762)
*   Pranav Dixit. *US law professor claims ChatGPT falsely accused him of sexual assault, says ‘cited article was never written’*. Business Today: [`www.businesstoday.in/technology/news/story/openai-chatgpt-falsely-accuses-us-law-professor-of-sexual-harassment-376630-2023-04-08`](https://www.businesstoday.in/technology/news/story/openai-chatgpt-falsely-accuses-us-law-professor-of-sexual-harassment-376630-2023-04-08)
*   Loreben Tuquero. *RFK Jr.’s health report shows how AI slips fake studies into research*: [`www.poynter.org/fact-checking/2025/rfk-jr-fake-citations-medical-journals/`](https://www.poynter.org/fact-checking/2025/rfk-jr-fake-citations-medical-journals/ )
*   *GitHub Copilot Trust Center page*: [`copilot.github.trust.page/`](https://copilot.github.trust.page/)

# Subscribe for a free eBook

New frameworks, evolving architectures, research drops, production breakdowns—AI_Distilled filters the noise into a weekly briefing for engineers and researchers working hands-on with LLMs and GenAI systems. Subscribe now and receive a free eBook, along with weekly insights that help you stay focused and informed.

Subscribe at https://packt.link/TRO5B or scan the QR code below.

![A qr code on a white background  AI-generated content may be incorrect.](img/B31534_Newsletter_NEW.png)

# 7

# Reading and Understanding Code Bases with GenAI

Writing code is rarely an isolated task. We will typically have to incorporate our Python snippets into a larger code base that includes project files, often structured under a `/src` folder, along with dependencies listed in a `requirements.txt` file and other non-project files, such as a **Dockerfile** that defines container specifications.

In this chapter, we will work with a code base that computes the **Manhattan distance** between two matrices represented as pandas DataFrames. With the help of ChatGPT, GitHub Copilot, and OpenAI API, we will explore how various GenAI tools can support us in efficiently understanding both non-project files and the main business logic. We will also examine how generating calls with sample parameters can improve our understanding of more complex code.

Here are the key topics covered in this chapter:

*   Reading and understanding the code base structure
*   Using LLMs to explain code
*   Interpreting non-project files
*   Creating calls with example parameters

# Technical requirements

To get the most out of this chapter, ensure you have the following:

*   GitHub Copilot account
*   IDE – either VS Code or PyCharm
*   OpenAI account with access to OpenAI API
*   Access to the book’s repository, available at [`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)
*   Virtual environment set up in VS Code or PyCharm
*   OpenAI API token

For assistance setting up a GitHub Copilot account, refer to *Chapter 3*. For instructions on setting up OpenAI API access and token generation, see *Chapter 2*. If you need help creating an OpenAI account or setting up a virtual environment in your IDE, refer to the *Appendix* for detailed guidance.

# Reading and understanding the code base structure

So far in the book, we have mostly explored code snippets that are limited to a single Python file. In this chapter, we will shift our focus and see how GenAI tools can support us in reading and understanding a broader code base.

Getting to know a code base usually involves reading through a variety of files. For instance, when a developer encounters a new project, they might do the following:

Explore entry points such as `main.py` or `app.py`

Identify the main project files, often found in a `/src` directory

Look for container and dependency management files such as `Dockerfile` and `requirements.txt`

Experiment with specific parts of the code

In this book’s repository, we provide a small code base example located under `ch7/`. Here is a directory tree view of its contents:

```

ch7/

├── app.py

├── src/

│   └── `manhattan.py` ├── Dockerfile

├── README.md

├── requirements.txt

```py

In this tree view, the core business logic that we will explore next is located in `src/manhattan.py`. In addition, we have the following:

`app.py`, which serves as the entry point and handles basic **Hypertext Transfer Protocol** (**HTTP**) `POST` requests, routing them to the business logic. As introduced in *Chapter 2*, HTTP `POST` is a standard method for sending data to a server.

**Dockerfile**, a text file that outlines the steps and dependencies needed to build a container image for running the application. We will return to this later in the chapter.

`requirements.txt`, which lists the application’s dependencies, such as *pandas* and *Flask*, as introduced in *Chapter 2*.

`README.md`, a markdown file commonly used to provide documentation about a code base. In our case, it includes examples of how to use the application.

Next, we will introduce the Manhattan distance, which serves as the core business logic of our application.

## Introducing the Manhattan distance

In this chapter, our code focuses on calculating the **Manhattan distance** between two points. This distance is defined as the sum of the absolute differences along each dimension. In two-dimensional space, we can relate this to classic computer games such as *Pacman*, where movement is restricted to vertical or horizontal directions, with no diagonal steps allowed. For example, consider Pacman and a ghost positioned in locations `(1,1)` and `(3,2)`, respectively, in *Figure 7.1*.

![Figure 7.1: Pacman and ghost positions](img/B31534_07_1.png)

Figure 7.1: Pacman and ghost positions

In this figure, the characters can move either horizontally or vertically. The Manhattan distance between them is two units along the *x* axis and one unit along the *y* axis, which totals 3:

![](img/B31534_07_001.png)

A simple Python implementation for calculating this distance might look like this:

```

def get_manhattan_distance(

x1: Tuple[int, int],

x2: Tuple[int, int], ) -> int:

    x_dist: int = abs(x1[0] - x2[0])

    y_dist: int = abs(x1[1] - x2[1])

    dist: int = x_dist + y_dist return dist

```py

In this implementation, we use two-dimensional vectors represented as `Tuple[int, int]` to represent a position on a board. However, the Manhattan distance can be generalized to higher dimensions computed between matrices of floats, as we will see next.

## Manhattan distance for matrices

The Manhattan distance, also referred to as the **L1 norm**, extends naturally to higher-dimensional data. It is widely used in image analysis when comparing two images and in machine learning research when evaluating prediction errors.

To compute the Manhattan distance between matrices, we can use pandas `DataFrame` objects. *pandas* is a standard library for data manipulation and should be listed in the book’s `requirements.txt` file and already installed in your virtual environment.

Here is an example of a DataFrame with two rows, `A` and `B`, and three columns labeled `a`, `b`, and `c`:

```

import pandas as pd

df1: pd.DataFrame = pd.DataFrame(

    data={ "A": [1, 2, 3], "B": [4, 5, 6],

    },

    index=["a", "b", "c"],

)

```py

We can implement the Manhattan distance using the *pandas* methods `.abs()` for absolute values and `.sum()` for summing along axes:

```

def get_manhattan_distance(

df1: pd.DataFrame,

df2: pd.DataFrame, ) -> np.float64:

    element_wise_dist: pd.DataFrame = (df1 - df2).abs()

    dist: float = element_wise_dist.sum().sum().astype(float) return dist

```py

The distance calculation uses `.sum()` twice: first to sum across rows, and then again to sum the resulting column totals. We convert the result to a float to standardize the output, since summing over integer values may return a *NumPy* `int64` data type.

Let’s take these two DataFrames:

```

A = [[1 3]

[2 4]]

B = [[5 7]

[6 8]]

```py

Calling `get_manhattan_distance` on these will return the following:

```

|5-1| + |6-2| + |7-3| + |8-4| = 16

```py

Now that we have a clear understanding of the core business logic and supporting code around the distance computation, we can explore how GitHub Copilot, ChatGPT, and OpenAI API can help us navigate and familiarize ourselves with the code base.

# Using LLMs to explain code

In *Chapter 3*, we noted that GitHub Copilot does not include the entire code base in the prompt. This is due to context window limitations, potential cost, and the fact that much of the content may not be relevant to the specific task.

However, this does not prevent GenAI from helping us understand the code bases we are working with. Rather than relying blindly on **Large Language Models** (**LLMs**) to identify key components, we will explore how to request explanations for both simple elements and more complex scenarios.

## Using the /explain command with GitHub Copilot

GitHub Copilot includes several slash commands, among them the `/explain` command, which is available in both the inline chat and the chat window. Unlike code completion tasks, the output of this prompt is explanatory text covering arguments, data transformations, and return values.

The command can be used alone or with extra instructions. For example, in PyCharm, we can ask Copilot to explain the `get_manhatt``a``n_distance` function by placing the cursor anywhere within the function signature, opening the inline chat window, typing `/explain`, and hitting *Enter*, as shown in *Figure 7.2*:

![Figure 7.2: Using GitHub Copilot /explain for methods](img/B31534_07_2.png)

Figure 7.2: Using GitHub Copilot `/explain` for methods

Another available option is to select the contents of the function, open a chat window, and type `/explain`. Note that in VS Code, you will need to choose `@workspace` `/explain` by either typing it directly or selecting the `/explain @workspace` option in the drop-down menu after typing `/explain`, as shown in *Figure 7.3*:

![Figure 7.3: Choosing @workspace /explain in VS Code chat](img/B31534_07_3.png)

Figure 7.3: Choosing @workspace /explain in VS Code chat

For either IDE, Copilot is likely to yield a general explanation about the purpose of the function, the data transformation, and the returned value, as shown in *Figure 7.4*.

![Figure 7.4: Sample /explain output in VS Code](img/B31534_07_4.png)

Figure 7.4: Sample `/explain` output in VS Code

If we wanted a broader analysis of the arguments and their type, for example, we could use this prompt:

```

/解释参数类型

```py

This should yield an extended explanation about the arguments, as shown in *Figure 7.5*.

![Figure 7.5: Extended /explain argument types with GitHub Copilot](img/B31534_07_5.png)

Figure 7.5: Extended /explain argument types with GitHub Copilot

![](img/1.png) **Quick tip**: Need to see a high-resolution version of this image? Open this book in the next-gen Packt Reader or view it in the PDF/ePub copy.

![](img/2.png) **The next-gen Packt Reader** is included for free with the purchase of this book. Scan the QR code OR go to packtpub.com/unlock, then use the search bar to find this book by name. Double-check the edition shown to make sure you get the right one.

![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png)

Here, we see a detailed explanation of the arguments `df1` and `df2`, including a note that `df2` is expected to have the same shape as `df1` for the function to work properly. This expectation is not mentioned in the plain `/explain` prompt, but when we ask about a specific aspect of the code, we get a more in-depth explanation.

Next, we will see how we can replicate this outcome through direct prompting with ChatGPT and OpenAI API.

## Using ChatGPT to explain code

While Copilot includes a built-in slash command for code explanations, we can apply the **five S’s framework** introduced in *Chapter 4* to achieve similar results with ChatGPT, even when using older or more cost-effective models such as *GPT-4o*. Unlike GitHub Copilot, which follows predefined instructions about what to explain based on the Python object, ChatGPT allows us to tailor the explanation to our specific needs.

For instance, the following prompt focuses on describing the function’s purpose, its arguments and types, the data flow, expected output, and possible edge cases:

```

CONTEXT: 你被提供了：1. 一个带有 {{ FUNCTION }} 封闭的 Python 函数 2. 带有 {{ HEADERS }} 封闭的解释点。任务：使用解释点解释函数。函数：{{ ...省略以节省空间 ... }}

HEADERS: {{{ 1. 函数目的 2. 参数及其类型 3. 步骤数据流 4. 输出及其类型 5. 可能的边缘情况

}}}

EXPLANATION:

```py

When using *GPT-4o* with this structure, we received an explanation that covered all bullet points with the headers, as partially shown in *Figure 7.6*:

![Figure 7.6: ChatGPT returned extended explanation](img/B31534_07_6.png)

Figure 7.6: ChatGPT returned extended explanation

For reference, here is the output generated by ChatGPT under the edge cases header, which adds value by uncovering situations where the function might fail or produce unexpected behavior:

```

5\. 边缘情况

形状不匹配：如果 df1 和 df2 的形状不同，减法操作将引发 ValueError。非数值列：如果 DataFrame 包含非数值数据，减法操作将引发 TypeError 或产生影响结果的 NaNs。缺失值（NaNs）：如果任一 DataFrame 包含 NaNs，除非事先明确处理，否则输出距离可能为 NaN。空 DataFrame：如果两个输入都是空 DataFrame，则结果将为 0.0。

```py

Although writing a prompt for ChatGPT might take slightly more effort compared to using the `/explain` command, it can be worthwhile when we need more targeted explanations, such as uncovering edge cases.

Next, we will demonstrate how to achieve this using OpenAI API, which may be more appropriate for scenarios where the repository becomes larger and we want to generate explanations for many functions programmatically.

## Using OpenAI API to explain code

Using the same prompt structure from ChatGPT, we can make a programmatic call to OpenAI, following the best practices introduced in *Chapter 5*.

We will define the same system prompt components that mirror our ChatGPT prompt:

```

SURROUND = """...省略以节省空间...""" SINGLE_TASK = """...省略以节省空间...""" HEADERS = """...省略以节省空间"""

```py

We will add a `get_user_prompt` function that merges the `HEADERS` prompt piece with the source code of the function:

```

def get_user_prompt(func: callable) -> str: return f"""

FUNCTION: {{{{{{ {inspect.getsource(func)} }}}}}}

HEADERS: {{{{{{ {POINTS} }}}}}}

EXPLANATION:

"""

```py

Then, we can call OpenAI API using the *gpt-4o-mini* model:

```

if __name__ == "__main__":

    client: OpenAI = OpenAI()

    system_prompt = f"{SURROUND}  {SINGLE_TASK}" user_prompt = get_user_prompt(get_manhattan_distance)

    completion: ChatCompletion = client.chat.completions.create(

        model="gpt-4o-mini",

        messages=[

            {"role": "system", "content": system_prompt},

            {"role": "user", "content": user_prompt},

        ],

    ) print("Explanation:", completion.choices[0].message.content)

```py

Just as with ChatGPT, we will receive a detailed explanation of the function, covering all points specified. For reference, here is a sample output from running this script:

```

函数目的：< ...省略以节省空间... >

参数及其类型：该函数接受两个参数：

* df1: 一个 pandas DataFrame，代表第一组数据。* df2: 一个 pandas DataFrame，代表第二组数据。这两个 DataFrame 都应具有相同的形状和结构，以便计算有效。逐步数据流：< ...省略以节省空间... >

可能的边缘情况：

* 如果 df1 和 df2 的形状不同，由于无法对不同大小的数据框执行元素级操作，函数可能会引发一个值错误。* 如果任一 DataFrame 为空，由于没有元素可以计算差异，函数将返回 0.0 的距离。* 需要考虑 NaN（非数字）值的处理，因为当它们存在于任一 DataFrame 中时，可能会影响计算。

```py

The output here also provides an overview of the edge cases. In later chapters of the book, we will explore how to make use of this when designing a test suite for functions.

Next, we will explore how to extend the use of the `/explain` command beyond `.py` files using various GenAI tools.

# Explaining non-project files

The `/explain` command is not limited to `.py` files or core business logic. For instance, in our Manhattan distance code base, we can use Copilot to interpret an entire non-project file or a specific section of it.

## Explaining an entire file

There are times when we may want a summary of a complete non-project file. For example, consider the `requirements.txt` file in our project:

```

pandas==2.2.3 flask==3.1.0

```py

To get a general explanation, we can highlight the entire content with the cursor, then open the inline chat or chat window and enter `/explain`. *Figure 7.7* shows an example of this using the chat window in VS Code:

![Figure 7.7: Chat window explanation of a full file highlighted content](img/B31534_07_7.png)

Figure 7.7: Chat window explanation of a full file highlighted content

In this case, Copilot accurately recognized that `requirements.txt` lists the dependencies needed for the code base to run properly. For common non-project files, we can generally expect reliable explanations since LLMs have encountered many similar examples during training.

Next, we will look at how to ask for a more detailed explanation of a specific line within a non-project file by providing the right context.

## Explaining with context

While it is useful to understand a file as a whole, there are often specific lines that may be unclear and require a deeper explanation.

Take the `Dockerfile` from our Manhattan distance project as an example. **Docker** is a widely used tool among software developers for packaging applications in a consistent and reproducible way. A key element in this process is the `Dockerfile`, a plain text file typically placed at the project root that outlines the environment setup. This includes specifying a base image (such as a Python environment), listing dependencies (like the *pandas* library), and providing commands to build and run the container (such as opening a port to receive HTTP `POST` requests).

Below is the Dockerfile we used for our Manhattan distance application:

```

FROM python:3.10-slim

WORKDIR /app

COPY requirements.txt . RUN pip install -r requirements.txt

COPY . . EXPOSE 5000 CMD ["python", "app.py"]

```py

Copilot can provide an explanation for the entire file, but there are times when we want to focus on a specific line. For instance, we may want to understand the meaning of `EXPOSE 5000`. Although it might seem like this command publishes port `5000` for incoming requests, it serves as documentation only. The application will still need to explicitly expose this port when launching the container, using a shell command such as `docker run -p 5000:5000`. When we highlight just this line and request an explanation, Copilot incorporates context from nearby lines, the filename and extension, and other signals to generate a relevant and accurate response, as shown in *Figure 7.8*:

![Figure 7.8: Copilot explanation about exposed port from the Dockerfile](img/B31534_07_8.png)

Figure 7.8: Copilot explanation about exposed port from the Dockerfile

Copilot correctly identified that the port specification indicates the port on which the application is listening. For common files such as `Dockerfile`, the plain `/explain` command usually provides a sufficient one-line explanation.

Next, we will explore how to get similar explanations in non-project files working with ChatGPT.

## Explaining non-project files with ChatGPT

When seeking an explanation for a specific line within a non-project file or the entire file itself, the best practice is to provide the full content of the file along with the line in question and the standard filename and extension. In the case of a `Dockerfile`, there is no extension (such as `.txt` or `.py`), so simply specifying `Dockerfile` is sufficient.

For instance, if we want to understand the role of an exposed port in a `Dockerfile`, we should include both the entire file contents and the specific line to get a more accurate explanation, as demonstrated in the following prompt:

```

CONTEXT: 你提供的信息：

1\. 包含{{{ DOCKERFILE }}}的 Dockerfile

2\. 文件中包含{{{ LINE }}}的行。TASK: 解释该行的目的。DOCKERFILE: {{{ ...省略以节省空间... }}}

LINE: {{{EXPOSE 5000}}}

EXPLANATION:

```py

This prompt effectively identifies the function of the line in the `Dockerfile`, as shown in *Figure 7.9*:

![Figure 7.9: Expose 5000 line explanation in ChatGPT](img/B31534_07_9.png)

Figure 7.9: Expose 5000 line explanation in ChatGPT

In general, when using ChatGPT to explain a line of code or a line from a non-project file, it is helpful to include a broader context than just the target line. For example, when explaining a method within a class, include the entire class definition. If a function uses a custom argument type, include the definition of that type as well. This leads to more precise and useful explanations. Later in the chapter, we will introduce debugging strategies for complex scenarios where a simple textual explanation does not provide sufficient insight into the purpose of a code block.

Next, we will explore how to use a similar approach when working with OpenAI API.

## Explaining non-project files with OpenAI API

Similar to ChatGPT, we can use OpenAI API to explain specific lines from non-project files. Let us revisit the `Dockerfile` example and apply a comparable system prompt:

```

SURROUND = """你提供的信息：

1\. 包含{{{ DOCKERFILE }}}的 Dockerfile

2\. 文件中包含{{{ LINE }}}的行。SINGLE_TASK = "你的任务是解释该行的目的。"

```py

Unlike earlier examples where we passed a function’s source code to OpenAI API, this time we want to send the entire `Dockerfile` content. We can do this by using Python’s built-in `open` function inside the `get_user_prompt` function:

```

def get_user_prompt(path: str, line: str) -> str: with open(path, 'r') as file:

        dockerfile_content = file.read() return f"""

DOCKERFILE: {{{{{{ {dockerfile_content} }}}}}}

LINE: {{{{{{ {line} }}}}}}

EXPLANATION:

"""

```py

We can then call OpenAI API using the following code:

```

if __name__ == "__main__":

    client: OpenAI = OpenAI()

    system_prompt = f"{SURROUND}  {SINGLE_TASK}" user_prompt = get_user_prompt( '../../ch7/Dockerfile', 'EXPOSE 5000')

    completion: ChatCompletion = client.chat.completions.create(

        model="gpt-4o-mini",

        messages=[

            {"role": "system", "content": system_prompt},

            {"role": "user", "content": user_prompt},

        ],

    ) print("Explanation:", completion.choices[0].message.content)

```py

For reference, running this script produced the expected result, identifying the line’s purpose as specifying the port to be exposed. Here is an example output:

```

说明：Dockerfile 中的 `EXPOSE 5000` 行用于通知 Docker，容器内运行的应用程序将监听端口 5000 的传入网络连接。当从该 Docker 镜像创建容器时，端口 5000 将对外公开，使用户或其他应用程序能够连接到容器中运行的应用程序提供的服务。`然而，这个命令实际上并没有发布端口`；要使端口从 Docker 环境外部可访问，用户必须在运行容器时将其显式映射到主机机器上的端口，通常使用 `docker run` 命令的 `-p` 选项。总之，`EXPOSE 5000` 是一个文档功能，表示预期的服务端口，并增强了 Docker 容器的可理解性。

```py

To conclude, both ChatGPT and OpenAI API can deliver accurate results even when using smaller models such as *GPT-4o*, if we supply the necessary context, including the filename and extension if it exists, its contents, and the specific line we want explained.

GitHub Copilot is best suited for quick, informal explanations. For more control over the prompt and instructions, ChatGPT is a better fit. When a programmatic solution is required, OpenAI API becomes the preferred choice.

Next, we will explore how to harness the power of GenAI to handle more advanced cases where a simple explanation is not enough, and interaction with the object is required for deeper understanding.

# Creating calls with example parameters

As our Python objects or non-project files become more complex, a straightforward explanation might not be enough to help us understand the code in front of us. This is especially true when the Python object is part of a class, lacks type hints in its signature, contains no docstring, and strays from best practices.

Take, for instance, the private method `_constructor_from_mgr` in the widely used pandas `DataFrame` class. This method constructs a DataFrame from a set of data blocks and their associated axes. For your reference, here is the source code, which lacks argument type hints, a docstring, or any reference to tests:

```

def _constructor_from_mgr(self, mgr, axes) -> DataFrame:

    df = DataFrame._from_mgr(mgr, axes=axes) if type(self) is DataFrame: # 这也会工作 `if self._constructor is DataFrame`, 但

        # 这个检查稍微快一点，对最常见的用例有好处。

        return df elif type(self).__name__ == "GeoDataFrame": # Shim until geopandas can override their _constructor_from_mgr

        # 因为它们对 Manager 和 DataFrame 的行为不同

        return self._constructor(mgr) # 我们假设子类的 __init__ 方法知道如何处理一个

    # pd.DataFrame 对象。

    return self._constructor(df)

```py

One issue here is the naming of the first argument. Although it is called `manager`, a name typically associated with the `_mgr` property of a DataFrame, it refers to a block of data, which is essentially the cell content without axis labels. This misleading name, combined with the absence of type hints, a docstring, or proper testing, makes the code block hard to understand for both humans and GenAI applications.

For reference, here is the explanation output from Copilot when prompting `/explain` from a PyCharm inline chat:

```

_constructor_from_mgr 方法是 DataFrame 类中的一个辅助函数。它用于从给定的 BlockManager（或 ArrayManager）及其相关轴创建一个新的 DataFrame 实例。关键点：

1. 参数：

mgr: 持有 DataFrame 实际数据的 BlockManager 或 ArrayManager。axes: 新 DataFrame 的轴（索引和列）。2. 返回值：

它返回一个新的 DataFrame 对象，该对象由提供的管理器和轴构建。示例片段：

def _constructor_from_mgr(self, mgr, axes) -> DataFrame:

    df = DataFrame._from_mgr(mgr, axes=axes)

这里，_from_mgr 是一个类方法，用于从给定管理器和轴初始化 DataFrame。此方法确保新的 DataFrame 与提供的数据结构正确对齐。

```py

This output includes all the elements we are looking for, such as arguments, the return value, and some level of data transformation. However, deciphering the explanation can be just as challenging as deciphering the code itself. We propose a better approach by debugging the code using the generated content.

## Debugging with GitHub Copilot

Copilot is built for code generation, which makes it useful for interacting with our Python code. If we take the `get_manhattan_distance` function as an example, prompting Copilot with a partial call to the function can result in a completion that includes example arguments.

We can do this by writing the function call directly:

```

get_manhattan_distance(

```py

Or, we can do it by assigning the result to a variable with a matching type hint for the function’s return value:

```

d: float = get_manhattan_distance(

```py

In both cases, Copilot is expected to generate two `DataFrame` arguments for the function. An example of this kind of completion in PyCharm is shown in *Figure 7.10*:

![Figure 7.10: Sample call completed by GitHub Copilot](img/B31534_07_10.png)

Figure 7.10: Sample call completed by GitHub Copilot

Keep in mind that if your IDE automatically inserts a closing bracket, `)`, after you type the opening one, `(`, you may need to press *Enter* to activate Copilot’s suggestion.

This generated completion can serve as an entry point for interacting with the function through the debugger. In PyCharm, we can initiate debug mode by right-clicking the filename and selecting **Debug**, as illustrated in *Figure 7.11*:

![Figure 7.11: Debug mode in PyCharm](img/B31534_07_11.png)

Figure 7.11: Debug mode in PyCharm

In VS Code, debugging is done by clicking the **play** icon in the top-right corner and selecting **Python Debugger: Debug Python File**, as shown in *Figure 7.12*:

![Figure 7.12: Running the Debugger in VS Code](img/B31534_07_12.png)

Figure 7.12: Running the Debugger in VS Code

Running the file in debug mode allows us to step through the code line by line, offering a clearer understanding of its internal workings. For example, when using PyCharm’s debugger, we can inspect the variables within the function and follow the data transformation as it happens, as seen in *Figure 7.13*:

![Figure 7.13: Debug mode in PyCharm showing internal function arguments](img/B31534_07_13.png)

Figure 7.13: Debug mode in PyCharm showing internal function arguments

This gives us visibility into the intermediate values within `get_manhattan_distance`.

The authors frequently rely on debugging to interact with the code they read and write. This hands-on approach supports faster development of intended functionality and offers deeper insights into complex code logic. This far exceeds reading source code, using GenAI explanations, or consulting docstrings.

Next, we will explore how generating sample calls can help us better understand complex code blocks, such as the `_constructor_from_mgr` method in the pandas `DataFrame` class.

### Debugging dependency code

Just like with the `get_manhattan_distance` case, we can use Copilot to help generate sample code for debugging the `_constructor_from_mgr` method. Since this is a class method, we will split our prompt into two parts. The first prompt generates a sample instance of the class, and the second invokes the method.

We will begin by asking Copilot to complete a `DataFrame` instance. A sample prompt may look like this:

```

coordinates_a : pd.DataFrame =

```py

This prompt offers sufficient context for Copilot to suggest an assignment. As shown in *Figure 7.14*, Copilot begins by proposing an initial completion for a `pd.DataFrame`.

![Figure 7.14: Initial completion in PyCharm](img/B31534_07_14.png)

Figure 7.14: Initial completion in PyCharm

When we accept the suggestion, Copilot typically proposes sample data that fits the DataFrame’s name, as illustrated in *Figure 7.15*:

![Figure 7.15: Chained completion in PyCharm](img/B31534_07_15.png)

Figure 7.15: Chained completion in PyCharm

At this point, we can either trigger additional columns by accepting chained suggestions or type `}` to flag to Copilot that we do not want any additional columns. We then move on to the method call with the following prompt:

```

coordinates_a._constructor_from_mgr(

```py

Note that your IDE may automatically complete the closing bracket, `)`. In that case, press *Enter* between the brackets to let Copilot generate a completion suggestion.

For example, in *Figure 7.16*, Copilot proposes using the `coordinates_a._mgr` and `coordinates_a.axes` properties as the calling parameters.

![Figure 7.16: Parameter completion](img/B31534_07_16.png)

Figure 7.16: Parameter completion

With the two proposed parameters, we can debug the method as shown in *Figure 7.17* and gain a better understanding of its behavior.

![Figure 7.17: Debugging _constructor_from_mgr using Copilot’s suggestion](img/B31534_07_17.png)

Figure 7.17: Debugging _constructor_from_mgr using Copilot’s suggestion

To conclude, Copilot can supercharge the process of debugging sections of the code base, allowing us to better understand both simple and complex implementations. We rely heavily on debugging as a daily practice to deepen their understanding of the code they interact with.

Next, we will explore how ChatGPT and OpenAI API offer distinct characteristics that we can utilize.

## Customizing call parameters with ChatGPT and OpenAI

GitHub Copilot is generally better suited for quickly generating debugging calls to trigger Python objects, as it can access relevant context, such as the class code, when we are working with a method. For cases where we want specific characteristics of the sample parameters, prompting ChatGPT and OpenAI may be more suitable.

For example, to generate suitable arguments for debugging the `get_manhattan_distance` function, we might want five rows and three columns, and can use the following prompt:

```

环境：你提供的是：

1. 一个用 {{{ FUNCTION }}} 封闭的 Python 函数

2. 参数要求用 {{ REQUIREMENTS }} 封闭。任务：调用函数并传递数据要求

函数：{{{ ... 省略以节省空间 ... }}}

要求：{{{

1. 5 行

2. 3 列

3. 单元格中的浮点数和整数

}}}

CALL:

```py

For reference, the output is shown in *Figure 7.18*:

![Figure 7.18: Call parameters for get_manhattan_distance](img/B31534_07_18.png)

Figure 7.18: Call parameters for get_manhattan_distance

In this example, both DataFrames, `df1` and `df2`, have the same shape of five rows and three columns, which makes them appropriate arguments for the function call.

The OpenAI API call is similar, and you can find the full script at `ch7/prompts/openai_debug.py` for later reference.

To conclude, we turn to ChatGPT and OpenAI API when our data requirements are beyond trivial for a quick completion that Copilot might otherwise handle well. Later in the book, we will explore how to build on these data generation methods to create a robust test suite.

### Debugging dependency code

When using ChatGPT or OpenAI API to generate test code for a dependency package, it is important to provide enough context for the model to produce a desirable call. The amount of context required depends on how widely the library is used. For standard packages such as *pandas*, including just the relevant method may be enough. For custom or private repository classes, it is usually best to include the entire class definition.

For example, the `DataFrame` class in pandas is about 12,000 lines long, which is too much to include in a prompt. However, because pandas is highly popular, we can provide only the `_constructor_from_mgr` method and still receive a relevant response.

Below is a sample prompt used with ChatGPT to generate a call to the `_constructor_from_mgr` method:

```

CONTEXT: 给定 Pandas DataFrame 2.2.3 类，你将获得以下内容：

1. 调用包含在{{{ FUNCTION }}}中的 Pandas DataFrame 方法

2. 包含在{{ REQUIREMENTS }}}中的参数要求。任务：生成一个符合数据要求的示例方法调用。FUNCTION: {{{ ... 省略以节省空间 ... }}}

REQUIREMENTS: {{{

1. 5 行

2. 3 列

3. 单元格中的浮点数和整数

}}}

CALL:

```py

*Figure 7.19* shows an example output from *GPT-4o* in response to this prompt.

![Figure 7.19: Sample test call to _constructor_from_mgr](img/B31534_07_19.png)

Figure 7.19: Sample test call to _constructor_from_mgr

Here, ChatGPT successfully generated a method call using `df._mgr` and `df.axes`, producing a DataFrame with the required dimensions.

Since OpenAI API follows a similar pattern, we have provided the full script in `ch7/prompts/openai_debug_pandas.py` for reference.

In later chapters, we will build on this approach to supercharge the generation of robust test suites.

## Putting it all together

Now that we have reviewed different approaches to shorter objects, explored tailored explanations for Python objects and non-project files, considered programmatic concerns, and looked at scenarios where a textual explanation is not sufficient, we can summarize everything in a pros and cons table for each of the tools:

| **GenAI app** | **Pros** | **Cons** |
| **GitHub Copilot** | Provides quick responses with relevant context. It supports the use of `/explain` as is and allows us to add additional requirements. | Does not support tailored explanations, such as when we need to include edge cases for `get_manhattan_distance`. |
| **ChatGPT** | Enables tailored explanations and gives us flexibility to add or remove context. | Requires more effort to craft prompts. |
| **OpenAI API** | Suitable for programmatic solutions and automation. | Significantly more effort compared to GitHub Copilot and ChatGPT. |

In our own work, we typically begin with Copilot when we need an explanation. As our requirements expand, we move to Copilot’s chat window, ChatGPT, or OpenAI API. When dealing with more complex objects, we always recommend incorporating debugging into the reading process to better understand the code.

# Summary

In this chapter, we expanded our focus beyond `.py` files and explored how GenAI can help us understand entire code bases. Using GitHub Copilot, we applied the `/explain` command in its plain form as well as with more tailored instructions to grasp the role of the `get_manhatt``a``n_distance` function. We also applied this command to understand non-project files such as `requirements.txt` and `Dockerfile`.

Next, we used ChatGPT to craft prompts that offered useful explanations about edge cases and argument types. We then moved on to OpenAI API to generate a script that programmatically provided multiple explanations with one call.

We concluded by generating sample values that are useful for interacting with our code through the debugger. This approach is especially helpful when dealing with more complex implementations.

In the next chapter, we will dive into prompt engineering techniques to improve the quality of our generated code. Through **few-shot learning**, also known as **in-context learning**, we will guide Copilot, ChatGPT, and OpenAI API to follow a specific style guide aligned with our production standards. We will also explore additional techniques to shape prompts for better outcomes.

# Quiz time

Before you proceed to the next chapter, make sure that you can confidently answer the following questions:

**Question 1**: How can we address explanations of complex Python objects?

**Answer**: In cases where the object is relatively simple, we can utilize the GitHub Copilot `/explain` slash command to help us better grasp the arguments, data transformation, and return values. For more complex objects, we can use debugging by generating calls to the object with GitHub Copilot, ChatGPT, and OpenAI API.

**Question 2**: When asking ChatGPT to explain a single line in a Dockerfile, what context should be added?

**Answer**: It is recommended to include the full contents of the Dockerfile along with the filename and extension, and the specific line in question. This gives ChatGPT the context needed for a more accurate explanation.

# Further reading

To learn more about the topics that were covered in this chapter, look at the following resources:

*   Dockerfile, Wikipedia: [`realpython.com/primer-on-python-decorators/`](https://realpython.com/primer-on-python-decorators/)
*   PyCharm debugging: [`www.jetbrains.com/help/pycharm/part-1-debugging-python-code.html#step`](https://www.jetbrains.com/help/pycharm/part-1-debugging-python-code.html#step)
*   VS Code debugging: [`code.visualstudio.com/docs/python/debugging`](https://code.visualstudio.com/docs/python/debugging)

|  
#### Unlock this book’s exclusive benefits now

Scan this QR code or go to [packtpub.com/unlock](http://packtpub.com/unlock), then search for this book by name. | ![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png) |
| *Note: Keep your purchase invoice ready before you start.* |

# 8

# An Introduction to Prompt Engineering

In this chapter, we will introduce the practice of **prompt engineering**, a field of study that started in 2020, which offers advanced techniques for refining prompts to achieve more reliable, predictable, and desirable outcomes in **large language model** (**LLM**)-based applications.

We will focus on an effective prompt engineering technique for code generation with GenAI: few-shot learning, also known as in-context learning. This approach, when used in the context of code-related tasks, guides the model toward producing outputs that align with a specific coding style or objective.

We will focus on how the few-shot learning technique can enhance the model’s output for more accurate and style-consistent code generation. While there are many different uses of few-shot learning in code-related tasks, the focus on style is a useful example for maintaining consistency in a repository. This includes enforcing type hints, adding docstrings, or following a specific logging convention. By aligning the generated code with the required style guide, we can reduce the need for manual customization and accept the GenAI output as-is.

In this chapter, we will cover the following topics:

*   Utilizing prompt engineering for coding
*   Enhancing prompts with few-shot examples
*   Leveraging few-shot learning with ChatGPT
*   Working with few-shot learning for OpenAI API
*   Crafting a style guide for GitHub Copilot
*   Introducing more prompt engineering techniques

# Technical requirements

To get the most out of this chapter, ensure you have the following:

*   GitHub Copilot account
*   IDE – either VS Code or PyCharm
*   OpenAI account with access to OpenAI API
*   Access to the book’s repository, which includes the prompt samples and style guides featured in this chapter, available at [`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)
*   Virtual environment set up in VS Code or PyCharm
*   OpenAI API token

For assistance setting up a GitHub Copilot account, refer to *Chapter 3*. For instructions on setting up OpenAI API access and token generation, see *Chapter 2*. If you need help creating an OpenAI account or setting up a virtual environment in your IDE, refer to the *Appendix* for detailed guidance.

# Utilizing prompt engineering for coding

In *Chapter 4*, we explored the three pillars of achieving quality output: **model mastery**, **evaluation metrics**, and **precise prompts**. We also discussed how following the five S’s best practices for prompts (structured, surrounded, single-tasked, specific, and short) can significantly enhance the quality of model output. Using OpenAI’s example of an effective prompt, we demonstrated how aligning with these principles, such as focusing exclusively on error fixes and providing a clear list of issues to address, could improve results.

As tasks grow more complex, advanced techniques are essential to guide models toward achieving desired outcomes. LLMs may need additional instructions to adhere to a specific style guide, pass a unit test suite, or fix reproducibility issues.

Since the advent of LLMs in 2020, prompt engineering has developed into a practice that refines and structures prompts to achieve better results and address more complex scenarios. There are now many strategies that guide the model toward more desirable outcomes, including the following:

*   Structuring prompts in a way that aligns with LLM capabilities
*   Providing additional context to clarify the problem
*   Including specific guidelines for the desired output
*   Guiding the model through a reasoning process
*   Defining constraints and boundaries for the expected output
*   Providing external feedback to iteratively refine results

In coding-related tasks, prompt engineering is valuable for a variety of applications including creating style guides for code refactoring, breaking down complex challenges into manageable steps, and generating production-standard code. We will explore in depth a range of prompt engineering techniques designed to supercharge various stages of the **software development life cycle** (**SDLC**) throughout this book.

Next, we will take an in-depth look at the few-shot learning technique, which incorporates specific guidelines for desired outputs, and examine its impact on shaping the coding style of the model’s suggestions. Later in the chapter, we will preview other prompt engineering techniques that will be explored in detail in later chapters.

# Enhancing prompts with few-shot examples

**Few-shot learning**, also known as **in-context learning**, is a prompt engineering technique where we include a few examples of desirable outputs directly within the prompt. This method can be extended to incorporate examples of incorrect output or edge cases, enabling the model to differentiate between what constitutes a good result and what does not. By analyzing these patterns, the model can infer how to structure an optimal response for the given task.

To delve deeper into the research behind this approach, refer to *Language Models are Few-Shot Learners* by Brown et al. ([`arxiv.org/abs/2005.14165v4`](https://arxiv.org/abs/2005.14165v4)).

Few-shot learning research demonstrates how, with a few examples (or **shots**) of input-output pairs, a model can infer patterns from the relationships between these examples and complete tasks in a style consistent with the provided samples. For instance, the following prompt, taken from the study, illustrates the predictability and consistency of an LLM when solving arithmetic problems. Utilizing few-shot prompting increases the predictability of the output, as the model is likely to generate responses that align with the style of the provided few-shot examples as shown here:

```

指示：解决以下算术问题。示例：

问题：5 加 3 等于多少？答案：8

问题：12 减去 4 等于多少？答案：8

问题：7 乘以 6 等于多少？答案：42

问题：15 除以 3 等于多少？答案：

```py

The model’s output was as follows:

```

5

```py

Compared to prompts that only specify the task (`Solve the following arithmetic problem`), this example-based approach reduces ambiguity. The model aligns its output more closely to the expected structure, providing only the number as the answer, without additional explanation or formatting inconsistencies.

Few-shot prompting is a useful technique for a variety of coding-related tasks, such as code refactoring, code analysis, and code generation. By including specific examples in the prompt, we can guide the model to produce outputs that align with our desired patterns.

## Few-shot learning for code refactoring

In a code refactoring scenario, we may want to transform `print` statements into structured `logger` messages, a common practice for maintaining production-level software. Replacing the variety of `print` statements across many files is both error-prone and tedious. However, we can use an LLM with a prompt with clear instructions and a few examples. For example, we can enrich a request to refactor the following `print` message:

```

print('错误！找不到文件：passwords.txt')

```py

We can refactor it to a log message, with a few examples:

```

Old: print('以 verbose=True 开始处理 config.txt')

修改后：logger.info('Processing started', extra={'stage': 'start', file: 'config.txt'})

Old: print('警告！无法从 user_info.csv 加载用户数据')

修改后：logger.warning('User data failed to load', extra={'module': 'user_loader', 'status': 'failure', file: 'user_info.csv'})

Old: print('错误！找不到文件：passwords.txt')

修改后：

```py

![](img/3.png)**Quick tip**: Enhance your coding experience with the **AI Code Explainer** and **Quick Copy** features. Open this book in the next-gen Packt Reader. Click the **Copy** button

(**1**) to quickly copy code into your coding environment, or click the **Explain** button

(**2**) to get the AI assistant to explain a block of code to you.

![A white background with a black text  AI-generated content may be incorrect.](img/image_%282%29.png)

**![](img/4.png)** **The next-gen Packt Reader** is included for free with the purchase of this book. Scan the QR code OR visit packtpub.com/unlock, then use the search bar to find this book by name. Double-check the edition shown to make sure you get the right one.

![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png)

The examples in this prompt highlight the distinctions between different logging levels with examples of transforming `print` messages into `info` and `warning` logging messages. The examples also demonstrate static log messages with additional information provided through the `extra` parameter.

Next, we will see how enhancing our prompt with few-shot examples improves the output we get from ChatGPT.

# Leveraging few-shot prompting with ChatGPT

When using ChatGPT, if applying the **five S’s framework** from *Chapter 4* does not produce the desired results, we can enhance our prompts with a few-shot approach. In this case, we will still follow the five S’s framework but incorporate **indexed variables** that represent a series of inputs and outputs for the task.

## Few-shot structure

A typical approach to implement few-shot prompting in ChatGPT is by extending the five S’s framework to include indexed variables such as `{{{ Input_i }}}` and `{{{ Output_i }}}`. This implies that the context references these variables, for example:

```

CONTEXT: 你将获得以下内容：

1. 包含在{{{ OLD }}}中的 Python 代码片段

2. 包含在{{{ OLD_i }}}中的示例，随后是包含在{{{ REFACTORED_i }}}中的期望输出

```py

We then supply the `OLD_i` and `REFACTORED_i` examples, followed by `{{{ OLD }}}`, as such:

```

`OLD_1: {{{ }}}`

`REFACTORED_1: {{{ }}}`

`OLD_2: {{{ }}}`

`REFACTORED_2: {{{ }}}`

`...`

`OLD: {{{ }}}`

```py

Overall, a ChatGPT prompt that uses few-shot examples can be structured in this way:

```

CONTEXT: 你将获得以下内容：

1. ... 2. 包含在{{{ Input_i }}}中的示例，随后是包含在{{{ Output_i }}}中的期望输出

任务：... Input_1: {{{ ... }}}

Output_1: {{{ ... }}}

Input_2: {{{ ... }}}

Output_2: {{{ ... }}}

... 输入：{{{ }}}

CUE:

```py

The labels for inputs and outputs should reflect their relationship and remain consistent across examples. For example, when solving arithmetic problems, `question` and `answer` are appropriate labels. When transforming `print` statements to log messages or performing other refactoring tasks, `old` and `refactored` make more sense.

## Improvement in output with code refactoring

Let us examine a case where we want to refactor `print` statements into structured logging. This involves using appropriate logging levels, enforcing static messages, and including extra parameters.

To observe the default behavior without applying a few-shot approach, we can navigate to [`chatgpt.com/`](https://chatgpt.com/), start a new conversation with the *GPT-o3-mini-high* model, and prompt it to refactor a `print` statement into a log message using the following:

```

CONTEXT: 你将获得一个包含在{{{ OLD }}}中的 Python 代码片段。任务：将代码片段重构为日志消息。OLD: {{{ print('错误！找不到文件：passwords.txt') }}}

REFACTORED:

```py

The *GPT-o3-mini-high* model excels at coding tasks and is likely to generate a log message with an `error` level. However, without explicit instructions on structuring the log message, it may not use a logger instance nor distinguish the static log message from additional details such as the filename, as shown in *Figure 8.1*:

![Figure 8.1: Working with Canvas in ChatGPT](img/B31534_08_01.jpg)

Figure 8.1: Working with Canvas in ChatGPT

We can improve the model’s output by providing few-shot examples demonstrating how to extract key details from a `print` statement and use a logger instance. For example, we can refactor a `print` message to include a filename and verbosity setting:

```

print('以 verbose=True 开始处理 config.txt')

```py

We can refactor it into a structured log message:

```

logger.info('Processing started', extra={'verbose': True, file: 'config.txt'})

```py

This example highlights the extraction of essential details to improve logging clarity. Similarly, we can add another example with `print` statements containing user and file path information:

```

print('警告！无法从 user_info.csv 加载用户 U-232 数据')

```py

We can refactor it into the following structured log message:

```

logger.warning('用户数据加载失败', extra={'user': 'U-232', 'file': 'user_info.csv'})

```py

A complete prompt with these few-shot examples might be structured as follows:

```

CONTEXT: 你将获得以下内容：

1. 包含在{{{ OLD }}}中的 Python 代码片段

2. 包含在{{{ OLD_i }}}中的示例，随后是包含在{{{ REFACTORED_i }}}中的期望输出

任务：将代码片段重构为日志消息。OLD_1: {{{ print('以 verbose=True 开始处理 config.txt') }}}

REFACTORED_1: {{{ logger.info('Processing started', extra={'verbose': True, file: 'config.txt'}) }}}

OLD_2: {{{ print('警告！无法从 user_info.csv 加载用户 U-232 数据') }}}

REFACTORED_2: {{{ logger.warning('User data failed to load', extra={'user': 'U-232', 'file': 'user_info.csv'}) }}}

OLD: {{{ print('错误！找不到文件：passwords.txt') }}}

REFACTORED:

```py

Providing these two examples as guidance for the model will capture the desired output, as illustrated in *Figure 8.2*:

![Figure 8.2: Improved logging suggestion](img/B31534_08_02.jpg)

Figure 8.2: Improved logging suggestion

This time, the model successfully extracted the parameters from the static log message and used the logger instance instead of a direct logging message, following the patterns demonstrated in the few-shot examples. We will revisit logging practices in greater detail in *Chapter 15*, so stay tuned.

Next, we will explore how adopting a Python-formatted **style guide** with Copilot can go beyond traditional linting and code formatting tools. This few-shot approach is proactive, adaptable, and context-aware, enabling Copilot to predict our intended implementation easily.

# Crafting a style guide for GitHub Copilot

GitHub Copilot functions as a personalized AI assistant, predicting our next coding moves. Because LLMs excel at imitating style, Copilot quickly adapts to any style preferences it observes during a session.

For example, suppose we have a file named `ch8/code_samples/math_calculations.py` with two functions (`get_area` and `get_arithmetic_mean`), both implemented without type hints and with single-line function signatures:

```

import numpy as np def get_area(radius):

return np.pi * radius ** 2

def get_arithmetic_mean(x1, x2):

return (x1 + x2) / 2

```py

If we then start typing a new function signature for `get_euclidean_distance`, Copilot is likely to generate an implementation in the same style, with no type hints and one-line signatures, as shown in *Figure 8.3*:

![Figure 8.3: Copilot preserving our coding style](img/B31534_08_03.jpg)

Figure 8.3: Copilot preserving our coding style

Alternatively, if our code implements type hints, hanging indents, and docstrings, Copilot will generate suggestions that reflect this updated style. For example, here is an alternate implementation of `get_area` and `get_arithmetic_mean`:

```

系统提示 = f"{包围} {SINGLE_TASK}"

半径: float,

) -> float: """

计算给定半径的圆的面积。

""" 面积: float = np.pi * 半径 ** 2

    返回面积 def get_arithmetic_mean(

x1: float,

x2: float,

) -> float: """

计算两个数的算术平均值。

""" 算术平均值: float = (x1 + x2) / 2

    返回算术平均值

```py

Based on this coding preference, *Figure 8.4* shows the suggested implementation of `get_euclidean_distance` reflecting the new coding style:

![Figure 8.4: Copilot’s adapted coding style](img/B31534_08_04.jpg)

Figure 8.4: Copilot’s adapted coding style

As developers, we would like a more robust method for informing Copilot of our preferred style guidelines without having to repeat them every session. We can achieve this by using a few-shot learning approach: creating a dedicated style guide file, as we will see next.

## Style guide file

A simple way to include our preferred style guide in Copilot is to maintain a single file outside the main project folder that we can copy and paste in place when we start a new Copilot session. Copying and pasting this file’s content makes our coding style part of the active session, although we hope that future versions of Copilot will introduce a more convenient method. For example, a sample file located at `ch8/code_samples/style_guide.py`, shown in *Figure 8.5*, includes two functions: `get_area` and `get_arithmetic_mean`.

![Figure 8.5: Style guide](img/B31534_08_05.jpg)

Figure 8.5: Style guide

This file does not include a docstring, as adding one is considered a separate task from implementing the function. We will explore this topic in more detail in later chapters.

Next, if we open a new file at `ch8/code_samples/distances.py` and begin typing the signature of `get_euclidean_distance`, Copilot is likely to generate an implementation that aligns with that formatting, as shown in *Figure 8.6*:

![Figure 8.6: Preserved coding style](img/B31534_08_06.jpg)

Figure 8.6: Preserved coding style

Our coding preferences remain consistent in the new file, showing that Copilot has effectively captured our desired style. In later chapters, we will explore how adding more Python elements, such as decorators, to the style guide can further refine and expand our preferred coding approach.

Style guide as a next-generation code formatter

If you are used to code formatters or linters, you will notice that implementing a style guide may remind you of a code formatting initiative, but is more advanced. First, because the style guide approach is proactive rather than reactive, we get suggestions already formatted the way we want. Second, it offers more flexibility: we can adopt the *show, don’t tell* method by simply demonstrating our preferred style to Copilot. Finally, we can go beyond traditional formatters by including preferences such as type hints, which are not always clear using older methods.

Next, we will explore how to apply few-shot learning with OpenAI, using this technique to refactor code at scale.

# Working with few-shot learning for OpenAI API

For large-scale tasks, such as generating code implementations from function signatures, we can use OpenAI API programmatically and apply few-shot learning to illustrate the desired outcome effectively. To do this, we provide indexed examples of input and output and reference these examples in the system prompt.

The system prompt should reference the indexed input and output examples as follows:

```

def print_fibonacci_sequence(n: int) -> None:

单个任务 = "你的任务是 [...]。"

```py

Next, we update the `get_user_prompt` function to include the provided examples, ensuring that the labels align with those in the system prompt:

```

def get_user_prompt(some_input: str, few_shots: list) -> str:

    提示 = ""

    for i, (input_, output_) in enumerate(few_shots):

        提示 += f"""

    输入 _{i + 1}:  {{{{{{ {input_} }}}}}}

    输出 _{i + 1}:       {{{{{{ {output_} }}}}}}"""

    导入 numpy as np def get_area(

    输入:          {{{{{{ {some_input} }}}}}}

    输出:

    """

    return prompt

```py

Similarly, we replace `INPUT_i` and `OUTPUT_i` with task-specific labels, such as `FUNCTION_i` and `CODE_i` for code completion tasks.

## Implementing code with OpenAI API

In *Chapter 2*, we built a code completion program that generates a Python implementation based on a function signature. For example, when implementing `print_fibonacci_sequence`, we provided a prompt that requested only the function’s implementation, without additional explanations or output samples.

A more effective approach is to include a few examples that demonstrate the desired output format. For instance, we can provide implementations for `get_area` and `get_arithmetic_mean`, both based solely on their function signatures:

```

completion: openai.ChatCompletion = (

输出 _1 = """def get_area(radius: float) -> float:"""

    面积: float = np.pi * 半径 ** 2

    return area"""

输入 _2 = """def get_arithmetic_mean(x1: float, x2: float) -> float:"""

输出 _2 = """def get_arithmetic_mean(x1: float, x2: float) -> float:

    算术平均值: float = (x1 + x2) / 2

    FEW_SHOTS = [

函数:          {{{{{{ {signature} }}}}}}

    (输入 _1, 输出 _1),

    (输入 _2, 输出 _2),

]

```py

With these examples, we can construct a system prompt and user prompt that encourage the model to generate only the function implementation without additional explanations. The system prompt would be structured as follows:

```

包围 = """你将获得：

系统提示 = f"{包围} {SINGLE_TASK}"

单个任务 = "你的任务是实现该函数。"

```py

Next, we define a function to generate the user prompt, ensuring consistency with the system prompt’s structure:

```

def get_user_prompt(signature: str, few_shots: list) -> str:

    1. 一个 Python 函数签名包含在 {{{ 函数 }}} 中。2. 示例签名包含在 {{{ 函数 _i }}} 后面，然后是相应的实现包含在 {{{ 代码 _i }}} 中。"""

    for i, (input_, output_) in enumerate(few_shots):

        提示 += f"""

    函数 _{i + 1}:  {{{{{{ {input_} }}}}}}

    代码 _{i + 1}:       {{{{{{ {output_} }}}}}}"""

    提示 += f"""

    a, b = b, a + b print() # To add a newline after printing the sequence

    输入 _1 = """def get_area(radius: float) -> float:"""

    """

    return prompt

```py

For the implementation of `print_fibonacci_sequence`, we define the system and user prompts as follows:

```

return 算术平均值"""

用户提示 = get_user_prompt("def print_fibonacci_sequence(n: int) -> None:", FEW_SHOTS)

```py

Finally, we call the API with the following snippet:

```

客户端: OpenAI = OpenAI()

3. 变量赋值的逻辑作用域

    client.chat.completions.create(

        模型="gpt-4o-mini",

        消息=[

            {"role": "system", "content": system_prompt},

            {"role": "user", "content": user_prompt},

        ],

    )) print(completion.choices[0].message.content)

```py

By structuring the prompt this way, the model is more likely to follow the expected output format. Running the preceding example, which is available in `ch8/code_samples/openai_fibonacci.py`, we got the following function implementation:

```

提示 = ""

    a, b = 0, 1

    for _ in range(n): print(a, end=' ')

        1. 一个 [...] 包含在 {{{ 输入 }}} 中。2. 示例 [...] 包含在 {{{ 输入 _i }}} 后面，然后是相应的 [...] 包含在 {{{ 输出 _i }}} 中。"""

```py

This implementation aligns with our provided examples and does not include surrounding explanations.

Fine-tuning as a better approach to OpenAI API

When scaling projects, **fine-tuning** offers a more effective way to specialize a model for a specific task, such as generating code in a preferred style. This process involves training a pre-trained model such as *GPT-4o-mini* on a set of high-quality examples, allowing it to adjust its internal settings to better align with our preferences. We will explore this topic in greater detail in *Chapter 11*.

Having explored few-shot learning with ChatGPT, GitHub Copilot, and OpenAI API, we will now introduce additional prompt engineering techniques, which we will examine in greater detail in the upcoming and later chapters of the book.

# Introducing more prompt engineering techniques

Variations of few-shot prompting can include edge cases, progressively complex examples, or contrastive examples that highlight both correct and incorrect outcomes. These variations on few-shot prompting enhance a model’s ability to generalize across diverse task requirements. The examples in this chapter on type hinting and style formatting are just the tip of the iceberg of how prompt engineering can be used.

In other scenarios of the SDLC, we will see how using different prompt engineering techniques can become handy.

## Bug fix at scale with prompt engineering

Refer to the OpenAI example of effective prompts for fixing buggy code, enhanced with the refinements discussed in *Chapter 4*:

```

上下文: 你将在 Python 编辑器中提供 Python 代码，描述包含在 {{{ 描述 }}} 中

可能包含错误，包含在 {{{ 错误 }}} 中。任务：修复代码中的错误。描述：{{{ 执行 10 次乘法测验并验证答案 }}}}

错误: {{{

1. 编译

2. 随机数生成的可重复性

提示 += f"""

4. 输入类型转换的错误处理

}}}

```py

While this prompt successfully identified all errors in the code, we cannot guarantee that GenAI applications will consistently capture all errors in different code snippets.

To improve results, we can explore techniques such as iterative prompting, where the output is verified for compilation and refined through model reiteration if needed. Template-based prompting can enforce a specific format for error descriptions, ensuring consistency and clarity in the output. Additionally, chain-of-thought prompting helps guide the model through a logical reasoning process, improving its ability to understand and fix code issues. Let’s explore these in the next subsections.

## Iterative prompting

**Iterative prompting** involves engaging the model repeatedly within a feedback loop that refines its output based on evaluations of previous responses. This feedback can be manual, such as asking ChatGPT to revise its response to address unidentified errors, or automated, such as compiling code generated by OpenAI API or running it against a suite of unit tests. The resulting feedback, whether a traceback error message or failed test results, can be reintroduced to the model, continuing the cycle until specific criteria are satisfied.

For instance, if the goal is to address compilation issues, an iterative mechanism could involve attempting to compile the output and feeding the traceback error messages back to the model for refinement if the code fails to compile:

```

for i in range(10): try: exec(user_code) print(f"成功编译:\n {user_code}") break

    except SyntaxError as se:

        user_code = get_refined_output(user_code, traceback.format_exc())

```py

Here, we will repeatedly prompt the model with traceback messages from the suggested code until it successfully compiles. Alternatively, we could evaluate the code by running it against a test suite or using other evaluation mechanisms, which we will explore in later chapters of the book.

## Template-based prompting

**Template-based** prompting involves providing specific guidelines for structuring the desired output. For instance, when fixing code, we may want to understand the type of error being addressed, such as whether it is a compilation error, a logical issue, or something else. In such cases, the output could follow this structure:

```

这段代码因为 { ERROR TYPE} 需要修复。修复后的代码是 { CODE }。

```py

To guide the model toward generating this output, we include hints about the template within the context and provide a structure like this:

```

CONTEXT: 您将获得一个包含在 {{{ CODE }}} 中的 Python 代码，该代码无法编译，以及一个包含在 {{{ TRACEBACK }}} 中的错误跟踪信息，以及一个包含在 {{{ TEMPLATE }}} 中的输出模板。TASK: 使用提供的模板修复代码中的错误。TEMPLATE: 这段代码因为 { ERROR TYPE } 需要修复。修复后的代码是 { CODE }。

```py

Here, we guide the model by providing a specific template that includes placeholders for the error type and the fixed code. This approach differs from few-shot prompting in how the output is constructed; rather than offering input-output examples, we define the structure of the output with variables for the model to populate. These two techniques can be used independently or in combination to achieve the desired results.

## Chain-of-thought prompting

**Chain-of-thought** (**CoT**) prompting involves guiding the model through a step-by-step reasoning process toward a final answer. In coding, we apply CoT by referencing functions that are yet to be implemented, serving as a reasoning framework for the GenAI tool, which later fills in the implementation details. For instance, when validating that a code has no bugs, the process may involve the following steps:

1.  Validating syntax
2.  Checking compilation
3.  Ensuring reproducibility across runs

Using CoT, we can explicitly reference functions that handle each of these steps while leaving the actual implementation for GenAI to complete. In code, this might look like this:

```

def validate_no_bugs_in_source_code(sc: str) -> None:

    validate_syntax(sc)

    validate_compilation(sc)

    validate_reoroducibility_across_runs(sc)

```py

Here, `validate_no_bugs_in_source_code` outlines the logical steps needed to verify that the source code is bug-free but does not contain implementation details. GenAI tools are particularly effective at generating low-level implementations, and when typing the first referenced function, `validate_syntax`, Copilot can generate a suitable implementation, as illustrated in *Figure 8.7*:

![Figure 8.7: GitHub Copilot suggested implementation of validate_syntax](img/B31534_08_07.jpg)

Figure 8.7: GitHub Copilot suggested implementation of validate_syntax

CoT is one of the most effective prompt engineering techniques for coding tasks, and we will explore its applications further in the upcoming chapters.

## Exploring additional methods

This book covers a selection of prompt engineering techniques among the many available. For a broader exploration of prompting strategies, *Unlocking the Secrets of Prompt Engineering: Master the art of creative language generation to accelerate your journey from novice to pro* by Packt delves into numerous other techniques applicable to diverse use cases.

# Summary

In this chapter, we introduced few-shot learning as a prompt engineering technique to guide LLMs toward more predictable and desired outcomes. We demonstrated its application in scenarios such as implementing a specific logging structure and following a particular coding style.

We explored how to implement few-shot prompting across different GenAI applications. In ChatGPT and OpenAI API, we utilized specific keyword combinations such as `question` and `answer` or `old` and `refactored` to structure the few-shot examples. With GitHub Copilot, we leveraged a style guide file to influence code completion output.

We also introduced additional prompt engineering techniques that are valuable for scaling bug fixes. Iterative prompting enables models to refine their output by utilizing feedback from compilation checks until the code compiles successfully. Template-based prompting leads the model toward producing outputs with a specific structure. Furthermore, CoT prompting breaks down solutions into clear, step-by-step reasoning processes.

In the next chapters, we will delve deeper into the mechanics of CoT, and chaining, and see how to apply them with ChatGPT, OpenAI API, and GitHub Copilot.

# Quiz time

Before you proceed to the next chapter, make sure that you can confidently answer the following questions:

**Question 1**: When should we use prompt engineering?

**Answer**: Prompt engineering should follow best practices to achieve desirable outcomes from LLMs. However, when standard guidelines are insufficient, advanced prompting techniques may be necessary. In this chapter, we saw how few-shot learning helped align outputs with a specific style guide, making results more predictable and desirable.

**Question 2**: Can we use plain English to describe the desired outcome instead of providing few-shot examples in code?

**Answer**: While it is theoretically possible to use plain English to describe coding styles and desired outputs, this approach is less effective. Like mathematical equations or music notes, code acts as a concise and precise notation system. LLMs, trained extensively on code, interpret it more accurately than plain-text descriptions.

# Further reading

To learn more about the topics that were covered in this chapter, take a look at the following resources:

*   *PEP-8 Style Guide for Python Code*: [`peps.python.org/pep-0008/`](https://peps.python.org/pep-0008/)
*   Brown, T. B., Mann, B., Ryder, N., Subbiah, M., Kaplan, J., Dhariwal, P., ..., and Amodei, D. (2020). *Language Models are Few-Shot Learners*. OpenAI. Retrieved from [`arxiv.org/abs/2005.14165v4`](https://arxiv.org/abs/2005.14165v4)
*   Sahoo, P., Singh, A. K., Saha, S., Jain, V., Mondal, S., and Chadha, A. (2024). *A systematic survey of prompt engineering in large language models: Techniques and applications*. Indian Institute of Technology Patna, Stanford University, and Amazon AI. Retrieved from [`arxiv.org/abs/2402.07927v1`](https://arxiv.org/abs/2402.07927v1)

# Subscribe for a free eBook

New frameworks, evolving architectures, research drops, production breakdowns—AI_Distilled filters the noise into a weekly briefing for engineers and researchers working hands-on with LLMs and GenAI systems. Subscribe now and receive a free eBook, along with weekly insights that help you stay focused and informed.

Subscribe at [`packt.link/TRO5B`](https://packt.link/TRO5B) or scan the QR code below.

![A qr code on a white background  AI-generated content may be incorrect.](img/B31534_Newsletter_NEW.png)

# 9

# Advanced Prompt Engineering for Coding-Related Tasks

Some coding tasks extend beyond simple, single-task initiatives. For these more complex scenarios, advanced prompt engineering techniques such as **chain of thought** (**CoT**) and **chaining** can be highly effective when working with **large language models** (**LLMs**). This chapter will explore how to use these techniques when working with OpenAI API, ChatGPT, and GitHub Copilot on challenges that often require more than just the initial prompt to achieve the desired output.

We will walk through an example of implementing a geometric mean calculator for portfolio returns that handles negative net returns. By applying CoT prompting, we will guide the model with explicit reasoning steps and achieve desirable results, even with a lighter model such as **GPT-4o mini**. Then, using chaining, we will improve the initial implementation by enhancing its type hints and refining the docstring.

This chapter covers the following topics:

*   Extending the prompt implementation scope
*   Leveraging CoT reasoning for code completion
*   Using prompt chaining with LLMs

# Technical requirements

To get the most out of this chapter, ensure you have the following:

*   GitHub Copilot account
*   IDE – either VS Code or PyCharm
*   OpenAI account with access to OpenAI API
*   Access to the book’s repository, available at [`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)
*   Virtual environment set up in VS Code or PyCharm
*   OpenAI API token

For assistance with setting up a GitHub Copilot account, refer to *Chapter 3*. For instructions on setting up OpenAI API access and token generation, see *Chapter 2*. If you need help creating an OpenAI account or setting up a virtual environment in your IDE, refer to the *Appendix* for detailed guidance.

# Extending the prompt implementation scope

Until now, we have mainly worked with short functions spanning only a few lines of code, applying our best practices for prompt precision to generate effective code using GitHub Copilot, OpenAI, and ChatGPT.

However, in many real-world scenarios, our tasks will not fit within such a narrow scope. We may need to handle input casting, switch cases, or adapt implementations beyond a raw mathematical formula. This chapter explores how we can extend the scope of coding tasks by applying advanced prompt engineering techniques.

## Extending the geometric mean scope

Let us revisit the geometric mean implementation from *Chapter 3*. The geometric mean is a method of averaging numbers that have a multiplicative nature, such as financial portfolio growth rates, population growth rates, or drug concentrations that change exponentially over time. The geometric mean is defined as the nth root of the product of the inputs, as follows:

![@holatex \begin{document} $$ \text{Geometric Mean} = \left( \prod_{i=1}^n x_i \right ) ^{\frac{1}{n}} $$ \end{document}](img/B31534_03_002.png)

For a more detailed explanation of the concept, refer to *Chapter 3*.

However, when some of the inputs are negative, such as net portfolio returns, the standard formula becomes insufficient. For example, consider IBM’s stock returns from 2000 to 2002, where two years had negative returns:

```

IBM_YEARLY_RETURNS: Dict[str, float] = { "2000": -0.2084, "2001": 0.4300, "2002": -0.3547 }

```py

If we were to use the geometric mean formula as is, we would get an average yearly return of 32%:

![](img/B31534_09_002.png)

This result, however, is incorrect. A $1,000 investment in IBM stock in 2000 would shrink to approximately $730 by the end of 2002, reflecting a total decline of about 27%. Thus, we would expect an average annual return closer to -10%.

One way to handle negative returns is by using gross returns instead. This involves converting net returns to gross values, computing their product, and extracting the nth root:

```

从 typing 导入 Dict

导入 numpy 作为 np def get_average_return(

net_returns: Dict[str, float], ) -> float: # 第 1 步：计算年总收益 gross_returns: np.ndarray = np.array(list(net_returns.values())) + 1

    # 第 2 步：计算总收益的几何平均数 power: float = 1 / len(gross_returns)

    gross_average: float = np.prod(gross_returns) ** power # 第 3 步：计算净平均回报 net_average: float = gross_average - 1

    return net_average

```py

Applying this function to IBM’s returns produces an average return of -10%:

```

net_returns: [-0.2084, 0.43, -0.3547]

gross_returns: [0.7916, 1.43, 0.6453]

gross_average: 0.9006

net_average: -0.099

```py

This implementation is more extensive than the functions we have generated so far, so it may require more advanced techniques to get desirable results with minimal iterations.

Next, we will compare baseline responses from GitHub Copilot, ChatGPT, and OpenAI API, examining their limitations and potential pitfalls.

## Evaluating baseline outputs

In *Chapter 6*, we discussed how GitHub Copilot, ChatGPT, and OpenAI API each have strengths in different coding-related tasks. Copilot excels at code completion but can fall short when generating larger blocks of starter code. ChatGPT is better suited for producing more extensive initial code, though it often includes longer functions with excessive comments and computations. OpenAI API requires more effort to craft effective prompts but offers greater flexibility through programmatic automation and control over prompt history. For a refresher on these differences, you can revisit *Chapter 6*.

These differences become apparent when implementing the geometric mean for portfolio returns over multiple years. Each tool requires different strategies to refine and enhance the quality of the generated output.

### GitHub Copilot baseline

To apply best practices for prompt precision with Copilot, we can start by providing the function signature for `get_geometric_mean` as follows:

```

def get_geometric_mean(

net_returns: Dict[str, float], ) -> float:

    ...

```py

This gives Copilot a clear starting point with the function name, an argument specifying the use case of net returns, and an expected return type. However, this prompt alone may not be sufficient to guide Copilot in handling negative inputs, as demonstrated in *Figure 9.1*.

![Figure 9.1: Copilot’s completion does not support negative net returns](img/B31534_09_01.png)

Figure 9.1: Copilot’s completion does not support negative net returns

This implementation would yield incorrect results for negative inputs and should not be used. Later in the chapter, we will see how CoT can help us get the correct implementation we are after.

### ChatGPT baseline

ChatGPT, on the other hand, presents a different challenge. While newer models, such as o3, excel at deeper reasoning (as discussed later in this chapter) and may produce more accurate implementations, more effort is required to prompt ChatGPT effectively than with Copilot. Additionally, achieving a coding format that aligns with our preferences is more challenging.

To replicate the GitHub Copilot implementation, we used the following prompt:

```

CONTEXT: 您将获得一个包含在 {{{ FUNCTION }}} 中的 Python 函数签名。TASK: 实现这个函数。FUNCTION: {{{ defget_geometric_mean(\n\t\tnet_returns: Dict[str, float],\n) -> float: }}}

CODE:

```py

Using the o3-mini-high model, we generated a functionally correct implementation. However, the resulting code was cluttered with excessive inline comments and docstrings, making it time-consuming to clean up. *Figure 9.2* illustrates this output in ChatGPT.

![Figure 9.2: ChatGPT implementation](img/B31534_09_02.png)

Figure 9.2: ChatGPT implementation

![](img/1.png) **Quick tip**: Need to see a high-resolution version of this image? Open this book in the next-gen Packt Reader or view it in the PDF/ePub copy.

![](img/2.png) **The next-gen Packt Reader** is included for free with the purchase of this book. Scan the QR code OR go to packtpub.com/unlock, then use the search bar to find this book by name. Double-check the edition shown to make sure you get the right one.

![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png)

For reference, the proposed code by ChatGPT is as follows:

```

导入 math 和 Dict 类型

def get_geometric_mean(net_returns: Dict[str, float]) -> float: """ [... 省略以节省空间 ...] """

    if not net_returns: return 0.0

    # 计算每个净收益的 (1 + return) 的乘积 product = math.prod(1 + r for r in net_returns.values())

    n = len(net_returns) # 计算乘积的第 n 次方根并减去 1 以获得几何平均数 geometric_mean = product ** (1 / n) - 1

    return geometric_mean

```py

This code is functionally correct but includes several undesired elements:

*   Unnecessary docstring
*   Input validation
*   Excessive comments
*   Inline computations

Later in the chapter, we will explore how CoT and chaining requests to the initial implementation can help us achieve the desired output.

### OpenAI API baseline

We used the o3-mini-2025-01-31 model via OpenAI API and found that its output closely mirrored what ChatGPT produced. To evaluate this, we ran the script located at `ch9/baseline/baseline_openai.py`, using the following system and user prompts:

```

SURROUND = "您将获得一个包含在 {{{ FUNCTION }}} 中的 Python 函数签名。" SINGLE_TASK = "您的任务是实现这个函数。" SRC_CODE = """def get_geometric_mean(\n\tnet_returns: Dict[str, float],\n) -> float:"""

def get_user_prompt(src: str) -> str:

    返回 f"""

FUNCTION: {{{{{{ {src} }}}}}}

CODE:

"""

```py

We then called the model using the following code:

```

if __name__ == '__main__':

    client: OpenAI = OpenAI()

    system_prompt = f"{SURROUND}  {SINGLE_TASK}" user_prompt = get_user_prompt(SRC_CODE)

    completion: ChatCompletion = client.chat.completions.create(

        model="o3-mini-2025-01-31",

        messages=[

            {"role": "system", "content": system_prompt},

            {"role": "user", "content": user_prompt},

        ],

    )

    output = completion.choices[0].message.content print(output)

```py

The output generated by OpenAI API was very similar to the one produced by ChatGPT, as seen in the following sample result:

```

def get_geometric_mean(net_returns: Dict[str, float]) -> float:

    # 返回 0.0 如果没有回报（也可以选择抛出异常）

    if not net_returns:

        return 0.0

    import math

    # 计算每个期间的(1 + 回报)的乘积

    product = 1.0

    n = len(net_returns)

    for r in net_returns.values():

        product *= (1 + r)

    # 计算几何平均数：乘积的 n 次方根然后减去 1

    geom_mean = math.pow(product, 1 / n) - 1

    return geom_mean

```py

In this implementation, the functionality is correct, but the formatting is less than ideal due to excessive inline comments, unnecessary input validation, and even an import statement placed inside the function. Later in the chapter, we will see how to refine this implementation using CoT and chaining to achieve desirable results even when working with lower-cost models such as GPT-4o mini.

In summary, as our implementation scope expands beyond simple and short functions, applying more advanced techniques becomes essential to achieving the desired results.

Next, we will see how we can utilize advanced prompt engineering techniques and get the implementation we want faster, and see which application (either Copilot, OpenAI API, or ChatGPT) is most suitable for each technique.

# Leveraging CoT reasoning with LLM

In *Chapter 8*, we explored how guided reasoning with CoT can help LLMs produce better code by following a step-by-step reasoning process. This step-by-step thinking encourages models to tackle problems in a structured way, leading to more accurate and desirable outputs.

As a simple exercise, consider the following sequence:

17, 34, 14, 28, 8, 16

This sequence follows two rules – first, multiply the previous number by 2 to get the next one; then subtract 20 to get the following number:

34 = 17 x 2

14 = 34 – 20

28 = 14 x 2

8 = 28 – 20

16 = 8 x 2

The next number should be -4, which is 16 - 20\. However, prompting Copilot to predict the next number in the sequence is not straightforward, as shown in *Figure 9.3*.

![Figure 9.3: Copilot fails to predict the correct next number](img/B31534_09_011.png)

Figure 9.3: Copilot fails to predict the correct next number

In this case, Copilot failed to predict the next number accurately, suggesting 4 instead of -4\. This demonstrates that the model did not fully grasp the sequence’s logic. To improve the outcome, we can guide the model by prompting it to reason through the relationship between the current number and the previous one before making a final prediction, as shown in *Figure 9.4*.

![Figure 9.4: Reasoning steps provided for the next number](img/B31534_09_04.png)

Figure 9.4: Reasoning steps provided for the next number

*Figure 9.4* shows that, by adding comments in rows 4-8, Copilot predicted the next number in the sequence correctly and also explained its reasoning for the final number, 6\. Similarly, as we will explore later in this chapter, incorporating reasoning steps into our coding tasks can help the model produce more desirable outcomes.

## CoT in the GPT-o series

CoT has proven so effective across a range of domains requiring complex reasoning that it was built into the GPT-o series. This means the model will automatically identify the necessary steps to complete a task before arriving at the final answer.

For the sequence completion example we explored earlier in the chapter, we could use the GPT-o1 model without additional guidance, as shown in *Figure 9.5*.

![Figure 9.5: Built-in CoT in o1](img/B31534_09_05.png)

Figure 9.5: Built-in CoT in o1

From the ChatGPT output, we can see that the model recognized this as a sequence pattern task, with an internal process for handling reasoning in such cases. The model took 47 seconds to process the task, which included problem analysis, problem recognition, and estimating the next number, as shown in *Figure 9.6*.

![Figure 9.6: Thought process in ChatGPT](img/B31534_09_06.png)

Figure 9.6: Thought process in ChatGPT

Here, we can see that ChatGPT is analyzing the sequence, which is one of the reasoning steps in CoT to get to the final answer.

### o-series adoption

Models from the o series are now available through ChatGPT and OpenAI API. However, they come at a higher cost than their predecessors, as illustrated in *Figure 9.7*:

![Figure 9.7: Costs of o-series models for OpenAI API calls](img/B31534_09_07.png)

Figure 9.7: Costs of o-series models for OpenAI API calls

The o1 model, for example, is priced at $15 per million input tokens and $60 per million output tokens, making it six times more expensive than GPT-4o and 1,000 times more expensive than GPT-4o mini, as shown in *Figure 9.8*.

![Figure 9.8: GPT-4o pricing for OpenAI API calls](img/B31534_09_08.png)

Figure 9.8: GPT-4o pricing for OpenAI API calls

Due to this significant cost difference, o-series models are used less frequently in applications. When selecting the right model for yourself or your company, it is important to weigh the trade-off between cost and output quality. If more affordable models, such as GPT-4o, deliver satisfactory results and meet expectations, it may be prudent to continue using them. However, the o1 and o3 models have been shown to give significantly better outcomes, so it might be worth using them first or as a fallback, even at a higher cost.

## Using CoT for GitHub Copilot

The CoT approach is one of our most frequently used strategies when working with GitHub Copilot. When applied effectively, it can simplify the development of entire code segments, leading to cleaner and more readable implementations.

This method involves structuring the reasoning process by referencing functions that have yet to be implemented. For example, when calculating the geometric mean for net returns, we can break it down into three logical steps:

1.  Convert input to gross returns.
2.  Compute the geometric mean of the gross returns.
3.  Convert back to the net returns.

Expressing these steps in code involves defining each operation as a function, as shown in the following code:

```

def get_average_return(

net_returns: Dict[str, float], ) -> float:

    gross_returns: np.ndarray = get_gross_returns(net_returns)

    gross_average: float = get_geometric_mean(gross_returns)

    net_average: float = get_net_average(gross_average) return net_average

```py

This function does not include any implementation details and only outlines the functions or steps to be completed. Since the functions are not yet implemented, typing their names in an IDE may look like an error, as shown in *Figure 9.9*:

![Figure 9.9: Error underline in the CoT definition](img/B31534_09_09.png)

Figure 9.9: Error underline in the CoT definition

This underlying error indicator is expected and resolved as Copilot generates the implementation for the function at hand.

This reasoning approach facilitates the generation of accurate and predictable code when working with the AI pair programmer. As each function is implemented (such as `get_gross_returns`, `get_geometric_mean`, etc.), Copilot learns enough context to write the correct provided parameters, how the return value is used, and the expected type hints.

Additionally, we can predict how Copilot will complete the code and in what order. The implementation will follow the sequence of function calls in `get_average_return`. Indeed, as we press *Enter* twice and start typing `def`, Copilot will suggest an implementation for `get_gross_returns`, as shown in *Figure 9.10*:

![Figure 9.10: Copilot predicts the implementation of the first called function](img/B31534_09_10.png)

Figure 9.10: Copilot predicts the implementation of the first called function

Once we accept the implementation and hit *Enter* twice again, Copilot will suggest the next function in the call sequence, `get_geometric_mean`, as shown in *Figure 9.11*:

![Figure 9.11: Copilot predicting the next function definition](img/B31534_09_11.png)

Figure 9.11: Copilot predicting the next function definition

Here, we did not need to type anything. Just a two-line break, resembling the space between `get_average_return` and `get_gross_returns`, was enough to trigger a fully predictable implementation in this file. This demonstrates the optimal use of Copilot, truly leveraging the power of an AI pair programmer. For your reference, here is the full implementation suggested by Copilot:

```

def get_gross_returns(

net_returns: Dict[str, float], ) -> np.ndarray:

    gross_returns: np.ndarray = np.array( list(net_returns.values())

    ) + 1

    return gross_returns def get_geometric_mean(

gross_returns: np.ndarray, ) -> float:

    gross_average: float = np.prod(gross_returns) ** ( 1 / len(gross_returns)

    ) return gross_average def get_net_average(

gross_average: float, ) -> float:

    net_average: float = gross_average - 1

    return net_average

```py

This implementation successfully captures the intended logic, and its structuring across different levels of abstraction is superior to what even the most advanced o3 models produce via ChatGPT and OpenAI API. This serves as a strong example of how effective prompting techniques can outperform more powerful and costly models.

Educating your colleagues

Next time you notice a colleague trying to use inline comments in GitHub Copilot such as `# step 1: Compute the gross returns`, suggest they try using CoT instead. This approach will not only be more efficient and a better way to use Copilot, but it will also help the team maintain higher-quality code.

Next, we will explore how to replicate the desired outputs with ChatGPT and OpenAI API, even when using more affordable models such as GPT-4o mini.

## CoT for the geometric mean with ChatGPT

The same CoT approach can be applied to coding tasks, such as implementing a `get_average_return` function that supports negative returns. Rather than supplying the function signature, we will provide a full implementation of `get_average_return` as we did with Copilot and prompt the model to complete the lower-level details. A prompt for this might look like the following:

```

CONTEXT: 你被提供了一个 Python 函数，该函数包含在{{{ FUNCTION }}}中，调用了一些需要完成的函数。任务：实现缺失的函数。函数：{{{def get_average_return(\n\t\tnet_returns: Dict[str, float],\n) -> float: \n\tgross_returns: np.ndarray = get_gross_returns(net_returns) \n\tgross_average: float = get_geometric_mean(gross_returns) \n\tnet_average: float = get_net_average(gross_average) \n\treturn net_average }}}

代码：

```py

This prompt outlines the necessary reasoning steps to generate the correct code. For reference, here is the output produced by ChatGPT using the GPT-4o mini model with the given prompt:

```

def get_gross_returns(net_returns: Dict[str, float]) -> np.ndarray:

    """ ... 省略以节省空间 ... """

    return np.array([1 + net_return for net_return in net_returns.values()])

def get_geometric_mean(values: np.ndarray) -> float:

    """ ... 省略以节省空间 ... """

    return np.prod(values) ** (1 / len(values))

def get_net_average(gross_average: float) -> float:

    """ ... 省略以节省空间 ... """

    return gross_average - 1

def get_average_return(net_returns: Dict[str, float]) -> float:

    gross_returns: np.ndarray = get_gross_returns(net_returns)

    gross_average: float = get_geometric_mean(gross_returns)

    net_average: float = get_net_average(gross_average)

    return net_average

```py

This output is more satisfactory than the baseline, even though it was generated with GPT-4o model instead of the more advanced O-series. It no longer includes inline comments or input validation, which significantly reduces the amount of manual editing required. Later in the chapter, we will see how chaining can help produce even more polished results that are ready to use as is.

Next, we will apply this approach using OpenAI API.

## CoT with OpenAI API

We can leverage CoT prompting and provide a full implementation of `get_average_return` as we did with Copilot and ChatGPT. The system and user prompts may look as follows:

```

SURROUND = "你被提供了一个 Python 函数，该函数包含在{{{ FUNCTION }}}中，调用了一些需要完成的函数。" SINGLE_TASK = "你的任务是实现缺失的函数。" def get_user_prompt(func: callable) -> str:

    return f"""

    函数：{{{{{{ {inspect.getsource(func)} }}}}}}

    代码：

    """

```py

We will integrate these prompt pieces into an OpenAI API call, including the system prompt, user prompt, and a GPT-4o mini model, as shown here:

```

if __name__ == '__main__':

    client: OpenAI = OpenAI()

    system_prompt = f"{SURROUND}  {SINGLE_TASK}" user_prompt = get_user_prompt(get_average_return)

    completion: ChatCompletion = client.chat.completions.create(

        model="gpt-4o-mini",

        messages=[

            {"role": "system", "content": system_prompt},

            {"role": "user", "content": user_prompt},

        ],

    )

    output = completion.choices[0].message.content print(output)

```py

Note that the code sample can be found in this book’s repository at `ch9/cot/cot_openai.py`. For reference, here is sample output from the call:

```

import numpy as np

from typing import Dict

def get_gross_returns(net_returns: Dict[str, float]) -> np.ndarray:

    """将净收益转换为毛收益。"""

def get_geometric_mean(gross_returns: np.ndarray) -> float:

    """计算一组净收益的几何平均值。返回值："""

def get_net_average(gross_average: float) -> float:

    """将毛平均收益转换回净平均收益。"""

def get_average_return(net_returns: Dict[str, float]) -> float:

    ... 省略以节省篇幅 ...

```py

Here, we obtained a better implementation than the baseline, maintaining the desired level of abstraction and avoiding input validation and inline comments.

While leveraging CoT is highly effective when using GitHub Copilot, it is not always sufficient to produce ready-to-use code with ChatGPT or OpenAI API. To address this, we can incorporate chaining through follow-up prompts, as we will demonstrate next.

# Using prompt chaining for LLMs

Prompt chaining is another highly effective prompt engineering technique that helps us achieve better results from LLMs. It involves breaking down tasks into smaller, sequential steps that are more efficiently completed individually.

For instance, when implementing `get_average_return`, we may want to enhance ChatGPT’s or OpenAI’s initial output by adding type hints and avoiding inline calculations in the return statement. With GitHub Copilot, we might want to construct a barebones implementation first and add a Google Style docstring later.

Although we could include all these elements in the initial prompt, it is often more natural and effective to start with an implementation that is functionally correct. From there, we can refine the code step by step through a series of follow-up prompts.

## Chaining with ChatGPT

Applying chaining with ChatGPT is very intuitive given that the UI is already designed for a conversational style. The chat history helps us reference previous prompt pieces without needing to retype them.

For instance, say that we wanted to improve the implementation of `get_average_return` with a Google Style docstring rather than an arbitrary one, and type hints to variables in all functions. Including all these elements in one prompt would defy the single-task best practice and result in suboptimal outputs. Instead, we recommend the following approach:

*   For chained prompts with the same context, focus only on the new task
*   For chained prompts with a different context, such as adding test cases, use a full prompt following the five S’s best practices

For the task of coding `get_average_return`, adding type hints for variables, revising the docstring to be in a Google Style format, and adding a test suite can be done with the following strategy:

*   **Prompt 1**: Write the full code prompt using the five S’s for the `get_average_return` implementation with a CoT.
*   **Prompt 2**: Add type hints to all variables.
*   **Prompt 3**: Change the docstring to Google Style.
*   **Prompt 4**: Write unit tests. In this step, we will specify the test cases we want to cover, creating a new context. As a result, we need to provide a complete prompt that follows the five S’s best practices.

For example, prompt 2, which focuses on the single task of removing comments, is simply as follows:

```

为所有变量添加类型提示。

```py

This will produce an updated implementation without the inline comments, as shown in *Figure 9.12*.

![Figure 9.12: Added type hints to variables](img/B31534_09_12.png)

Figure 9.12: Added type hints to variables

The initial implementation has been updated to include type hints for variables across the different functions. For instance, in the first function, `get_gross_returns`, the `gross_returns` variable is now correctly annotated with the `np.ndarray` type and returned in the following line.

In prompt 3, the focus shifts to improving the docstring. We continue with a single-task prompt:

```

include Google Style docstring.

```py

This prompt is expected to yield a better implementation, as demonstrated in *Figure 9.13*.

![Figure 9.13: Refined docstring](img/B31534_09_13.png)

Figure 9.13: Refined docstring

The result confirms that we successfully obtained the desired docstring for the `get_gross_return` function in Google Style format. For reference, here are the docstrings generated by ChatGPT for the `get_geometric_mean`, `get_net_average`, and `get_average_return` functions:

```

def get_geometric_mean(gross_returns: np.ndarray) -> float:

    """计算毛收益的几何平均值。参数：

    gross_returns (np.ndarray): 与净收益相对应的毛收益数组。返回值：

    float: 净收益的几何平均值。"""

... 省略以节省篇幅 ... def get_net_average(gross_average: float) -> float: """将毛平均收益转换为净平均收益。参数：

    gross_average (float): 毛收益的几何平均值。返回值：

    float: 对应的净平均收益。"""

... 省略以节省篇幅 ... def get_average_return(net_returns: Dict[str, float]) -> float: """从净收益字典中计算净收益的几何平均值。参数：

    net_returns (Dict[str, float]): 每期的净收益字典。返回值：

    float: 净收益的几何平均值。"""

... 省略以节省篇幅 ...

```py

In later chapters of the book, we will explore a more robust approach to generating docstrings, along with additional chained tasks such as input validation, monitoring, and unit testing.

One limitation of the ChatGPT interface is the lack of control over how prompts are constructed and sent to the underlying model, especially as the conversation grows longer. In the next section, we will see how to gain more control over the chat history by using OpenAI API.

## Selective history with OpenAI API

When working with OpenAI API for chained tasks, we can take a selective approach and explicitly choose which parts of the conversation history to include in each prompt.

Let us consider the first three prompts from the previous ChatGPT session:

*   **Prompt 1**: Leverage CoT for the `get_average_return` implementation
*   **Prompt 2**: Add type hints
*   **Prompt 3**: Refine the docstring

A straightforward way to replicate this workflow with OpenAI API is to continuously append the chained prompt and the corresponding output to our messages list, as shown here:

```

messages = [{"role": "system", "content": system_prompt}]

prompt_1 = get_user_prompt(get_average_return)

prompt_2 = "Add type hints to all variables." prompt_3 = "include Google Style docstring."

for prompt in [prompt_1, prompt_2, prompt_3]:

    messages.append({"role": "user", "content": prompt})

completion: ChatCompletion = client.chat.completions.create(

    model="gpt-4o-mini",

    messages=messages,

)

output: str = completion.choices[0].message.content

messages.append({"role": "assistant", "content": output})

```py

In this naive setup, each user prompt and corresponding model response is appended to the conversation history. By the time we reach `prompt_3`, we expect the output to closely resemble what ChatGPT would generate. For reference, here is a sample response from the API that successfully produced a correct implementation, complete with Google Style docstrings and properly typed variables:

```

def get_gross_returns(net_returns: Dict[str, float]) -> np.ndarray:

    """将净收益转换为毛收益。参数：

        net_returns (Dict[str, float]): 键是标识符的字典，其中值是每个周期的净收益。返回值：

    (如股票代码)和值是净收益值（以小数表示）。返回值：

        np.ndarray: 与净收益相对应的毛收益数组。返回值：

    gross_returns: np.ndarray= np.array([1 + return_value for return_value in net_returns.values()])

    return gross_returns

```py

For reference, the full script can be found in `ch9/chaining/naive_chaining_openai.py`.

The naive approach works reasonably well when there are fewer than 5 follow-up prompts. However, as the chain grows, so does the length of the accumulated prompt, leading to increased token usage. For instance, running the preceding script peaked at 1,253 tokens by `prompt_3`, as illustrated in *Figure 9.14*.

![Figure 9.14: prompt_3 with 1,253 tokens](img/B31534_09_14.png)

Figure 9.14: prompt_3 with 1,253 tokens

As more prompts are added, the total token count increases, which results in higher usage costs and the risk of distracting the LLM from the specific task at hand.

A more efficient alternative for longer chains is a selective history strategy, where only the relevant parts of the interaction are passed along. Instead of including the entire interaction history in each follow-up request, we can simply pass the code generated in response to the first prompt, along with a new system prompt tailored to the next transformation task.

To isolate just the code from the assistant’s response, we can use the following utility function:

```

def get_refactor_user_prompt(assistant_output: str) -> str:

    code: str = re.sub( r"(.*?)```pypython(.*?)```(.*)", r"\2",

        assistant_output,

        flags=re.DOTALL

    ).strip()

    user_prompt: str = f"""

OLD: {{{{{{ {code} }}}}}}

REFACTORED:

"""

    return user_prompt

```py

This extracts the relevant code and formats it into a new user prompt for the next step in the chain.

In contrast to the static system prompt used in the naive approach, we now update the system prompt with each task:

```

prompt_1: str = f"{SURROUND} {SINGLE_TASK}"

prompt_2: str = "You are provided with a Python code enclosed in {{{ FUNCTION }}}. Your task is to add type hints to all variables." prompt_3: str = "You are provided with a Python code enclosed in {{{ FUNCTION }}}. Your task is to include Google Style docstring."

```py

We can then use a `prompts` dictionary to associate each prompt with the appropriate input-generation function, linking `prompt_1` to `get_user_prompt` for the initial implementation, and the subsequent prompts to `get_refactor_user_prompt` for the refactoring steps:

```

prompts: Dict[str, callable] = {

    prompt_1: get_user_prompt,

    prompt_2: get_refactor_user_prompt,

    prompt_3: get_refactor_user_prompt}

```py

This allows us to generate the user prompt dynamically for each task using the correct function:

```

for prompt, func in prompts.items():

    completion: ChatCompletion = client.chat.completions.create(

        model="gpt-4o-mini",

        messages=[

            {"role": "system", "content": prompt},

            {"role": "user", "content": func(next_input)},

        ],

    )

    next_input: str = completion.choices[0].message.content

```py

Notice how each API call now contains only a system prompt and a single user message. This keeps the interaction focused, passing along only what is necessary rather than the full chain of previous prompts and outputs.

For reference, here is a sample output from `prompt_3` using the selective history strategy:

```

def get_gross_returns(net_returns: Dict[str, float]) -> np.ndarray:

    """

    Convert net returns to gross returns. Gross Return is calculated as:

    Gross Return = 1 + Net Return. Args:

        net_returns (Dict[str, float]): 一个字典，键是标识符（例如，资产名称），值是对应的净收益。Returns:

        np.ndarray: 从提供的净收益中派生出的总收益数组。"""

    gross_returns: np.ndarray = np.array([1 + net_return for net_return in net_returns.values()])

    return gross_returns

```py

This output mirrors the quality of the naive approach, including type hints and a Google Style docstring. The key difference is efficiency: using selective history, we reduced the token count to just 296, which is less than 25% of the naive approach, as shown in *Figure 9.15*:

![Figure 9.15: Selective history reduces input tokens by over 75%](img/B31534_09_15.png)

Figure 9.15: Selective history reduces input tokens by over 75%

As chained tasks become more complex, the selective history strategy helps keep prompts short and focused. In later chapters, we will explore additional use cases for chaining across various stages of the **Software Development Life Cycle** (**SDLC**).

In summary, OpenAI API allows both automated execution of chaining and control over prompt history. By including only relevant information, we can reduce costs and help the model concentrate on the specific task at hand.

In the final subsection of this chapter, we will look at how chaining can be applied with GitHub Copilot, where we aim for the initial implementations to already follow the desired formatting.

## Chaining with Copilot

When working with Copilot for code completion tasks, we can also leverage chaining by breaking down the task into smaller steps. For tasks that go beyond the barebones implementation, such as adding docstrings, input validations, logs, and tests, it is best to align with a chained approach. For the chained tasks, we can use the chat interaction mode with Copilot. In later chapters of the book, we will see how to leverage code completion for chained tasks as well.

For example, a chaining flow to extend `get_average_return` with a docstring and input validation might look as follows:

1.  **Initial task**: Implement `get_average_return` with CoT.
2.  **Chained task 2**: Add docstrings to all functions.
3.  **Chained task 3**: Add input validation.

After generating the initial implementation of `get_average_return`, as shown earlier in the chapter, we can proceed to the second chained task, which focuses on adding docstrings to all functions in the file.

In VS Code, we can use Copilot Edits for this task by opening the chat window and selecting **Edit**. We will ensure that the working set includes the current file, `ch9/chaining/get_average_return.py`, and enter the following prompt:

```

Add Google Style docstring to all functions.

```py

This prompt will result in suggestions for adding type hints to the variables, as shown in *Figure 9.16*.

![Figure 9.16: Suggested edits to add a docstring](img/B31534_09_16.png)

Figure 9.16: Suggested edits to add a docstring

Here, we can see that Copilot correctly added a docstring to all functions with our preferred Google Style; for example, in line 26, a correct description of `get_gross_return` was added to the function.

In PyCharm, open GitHub Copilot Chat by clicking the Copilot icon in the bottom menu and selecting **Open GitHub Copilot Chat** or using the *Ctrl* + *Shift* + *C* keyboard shortcut. Enter the following prompt:

```

Add Google Style docstring to all functions.

```py

Copilot will suggest the necessary edits, adding a docstring to all functions, as seen in *Figure 9.17*:

![Figure 9.17: Suggested edits to add a docstring using PyCharm](img/B31534_09_17.png)

Figure 9.17: Suggested edits to add a docstring using PyCharm

In both VS Code and PyCharm, Copilot suggests the appropriate docstring for each function. Later in this book, we will apply chaining along with other prompt engineering techniques to address SDLC tasks. For example, in *Chapter 14*, we will explore how to combine CoT and chaining to profile the runtime and space complexity of our code.

# Summary

In this chapter, we explored how to achieve desirable outcomes from LLMs by effectively applying CoT and chaining for coding tasks with an extended scope.

With CoT prompting, we saw how introducing reasoning steps into our prompts enables the model to handle more nuanced challenges, such as implementing a geometric mean function that supports negative net returns. We used function names as intermediate reasoning steps, while relying on Copilot, ChatGPT, and OpenAI API to fill in the implementation details.

Through chaining, we began with an initial implementation that is functionally correct and iteratively improved by adding type hints and refining docstrings. When using OpenAI API, we introduced a selective history approach to make chaining more efficient, which still holds as the chain of tasks gets longer.

In the next chapter, we will delve deeper into refactoring code with GenAI applications. Later in the book, we will introduce advanced prompt engineering techniques at various stages of the SDLC.

# Quiz time

Before you proceed to the next chapter, make sure that you can confidently answer the following questions:

**Question 1**: Is prompt engineering always necessary when working with GenAI?

**Answer**: Not always. For tasks with a smaller scope, such as implementing a short function, the five S’s framework is often enough to guide the model toward a good result. Prompt engineering becomes more important when the task grows in complexity, requiring us to either break it into smaller parts or guide the model with reasoning steps to help it succeed.

**Question 2**: How is CoT applied with GitHub Copilot?

**Answer**: To apply CoT with Copilot, we specify our reasoning steps in abstracted functions. This approach helps Copilot understand the reasoning behind the desired implementation, allowing it to generate the next lines of code with minimal input, often just by hitting *Enter*.

**Question 3**: Is chat history irrelevant when using prompt chaining?

**Answer**: No. In chaining, we make use of the previously provided context and supporting data, such as code specifications and reasoning steps, and refer to them again, just as we would reference variables in our code. When additional context is needed, such as test cases to include in our test suite, we rebuild the full prompt.

# Further reading

To learn more about the topics that were covered in this chapter, refer to the following resources:

*   Geometric mean in financial applications, Wikipedia: [`en.wikipedia.org/wiki/Geometric_mean#Financial`](https://en.wikipedia.org/wiki/Geometric_mean#Financial)
*   OpenAI learning to reason (CoT): [`openai.com/index/learning-to-reason-with-llms/`](https://openai.com/index/learning-to-reason-with-llms/)

|  
#### Unlock this book’s exclusive benefits now

Scan this QR code or go to [packtpub.com/unlock](http://packtpub.com/unlock), then search for this book by name. | ![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png) |
| *Note: Keep your purchase invoice ready before you start.* |

# 10

# Refactoring Code with GenAI

Software developers write in programming languages to instruct a computer to perform specific tasks. The source code in the programming language is translated by a compiler or interpreter into executable computer instructions. One might conclude that programming is only artificial communication with a computer, but it is much more than that.

The true, implicit goal of a computer program is to communicate with other developers. Once code is written, it is frequently read many times, hours, weeks, or even years later, by the same or other developers. The developers will read the code to understand it, debug it, and integrate it with other systems. The goal must be to communicate with the precision required by software, while maintaining clarity for future developers.

Thus, code is written once but read many times. Before GenAI code generation became common, Python practitioners invested significant effort into code quality and style. Today, we can use prompting techniques with GenAI to enhance code quality and style more efficiently.

In *Chapter 7*, we introduced techniques for quickly reading and debugging GenAI-generated code. In this chapter, we will focus on using GenAI for **refactoring**, which means rewriting existing code to improve readability, structure, or performance while preserving its original functionality.

We will examine a poorly implemented function that computes the distance between two matrices. By applying the five S’s framework for prompt precision as introduced in *Chapter 4*, we will convert a nested loop into a vectorized operation. With **chain-of-thought** (**CoT**) prompting, we will restructure the function and delegate implementation details to GitHub Copilot, ChatGPT, and OpenAI API.

Topics covered in this chapter include the following:

*   Introducing code refactoring
*   Refactoring for better structure with GenAI
*   Refactoring for performance with GenAI

# Technical requirements

To get the most out of this chapter, ensure you have the following:

*   GitHub Copilot account
*   IDE – either VS Code or PyCharm
*   OpenAI account with access to OpenAI API
*   Access to the book’s repository, available at [`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)
*   Virtual environment set up in VS Code or PyCharm
*   OpenAI API token

For assistance setting up a GitHub Copilot account, refer to *Chapter 3*. For instructions on setting up OpenAI API access and token generation, see *Chapter 2*. If you need help creating an OpenAI account or setting up a virtual environment in your IDE, refer to *Appendix* for detailed guidance.

# Introducing code refactoring

Code is intended as communication to future software developers. Code that effectively and clearly communicates the purpose and mechanisms is described as **clean code**.

As described by Robert C. Martin (better known as *Uncle Bob*), clean code can be achieved through refactoring. Code refactoring is not merely modifying code, but a disciplined approach to continuously improving code. One aspect is removing the indiscriminate **code smell** that qualitatively characterizes poorly written code (see *Further reading*). A second aspect is improving the code’s actual design, which should improve its readability and maintainability. This is critical since firms spend an estimated 75% of their software development costs on the evolution and maintenance of software (Sommerville).

Software developers frequently dedicate time to refactoring, which involves rewriting sections of existing code while keeping the original functionality and purpose intact. The goal is to improve readability, structure, or performance. This is particularly evident in **Agile** software development, where continuous refactoring is linked to the sustainable evolution of code. The **Extreme Programming** (**XP**) agile methodology explicitly embraces refactoring along with ideals of collective ownership and the use of **Test-Driven Development** (**TDD**), as will be discussed in *Chapter 13*.

IDEs such as PyCharm and VS Code offer built-in tools for tasks such as extracting variables, functions, and methods, renaming code elements, and formatting code. Still, they fall short when it comes to more complex scenarios such as extracting a function from non-consecutive lines of code.

Next, we will use an example of a function that computes two types of distances and identify hidden issues caused by poor implementation. Later in the chapter, we will refactor it using GenAI tools.

## Manhattan and Euclidean distance

In *Chapter 7*, we introduced the **Manhattan distance** between two matrices, also known as the **L1 norm**, defined as the sum of absolute differences between corresponding elements. The code example provided used a *Flask* application that receives matrix data through HTTP requests. If you need a refresher on this topic, refer to *Chapter 7*.

Another way to measure the distance between matrices is the **Euclidean distance**, which is simply the straight-line distance. In two dimensions, the distance between points *(x1, y1)* and *(x2,y2)* is calculated as follows:

![](img/B31534_10_001.png)

When applied to a pair of two-dimensional matrices 𝑋 and 𝑌 of the same shape (with the same number of rows and columns), the distance is calculated as follows:

![](img/B31534_10_002.png)

This measure is also referred to as the **L2 norm** or **Frobenius** norm. It is widely used in tasks such as image similarity and machine learning, where it often represents the *squared error* of a prediction.

### Implementing the distance function

If we want to implement a function that computes both L1 and L2 norms based on a request, one way to approach this is to build upon our *Chapter 7* implementation of the Manhattan distance (L1) and extend it to include the Euclidean distance (L2) as well. A sample implementation, although poorly written, is as follows:

```

@app.route("/distances", methods=["POST"])

def calculate_distance():

    data = request.get_json()

    dist_type = data.get("distance") if dist_type == "L1": print("Info: computing L1 distance...")

        a = data.get("df1")

        b = data.get("df2")

        dist = np.sum(np.abs(a - b)) return jsonify({"distance": dist}) elif dist_type == "L2": print("Info: computing L2 distance...")

        a = data.get("df1")

        b = data.get("df2")

        dist_2 = 0

        for i in range(len(a)): for j in range(len(a[i])):

                dist_2 += (a[i][j] - b[i][j]) ** 2 dist = np.sqrt(dist_2) return jsonify({"distance": dist})

```py

![](img/31.png)**Quick tip**: Enhance your coding experience with the **AI Code Explainer** and **Quick Copy** features. Open this book in the next-gen Packt Reader. Click the **Copy** button

(**1**) to quickly copy code into your coding environment, or click the **Explain** button

(**2**) to get the AI assistant to explain a block of code to you.

![A white background with a black text  AI-generated content may be incorrect.](img/image_%282%291.png)

![](img/41.png)**The next-gen Packt Reader** is included for free with the purchase of this book. Scan the QR code OR visit [packtpub.com/unlock](https://packtpub.com/unlock), then use the search bar to find this book by name. Double-check the edition shown to make sure you get the right one.

![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png)

Maintaining this code may be challenging. For example, reading the parameters `a` and `b` is duplicated, so if we want to add validations such as checking that both matrices have the same shape, we need to do it twice. Such duplication of code is considered poor programming practice. If we plan to add unit tests, every test needs to mock the request. Adding another distance function would make the function even longer and harder to read.

Next, we will categorize the several types of refactoring and see how they apply to this example.

## Types of refactoring

When we refactor code, our goal is to maintain its functionality while improving its quality. There is always a risk that the modifications will break the code or inadvertently change the functionality. To avoid this, unit tests should be in place before making any significant changes to ensure that the code still runs correctly. In addition, refactoring should be performed as a set of incremental changes that do not alter the behavior of the code.

The term **refactoring** alone is not specific enough to define a single task, according to the **five S’s framework** introduced in *Chapter 4*. The changes we aim to make can vary from simple tasks such as renaming a variable to more extensive efforts such as redesigning an entire module.

To achieve clean code, there are several common refactoring approaches. First, larger and more complex functions should be divided into several that perform a single task. Second, duplicate code should be removed or abstracted by the **Do not Repeat Yourself** (**DRY**) principle. Variables and functions should be named for clarity. This principle also applies to arbitrary numeric constants and strings, so there should not be hardcoded values (also referred to as **magic numbers**), but instead have these values assigned to a meaningful constant name.

We typically divide refactoring tasks into three categories:

*   **Readability**: This includes tasks such as renaming objects, removing redundant imports or excessive comments, introducing constants instead of hardcoded numbers, or adding type hints. For example, within the implementation of `calculate_distance`, we might change the name of the variable `a` to `df1` to indicate that it represents a matrix in the request. We might also want to add type hints to the request parameters.
*   **Structure change**: This involves organizing code in a better way, such as extracting long code blocks into functions or classes. For example, within the implementation of `calculate_distance`, we might replace `print` statements with `logger` calls, improving how our code handles output. We might also extract the `L1` and `L2` calculations into separate functions.
*   **Performance**: This means adjusting the implementation to better handle space or runtime constraints. For example, within the implementation of `calculate_distance`, instead of using a nested `for` loop to calculate `L2`, we might apply vectorization using the *NumPy* library to improve efficiency.

There are already good capabilities for refactoring code, particularly for readability, using the built-in tools of our IDEs, as we will see next.

## Improving readability before GenAI

Modern IDEs such as VS Code and PyCharm offer built-in refactoring tools that help improve code readability. For example, in PyCharm, we can right-click a parameter we would like to rename and select **Refactor** | **Rename** to update the variable and all its references within the relevant scope (in this case, the `calculate_distance` function). This option is illustrated in *Figure 10.1*.

![Figure 10.1: PyCharm built-in refactoring tools for refactoring/renaming](img/B31534_10_1.png)

Figure 10.1: PyCharm built-in refactoring tools for refactoring/renaming

This figure also highlights other refactoring options such as changing a callable signature, extracting constants or methods, and more. The authors frequently use these features when refining existing code.

Similarly, VS Code allows us to right-click the parameter we want to change and select **Rename Symbol** to update the variable and all its references within the relevant scope, as shown in *Figure 10.2*.

![Figure 10.2: VS Code Rename Symbol](img/B31534_10_2.png)

Figure 10.2: VS Code Rename Symbol

The **Rename Symbol** option appears fourth from the bottom in the figure and performs a similar renaming operation as in PyCharm.

Next, we will explore the limitations of these built-in tools. Later in the chapter, we will use GenAI to address those challenges.

## Limitations of code refactoring with IDE tools

PyCharm and VS Code offer powerful refactoring features, but these are still limited.

For example, we may want to extract argument parsing logic for `a`, `b`, and `dist_type` into a separate function, such as the following:

```

def parse_request_parameters(r: request) -> Tuple[np.ndarray, np.ndarray, str]:

    a = np.array(r["df1"])

    b = np.array(r["df2"])

    dist_type = r["distance"] return a, b, dist_type

```py

This kind of structural refactoring helps reduce code duplication. However, current IDE tools are unable to extract these three parameters into a single function because they are not written in consecutive lines in the original implementation, as shown in *Figure 10.3*.

![Figure 10.3: Limitation of extracting a code block to a function](img/B31534_10_3.png)

Figure 10.3: Limitation of extracting a code block to a function

![A magnifying glass on a black background  AI-generated content may be incorrect.](img/11.png)**Quick tip**: Need to see a high-resolution version of this image? Open this book in the next-gen Packt Reader or view it in the PDF/ePub copy.

![](img/21.png)**The next-gen Packt Reader** is included for free with the purchase of this book. Scan the QR code OR go to [packtpub.com/unlock](https://www.packtpub.com/unlock), then use the search bar to find this book by name. Double-check the edition shown to make sure you get the right one.

![A qr code on a white background  AI-generated content may be incorrect.](img/Split-B-PEN-Unlock-QR.png)

In this figure, we cannot extract `dist_type`, `a`, and `b` into a separate function since the lines are not written in a continuous block. As functions become more complex, this approach might no longer be practical.

Next, we will examine how to handle structural refactoring challenges that are beyond the capabilities of IDE tools alone.

# Refactoring with chain-of-thought

In *Chapter 9*, we introduced **chain-of-thought** (**CoT**) as a key prompt engineering technique for working with GenAI to generate code. This method involves writing a high-level function as the prompt, while leaving the implementation details for the GenAI application to complete.

When refactoring code, we want to include the old implementation as an additional context for the model. This can help it better understand the intended functionality. For instance, in the case of the `calculate_distance` function, the previous implementation can clarify which parameters need to be extracted from the JSON request: `a`, `b`, and `dist_type`.

## Refactoring for a better structure

When reviewing the implementation of the `calculate_distance` function, we can break it down into three main steps:

1.  Extracting the request parameters
2.  Deciding whether to compute L1 (Manhattan) or L2 (Euclidean) distance
3.  Calculating the distance

A CoT prompt that reflects these steps could look like this:

```

@app.route("/distances", methods=["POST"])

def calculate_distance():

    a, b, dist_type = parse_request_parameters(request)

    dist_func = {"L1": get_manhattan_dist, "L2": get_euclidean_dist}.get(dist_type)

    dist = dist_func(a, b) return jsonify({"distance": dist})

```py

In this high-level implementation, we can observe the three main steps:

1.  Call a function called `parse_request_parameters` that should return the values for `a`, `b`, and `dist_type`.
2.  Map `dist_function` based on the value of `dist_type` from the request.
3.  Compute the distance using `a` and `b`.

Note that we have considerable flexibility in how we map `dist_type` to a function. This could involve more than an inline dictionary, such as using a function or an external dictionary. A less Pythonic but also acceptable approach would be to use a `switch-case` structure or an `if-else` block.

With this function in place, we can now explore how to implement a complete prompt for GitHub Copilot, ChatGPT, and OpenAI API.

## CoT for refactoring with GitHub Copilot

When using GitHub Copilot, the best practice is to start our prompt with the same function signature as the function we want to refactor. This tells Copilot that we are planning to re-implement the function. Note that Copilot may already suggest an implementation based on the signature alone. However, such an implementation is only as good as asking ChatGPT to refactor a function, since the prompt is not specific enough. For reference, one early completion that Copilot produced from the signature alone is shown in *Figure 10.4*.

![Figure 10.4: Copilot produced a weak refactoring suggestion](img/B31534_10_4.png)

Figure 10.4: Copilot produced a weak refactoring suggestion

In this example, the refactoring involved converting the `a` and `b` parameters to NumPy arrays. While this vectorization can be beneficial in some cases, it may be unnecessary in others. To guide Copilot toward a more suitable output, we use the CoT approach by providing the full CoT high-level implementation as shown earlier in the chapter. Like in *Chapter 9*, Copilot is expected to generate the implementations of the missing functions called by the high-level implementation, as illustrated in *Figure 10.5*.

![Figure 10.5: CoT approach triggers an implementation of missing functions](img/B31534_10_5.png)

Figure 10.5: CoT approach triggers an implementation of missing functions

In this case, Copilot correctly proposed starting with the `parse_request_parameters` function. Once accepted, it suggested a correct implementation for parsing `a`, `b`, and `dist_function`, as shown in *Figure 10.6*.

![Figure 10.6: Copilot implementation for parse_request_parameters](img/B31534_10_6.png)

Figure 10.6: Copilot implementation for parse_request_parameters

Here, Copilot effectively used the context from the previous version of the function. It suggested reading the value of `a` from the `df1` key in the request JSON, `b` from `df2`, and `dist_type` from `distance`. This highlights how providing relevant context can lead to desirable results.

For reference, here are the three implementations Copilot generated:

```

def parse_request_parameters(request):

    data = request.get_json()

    a = np.array(data.get("df1"))

    b = np.array(data.get("df2"))

    dist_type = data.get("distance")

    return a, b, dist_type

def get_manhattan_dist(a, b):

    print("Info: computing L1 distance...")

    return np.sum(np.abs(a - b))

def get_euclidean_dist(a, b):

    print("Info: computing L2 distance...")

    dist_2 = 0

    for i in range(len(a)):

        for j in range(len(a[i])):

            dist_2 += (a[i][j] - b[i][j]) ** 2

    return np.sqrt(dist_2)

```py

These functions mirror the original logic from `calculate_distance` while offering improved abstraction and avoiding code duplication. In a later section of the chapter, we will explore how to refactor for performance, including replacing nested loops with vectorized operations.

Next, we will explore how to apply the CoT approach for refactoring with ChatGPT and OpenAI API. This requires a bit more effort to set up effectively.

## Leveraging CoT for refactoring with ChatGPT and OpenAI API

Just like GitHub Copilot, we can also make use of ChatGPT and OpenAI API to refactor our code to have a better structure. To achieve this, we need to provide these tools with both the original implementation for context and the new structure we want to complete.

A structural refactoring prompt for ChatGPT can follow this general template:

```

CONTEXT: You are provided with

1\. Python function enclosed with {{{ fUNCTION }}} with calls to missing implementations. 2\. Old implementation enclosed with {{{ OLD }}} for reference. TASK: implement the missing functions. FUNCTION: {{{ ... omitted for brevity ... }}}

OLD: {{{ ... omitted for brevity ...}}}

CODE:

```py

Note that in contrast to CoT for new code, refactoring prompts requires giving ChatGPT both the new structure of the function and the reference implementation enclosed in `{{{ OLD }}}`. This format is like how we prompt Copilot and produces desirable results that preserve functionality, even when using more cost-effective models such as *GPT-4o*. *Figure 10.7* shows the output we received from *GPT-4o* for this prompt.

![Figure 10.7: ChatGPT suggested refactoring](img/B31534_10_7.png)

Figure 10.7: ChatGPT suggested refactoring

Here is the implementation for the missing functions proposed by ChatGPT:

```

def parse_request_parameters(req):

    data = req.get_json()

    dist_type = data.get("distance")

    a = np.array(data.get("df1"))

    b = np.array(data.get("df2"))

    return a, b, dist_type

def get_manhattan_dist(a, b):

    print("信息：计算 L1 距离...")

    return float(np.sum(np.abs(a - b)))

def get_euclidean_dist(a, b):

    print("信息：计算 L2 距离...")

    return float(np.sqrt(np.sum((a - b) ** 2)))

```py

This output resembles the structure Copilot suggested, focusing on extracting the distance calculations into smaller functions and removing redundancy. One notable difference is that ChatGPT was more consistent and used NumPy vectorization for both distance functions, and not just the Manhattan distance method.

### OpenAI API prompt

When we refactor code for improved structure, GitHub Copilot and ChatGPT often prove to be more suitable than OpenAI API. This is because using the API typically requires more manual effort to craft the prompt programmatically. OpenAI API becomes more practical only when we need to scale changes across multiple similar functions, and we find that refactoring the structure with CoT might not be one of these cases.

In summary, GenAI supports the restructuring of existing code by combining prior implementations with new instructions. We recommend trying this technique with code you encounter in your day-to-day work or even in third-party libraries.

Next, we will briefly introduce refactoring for performance using GenAI, a topic we will cover more extensively in *Chapter 14*.

# Performance refactoring with GenAI

Performance refactoring refers to changes made to the code that preserve its functionality while improving runtime or memory efficiency. One common approach is to use **vectorized computations**. These can reduce the runtime by benefiting from cache, lower overhead, and parallel computation.

For instance, in the GitHub Copilot implementation of `calculate_distance` example, this would mean replacing a nested `for` loop with a vectorized computation of the Euclidean distance. We will explore further runtime and space complexity in *Chapter 14*, including when and why to scale system capacity and the trade-offs involved. Until then, let us demonstrate how a simple optimization through vectorization might be applied.

## Performance refactoring with GitHub Copilot

As with the CoT approach, we will leverage the context of existing code along with our desired structure. This time, we will specify the library we would like to implement a code block instead of the original implementation.

For example, consider the function Copilot extracted for us to compute the Euclidean distance:

```

def get_euclidean_dist(a, b): print("信息：计算 L2 距离...")

    dist_2 = 0

    for i in range(len(a)): for j in range(len(a[i])):

            dist_2 += (a[i][j] - b[i][j]) ** 2

    return np.sqrt(dist_2)

```py

This function computes the squared distance `dist_2` and then returns its square root.

To vectorize the squared distance computation, we can use NumPy, a widely used Python library that supports optimized operations on arrays and matrices. In our prompt, our goal is to preserve the original logic:

1.  Compute the squared distance
2.  Compute the distance

To guide Copilot toward the desired refactoring, we can add a cue using a NumPy function call. The first prompt would be placed near the squared distance step:

```

Dist_2 = np.

```py

This is shown in *Figure 10.8*:

![Figure 10.8: Prompt with an np. library call as a cue](img/B31534_10_8.png)

Figure 10.8: Prompt with an np. library call as a cue

Then, for the square root step, we would add another cue:

```

dist = np.

```py

This is sufficient context for Copilot to complete the correct implementation using NumPy, as shown in *Figure 10.9*:

![Figure 10.9: Copilot recognized the correct function from the cue](img/B31534_10_9.png)

Figure 10.9: Copilot recognized the correct function from the cue

These inline completions can be highly effective. However, before applying performance optimizations, it is important to determine whether scaling or optimizing code is necessary. We will explore these considerations further in *Chapter 14*.

Next, we will look at how to achieve the same outcome using ChatGPT and OpenAI.

## Performance refactoring with ChatGPT and OpenAI

When using ChatGPT and OpenAI API for performance refactoring tasks such as vectorizing computations, common transformations such as adopting the NumPy package can be achieved by following the **five S’s best practices**, as introduced in *Chapter 4*. Like in *Chapter 7*, where we include the full file content in the prompt along with the specific line we want to explain, here, we also provide the complete function implementation together with the files that need refactoring.

Here is a sample prompt template that can be used in ChatGPT:

```

上下文：您提供的信息：

1. 一个 Python 函数实现用{{{ FUNCTION }}}括起来

2. 需要重构的代码行用{{{ OLD }}}括起来

3. 新代码中要使用的库用{{{ LIBRARY }}}括起来。

任务：使用指定的库为旧代码行返回一个新的实现。函数定义：{{{ ... }}}

旧代码：{{{     ... }}}

库：{{{ ... }}}

重构后的代码：

```py

Note that in this template, we are not requiring the model to follow the same sequence of steps as in Copilot, such as first computing `dist_2` and then applying the square root. This allows ChatGPT to suggest more common implementations that may take a different route. By specifying `LIBRARY`, we are explicitly guiding the GenAI tools toward an expected solution.

**Important note**

In *Chapter 14*, we will learn how to replace the library constraint with constraints on runtime and space capacity. If we do not specify either constraints or a library, the model will suggest the most popular implementation, which may not align with our goals. As a result, the response often lacks specific instructions and does not follow the five S’s framework.

For reference, let us consider a vectorization prompt for the `get_euclidean_distance` function that is available in this book’s repository at `ch10/prompts/``performance``_refactoring_chatgpt.txt`. The response we got from ChatGPT with the *GPT-4o* economic model is shown in *Figure 10.10*.

![Figure 10.10: ChatGPT proposed vectorized implementation](img/B31534_10_10.png)

Figure 10.10: ChatGPT proposed vectorized implementation

The implementation shown in the figure is a common implementation for calculating Euclidean distance. It vectorizes the element-wise distance and then uses the linear algebra module in NumPy to compute the norm. This version is typically easier to read and more flexible than what Copilot suggested.

**Note**

This prompt structure can be reused when comparing implementations across multiple libraries offering similar functionality. For instance, when evaluating alternatives between SciPy and NumPy, this format allows us to generate and compare implementations quickly.

Next, we will look at how to achieve equivalent results using OpenAI API.

### Vectorizing with OpenAI API

Creating a prompt for OpenAI API usually takes more effort than using ChatGPT to get comparable results. This approach is most suitable when we want to produce multiple new implementations at scale, such as converting many `for` loops to vectorized NumPy expressions.

To create a system prompt, we can adapt our ChatGPT prompt structure into two components:

```

SURROUND = """您提供的信息：

1. 一个 Python 函数实现用{{{ FUNCTION }}}括起来

2. 需要重构的代码行用{{{ OLD }}}括起来

3. 新代码中要使用的库用{{{ LIBRARY }}}括起来。"""SINGLE_TASK = "您的任务是使用指定的库为旧代码行返回一个新的实现。" LINES = """dist_2 = 0

for i in range(len(a)):

for j in range(len(a[i])):

dist_2 += (a[i][j] - b[i][j]) ** 2

"""

```py

We can define a `get_user_prompt` function as such:

```

def get_user_prompt(func: callable, library: str, lines: str) -> str: return f"""

函数定义：{{{{{{ {inspect.getsource(func)} }}}}}}

LINES: {{{{{{ {lines} }}}}}}

库：{{{{{{ {library} }}}}}}

重构代码：

"""

```py

We can then use both prompts when calling the service:

```

if __name__ == "__main__":

    client: OpenAI = OpenAI()

    system_prompt = f"{SURROUND}  {SINGLE_TASK}" user_prompt = get_user_prompt(get_euclidean_distance, "NumPy", LINES)

    完成任务：ChatCompletion = client.chat.completions.create(

        模型="gpt-4o-mini",

        messages=[

            {"role": "system", "content": system_prompt},

            {"role": "user", "content": user_prompt},

        ],

    ) print("解释:", completion.choices[0].message.content)

```py

For reference, the full script is available in `ch10/prompts/performance_refactoring_openai.py`. The output we obtained was equivalent to the result from ChatGPT.

To conclude, GitHub Copilot is the quickest way to get performance refactoring suggestions. ChatGPT is more suitable when we want widely adopted implementations or to quickly assess different libraries’ implementations with a reusable prompt. OpenAI API is helpful in less common cases when we want to generate bulk transformations across many files or a large code base.

## More advanced performance refactoring

In *Part 3* of the book, *Chapter 14* will address runtime and space complexity optimization. We will demonstrate how combining code completion tools with prompt engineering techniques such as **chaining** can help us find the right balance between space and time complexity.

We will use GitHub Copilot, ChatGPT, and OpenAI to assess the program’s current performance, estimate its runtime and space complexity in terms of **Big-O notation**, and introduce optimized solutions to extend input capacity with minimal trade-off. Stay tuned for a detailed exploration of these topics.

# Summary

In this chapter, we explored how GitHub Copilot, ChatGPT, and OpenAI API can assist in rewriting code while preserving its original functionality. These tools can enhance readability, improve structure, and boost performance.

Clean code is a shared goal among software developers, especially as projects grow and become complex. Most IDEs already offer strong built-in tools for refactoring, which we frequently use. However, when those tools reach their limits, GenAI can step in. It can support structural refactoring by using CoT techniques with the original implementation, or it can optimize performance through the five S’s framework.

Although refactoring is useful, writing clean and structured code from the start is usually simpler. In the next chapter, we will introduce **fine-tuning** with OpenAI API as an alternative to **few-shot learning**. Fine-tuning enables us to adapt a pretrained model to a specific domain, such as generating clean and well-organized code. Unlike prompt engineering, fine-tuning separates the specialization process from the prompt itself, which can be beneficial for larger-scale projects.

# Quiz time

Before you proceed to the next chapter, make sure that you can confidently answer the following questions:

**Question 1**: Why do we need GenAI for refactoring tasks if IDEs already provide built-in tools?

**Answer**: While built-in tools are powerful, they have limitations. For example, they can only extract code blocks to external functions when the lines are written consecutively in a single block. GenAI allows us to restructure Python objects more flexibly, using the CoT technique with the original implementation as a reference.

**Question 2**: How does the CoT approach differ when refactoring existing code compared to generating new code?

**Answer**: When generating new code, we typically describe the high-level function we want GenAI to complete. For refactoring, we also include the original implementation in the prompt. This helps GenAI understand the intended functionality, such as parsing specific JSON request keys or assigning them to specific variable names.

# Further reading

To learn more about the topics that were covered in this chapter, look at the following resources:

*Clean Code: A Handbook of Agile Software Craftsmanship* by Robert C. Martin (aka Uncle Bob): [`www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882`](https://www.amazon.com/Clean-Code-Handbook-Software-Craftsmanship/dp/0132350882)

*Code smell*: [`en.wikipedia.org/wiki/Code_smell`](https://en.wikipedia.org/wiki/Code_smell#cite_note-7)

*Refactoring: Improving the Design of Existing Code, Second Edition*: [`www.amazon.com/Refactoring-Improving-Existing-Addison-Wesley-Signature/dp/0134757599`](https://www.amazon.com/Refactoring-Improving-Existing-Addison-Wesley-Signature/dp/0134757599)

*Design Patterns: Elements of Reusable Object-Oriented Software*: [`www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612`](https://www.amazon.com/Design-Patterns-Elements-Reusable-Object-Oriented/dp/0201633612)

Mariane Anaya. *Clean Code in Python: Develop maintainable and efficient code, Second Edition*, 2021: [`www.packtpub.com/en-us/product/clean-code-in-python-9781800560215`](https://www.packtpub.com/en-us/product/clean-code-in-python-9781800560215)

Kent Beck and Cynthia Andres, *Extreme Programming Explained: Embrace Change*, 2004: [`www.amazon.com/Extreme-Programming-Explained-Embrace-Change/dp/0321278658`](https://www.amazon.com/Extreme-Programming-Explained-Embrace-Change/dp/0321278658)

Ian Sommerville. *Software Engineering*, 2015: [`www.amazon.com/Software-Engineering-10th-Ian-Sommerville/dp/0133943038`](https://www.amazon.com/Software-Engineering-10th-Ian-Sommerville/dp/0133943038)

# Subscribe for a free eBook

New frameworks, evolving architectures, research drops, production breakdowns—AI_Distilled filters the noise into a weekly briefing for engineers and researchers working hands-on with LLMs and GenAI systems. Subscribe now and receive a free eBook, along with weekly insights that help you stay focused and informed.

Subscribe at [`packt.link/TRO5B`](https://packt.link/TRO5B) or scan the QR code below.

![A qr code on a white background  AI-generated content may be incorrect.](img/B31534_Newsletter_NEW.png)

# 11

# Fine-Tuning Models with OpenAI

Concluding *Part 2*, this chapter explores how to train **large language models** (**LLMs**) to specialize in completing a specific task. This is achieved by **fine-tuning** the model’s parameters, known as **weights**, through the OpenAI platform. This is quite like the prompt engineering strategy **few-shot learning**, sometimes referred to as **in-context learning**, which we introduced earlier in the book as a technique for helping the model to specialize in a particular domain. Fine-tuning, however, is best suited for larger-scale projects where we want to separate the specialization aspect from the actual prompt.

We will delve into a use case where this specialization of the model is required to produce code while avoiding comments clutter. We will examine how outputs from the *GPT-4o mini* model may be programmatically correct but fail to follow our style guidelines and requirements for concise explanations and code comments. We will construct a fine-tuning **JSONL** file with high-quality examples that illustrate desired outcomes, initiate a fine-tuning job through the OpenAI website, and compare the improved results with the output of the base model.

This chapter covers the following topics:

*   Fine-tuning LLMs toward a specialization
*   Experimenting with the OpenAI Playground
*   Crafting a JSONL file for fine-tuning
*   Fine-tuning a model with the OpenAI GUI
*   Comparing our results

# Technical requirements

To get the most out of this chapter, ensure you have the following:

*   An OpenAI account with access to OpenAI API
*   Access to the book’s repository, available at [`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)

For instructions on setting up OpenAI API access, see *Chapter 2*. If you need help with creating an OpenAI account, refer to the *Appendix* for detailed guidance.

# Fine-tuning LLMs toward a specialization

When working on complex coding tasks with LLMs, we may need to employ **prompt engineering** techniques. In *Chapter 8*, we saw how including a few examples in the prompt implicitly instructs the model to follow the expected coding style when writing code. This *show, don’t tell* approach effectively guides the model by enriching our existing prompt, as illustrated in *Figure 11.1*:

![Figure 11.1: Few-shot learning prompt enrichment](img/B31534_11_01.png)

Figure 11.1: Few-shot learning prompt enrichment

By using this approach, the model adapts to produce outputs that align with the examples provided, effectively *specializing* in the given task.

## LLMs specialization

A **specialization** for LLMs focuses on a specific task or a set of closely related tasks. Here are some examples of specializations you might want your model to develop:

*   Generating completion code that follows a specific coding style
*   Creating a unit test suite that covers key scenarios such as happy paths, bad inputs, edge cases, and error handling
*   Assessing the quality of a function’s docstring
*   Refactoring `for` loops into comprehensions

We typically identify a specialization as either a single system prompt or a set of closely related system prompts, each incorporating the surrounding context and a single-task focus. These tasks are generally non-trivial for an LLM, such as code completion to reverse a string, requiring additional effort in prompt crafting, such as prompt engineering or fine-tuning.

For certain tasks, few-shot learning can be particularly effective. For example, if refactoring `for` loops into comprehensions never involves more than two levels of nesting, providing a few examples in the prompt may be sufficient to achieve reliable results.

However, for deeper specializations, such as breaking longer functions into helper functions to improve code quality, we may need to incorporate a larger set of training examples with the desired output, rather than just a few. We might include examples of naming conventions and indentation. Some examples may show the extraction of code blocks into helper functions, and others may show how to eliminate unnecessary explanations that come along with the code. Including all these examples directly in the prompt increases the prompt’s length and, therefore, the cost associated with the input token length. It also makes it harder to maintain.

## Fine-tuning an LLM

**Fine-tuning** a model is a process that aims to achieve better outputs by using a pre-trained model such as GPT-4o mini and training it toward a specialization using a small set of **training examples** that depict the intended output. The fine-tuning process adjusts the model’s parameters (or **weights**, as discussed in *Chapter 6*) to achieve the desired outcomes shown in the provided examples. This specialization process is shown in *Figure 11.2*:

![Figure 11.2: Leveraging fine-tuning for a better output](img/B31534_11_02.png)

Figure 11.2: Leveraging fine-tuning for a better output

The specialization process uses the crafted training examples to fine-tune the LLM, resulting in a new LLM that is ready to be prompted without requiring further examples in the prompts.

## Favoring fine-tuning over prompt engineering

Based on studies, and confirmed with our experience, fine-tuning requires more training examples than few-shot learning because the examples are retraining the model’s parameters, rather than simply being part of the prompt. In this chapter, we use 15 examples, which is slightly above the OpenAI API’s minimum of 10 for initiating a fine-tuning job. For more complex cases, tens or even hundreds of examples may be necessary, which can be time-consuming to find.

Fortunately, for most of our daily coding tasks, we will find that few-shot learning is sufficient where only a few examples are needed. However, for larger-scale projects, or when few-shot learning does not meet our needs, fine-tuning may be a better alternative. Generally, it is good practice to begin with the few-shot technique and turn to fine-tuning only when the results are not satisfactory.

### Task specializing in cleaner code

In *Chapter 7*, we noted that LLMs often include explanations and example usage along with the code. The LLMs also add code comments when function implementations become longer to compensate for less readable code. When working with higher-quality code, we may prefer the model to return only the code without extra explanations. Additionally, rather than relying on comments in lengthy functions, we might want the model to break the logic into smaller, more manageable functions.

This is a perfect use case for fine-tuning since the effort invested in creating a training file of examples is justified as it can be applied to an entire repository using short prompts alone. Later in the book, we will explore how fine-tuning supports advanced refactoring initiatives, such as extracting logging, monitoring, and error-handling responsibilities into separate functions.

Next, we will explore how to experiment with the OpenAI API Playground and observe that the *GPT-4o mini* model requires improvements in its output implementation. Later in the chapter, we will address these improvements through the fine-tuning process.

# Experimenting with the OpenAI API Playground

In this section, we will use OpenAI’s **graphical user interface** (**GUI**) Playground to quickly view our results for a given **preset**, which represents a combination of a model and the selected call parameters. This interface is an excellent tool for rapid experimentation and for comparing models before implementing them programmatically in our software.

To access the Playground, ensure that your OpenAI account has credits applied to unlock *tier 1*, as explained in *Chapter 2*. Then, go to [`platform.openai.com/playground/chat`](https://platform.openai.com/playground/chat). You can also reach it by navigating to the home page, [`platform.openai.com`](https://platform.openai.com), selecting **Playground** from the top-right menu, and then choosing the **Chat** option from the left menu. The opening screen of the Playground is shown in *Figure 11.3*:

![Figure 11.3: Opening screen of the Playground interface for OpenAI](img/B31534_11_03.png)

Figure 11.3: Opening screen of the Playground interface for OpenAI

On this page, we can craft prompts for OpenAI, as introduced in *Chapter 2*, and try different presets. This includes the system and user prompts, along with parameters such as temperature and maximum tokens. Additional parameters include the following:

*   **Top P** is an alternative to the temperature, setting a minimal probability threshold that the model’s output must meet. In some cases, higher values can prevent hallucinations.
*   The **Store logs** checkbox saves the prompt so it can be restored later.

We can also modify the response format and add functions. These topics will be discussed in detail in later chapters of this book.

Note that the experimentation in the Playground is free for tier 1 or higher accounts, but not all models are available. For instance, as of April 2025, *GPT-o1* and *GPT-o1-preview* models are not available in the reasoning models for experimentation. *Figure 11.4* shows the available models.

![Figure 11.4: Available reasoning models in the OpenAI API Playground](img/B31534_11_04.png)

Figure 11.4: Available reasoning models in the OpenAI API Playground

For the examples in this chapter, we will use the *GPT-4o mini 2024-07-18* model, which is cheaper to use with the API compared to the *GPT-o* series models.

## Computing quadratic roots with GPT-4o mini

As a benchmark for the model output, we will evaluate how GPT-4o mini handles implementing functions that extend beyond a few lines of code, such as computing the quadratic roots of the equation ![](img/B31534_11_001.png). To find the roots of this equation, we compute the two values that satisfy the quadratic formula:

![](img/B31534_11_002.png)

In our case, we want to return the roots only when they are real, which occurs when the discriminant ![](img/B31534_11_003.png) is larger than or equal to 0.

To obtain a function implementation that returns the real roots only, we define the function signature:

```

def get_quadratic_roots_only_if_real (a:int, b:int, c:int) -> Tuple[float, float]

```py

We will use this function signature in our prompt to the model. As usual, we will structure our prompt according to the five S’s framework, as introduced in *Chapter 4*, where the system prompt provides the surrounding context and specifies the single task to be completed, and the user prompt includes supplementary details, such as the function signature and a lead-in cue.

For the system prompt, we will add the following instruction:

```

您将提供一个 Python 函数签名用{{{ FUNCTION }}}括起来。您的任务是实现它。

```py

This instruction provides the model with sufficient context for the code completion task using a Python function signature.

For the user prompt, we will ask it to implement the `get_quadratic_roots_only_if_real` function and include the `CODE` lead-in cue:

```

函数定义：{{{def get_quadratic_roots_only_if_real (a:int, b:int, c:int) -> Tuple[float, float] }}}

代码：

```py

The function’s name, `get_quadratic_roots_only_if_real`, signals the model to return the quadratic roots only if they are real.

### Implementing the quadratic roots calculator

A typical approach to computing quadratic roots and returning them if they are real involves the following steps:

1.  Compute the discriminant ![](img/B31534_11_003.png).
2.  Verify that the discriminant is positive so that the roots are real.
3.  Return the two roots if real.

Since this function requires more than just a few lines of code, the LLM is likely to introduce comments within the code and include surrounding explanations with the implementation.

For reference, *Figure 11.5* shows the explanation provided by the model before the actual code implementation.

![Figure 11.5: Base model output with supplementary explanations](img/B31534_11_05.png)

Figure 11.5: Base model output with supplementary explanations

The following is the code output generated by the model:

```

```pypython
import math
from typing import Tuple
def get_quadratic_roots_only_if_real(a: int, b: int, c: int) -> Tuple[float, float]:
    # Calculate the discriminant
    discriminant = b * b - 4 * a * c
    # If discriminant is negative, there are no real roots
    if discriminant < 0:
        raise ValueError("The equation does not have real roots.")
    # Calculate the two solutions using the quadratic formula
    sqrt_disc = math.sqrt(discriminant)
    x1 = (-b + sqrt_disc) / (2 * a)
    x2 = (-b - sqrt_disc) / (2 * a)
    return (x1, x2) 
```

此实现涵盖了所有三个必需步骤：计算判别式、检查实根以及当适当的时候返回两个解。然而，解决方案中包含了冗余的解释和一个注释过多的函数。在本章的后面部分，我们将看到如何通过微调 LLM 来仅返回代码完成任务的代码，从而帮助我们实现更好的结果。

接下来，我们将看到如何准备训练数据以微调 GPT-4o mini 模型。我们稍后将比较这个模型与默认的 GPT-4o mini 模型。

# 制作用于微调的 JSONL 文件

微调模型时遇到的最初挑战之一是收集足够的训练示例。通过 OpenAI 微调模型时，需要至少 10 个训练示例。然而，对于大多数超出琐碎的任务，可能需要数十个甚至数百个示例，具体取决于任务。根据 OpenAI 的官方文档，通常需要 50 个训练示例才能达到满意的结果。

在我们的案例中，我们希望微调一个模型以生成仅包含代码而不包含注释的输出，15 个示例就足够了，正如我们在本章后面将要看到的。在构建我们的训练集时，我们将利用两种技术：类似于少样本学习的期望示例和**对比学习**。对比学习基于上下文学习理念，首先展示一个不正确或不完整的输出，然后是一个额外的用户-助手提示对，提供所需的输出。更多详情，请参阅本章的“进一步阅读”部分。

## 微调文件结构

我们将上传一个 JSONL 文件作为微调过程的训练数据，其中文件中的每一行都是一个有效的 JSON 对象，代表一个训练示例。最小提示应包括系统提示和一个包含用户提示和助手提示的训练示例。每个助手提示根据不希望得到的结果赋予权重 0，对于期望得到的结果赋予权重 1。在以下期望示例中，助手提示的权重为 1，并添加了行间距以提高清晰度：

```py
{"messages": [
  {"role": "system", "content": "You will be provided with a Python function signature enclosed with {{{ FUNCTION }}}. Your task is to implement it."},
  {"role": "user", "content": "FUNCTION: {{{def get_euclidean_distance(x1, y1, x2, y2):}}}\n CODE: "},
  {"role": "assistant", "content": "def get_euclidean_distance(x1, y1, x2, y2): \n return ((x1-x2)**2 + (y1-y2)**2)**0.5", "weight": 1}
]} 
```

这种格式可能看起来很熟悉，因为它类似于在 OpenAI API 调用中使用的 `messages` 参数。然而，在这种情况下，我们给助手消息分配了一个权重。前面的例子是包含在 `fine_tuning.jsonl` 文件中的训练实例，该文件位于 `ch11/fine_tuning.jsonl`，展示了 `get_euclidean_distance` 函数预期的实现方式。

最小训练行模板应如下所示，包含至少一个用户提示和一个助手提示。在这里，同样添加了行间距以提高清晰度：

```py
{"messages": [
{"role": "user", "content": "Your Content Here"},
{"role": "assistant", "content": "Your desired output here", "weight": 1}]} 
```

如果有助于细化专业化，我们还可以包含一个系统提示，正如我们在本章后面将要探讨的。

在对比学习示例中，我们将包括额外的用户提示和助手提示对。第一对表示一个不希望得到的结果，并分配了权重 0，如下所示：

```py
{"messages": 
{"role": "system", "content": "...omitted for brevity..."},
{"role": "user", "content": "FUNCTION: {{{def sum_of_squares(n: int) -> int:}}}\n CODE: "},
{"role": "assistant", "content": "Sure! here is the code:\n\n```python

在这个例子中，我们提供了两组用户和助手消息。最初的助手响应是不理想的，因为它包含了与代码一起的解释性文本，因此被分配了权重 0。第二个用户提示通过明确指示助手只提供代码来纠正这一点，这个响应被赋予了权重 1。

## 策略

构建微调训练文件的一个实用方法是，从期望输出的最简单情况开始，逐渐引入更复杂的示例，以涵盖我们希望模型发展的专业化。虽然我们在[*第八章*中看到的少量示例包括一两个案例，但对于微调，我们将使用 15 个示例，将 7-8 个示例分配给以下每个目标：

+   **仅代码**：正面和对比

+   **无注释**：正面和对比

这些示例足以生成没有周围解释和函数内注释的代码。完整的 JSONL 文件可在本书的存储库中找到，位于`ch11/fine_tuning.jsonl`。接下来，我们将展示每个先前目标的一个示例。

### 仅代码 – 五个训练示例

在这些情况下，我们将包括 1-2 行长度的函数的简单实现。每个示例都由一个用户和助手提示对组成，确保输出仅包含代码。以下是一个示例：

```py
{"messages": [
{"role": "system", "content": "You will be provided with a Python function signature enclosed with {{{ FUNCTION }}}. Your task is to implement it."}, 
{"role": "user", "content": "FUNCTION: {{{def get_arithmetic_mean(a, b)}}}\n CODE: "}, 
{"role": "assistant", "content": "def get_arithmetic_mean(a, b): \n return (a+b)/2", "weight": 1}]} 
```

在这个例子中，我们提供了一个没有周围解释的`get_arithmetic_mean`函数的理想实现。请注意，实际的 JSONL 行不包含额外的换行符。这是一个仅包含一个正例（权重为 1）的训练模式示例。此外，我们还将包括三个关于`get_``euclidean``_distance`、`reverse_string`、`is_even`和`is_odd`函数的示例。

### 对比代码示例 – 三个训练示例

除了提供高质量的示例，我们还可以包括对比示例。这些场景涉及一个初始的助手响应是不理想的，例如在代码中包含解释或注释，随后通过链式请求将输出精炼成更理想版本。链式用户提示应遵循在*第九章*中介绍的最佳实践，例如以下内容：

+   仅包含代码

+   删除代码注释

+   将低级细节提取到函数中

如*第九章*中所述，在构建链式提示时，我们避免使用诸如“*你的答案是错误的!*”之类的多余措辞，因为它不符合*简短*的最佳实践，也没有增加任何价值。相反，我们应该确定助手的输出是否严重错误，或者只需要进行轻微调整。

在第一种情况下，如果输出与预期相差甚远，用户提示应被精炼以产生更理想的结果，并且此示例不应包含在我们的训练数据中。在第二种情况下，如果模型的输出只需要进行轻微的调整，我们应该专注于提供关于必要调整的明确指导，例如指示模型仅返回代码或提取低级细节到辅助函数。这种类型的指示更精确且信息丰富。

例如，以下是一个对比代码训练示例，用于`is_palindrome`的实现，其中第一个助手提示包括解释和代码。此输出标记为权重`0`以表示不可取。随后是一个链式用户提示，指示助手仅返回代码，导致一个改进的实现，其权重为`1`：

```py
{"messages": [
{"role": "system", "content": "...omitted..."},
{"role": "user", "content": "FUNCTION: {{{def is_palindrome(s: str) -> bool:}}}\nCODE: "},
{"role": "assistant", "content": "A palindrome is a word, phrase, or [...] otherwise `False`.\n\n```python\ndef is_palindrome(s: str) -> bool:\n s = s.lower()\n return s == s[::-1]\n```py", "weight": 0},
{"role": "user", "content": "Include code only."},
{"role": "assistant", "content": "def is_palindrome(s: str) -> bool:\n s = s.lower()\n return s == s[::-1]", "weight": 1}]} 
```

最终的助手消息仅包含实现代码，并赋予权重`1`以表示期望的输出。微调文件还包括类似的对比示例，用于`sum_of_squares`和`flatten_list_of_lists`。

### 没有注释的代码 – 五个示例

在这些示例中，我们关注的是超出简单 1-2 行实现的函数，将更复杂的任务分解为低级抽象函数。这种方法提高了主函数的可读性，并消除了对内联注释的需求。例如，考虑`get_reversed_longer_string`的实现，它接受两个字符串作为输入，并返回较长字符串的逆序。它可以结构化为以下形式：

```py
def get_reversed_longer_string(s1:str, s2: str) -> str:
longer_s = get_longer_string(s1, s2)
reversed_longer_s = reverse_string(longer_s) return reversed_longer_s def get_longer_string(s1, s2): return s1 if len(s1) > len(s2) else s2 def reverse_string(s): return s[::-1] 
```

虽然存在更简洁的实现，但它们可能可读性较差。前面的结构使`get_reversed_longer_string`保持清晰，并将实现细节转移到专门的低级函数中。

为了将这种方法包含到我们的训练示例中，我们将添加以下内容：

```py
{"messages": [{"role": "system", "content": "...omitted for brevity..."}, {"role": "user", "content": "FUNCTION: {{{def get_reversed_longer_string(s1, s2):}}}\n CODE: "},
{"role": "assistant", "content": "def get_reversed_longer_string(s1, s2):\n longer_s = get_longer_string(s1, s2)\n reversed_longer_s = reverse_string(longer_s)\n return reversed_longer_s\n\ndef get_longer_string(s1, s2):\n return s1 if len(s1) > len(s2) else s2\n\ndef reverse_string(s):\n return s[::-1]", "weight": 1}]} 
```

这与我们的首选编码风格一致，即把低级功能提取到单独的函数中。同样，我们将包括以下内容的示例实现：

+   `get_max_multiplication_from_lists`

+   `get_maximal_second_element_squared`

+   `get_sum_of_absolute_differences`

+   `get_highest_even`

这五个实现将展示函数中抽象级别的分离，作为微调过程的指南。

### 没有注释的对比示例 – 两个示例

为了完善我们的数据集，我们将包括带有过多注释的初始实现示例，随后是一个经过改进的版本，其中低级细节被提取到单独的函数中。例如，考虑一个函数，它接受一个列表的列表，计算每个子列表中第二个元素的平均值：

```py
get_average_of_second_elements(numbers: List[List[int]]) 
```

这个函数比我们之前的示例涉及更复杂的逻辑，可能会导致带有过多注释的实现。为了引导模型向分离抽象级别的解决方案发展，我们首先提供一个带有内联注释的实现，然后提供一个改进输出的链式提示。一个初始错误的助手响应可能如下所示：

```py
def get_average_of_second_elements(numbers: List[List[int]]) -> float: if not numbers: # Check if the input list is empty
        return 0 second_elements = [sublist[1] for sublist in numbers] # Extract second elements
    return sum(second_elements) / len(second_elements) # Compute the average 
```

虽然这个实现是正确的，但内联注释增加了不必要的冗余。当将这个负面示例包含到我们的数据集中时，我们将其权重设置为`0`。

接下来，我们链式地添加一个用户提示，要求进行改进：

```py
Extract low level details to functions 
```

这导致了一个更简洁的实现：

```py
import statistics def get_average_of_second_elements(numbers: List[List[int]]) -> float:
    second_elements = get_second_elements(numbers) return statistics.mean(second_elements) def get_second_elements(numbers: List[List[int]]) -> List[int]: return [sublist[1] for sublist in numbers] 
```

通过将提取逻辑抽象到单独的函数中，`get_average_of_second_elements` 保持更易读。相应的示例如下：

```py
{"messages": [{"role": "system", "content": "...omitted for brevity..."}, {"role": "user", "content": "FUNCTION: {{{def get_average_of_second_elements(numbers: List[List[int]]):}}}\n CODE: "}, {"role": "assistant", "content": "def get_average_of_second_elements(numbers: List[List[int]]) -> float:\n if not numbers: # Check if the input list is empty\n return 0\n \n second_elements = [sublist[1] for sublist in numbers] # Extract second elements\n return sum(second_elements) / len(second_elements) # Compute the average", "weight": 0},
{"role": "user", "content": "Extract low level details to functions"},
{"role": "assistant", "content": "import statistics\n\n\ndef get_average_of_second_elements(numbers: List[List[int]]) -> float:\n second_elements = get_second_elements(numbers)\n return statistics.mean(second_elements)\n\n\ndef get_second_elements(numbers: List[List[int]]) -> List[int]:\n return [sublist[1] for sublist in numbers]", "weight": 1}]} 
```

此外，我们还将包括一个类似的对比示例 `get_smallest_squared`，使我们的总训练示例达到 15 个。

使用最终的 JSONL 数据集后，我们现在可以使用 OpenAI 的 GUI 进行微调。

# 使用 OpenAI GUI 微调模型

使用 OpenAI 对 LLM 进行微调可以通过 API 调用或通过 OpenAI 的 GUI 进行。在本章中，我们将重点介绍使用 GUI 启动微调工作。

## 微调模型的成本

微调 LLM 有两种类型的成本：

+   **工作成本**：截至 2025 年 4 月，微调模型每 1M 令牌的费用为 $3。例如，前面提供的包含大约 12K 令牌（文件中的 2K 令牌，6 次迭代）的 JSONL 文件微调费用约为 $0.04。模型或训练文件没有相关的存储费用。

+   **应用**：使用微调模型的定价取决于所使用的基模型。例如，基于 GPT-4o mini 的模型的成本为每 1M 输入令牌 $0.30 和每 1M 输出令牌 $1.20，如图 *图 11.6* 所示：

![图 11.6：GPT-4o 模型的微调成本](img/B31534_11_06.png)

图 11.6：GPT-4o 模型的微调成本

截至 2025 年 4 月，使用微调后的 GPT-4o mini 模型的费用是未微调模型的两倍。然而，尽管每令牌的成本更高，但微调后的模型可能更高效，因为其专业化允许更简洁的输入和输出，从而可能降低整体成本。

要检查当前和旧模型的最新定价，请访问 OpenAI 的定价页面：[`openai.com/api/pricing/`](https://openai.com/api/pricing/)。

考虑到这些成本，我们现在可以继续启动微调过程。

## 启动微调工作

我们可以直接通过 OpenAI 的 API GUI 使用我们的 JSONL 文件进行微调。虽然微调也可以通过编程方式进行，但我们将重点介绍 GUI 方法，因为这是迄今为止最常见的方法。

要启动工作，请访问 OpenAI 的平台主页 [`platform.openai.com/`](https://platform.openai.com/)，点击右上角的 **仪表板**，然后从左侧菜单中选择 **微调**，如图 *图 11.7* 所示：

![图 11.7：OpenAI API 平台中的微调页面](img/B31534_11_07.png)

图 11.7：OpenAI API 平台中的微调页面

要开始一个新的微调工作，请点击屏幕右上角的 **创建** 按钮。这将打开设置弹出窗口，如图 *图 11.8* 所示：

![图 11.8：微调工作弹出窗口](img/B31534_11_08.png)

图 11.8：微调工作弹出窗口

我们使用的微调设置如下：

+   **方法**：**监督**模式。根据我们的经验，这是进行编码风格专业化的最有效方法。

+   **基础模型**: **gpt-4o-mini 2024-07-18** (或最新可用的迷你模型)。此模型为我们提供的成果足够，且成本效益高。

+   **训练数据**：本章前面介绍的 JSONL 文件。

+   **后缀**（可选）：此部分附加到模型名称上以供识别，且不需要在调优作业中唯一。我们添加了 `clean-code` 后缀以供未来参考。

现在，我们可以通过点击 **创建** 来开始调优作业。

使用 15 个训练示例，整个过程应大约需要五分钟来完成。一旦完成，将显示成功消息，如图 *图 11.9* 所示：

![图 11.9：调优作业成功完成](img/B31534_11_09.png)

图 11.9：调优作业成功完成

调优作业处理了 12,500 个标记，运行了六个迭代（或 **epoch**）的我们的文件，该文件包含大约 2,000 个标记。调优模型可以在任何 OpenAI API 调用中使用或通过游乐场访问，我们将在本章后面探讨。

要监控调优作业的成本，导航到 OpenAI 使用页面 [`platform.openai.com/usage`](https://platform.openai.com/usage)，滚动到 **支出类别**，并查看调优费用，如图 *图 11.10* 所示：

![图 11.10：调优过程中产生的费用](img/B31534_11_10.png)

图 11.10：调优过程中产生的费用

在这里，我们可以看到使用 15 个训练示例和 12K 个标记进行模型调优的总费用为 $0.04。

### 使用调优模型

调优模型可以通过 OpenAI 游乐场或编程方式访问。在 *图 11.9* 中，OpenAI 为我们的调优模型在 **输出模型** 下给出了正式名称，格式如下：

```py
ft:{base model}:{account name}:{fine-tuning suffix}:{id} 
```

例如，我们的模型名称在此处显示，但您的模型名称可能不同：

```py
ft:gpt-4o-mini-2024-07-18:pazpaz-the-coder:clean-code:B5Ayo5q1 
```

要在代码中使用调优后的模型，替换标准模型引用：

```py
completion: openai.ChatCompletion = (
    client.chat.completions.create(
        model="gpt-4o-mini",
        messages=[{...])) 
```

使用调优模型的更新调用将如下所示：

```py
completion: openai.ChatCompletion = (
    client.chat.completions.create(
        model="ft:gpt-4o-mini-2024-07-18:pazpaz-the-coder:clean-code:B5Ayo5q1",
        messages=[{...] )) 
```

调优模型也可在 OpenAI 游乐场中找到，如图 *图 11.11* 所示：

![图 11.11：游乐场模型，包括我们的调优模型](img/B31534_11_11.png)

图 11.11：游乐场模型，包括我们的调优模型

在游乐场界面中，我们可以将其结果与基础模型进行比较，我们将在下一节中探讨。

# 比较我们的结果

现在我们已经调优了我们的自定义模型，我们可以评估其输出与基础模型输出的比较。为此，导航到 OpenAI 游乐场，[`platform.openai.com/playground/chat`](https://platform.openai.com/playground/chat)，选择 **gpt-4o-mini-2024-07-18** 作为基础模型，然后点击 **比较**，如图 *图 11.12* 所示：

![图 11.12：选择基础模型进行对比的游乐场比较](img/B31534_11_12.png)

图 11.12：选择基础模型进行比较的游乐场比较

接下来，添加微调模型，如图*图 11.13*所示：

![图 11.13：添加用于比较的模型](img/B31534_11_13.png)

图 11.13：添加用于比较的模型

我们将使用本章早期提到的相同系统消息，并将其应用于两个模型：

```py
You will be provided with a Python function signature enclosed with {{{ FUNCTION }}}. Your task is to implement it. 
```

接下来，我们将输入本章早期提到的相同用户消息：

```py
FUNCTION: {{{def get_quadratic_roots_only_if_real(a:int, b:int, c:int) -> Tuple[float, float] }}}
CODE: 
```

通过点击**运行**，我们可以运行比较，生成两个模型的响应。基础模型的输出包括解释和内联注释，而微调模型提供了一个更结构化的实现，如图*图 11.14*所示：

![图 11.14：比较基础模型（左）和微调模型（右）](img/B31534_11_14.png)

图 11.14：比较基础模型（左）和微调模型（右）

微调模型返回了一个更干净的实现，将计算抽象为单独的函数，保持了主要函数的简洁和可读性。以下是我们提出的完整实现：

```py
def get_quadratic_roots_only_if_real(a: int, b: int, c: int) -> Tuple[float, float]:
    discriminant = calculate_discriminant(a, b, c) if discriminant < 0: raise ValueError("Complex roots") return calculate_quadratic_roots(a, b, discriminant) def calculate_discriminant(a: int, b: int, c: int) -> float: return b**2 - 4*a*c def calculate_quadratic_roots(a: int, b: int, discriminant: float) -> Tuple[float, float]:
    root1 = (-b + discriminant**0.5) / (2*a)
    root2 = (-b - discriminant**0.5) / (2*a) return root1, root2 
```

此输出符合我们的微调目标，即在保持主要函数`get_quadratic_roots_only_if_real`清晰的同时，将计算分离到辅助函数中。与微调模型生成的 179 个 token 相比，基础模型生成了 535 个 token。尽管微调模型的每 token 成本更高，但最终它更经济高效。

总结来说，我们成功地将模型微调以专门返回干净的代码输出。这种有针对性的专业化是通过 15 个 JSONL 示例实现的，结合了正对比学习来引导模型的行为。

微调使我们能够针对特定任务调整预训练的 LLM，这使得它在自动化和大规模编码项目中特别有价值。在后面的章节中，我们将探讨进一步改进微调的方法，例如通过细化训练数据来将验证逻辑与核心功能分开。

### 行动中的微调

目前，我们只使用两个微调模型进行编码任务。第一个是我们在本章中构建的代码实现，提供了对新实现的不同视角。另一个是用于维护文档字符串，确保函数的代码与其文档字符串保持一致。对于范围更窄的任务，通常少量的学习就足够且更可取，因为它需要的努力更少。一般来说，只有在简单的提示工程技术无效或项目在仓库范围内运行时，才会考虑微调，这使得投资变得值得。

我们鼓励您经常尝试提示工程和微调。在本书的下一节中，我们将介绍额外的**软件开发生命周期**（**SDLC**）用例，您可以直接将其应用于您的代码库。

# 摘要

在本书的第二部分，我们更深入地探讨了 LLM。我们解释了它们是如何工作的，它们擅长什么，以及如何利用提示工程技术以获得更有效的结果。我们还涵盖了评估其输出的策略，以确保可靠性。

本章将少样本学习的概念进一步推进，通过展示如何微调一个 LLM 以专门针对给定任务。通过正例和对比训练示例，我们引导模型仅根据它们的签名生成函数实现，返回不带内联注释的干净代码。这种方法可以更广泛地应用于生成单元测试套件、维护文档字符串质量或重构整个存储库中的`for`循环等任务。

通过对 LLM、提示工程和输出评估的更深入理解，我们现在拥有了成为超级编码者的基本工具。我们可以确定给定任务的最佳工具，无论是 ChatGPT、OpenAI API 还是 Copilot，并使用最佳实践和高级技术来制定最有效的提示。此外，我们现在有了自信地评估模型输出质量的技能。

在本书的第三部分，我们将应用这些知识到高级 SDLC 任务中。我们将探讨 GenAI 如何在文档、测试、为运行时和内存效率扩展应用程序、日志记录、监控和错误处理等领域提供帮助。一些任务将依赖于与编码相关任务的五个 S 框架，而其他任务则需要更高级的提示工程策略或微调以达到最佳效果。

# 测验时间

在你进入下一章之前，请确保你能自信地回答以下问题：

**问题 1**：何时微调是一个好的方法？

**答案**：微调对于需要一致执行重复性任务的大型项目有益，例如从签名生成函数实现，同时遵循特定的编码标准。而不是在每个请求中依赖少样本学习或复杂的提示工程技术，微调允许将专门化过程与提示分离，使其更容易维护，在某些情况下，成本效益更高。

**问题 2**：微调涉及哪些成本？

**答案**：微调涉及两种类型的成本：

+   **训练成本**：运行微调作业时产生的一次性成本。

+   **使用成本**：与基础模型相比，微调模型通常在输入和输出方面每 token 的成本更高。例如，使用 GPT-4o mini，微调模型的使用成本是基础模型的两倍。

然而，微调的真实成本在于需要投入时间和精力来仔细构建训练示例，以确保模型与所需的专门化保持一致。

**问题 3**：为什么微调比少样本学习需要更多的训练样本？

**答案**：微调中的专业化过程与少样本学习在本质上有所不同。在少样本学习中，示例只是简单地包含在提示中，指导模型而不改变其内部参数。

另一方面，微调调整模型的权重以与期望的行为相一致。鉴于基础模型是在大量数据上预训练的，因此需要数十个甚至数百个微调示例与原始训练规模相比相对较小。

# 进一步阅读

要了解更多关于本章涵盖的主题，请查看以下资源：

+   Brown, T. B., Mann, B., Ryder, N., Subbiah, M., Kaplan, J., Dhariwal, P., ... & Amodei, D. (2020). *Language Models are Few-Shot Learners*. OpenAI. Retrieved from [`arxiv.org/abs/2005.14165v4`](https://arxiv.org/abs/2005.14165v4)

+   对比学习的 Deepchecks：[`www.deepchecks.com/glossary/contrastive-learning/`](https://www.deepchecks.com/glossary/contrastive-learning/)

+   OpenAI API 微调：[`www.datacamp.com/tutorial/fine-tuning-large-language-models`](https://www.datacamp.com/tutorial/fine-tuning-large-language-models)

+   OpenAI API 请求参数：[`platform.openai.com/docs/api-reference/responses/create`](https://platform.openai.com/docs/api-reference/responses/create)

+   LLMs 的数据营微调教程：[`www.datacamp.com/tutorial/fine-tuning-large-language-models`](https://www.datacamp.com/tutorial/fine-tuning-large-language-models)

|

#### 现在解锁本书的独家优惠

扫描此二维码或访问 [packtpub.com/unlock](http://packtpub.com/unlock)，然后按书名搜索。 | ![白色背景上的二维码 AI 生成的内容可能不正确。](img/Split-B-PEN-Unlock-QR.png) |

| *注意：在开始之前，请准备好您的购买发票。* |
| --- |

# 第三部分

# 使用 GenAI 从代码到生产

在本书的第三部分中，我们从简单的编码转向完整的 **软件开发生命周期**（**SDLC**）。我们首先关注编写文档字符串，然后是测试，因为这些几乎是生产就绪代码的必需品。下一个高级主题是按运行时和内存对系统进行应用程序扩展。本部分还将涵盖日志记录、监控和错误处理。

完成这些 SDLC 步骤的技术建立在第二部分中讨论的五 S 框架和高级提示工程技巧之上。

最后一章探讨了当前趋势，包括 vibe coding，并建议 GenAI 领域的下一步可能是什么。

本部分包含以下章节：

+   *第十二章*，*使用 GenAI 记录代码*

+   *第十三章*，*编写和维护单元测试*

+   *第十四章*，*GenAI 用于运行时和内存管理*

+   *第十五章*，*使用 GenAI 上线：日志记录、监控和错误*

+   *第十六章*，*架构、设计和未来*

# 12

# 使用 GenAI 记录代码

在本书的 *第三部分* 中，我们将介绍与 ChatGPT、OpenAI API 和 GitHub Copilot 一起工作时软件开发生命周期（SDLC）的高级实践。通过介绍 *第四章* 中引入的五 S 框架，以及 *第八章* 和 *第九章* 中介绍的提示工程技术，我们将了解如何将我们的 Python 应用程序投入生产。

在本章中，我们将介绍 Python 对象的文档字符串，它已经内置了 GitHub Copilot 的斜杠命令（即 /doc）。我们可以使用这个斜杠命令以纯格式或扩展它以满足特定的文档字符串要求。文档字符串已经是大多数 IDE 的一个功能，作为模板结构，其中参数将以固定的样式进行格式化，但标准模板不包括关于函数或其参数的任何描述性信息，除了它们的名称。GitHub Copilot 通常会为高质量的代码生成完整的文档字符串。

本章涵盖以下主题：

+   介绍软件文档

+   使用 GenAI 编写文档字符串

+   使用 GitHub Copilot、ChatGPT 和 OpenAI API 查找过时的文档字符串

+   实践见解

# 技术要求

要充分利用本章内容，请确保您具备以下条件：

+   GitHub Copilot 账户

+   IDE – 要么是 VS Code 或 PyCharm

+   具有访问 OpenAI API 的 OpenAI 账户

+   访问本书的仓库，可在 [`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI) 找到

+   在 VS Code 或 PyCharm 中设置的虚拟环境

+   OpenAI API 令牌

如需帮助设置 GitHub Copilot 账户，请参阅 *第三章*。有关设置 OpenAI API 访问和令牌生成的说明，请参阅 *第二章*。如果您需要帮助创建 OpenAI 账户或在 IDE 中设置虚拟环境，请参阅 *附录* 以获取详细指南。

# 介绍软件文档

软件工程师不仅编写大量的代码，还需要阅读和理解他人编写的代码。这些代码可能是其他开发人员在同一天编写的，或者是过去几十年维护的遗留系统的一部分。虽然干净、良好的代码是一个关键方面，但代码文档也是与开发人员沟通的基本方式。

软件文档有多种形式，满足不同的需求。技术文档包括源代码中的注释、API 描述、数据库模式以及软件架构图。用户文档是指导最终用户如何使用软件的指南。软件工程过程还增加了关于需求、规范、测试计划、CI/CD 管道、冲刺计划等方面的特定文档。本章重点介绍源代码的文档。

一个一般的指导原则是，文档应该关注“为什么”，而不是“是什么”。也就是说，代码是可读的，人们可以弄清楚它做什么，但代码实现的原因应该是需要记录的内容。其理由是，编写良好的代码对其所做之事是自我解释的，但代码的原因（即为什么）可以通过文档更好地理解。因此，代码文档可以解释代码，提高其可读性，并有助于后续的软件维护。

在 Python 中，代码中的文档约定是 docstring。Docstrings 通常位于 Python 模块、类和方法的开头。其目的是解释它们的功能和它们被包含的原因。Python 的 docstrings 即使只有一行，也用三引号（单引号或双引号）包围。然而，对于最常见的用于记录方法的 docstrings，它们应该包括参数、返回类型以及任何抛出的异常。

Docstrings 有几个不同的用途。首先，它们为模块、类、方法或函数提供开发者的文档。它们可以被编译成正式的文档资源。此外，这些形式的文档可以通过 Python 的`help()`函数访问。使用 docstrings 使代码更容易维护，从而降低了代码的终身成本。

Docstrings 的第二目的是基于**米勒定律**，也称为神奇的数字七加减二。根据乔治·米勒 1956 年的论文([`psychclassics.yorku.ca/Miller/`](https://psychclassics.yorku.ca/Miller/))，它指出人类可以在他们的工作记忆中保留 5 到 9 条信息。试图理解甚至中等长度的 Python 文件的软件开发者必须理解几个方法之间的交互。文档字符串和命名约定有助于快速理解抽象的方法。

虽然文档字符串可能看起来是标准的，但实际上有四种常见的格式。**PEP 257**约定是官方的 Python 标准，由一行没有字符串格式化的文本组成，强调可读性。**Google 风格**是最常见的之一，仍然强调可读性。它使用多行格式化来表示传入的参数、方法返回值和抛出的异常。**NumPy/SciPy 风格**被广泛使用，但主要用于科学软件。它具有与 Google 风格类似的内容，但使用不同的格式。**reStructuredText (reST**)或**Sphinx 风格**比其他风格包含更详细的信息。这种风格由 Sphinx 文档生成器使用，它可以直接从源代码生成 HTML、PDF 和 LaTeX 文档手册，具有完整的超链接和其他高级功能。本章将重点介绍广泛使用的单行**PEP 257**和**Google 风格**，但其他风格可以通过请求特定的文档字符串风格直接支持。我们在*进一步阅读*部分包含了一些资源，这些资源更详细地描述了 Python 的注释风格。

## 使用/explain GitHub Copilot 命令进行操作

作为本章的一个工作示例，我们使用支持在*第十章*中找到的距离计算的 Flask 例程。基本代码在 GitHub 仓库中显示，并在此处复制以供参考：

```py
from flask import Flask, request, jsonify import numpy as np
app = Flask(__name__) @app.route("/distances", methods=["POST"])
def calculate_distance():
    data = request.get_json()
    dist_type = data.get("distance")
    a = np.asarray(data.get("df1"))
    b = np.asarray(data.get("df2")) if a.shape != b.shape: return jsonify({"error": "Matrices must have the same shape"}) if dist_type == "L1":
        dist = np.sum(np.abs(a - b)) return jsonify({"distance": dist}) elif dist_type == "L2":
        dist = np.sqrt(np.sum((a - b) ** 2)) return jsonify({"distance": dist}) else: return jsonify({"error": "Invalid distance type"}) 
```

在 VS Code 中，只需突出显示方法，右键单击并选择 Copilot，然后选择**生成文档**，如图*图 12.1*所示，就可以自动编写文档字符串。请注意，我们已忽略**Copilot**下显示的**生成文档字符串**。该命令是 VS Code 的文档字符串模板方法，它为文档字符串和参数创建占位符，但不使用任何 AI 来编写注释或描述。

![图 12.1：通过突出显示方法和右键单击，Copilot 生成文档字符串](img/B31534_12_1.png)

图 12.1：通过突出显示方法和右键单击，Copilot 生成文档字符串

生成的文档字符串如图*图 12.2*所示。尝试多次后，我们得到了几个文档字符串的变体，其中一些行非常长或格式不同，还有一些包含了不同的信息。无论如何，文档字符串格式有一个简单的单行描述，但其余部分有一个随机的格式，不符合任何风格指南。特别是，文档字符串中的“期望…”部分不清楚。

![图 12.2：GitHub Copilot 为构造不良的函数生成模糊的文档字符串](img/B31534_12_2.png)

图 12.2：GitHub Copilot 为构造不良的函数生成模糊的文档字符串

另一个常见的情况是 GitHub Copilot 生成多行文本作为文档字符串，不包括参数、返回值等。*图 12.2* 在这方面失败了，有两行解释，然后是 expects（`This endpoint expects...`）和 returns（返回值）部分。虽然存在多行和单行文档字符串，但更倾向于单行而不是详尽的描述，尤其是对于低级方法。如果这样的方法需要多行，通常认为将方法重构为多个执行单个任务的更简单的方法是良好的实践。

Copilot 的文档字符串创建通常相当不错，但偶尔也可能出现错误。正如前一个例子中所示，你可能会遇到它表现不佳的情况。其中一些情况是由于底层代码的复杂性造成的。与其修复文档字符串，一个更受欢迎的解决方案是将代码重构为更简单的形式并重新创建文档字符串。在许多情况下，`/explain` 函数非常有信息量。在 *图 12.3* 中，我们通过在同一个函数内部使用 GitHub Copilot 编辑器内联聊天来应用 `/explain`：

![图 12.3：使用 /explain 对 calculate_distance 进行描述，说明了一个复杂的方法](img/B31534_12_3.png)

图 12.3：使用 /explain 对 calculate_distance 进行描述，说明了一个复杂的方法

在 GitHub Copilot 聊天中，使用 `/explain calculate_distance()` 命令也有类似的功能，它通常会返回更详细的解释。尽管两者都提供了清晰的解释，但内容在技术上比较复杂，这就是我们建议按照以下方式重构代码的原因：

```py
import numpy as np from flask import Flask, request, jsonify
app = Flask(__name__) @app.route("/distances", methods=["POST"])
def calculate_distance():
    a, b, dist_type = parse_request_parameters(request)
    dist_func = {"L1": get_manhattan_dist, "L2": get_euclidean_dist}.get(dist_type)
    dist = dist_func(a, b) return jsonify({"distance": dist}) def parse_request_parameters(request):
    data = request.get_json()
    a = np.array(data.get("df1",))
    b = np.array(data.get("df2",))
    dist_type = data.get("distance") return a, b, dist_type def get_manhattan_dist(a: np.ndarray, b: np.ndarray) -> float: return np.sum(np.abs(a - b)) def get_euclidean_dist(a: np.ndarray, b: np.ndarray) -> float: return np.sum((a - b) ** 2) 
```

本节介绍了一种指导 GenAI 编写文档字符串的方法。下一节将提供其他方法。

# 使用 GenAI 编写文档字符串

本节描述了为单个方法以及整个 Python 文件创建文档字符串的不同技术。文档字符串可以提高代码的可读性，并且通常作为组织**持续集成/持续开发**（**CI/CD**）流程的一部分而被要求。使用 GenAI 创建文档字符串可以加快软件开发过程的速度。

## 单个方法的文档字符串

在 VS Code 中生成文档字符串的最简单方法是在方法签名之后的空白行上简单地输入三个双引号“““或等效的单引号，如图 *图 12.4* 所示，结果在下面的代码块中显示，可以通过按 tab 键接受：

![图 12.4：使用三个单引号或双引号发起对文档字符串的请求](img/B31534_12_4.png)

图 12.4：使用三个单引号或双引号发起对文档字符串的请求

```py
def get_euclidean_dist(a: np.ndarray, b: np.ndarray) -> float: '''Calculates the squared Euclidean distance between two arrays.'''
    return np.sum((a - b) ** 2) 
```

如我们所见，它描述了该方法，但这是 **PEP 257** 风格的最简单形式，只有一行字符串，没有参数或返回值。

如果我们想要不同的文档字符串风格，可以使用 Copilot 编辑器内联聊天（`/doc Google style`）或任何其他指定的风格请求。*图 12.5* 展示了 Google 风格的结果。

![图 12.5：使用内联 /doc Google style 的 Google 风格文档字符串](img/B31534_12_5.png)

图 12.5：使用内联 /doc Google style 的 Google 风格文档字符串

这种使用在线编辑器内联聊天的方法不会为文件中的所有方法创建文档字符串。接下来将讨论在文件级别工作的其他技术。

类似地，使用 GitHub Copilot 聊天功能，我们可以突出显示单个方法，例如 `get_``euclidean``_dist`，并使用 `/doc Google style` 命令请求 Google 风格的文档字符串。如图 12.6 左侧所示，原始（上方）和新（下方）的文档字符串展示了保留或撤销更改的选项。

![图 12.6：使用 GitHub Copilot 聊天在单个方法上更改到 Google 风格](img/B31534_12_6.png)

图 12.6：使用 GitHub Copilot 聊天在单个方法上更改到 Google 风格

## 整个文件的文档字符串

GitHub Copilot 和 ChatGPT 可以通过聊天模式一次性为单个文件中的所有方法生成文档字符串，这非常有用。这取决于你使用的 VS Code 或 PyCharm 版本，可能不适用于内联聊天，因此生成的代码可能需要在聊天窗口中复制并粘贴回代码库。我们发现在截止日期前尝试提交代码时，这种方法很有用。然而，在实践中，我们建议与代码一起编写文档字符串，因为生成式 AI 应该经过验证，这最好在编写代码时完成。稍后的部分，“使用 GitHub Copilot、ChatGPT 和 OpenAI API 查找过时的文档字符串”将描述策略。

第一步是请求 GitHub Copilot 为你的当前 Python 文件编写文档字符串，如图 12.7 所示。我们将使用之前相同的代码，使用基于 Flask 的距离计算。

![图 12.7：GitHub Copilot 聊天请求生成整个文件的文档字符串](img/B31534_12_7.jpg)

图 12.7：GitHub Copilot 聊天请求生成整个文件的文档字符串

上传或粘贴文件后，结果将在以下代码块中显示。结果出现在聊天中，必须从其中复制到代码开发窗口。我们没有指定文档字符串的类型，它可能默认为 Google 风格或 `/doc Google style` 的等效风格。通过将提示修改为 `/doc single line style`，代码将生成相应的单行文档字符串。这两种版本都包含在这本书的 GitHub 仓库中。

```py
from flask import Flask, request, jsonify
app = Flask(__name__) @app.route("/distances", methods=["POST"])
def calculate_distance(): """Calculate distance between two vectors.""" a, b, dist_type = parse_request_parameters(request)
    dist_func = {"L1": get_manhattan_dist, "L2": get_euclidean_dist}.get(dist_type)
    dist = dist_func(a, b) return jsonify({"distance": dist}) def parse_request_parameters(request): """Parse and validate request parameters.""" data = request.get_json()
    a = np.array(data.get("df1",))
    b = np.array(data.get("df2",))
    dist_type = data.get("distance") return a, b, dist_type def get_manhattan_dist(a: np.ndarray, b: np.ndarray) -> float: """Calculate Manhattan distance."""
    return np.sum(np.abs(a - b)) def get_euclidean_dist(a: np.ndarray, b: np.ndarray) -> float: """Calculate Euclidean distance."""
    return np.sum((a - b) ** 2) 
```

![](img/3.png)**快速提示**：使用 **AI 代码解释器** 和 **快速复制** 功能增强你的编码体验。在下一代 Packt Reader 中打开这本书。点击 **复制** 按钮

（**1**）快速将代码复制到您的编码环境，或点击**解释**按钮

（**2**）让 AI 助手为您解释一段代码。

![白色背景，黑色文字的 AI 生成内容可能不正确。](img/image_%282%29.png)

**![](img/4.png)** **新一代 Packt 阅读器**随本书免费赠送。扫描二维码或访问 packtpub.com/unlock，然后使用搜索栏通过名称查找此书。请仔细核对显示的版本，以确保您获得正确的版本。

![白色背景上的二维码，AI 生成内容可能不正确。](img/Split-B-PEN-Unlock-QR.png)

使用这些方法，我们可以为单个方法或整个文件创建文档。重构代码经常导致代码和 docstrings 不同步的问题。下一节将讨论克服这个问题的策略。

# 使用 GitHub Copilot、ChatGPT 和 OpenAI API 查找过时的 docstrings

软件工程师之间常见的辩论之一是，在编写代码时还是在代码稳定后编写文档。一种观点是，docstring（以及测试用例）应该同时编写。主要论点是，当开发者正在处理代码的逻辑并理解其目的时，代码的意图最为清晰。问题是，随着代码的常规重构，docstring 注释和测试用例必须进行适应，使得原始版本变得过时。另一种观点是，文档可以也应该在代码稳定后编写，以最大限度地减少注释的重写。

新一代 GenAI 技术使得辩论变得无关紧要，因为它提供了两种解决方案。第一种解决方案简单来说就是重新生成和更新方法或文件级别的所有注释。上一节描述了这种策略。我们可以使用 GitHub Copilot 或 ChatGPT 为整个文件编写 docstrings，这将更新或重新编写所有 docstrings。

第二种策略更为具体，因为它可以检测过时或**陈旧**的注释，以便手动或自动调整这些注释。这种方法的优点是，可以更新个别方法，而不会改变之前生成或验证的注释。如果我们已经单独编写、验证或以其他方式投入精力在 docstrings 上，我们不希望它们被覆盖。

对于注释，我们已根据之前的示例创建了两个版本的欧几里得距离，通过复制并修改代码来实现。新代码在此处显示。如您所见，第一种方法返回欧几里得距离，第二种方法返回欧几里得距离的平方，但 docstrings 尚未更新，实际上由于我们的复制粘贴方法，它们是相同的。

```py
def get_euclidean_dist(a: np.ndarray, b: np.ndarray) -> float: """Return the squared Euclidean (L2) distance between two arrays."""
    return np.sqrt(np.sum((a - b) ** 2)) def get_euclidean_squared_dist(a: np.ndarray, b: np.ndarray) -> float: """Return the squared Euclidean (L2) distance between two arrays."""
    return np.sum((a - b) ** 2) 
```

使用 GitHub Copilot 或 ChatGPT，我们可以简单地询问是否有任何 docstrings 不同步，如图*12.8*所示。这种方法巧妙地识别了`get_``euclidean``_dist`中的平方根函数调用，并建议更新 docstring：

![图 12.8：使用 GitHub Cop﻿ilot 识别过时的 docstrings](img/B31534_12_8.png)

图 12.8：使用 GitHub Copilot 识别过时的 docstrings

更好的方法是使用 OpenAI API 在文件中单独比较代码和 docstrings。示例代码可以在本章名为`openai_docstring_review.py`的存储库中找到，该代码在`distance_versions.py`文件上运行。下面显示了每个方法的输出结果。

输出解释了逻辑，并提供了 docstring 是否正确对应代码实现的答案。它正确地识别出`get_``euclidean``_dist`方法不匹配。

```py
Function: calculate_distance
Docstring: Calculate distance between two arrays from a POST request. Source: @app.route("/distances", methods=["POST"])
def calculate_distance():
<…code deleted for space…>
Matches: The docstring matches the implementation. Both the docstring and the function's purpose convey that the function is designed to calculate the distance between two arrays based on parameters received from a POST request. Therefore, the conclusion is:
MATCHES: Yes
Function: get_euclidean_dist
Docstring: Return the squared Euclidean (L2) distance between two arrays. Source: def get_euclidean_dist(a: np.ndarray, b: np.ndarray) -> float:
<…code deleted for space…>
Matches: The provided docstring states that the function returns the "squared Euclidean (L2) distance between two arrays," but the implementation actually returns the Euclidean distance (not squared) by taking the square root of the sum of squared differences. Therefore, the docstring does not accurately describe the implementation. Thus, the conclusion is that the docstring does NOT match the implementation. Function: get_euclidean_squared_dist
Docstring: Return the squared Euclidean (L2) distance between two arrays. Source: def get_euclidean_squared_dist(a: np.ndarray, b: np.ndarray) -> float:
<…code deleted for space…>
Matches: The docstring and the function implementation match. The function `get_euclidean_squared_dist` computes the squared Euclidean distance (also known as the L2 distance) between two numpy arrays `a` and `b`, and the docstring accurately describes this functionality. Therefore, the answer is:
MATCHES
Function: get_manhattan_dist
Docstring: Return the Manhattan (L1) distance between two arrays. Source: def get_manhattan_dist(a: np.ndarray, b: np.ndarray) -> float:
<…code deleted for space…>
Matches: MATCHES: Yes 
```

本章介绍了创建 docstrings 的几种技术。它还介绍了寻找过时注释问题的不同策略。在下一节中，我们将根据我们如何使用 GenAI 编写 docstrings 提供建议。

# 实用见解

在 GitHub Copilot、ChatGPT 和 OpenAI API 的选择中，我们发现 Copilot 在编写 docstrings 方面最为方便。在集成环境中进行配对编程的便利性使得请求文档变得简单，而不是在其他地方复制粘贴代码。Copilot 聊天通常可以自行准确定位过时的注释。我们遇到的一个问题是，发送代码到 Copilot 的上下文不可见。如果你复制代码并询问注释是否最新，可能会错过一些未包含在上下文中的方法。这个问题可以通过在原地复制粘贴代码来更新上下文来解决。

我们建议在每个方法编写代码后创建 docstrings，或者在方法代码稳定后至少创建 docstrings，如果不是在每次重构后。我们进一步建议检查 docstring 是否准确反映了实现。在章节开头，我们讨论了文档应该反映为什么编写特定的方法，而不是描述代码的功能。当前技术对于“是什么”是相当合理的，但忽略了“为什么”，这是软件工程师阐述的机会。

# 摘要

文档字符串是维护高质量代码的标准做法。它们使未来的软件读者能够理解代码，这对于调试、功能增强等非常重要。我们建议在编写代码后立即包含文档字符串。GitHub Copilot 提供了多种为单个方法编写文档字符串的方法，包括使用高亮方法上的 Copilot 菜单的三种单引号或双引号。这些方法将产生单行文档字符串、Google 文档字符串风格或其他指定为命令的风格。

编写软件的挑战之一是保持文档字符串与代码同步。所有方法都可以识别代码和文档字符串之间的差异，这是识别可以解决的问题的首选方法。或者，可以在方法或文件级别更新文档字符串，替换任何现有的文档字符串。

# 测验时间

在你进入下一章之前，请确保你能自信地回答以下问题：

**问题 1**：生成代码文档字符串的三个方法是什么？

**答案**：本章讨论的三种方法如下：

1.  GitHub Copilot 可以通过在方法签名之后的行中打开`"""`或`'''`来推荐代码

1.  可以通过突出显示一个方法并使用其菜单来生成文档字符串来调用 GitHub Copilot

1.  可以使用 ChatGPT 或 Copilot 为所有方法添加文档字符串

**问题 2**：保持文档字符串与底层代码一致的两个方法是什么？

**答案**：第一种方法仅仅是覆盖任何文档字符串。这确保了 GenAI 为所有方法生成基于底层代码的文档字符串。如果文档字符串不一致，则会被覆盖。不幸的是，这会覆盖所有之前创建的文档字符串，如果你在编写或检查它们上投入了时间和精力，这可能是不可取的。

第二种方法使用 GitHub Copilot 或 ChatGPT 来询问代码和文档字符串之间是否存在差异。也可以使用 OpenAI API 将每个代码实现与文档字符串进行匹配，并针对每个案例返回它们是否匹配，正如在`openai_docstring_review.py`示例代码中所示。如果文档字符串是最新且经过验证的，那么第二种方法中的任何选项都是首选。

**问题 3**：鉴于 GenAI 可以生成高质量的文档字符串，是否需要检查文档字符串，或者它们可以简单地重新生成？

**答案**：虽然质量通常相当高，但错误的文档字符串可能会让未来的开发者感到困惑。强烈建议使用 GenAI 来节省时间，但使用人类智慧来验证它们是否正确。目前，信任但核实是最好的方法。

# 进一步阅读

+   米勒定律，也称为神奇数字 7 加减 2：[`en.wikipedia.org/wiki/The_Magical_Number_Seven,_Plus_or_Minus_Two`](https://en.wikipedia.org/wiki/The_Magical_Number_Seven,_Plus_or_Minus_Two)

+   文档字符串格式类型：[`www.geeksforgeeks.org/python-docstrings/`](https://www.geeksforgeeks.org/python-docstrings/)

+   进一步格式化文档字符串：[`www.linkedin.com/pulse/python-docstrings-formats-samuel-thomas/`](https://www.linkedin.com/pulse/python-docstrings-formats-samuel-thomas/)

# 免费订阅电子书

新框架、演进的架构、研究动态、生产分解——AI_Distilled 将噪音过滤成每周简报，供与 LLM 和 GenAI 系统动手操作的工程师和研究人员阅读。现在订阅，即可获得免费电子书，以及每周的洞察力，帮助您保持专注并获取信息。

在[`packt.link/TRO5B`](https://packt.link/TRO5B)订阅或扫描下面的二维码。

![白色背景上的二维码 AI 生成的内容可能不正确](img/B31534_Newsletter_NEW.png)

# 13

# 编写和维护单元测试

软件工程的任务可以理解为交付高质量产品，从而为顾客的商业价值做出贡献。在这个技术时代，顾客有着高标准，并要求卓越。

质量的概念在多年中已被以不同的方式解释。然而，以下有两个关键方面：

+   它必须满足用户需求

+   它必须无缺陷

这两个要求通过验证和验证过程得到体现，这些过程断言软件实现了既定的目标，且没有任何缺陷。有许多软件工程技术旨在实现这些目标，包括代码审查、结对编程等，但最常见的是测试。尽管有许多书籍专注于软件测试的艺术和实践，但本章专注于单元测试，这是最广泛使用的方法。“测试驱动开发”（**TDD**）是一种流行的敏捷软件开发方法。与其先编写代码并确保其通过单元测试正确运行，不如先编写单元测试用例，然后编写通过测试的最少代码。该实践的拥护者声称，这种方法具有优越的代码质量和固有的可测试设计。在本章中，我们将把正在开发的主要代码称为**实现代码**，将单元测试称为**测试代码**。

在 GenAI 编码中，有人可能会认为测试比传统编程更为关键。生成式 AI 流程涉及根据其他代码中的注释和/或方法签名来编写代码，这缺乏开发者通常应用的精确性，因为这是为了超级加速、更快地编码而做出的权衡。单元测试作为检查代码是否按测试指定的方式正确运行的检查。结合在编写代码时的代码审查，它提供了一种正确性的检查。

本章致力于使用 GitHub Copilot 和 ChatGPT 来提升我们创建单元测试的能力。在本章中，我们将涵盖以下主题：

+   使用 GenAI 的单元测试

+   数据驱动测试

+   测试驱动开发

+   使用 GenAI 创建示例数据

+   实践见解

# 技术要求

为了充分利用本章内容，请确保您具备以下条件：

+   一个 GitHub 账户

+   访问您首选的 IDE – 要么是 VS Code 或 PyCharm

+   可以访问本书的代码库，位于[`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)

+   在您首选的 IDE、VS Code 或 PyCharm 中设置了一个虚拟环境

如需帮助设置 GitHub Copilot 账户，请参阅*第三章*。有关设置 OpenAI API 访问和令牌生成的说明，请参阅*第二章*。如果您需要帮助创建 OpenAI 账户或在您的 IDE 中设置虚拟环境，请参阅*附录*以获取详细指导。

# 使用 GenAI 的单元测试

GenAI 在编写单元测试方面可以节省大量时间。正如其名所示，每个单元测试都是为了测试代码的单个单元或某个方面。实际上，它们专注于可以分离和独立测试的最小代码片段。共同来看，它们提供了代码在组件级别正确运行的信心，并在代码重构时提供了早期的问题信号。通常，相同的开发者编写代码实现和单元测试。单元测试证明了代码按预期正确运行，也可能有助于定义需求。

单元测试的本质要求对业务和软件需求有深入的理解，以及每个方法如何满足这些需求。必须考虑每个方法预期的功能以及各种边缘情况，并将这些情况纳入测试框架中。这包括对测试框架、方法调用、测试命名、断言形式和实际测试的决定。IDEs 当然可以帮助测试框架，但实际测试需要开发者的时间、思考和可能还需要策略。这些往往成为初级或不太有动力的开发者遇到的障碍，他们可能认为这些与核心软件编码任务无关。当前的 GenAI 工具提供了一种常见的方法，即从现有代码中编写单元测试，或者从现有单元测试中编写代码，这是 TDD。

GenAI 功能不是测试人员或测试的替代品，但它使熟练的测试人员更加高效。开发者可以在更短的时间内编写更多测试，并专注于更复杂的案例。通用的、更简单的单元测试可以由 GenAI 编写，通常准确性很高。然而，如果生成的测试不完整，可以请求或提示 GenAI 创建额外的测试，以提供更好的覆盖率和代码的信心。

作为示例代码，我们使用创建给定文本字符串的 n-gram 的概念，这在 *第六章* 中介绍过。**N-gram** 简单地说，是字符串中任意位置开始的 N 个字母的相邻组，不超出字符串的左右边界。例如，从序列 “abcde” 中得到的 3-gram 是 [“abc”， “bcd”， “cde”]。由于我们想要限制可能的字符范围，我们只考虑了小写字母和空格，但留下了制表符和换行符。大写字母被转换为小写，并且数字和符号都被移除。此外，由于英文类型使用单空格，我们用单个空格替换了所有相邻的空格。此段代码如下：

```py
import re def lowercase_remove_punct_numbers(text, supercharte=True): return re.sub(r'[^a-z\s]', '', text.lower()) def multiple_to_single_spaces(text):
    letters_single_spaces = re.sub(r'\s+', ' ', text) return letters_single_spaces def create_ngrams(text, n) -> list: '''create a list of n-gram tuples from the input text.''' processed_text = lowercase_remove_punct_numbers(text)
    single_space_processed = multiple_to_single_spaces(processed_text)
    u = [single_space_processed[i:i+n] for i in range(len(single_space_processed)-n+1)] return u if __name__ == "__main__":
    text = "This is a sample text $ABC% for creating n-grams." n = 3
    print(create_ngrams(text, n)) 
```

此函数的输出是跨越文本输入字符串的 3-gram 列表：

```py
['thi', 'his', 'is ', 's i', ' is', 'is ', 's a', ' a ', 'a s', ' sa', 'sam', 'amp', 'mpl', 'ple', 'le ', 'e t', ' te', 'tex', 'ext', 'xt ', 't a', ' ab', 'abc', 'bc ', 'c f', ' fo', 'for', 'or ', 'r c', ' cr', 'cre', 'rea', 'eat', 'ati', 'tin', 'ing', 'ng ', 'g n', ' ng', 'ngr', 'gra', 'ram', 'ams'] 
```

如果我们开始单元测试但尚未设置测试框架，可以使用带有提示 `@workspace /setupTests` 的 GitHub Copilot Chat，它将提供选择两个主要框架之一的选项：`pytest` 或 `unittest`，如图 13.1 所示。如果您是第一次安装 unittest，这些说明很有用。

![图 13.1：@workspace /setupTests 提供了选择两个主要测试框架的选项](img/B31534_13_1.png)

图 13.1：@workspace /setupTests 提供了选择两个主要测试框架的选项

要生成单元测试，首先从实现代码中选择一个单一的方法，例如 `lowercase_remove_punct_numbers` 代码。然后，输入 `@workspace /tests generate unit tests` 命令。或者，明确输入目标方法的名称，例如 `@workspace /tests generate unit tests for lowercase_remove_punct_numbers`，到 GitHub Copilot Chat 中。它将首先解释它将生成的测试，然后编写相应的单元测试文件。测试解释如图 13.2 所示：

![图 13.2：GitHub Copilot 提供的测试计划以及方法的代码](img/B31534_13_2.png)

图 13.2：GitHub Copilot 提供的测试计划以及方法的代码

用户将被提示保存生成的测试文件。以下代码显示了输出单元测试可能的样子，尽管它们的顺序和测试数量可能会有所不同：

```py
import unittest from src.ngrams import lowercase_remove_punct_numbers # File: test_ngrams.py
class TestLowercaseRemovePunctNumbers(unittest.TestCase): def test_mixed_input(self):
        text = "Hello, World! 123" expected = "hello world"
        self.assertEqual(lowercase_remove_punct_numbers(text), expected) def test_lowercase_only(self):
        text = "this is a test" expected = "this is a test"
        self.assertEqual(lowercase_remove_punct_numbers(text), expected) def test_punctuation_and_numbers(self):
        text = "!@#$%^&*()1234567890" expected = ""
        self.assertEqual(lowercase_remove_punct_numbers(text), expected) def test_empty_string(self):
        text = "" expected = ""
        self.assertEqual(lowercase_remove_punct_numbers(text), expected) def test_spaces_and_special_characters(self):
        text = "   Hello!! World?? " expected = "   hello   world   "
        self.assertEqual(lowercase_remove_punct_numbers(text), expected) if __name__ == "__main__":
    unittest.main() 
```

测试代码在某种程度上是合理的，因为它主要证明了正则表达式和转换为小写是正确的。可以使用 `python -m unittest test_lowercase_remove_punct_numbers.py` 命令从父级运行测试。

创建测试是一个迭代的过程，由 GenAI 创建的一些测试函数可能是不必要的或错误的。在其他情况下，可能需要添加额外的测试，GitHub Copilot 编辑器内联聊天功能有助于在测试文件内创建这些测试。例如，我们使用`/tests`请求包含 10 位电话号码以证明它们会被正确处理，这在测试文件中产生了内联代码。这个过程在*图 13.3*中展示：

![图 13.3：在测试代码中使用编辑器内联聊天添加新的测试](img/B31534_13_3.png)

图 13.3：在测试代码中使用编辑器内联聊天添加新的测试

在某些情况下，编辑器内联聊天更方便，因为它会直接添加到代码中，而 GitHub Copilot 聊天可能会创建一个新的测试文件。在任何情况下，对单个测试，如电话号码或标点符号的请求，可能会导致多个额外的测试。开发者可以通过点击按钮单独接受或拒绝这些测试。审查测试很重要，因为测试的准确性关系到代码的正确性。

而不是为每个方法单独编写测试，整个文件可以转换为单元测试。使用 GitHub Copilot 聊天和`@workspace /tests create unit tests for ngrams.py`命令，Copilot 通常会，但并不总是，为`ngrams.py`中的每个方法生成一个测试计划。然后，它将创建一个输出测试文件，你必须命名以保存。使用`unittest`约定，每个方法将在该文件中拥有一个或多个单元测试的类。完整的测试集在此处未展示，但可以在书籍 GitHub 仓库中的`test_ngrams.py`文件中找到。

使用注释格式添加额外测试到测试文件的指南。通过输入注释（在 Python 中以`#`开头），GitHub Copilot 会读取注释并建议代码。尽管它应该是等效的，但我们发现这种方法有时不如使用编辑器内联聊天或 GitHub Copilot 聊天准确。如图*图 13.4*所示，预期的答案错误地包含了应该被移除的数字：

![图 13.4：这个由#注释生成的测试，错误地包含了数字](img/B31534_13_4.png)

图 13.4：这个由#注释生成的测试，错误地包含了数字

使用`#test create_ngrams with a 10-digit phone number and make sure the numbers are removed`请求修改测试后，测试中包含的数字减少了。然而，单元测试的正确和错误响应的变异性意味着检查它们必须是验证过程的一部分。

如果我们使用编辑器内联聊天功能重复添加类似形式的邮政编码 12345-6789 的过程，结果会更加令人鼓舞，如 *图 13.5* 所示。它不仅正确地产生了测试，还添加了几个额外的测试。然而，作为一个注意事项，内联聊天并不总是产生准确的测试，有时会错误地包含数字。

![图 13.5：编辑器内联聊天产生的正确测试以及其他测试](img/B31534_13_5.png)

图 13.5：编辑器内联聊天产生的正确测试以及其他测试

本节描述了 GitHub Copilot 如何从实现代码中创建单元测试，无论是针对单个方法还是整个文件。下一节将描述 ChatGPT 如何实现类似的结果。

## 用于测试的 ChatGPT

ChatGPT 也可以用来编写单元测试。以下是一个编写 Python 单元测试的示例提示：

```py
You are a Python testing assistant. Given Python code enclosed within {{{ }}}, generate unit tests using the unittest framework. For each function or method in the code:
1.Create a corresponding test method within a unittest.TestCase subclass. 2.Use meaningful test method names that reflect the function being tested. 3.Include appropriate assertions based on the function's logic and expected behavior. 4.Use mock objects or patching where necessary (e.g., for I/O, APIs, or external dependencies). 5.If a function has multiple logical branches or edge cases, include test cases for them. 6.Do not include the original code in the output—only the test code. 7.Import any modules or classes necessary for the tests to run. 8.Format your output as a complete, valid Python test file using the unittest module. ________________________________________
Input:
python
{{{
# Paste Python code here
}}}
________________________________________
Output: 
```

将此模板应用于 `ngrams.py` 代码产生了七个不同的测试，无需进一步说明。该文件列在 GitHub 仓库中的 `test_ngrams_chatgpt.py` 文件中。创建的测试之一是错误的，并随后失败，如 *图 13.6* 所示。测试错误地建议 `$` 和 `s` 是等效的，而不是用空格替换美元符号。

![图 13.6：ChatGPT 在 ngrams.py 中产生了七个测试中的一个错误测试](img/B31534_13_6.png)

图 13.6：ChatGPT 在 ngrams.py 中产生了七个测试中的一个错误测试

当被提示“是否应该包含额外的测试？”时，ChatGPT 产生了一组额外的测试，如 *图 13.7* 所示，每个测试都包含代码，并提供了将它们转换为代码库的选项：

![图 13.7：当被提示时 ChatGPT 建议的附加测试](img/B31534_13_7.png)

图 13.7：当被提示时 ChatGPT 建议的附加测试

作为单元测试的补充，也可以直接在 ChatGPT 中运行额外的测试，并将其包含在整体测试套件中。GitHub 仓库中的 `test_ngrams_chatgpt_extra.py` 文件显示了生成的测试。除了在 ChatGPT 中运行测试外，该平台还解释了测试失败的原因。*图 13.8* 展示了对测试失败和制表符及换行符处理的宝贵讨论，这可能是失败的测试或原始代码的问题。这种对代码的洞察将有助于提高整体质量。ChatGPT 提出了更改测试并重新运行它们的建议：

![图 13.8：ChatGPT 失败文本的解释](img/B31534_13_8.png)

图 13.8：ChatGPT 失败文本的解释

即使需要多次请求，ChatGPT 在编写单元测试方面显然是有效的。它还可以编写其他类型的测试，例如数据驱动测试，这是下一节的主题。

# 数据驱动测试

GitHub Copilot 或 ChatGPT 提示可以启用数据驱动或随机测试，以补充单元测试覆盖率。使用 Copilot 的`Generate data driven tests for lowercase_remove_punct_numbers`提示生成了以下代码：

```py
import unittest from src.ngrams import lowercase_remove_punct_numbers class TestLowercaseRemovePunctNumbers(unittest.TestCase): def test_data_driven(self):
        test_cases = [ # (input, expected_output) ("Hello, World! 123", "hello world "),
            ("ABCdef", "abcdef"),
            ("1234!@#$", ""),
            ("A1! b2@ C3#", "a b c"),
            ("", ""),
            ("   ", "   "),
            ("Python3.8_is#awesome!", "pythonisawesome"),
            ("No PUNCTUATION", "no punctuation"),
            ("MiXeD CaSe &*^%", "mixed case "),
            ("newline\nTab\tSpace ", "newline\ttab\tspace "),
        ] for input_text, expected in test_cases: with self.subTest(input=input_text): self.assertEqual(lowercase_remove_punct_numbers(input_text), expected) if __name__ == "__main__":
    unittest.main() 
```

此文件可以在本书的 GitHub 仓库中找到，作为`test_data_driven_ngrams.py`。这个例子以及上一节中的单元测试展示了 GenAI 如何从实现代码中创建测试。GitHub Copilot 和 ChatGPT 使用此代码来识别有意义的测试用例，包括许多边缘情况。为了提高覆盖率，可以手动编写额外的测试，或使用 GenAI 半自动编写，或者简单地请求额外的测试。这些单元测试可以像其他类型的测试一样扩展，例如集成测试、性能测试和 A/B 测试。

如这两节所述，可以使用 GenAI 从实现代码中编写单元测试和数据驱动测试。虽然从实现代码中创建测试代码是可行的，但应该考虑先编写测试代码而不是实现代码。这种方法被称为测试驱动开发，将在下一节中描述。

# 测试驱动开发

**测试驱动开发**（**TDD**）是 20 世纪 90 年代由 Kent Beck 提出的**极限编程**（**XP**）敏捷软件开发方法的一个组成部分。他的两本书可以在*进一步阅读*部分找到。TDD 的主要概念是先编写单元测试，然后由于没有代码支持而失败。随后，软件工程师编写代码直到测试通过。普遍认为这种做法可以提高代码设计并增强可测试性。例如 Mäkinen & Jürgen Münch 的研究（[`link.springer.com/chapter/10.1007/978-3-319-03602-1_10`](https://link.springer.com/chapter/10.1007/978-3-319-03602-1_10)）等实证研究通常支持 TDD 的价值。这种方法也使软件工程师专注于通过测试而不是添加其他功能。

是否先编写测试用例还是最后编写，常常成为宗教般的辩论，双方都有虔诚的追随者。我们在此不尝试解决这个问题。如果我们相信通用人工智能（GenAI）总是编写出完美无缺的代码，这些代码精确且干净地满足所有要求，那么使用测试用例还是代码来编写另一个并不重要。Jiri 等人最近在 2024 年发表的一篇 IEEE 研究（[`ieeexplore.ieee.org/document/10685204`](https://ieeexplore.ieee.org/document/10685204)）表明，人类编写的单元测试比 GenAI 编写的单元测试错误更少，但技术正在快速发展，正在缩小这一差距。这让我们陷入了一个困境，即代码可能存在缺陷，测试可能并不完美，但我们仍然需要它们都是准确的。软件工程师更常见的做法是使用 GenAI 编写代码，然后使用 GenAI 编写测试，这反映了他们的开发实践。在测试驱动开发（TDD）中，有潜力使用 GenAI 编写完美的测试，也许使用 GenAI 来证明实现通过了测试和它们认为的要求。实际上，我们可以更进一步，使用 GenAI 迭代并编写满足这些要求的代码。

作为本节的示例，我们将使用两个矩形的交集问题，这个问题简单地识别两个矩形之间的重叠区域。为了简化问题，我们将矩形定义限制为使用两个点——矩形的左下角和右上角的 x 和 y 坐标。在我们的表示法中，矩形表示为(*xll*, *yll,* *xur*, *yur*)，如图*图 13.9*所示：

![图 13.9：相交矩形问题](img/B31534_13_9.png)

图 13.9：相交矩形问题

而不是立即开始编写结果代码，我们将首先考虑各种测试用例，这些用例被分解为以下几类：

1.  相交矩形（*图 13.10*）：

![图 13.10：重叠矩形的示例测试用例](img/B31534_13_10.jpg)

图 13.10：重叠矩形的示例测试用例

1.  非相交矩形（*图 13.11*）：

![图 13.11：非重叠矩形的示例测试用例](img/B31534_13_11.jpg)

图 13.11：非重叠矩形的示例测试用例

1.  无效矩形（*图 13.12*）：

![图 13.12：无效矩形的示例测试用例，这些矩形不符合我们的定义](img/B31534_13_12.png)

图 13.12：无效矩形的示例测试用例，这些矩形不符合我们的定义

作为 TDD 过程的一部分，我们首先使用 GenAI 编写单元测试。使用描述性的测试名称有助于准确创建测试代码。以下代码片段展示了几个测试用例，以说明这一想法（包含 21 个单元测试的完整文件可在本书的 GitHub 仓库中找到，文件名为`test_rectangle_intersection.py`）：

```py
import unittest from rectangle_intersection import rect_intersection_area class TestRectangleIntersectionArea(unittest.TestCase): def test_intersecting_rectangles(self):
        rect1 = (0, 0, 4, 4)
        rect2 = (2, 2, 6, 6) self.assertEqual(rect_intersection_area(rect1, rect2), 4) def test_intersecting_rectangles_swapped(self):
        rect1 = (2, 2, 6, 6)
        rect2 = (0, 0, 4, 4) self.assertEqual(rect_intersection_area(rect1, rect2), 4) def test_non_intersecting_rectangles(self):
        rect1 = (0, 0, 2, 2)
        rect2 = (3, 3, 5, 5) self.assertEqual(rect_intersection_area(rect1, rect2), 0) 
```

为了使测试在 TDD 流程的下一步中适当地失败，我们需要一个存根文件，`rectangle_intersection.py`，包含 `rect_intersection_area(rect1, rect)`，它任意返回 `None`。此代码的示例如下，并存储在同一文件夹中的 `rectangle_intersection.py`。这些名称基于前面测试文件代码开头的 `import` 语句，如下所示：

```py
def rect_intersection_area(rect1, rect): return None 
```

使用 TDD 流程，我们将代码的要求编码为测试。唯一缺少的部分是实际实现。通常，我们会迭代编写实现和运行测试，以确保代码按预期工作。使用 GenAI，我们可以将这个过程替换为向 GenAI 发送请求，以迭代编写代码，直到所有测试通过。我们将讨论如何使用 GitHub Copilot 在 VS Code 和 PyCharm IDE 中实现这一点，然后展示使用 ChatGPT 的 TDD 方法。

## 在 VS Code 中使用 GitHub Copilot 进行 TDD

VS Code 中的 TDD 方法可以说是最直接的。首先，我们确保 `rectangle_intersection.py` 和 `test_rectangle_intersection.py` 都已打开，然后运行后者单元测试文件。然后，我们可以在 Copilot 聊天窗口中使用此命令：

```py
@terminal /fix rect_intersection_area according to the unit test failure 
```

这在相同的聊天窗口中产生了一组更新的代码，我们将其复制粘贴作为 `rectangle_intersection.py` 实现的替代。如下所示：

```py
def rect_intersection_area(rect1, rect2): """
 Calculate the area of intersection between two rectangles.
 Each rectangle is represented as a tuple (x1, y1, x2, y2):
 - (x1, y1): bottom-left corner
 - (x2, y2): top-right corner
 """
    # Calculate the overlapping region x_overlap = max(0, min(rect1[2], rect2[2]) - max(rect1[0], rect2[0]))
    y_overlap = max(0, min(rect1[3], rect2[3]) - max(rect1[1], rect2[1])) # If there is an overlap, calculate the area
    return x_overlap * y_overlap 
```

对新实现运行相同的单元测试将失败的测试数量从 21 减少到 9。大多数失败是由对无效矩形未抛出异常引起的。这些异常包含在测试中，但被 GenAI 忽略了。

我们使用相同的 `/fix` 命令重复了该过程，以产生代码实现的下一个迭代版本，但错误仍然存在。在某些情况下，运行该过程两三次可以解决错误。在其他情况下，我们需要手动修改 `/fix` 命令，以提供更明确的指示：

```py
@workspace /fix rectangle_intersection_area according to the unit test failure and be sure to raise ValueError for invalid rectangle dimensions 
```

生成的实现通过了所有单元测试，如下所示：

```py
def rect_intersection_area(rect1, rect2): """
 Calculate the area of intersection between two rectangles.
 Each rectangle is represented as a tuple (x1, y1, x2, y2):
 - (x1, y1): bottom-left corner
 - (x2, y2): top-right corner
 """
    # Ensure the rectangles are valid
    if rect1[0] >= rect1[2] or rect1[1] >= rect1[3]: raise ValueError(f"Invalid rectangle dimensions for rect1: {rect1}") if rect2[0] >= rect2[2] or rect2[1] >= rect2[3]: raise ValueError(f"Invalid rectangle dimensions for rect2: {rect2}") # Calculate the overlapping region x_left = max(rect1[0], rect2[0])
    y_bottom = max(rect1[1], rect2[1])
    x_right = min(rect1[2], rect2[2])
    y_top = min(rect1[3], rect2[3]) # Check if there is an actual overlap
    if x_left < x_right and y_bottom < y_top: return (x_right - x_left) * (y_top - y_bottom) else: return 0  # No overlap 
```

在本节中，我们使用 VS Code 聊天中的一条简单单行命令创建了一个实现。它使用实现代码、单元测试和测试输出直接编写改进的实现代码。

## 在 PyCharm 中使用 GitHub Copilot 进行 TDD

在 PyCharm 中使用 TDD 方法并不像在 VS Code 中那样简单。截至 2025 年 1 月，GitHub Copilot 无法访问 PyCharm 的终端窗口，这意味着它无法直接访问失败的单元测试。失败的测试输出通知 Copilot 在实现中需要修复的内容，因此这是一个关键组件。作为解决方案，我们可以将失败的错误消息粘贴到 GitHub Copilot 聊天窗口中：

```py
CONTEXT: You will be given an error message enclosed in {{{ERROR}}}. TASK: Fix the implementation of rectangle_intersection_area _mean so it passes all tests. ERROR: {{{ ... <omitted for brevity> ... }}}
FIXED CODE: 
```

无论是在内联聊天窗口还是聊天窗口中，这个提示都应该生成一个完全功能的实现，该实现可以通过单元测试。

对于使用 PyCharm 的 TDD，我们需要在聊天中使用更完整的模板调用，以传递失败的单元测试的输出。有了这些信息，以及实现和测试代码，新的实现代码版本旨在解决这些问题并通过单元测试。ChatGPT 也可以采用类似的方法，这将在下文中描述。

## 使用 ChatGPT 进行 TDD

作为 TDD 过程的一部分，ChatGPT 还可以根据现有实现代码、单元测试代码以及单元测试执行的错误或结果，生成基于组合的改进实现代码。我们使用三重括号包围每个这些组件：

```py
CONTEXT: You are provided with
1\. Python function enclosed with {{{ FUNCTION }}} that has a bug. 2\. Test suite code enclosed with {{{ UNIT TESTS }}}. 3\. Error message enclosed with {{{ ERROR }}}. TASK: Fix the function implementation
FUNCTION: {{{def rect_intersection_area(rect1, rect2):
    return None
 }}}
UNIT TESTS: {{{ ... omitted for brevity ... }}}
ERROR: {{{ ... omitted for brevity ... }}}
CODE: 
```

在这个例子中，ChatGPT 生成了以下输出代码，它与 GitHub Copilot 的输出相似，但略有不同。ChatGPT 解释了实现方式，并且所有创建的测试在第一次迭代中都通过了。

```py
def rect_intersection_area(rect1, rect2):
    x1_1, y1_1, x2_1, y2_1 = rect1
    x1_2, y1_2, x2_2, y2_2 = rect2 # Validate input rectangles
    def is_invalid_rect(x1, y1, x2, y2): return x1 >= x2 or y1 >= y2 if is_invalid_rect(x1_1, y1_1, x2_1, y2_1) or is_invalid_rect(x1_2, y1_2, x2_2, y2_2): raise ValueError("Invalid rectangle with non-positive width or height") # Find intersection bounds inter_left = max(x1_1, x1_2)
    inter_right = min(x2_1, x2_2)
    inter_bottom = max(y1_1, y1_2)
    inter_top = min(y2_1, y2_2) # Check if rectangles intersect
    if inter_left >= inter_right or inter_bottom >= inter_top: return 0
    # Compute and return intersection area
    return (inter_right - inter_left) * (inter_top - inter_bottom) 
```

如果测试没有通过，新的代码需要复制并粘贴到 IDE 中，替换之前的版本。需要对新的代码重新运行单元测试。需要将修改后的实现代码和由此产生的单元测试错误再次复制到 ChatGPT 模板中。

TDD 方法的优势在于它断言实现是正确的，基于代码通过了单元测试的事实。在这个简单示例中生成的代码相当合理，但更复杂的任务可能会生成质量较低的函数代码。在这种情况下，应该重构代码。然而，有完整的测试集继续证明代码满足功能要求，这要容易得多。

TDD 是否是理想策略仍有争议。没有 TDD，用户会专注于实现，GenAI 当然可以创建合理的测试。正如我们所观察到的，一些测试可能会失败，一些可能表明实现的局限性。软件开发者必须理解所有测试，并提供足够的逻辑覆盖率，以确保对实现的信心。使用 TDD，认知努力在于确保测试足够充分，从而生成代码。如果 GenAI 提供实现，开发者最多需要做的就是重构代码。

无论代码或测试先写，测试通常需要有意义的数据集。下一节将描述如何使用 GenAI 创建真实数据。

# 使用 GenAI 创建样本数据

测试的一个方面是数据的可用性，这些数据代表了你将在野外遇到的那种类型。如果你过去几年参与过创建模拟数据，你一定会欣赏 GenAI 对此问题的方法。新的技术可以创建各种类型的数据，只需一个你需要的特定提示即可。例如，以下提示在 ChatGPT 或 GitHub Copilot 中都有效：

```py
create a table with 10 rows and the following columns:
5 digit integer id called "ID"
first name
last name
address consisting of a number, street name, and whether it is a st., dr. or ave. city
country
disease
age 
```

结果的表格输出如图 13.13 所示，包括典型的名称、地址格式、疾病等。这类数据可以保存到文件中并用于测试。尽管这种数据可以即时生成，但单元测试的目的是创建可重复的测试，以实现一致的结果。测试通常作为 CI/CD（持续集成/持续部署）方法的一部分添加到回归测试包中，并定期重新运行，以确保随着代码版本的演变，过去的错误不会再次发生。因此，数据应被存储和重复使用。

![图 13.13：GitHub Copilot 生成的模拟数据示例表](img/B31534_13_13.png)

图 13.13：GitHub Copilot 生成的模拟数据示例表

当然，数据不仅限于地址，还可以更技术化，例如 `创建一个包含 15 到 25 个核苷酸长度的 3 个序列的 FASTA 文件` 提示，它返回如图 13.14 所示的三个生物信息学 DNA 序列：

![图 13.14：包含三个 DNA 序列的 FASTA 生物信息学序列文件](img/B31534_13_14.png)

图 13.14：包含三个 DNA 序列的 FASTA 生物信息学序列文件

如前所述的输出所示，它建议将文件保存为 `.fasta` 文件。实际上，它可以在任何格式中创建和保存数据，包括表格、JSON、CSV 等。

在脚本编写时，另一个常用的用例是为函数创建一些临时数据，可能在 Jupyter 笔记本中。考虑欧几里得距离方法：

```py
def get_euclidean_dist(a: np.ndarray, b: np.ndarray) -> float: """Return the squared Euclidean (L2) distance between two arrays."""
    return np.sqrt(np.sum((a - b) ** 2)) 
```

GitHub Copilot 使用 `为 get_``euclidean``_distance() 创建样本输入` 提示生成了一些可以直接应用的输入样本，如图 13.15 所示：

![图 13.15：GitHub Copilot 为函数创建非正式测试的示例输入](img/B31534_13_15.png)

图 13.15：GitHub Copilot 为非正式测试创建函数的示例输入

在 TDD（测试驱动开发）过程中，开发者首先编写单元测试代码，然后编写实现代码以通过单元测试。单元测试可以由开发者使用标准的 GenAI 方法编写，以验证实现代码是否符合要求。从 VS Code 或 PyCharm，GitHub Copilot 可以仅从单元测试代码中迭代创建实现代码。ChatGPT 通过提示模板提供类似的功能。下一节将提供有关如何最好地使用 GenAI 方法来完成实现和测试代码的建议。

# 实践见解

测试一直是从“经典 AI”模板到现在的 GenAI 时代的技术焦点。始终存在一种趋势，即先编写代码，然后编写测试，以便使组织接受。这些新的 GenAI 工具肯定可以加快编码过程的速度。检查代码的验证过程不应只是单次视觉检查，而应涉及可以反复应用的单元测试，以断言代码的正确性。

不同的 GenAI 解决方案会产生略微不同的结果，但通常我们更倾向于使用 GitHub Copilot 来创建测试，因为与代码的紧密集成和迭代方法使得在 IDE（无论是 VS Code 还是 PyCharm）内使用单个工具更容易。通过在浏览器中保持相似的测试代码打开，由于额外的上下文，准确性和风格都会得到提升。

无论使用哪种特定的通用人工智能（GenAI）工具，检查实现和测试代码都是至关重要的。使用 GenAI 从实现中创建测试代码或反之亦然有助于最小化错误，因为通过单元测试通过的实现代码至少达到了一级的需求验证。失败的单元测试为重新思考实现和测试代码的需求提供了机会。

# 摘要

在本章中，我们探讨了使用 GenAI 进行测试的各个方面。尽管有许多类型的测试，它们是许多书籍的主题，但最常见的测试是单元测试。在单元测试中，每个测试都应该测试功能的一个单一点，并且应该独立于其他测试。共同地，一套完整的单元测试证明了代码实现按预期工作。如果代码在未来被重构、增强或集成，相同的单元测试将断言功能的正确性。

本章描述了几种从实现中创建测试的方法。GitHub Copilot 和 ChatGPT 都可以用来轻松地为单个方法或整个 Python 文件编写单元测试。这两种技术在一开始提供测试类型和覆盖范围方面都有一些可变性。在某些情况下，测试可能不正确，可能需要额外的提示或手动修正。在其他情况下，提示可能有助于添加更多测试以改进边缘情况的覆盖范围。开发者必须谨慎，确保测试准确捕捉需求，并且足以断言代码的正确性。

TDD（测试驱动开发）是极限编程（Extreme Programming）中的一种方法，其中首先编写单元测试，并且按照定义，这些测试会失败。实现代码被编写以通过所有单元测试。GenAI 可以帮助建议测试代码，特别是当使用描述性的方法名称时。使用一系列测试，GitHub Copilot 或 ChatGPT 可以迭代地自动生成实现代码。这个过程会重复进行，直到单元测试通过。通过首先编写完整的测试集，开发者传达了测试的范围和不同边缘情况下的行为。与生成的实现代码的唯一必要交互可能是重构以提高质量，这可以通过单元测试更容易实现。

本章还涵盖了两个额外主题，涉及为测试丰富数据。GenAI 可以通过合成不同场景来创建更复杂的测试。数据驱动测试为输入和输出创建测试对，以测试多个场景。此外，该技术可以创建适用于广泛学科的逼真测试集。

在下一章中，我们将介绍 GenAI 如何从执行速度和内存管理方面识别容量限制的方法。我们还将展示 GenAI 如何在这些两个约束下优化代码以提高性能。

# 测验时间

在您进入下一章之前，请确保您能够自信地回答以下问题：

**问题 1**：TDD 的优势是什么？

**答案**：TDD，即测试驱动开发，是一种先编写测试，然后编写实现代码的方法论。测试覆盖了所需功能范围和边缘情况，以确保它们符合预期。使用 TDD 确保测试被编写，并且代码（由人类或 GenAI 编写）能够正确运行。实证结果表明，实现通常结构更合理，更易于测试。

**问题 2**：如果软件包含实现和单元测试，是否还需要手动验证？

**答案**：毫无疑问，一套完整的单元测试和正确的实现有助于识别失败或对需求的理解错误。失败的测试很可能是由于测试有缺陷或实现有缺陷，这提供了一个审查需求的机会。虽然测试有助于识别这些问题，但我们观察到许多情况下生成的测试缺乏全面覆盖，并且可能是不正确的。同样，也有许多不正确的实现例子。作者建议除了完整的单元测试外，还应进行手动验证。

# 进一步阅读

+   Kent Beck 关于极限编程的书籍。2000 年。*极限编程：拥抱变化*。

+   Kent Beck 关于测试驱动开发的书籍。2002 年。*通过示例进行测试驱动开发*。

+   *测试驱动开发的影响：经验研究的比较分析*。Simo Mäkinen & Jürgen Münch：[`link.springer.com/chapter/10.1007/978-3-319-03602-1_10`](https://link.springer.com/chapter/10.1007/978-3-319-03602-1_10)

+   *利用大型语言模型进行 Python 单元测试*。Medlen Jiri，Bari Emese，Patrick Medlen。2024 年：[`ieeexplore.ieee.org/document/10685204`](https://ieeexplore.ieee.org/document/10685204)。

|

#### 现在解锁本书的独家优惠

扫描此二维码或访问[packtpub.com/unlock](http://packtpub.com/unlock)，然后通过名称搜索此书。 | ![白色背景上的二维码 AI 生成的内容可能不正确。](img/Split-B-PEN-Unlock-QR.png) |

| *注意：在开始之前，请准备好您的购买发票。* |
| --- |

# 14

# GenAI 用于运行时和内存管理

在大数据、人工智能和密集数据处理的时代，编写良好的 Python 程序的一个基本特征是它们能够有效地管理**内存使用**和**运行时性能**。作为**软件开发生命周期（SDLC）**的一部分，分析我们的程序、预测性能限制并努力在这两方面实现效率是常见的做法。

除了利用传统工具来分析程序性能和解决低效问题外，我们还可以利用**大型语言模型（LLMs）**的**模型掌握能力**来对代码片段进行代码分析、分析最大容量，并优化代码以处理更大的工作负载。

在本章中，我们将检查两个低效实现的例子：一个具有显著运行时开销的斐波那契计算器和一个需要大量内存进行大矩阵统计分析的功能。通过利用提示精确最佳实践和**链式**提示工程技术，我们将展示如何通过 GenAI 应用程序帮助分析性能指标、估计最大容量，并有效地优化代码以处理更大的输入。

本章涵盖的主题包括：

+   介绍时间和空间复杂度分析

+   使用 GitHub Copilot 分析运行时和内存消耗

+   使用 ChatGPT 分析最大容量

+   使用链式提示优化代码

# 技术要求

为了充分利用本章内容，请确保您具备以下条件：

+   GitHub Copilot 账户

+   IDE – VS Code 或 PyCharm

+   具有访问 ChatGPT 和 OpenAI API 的 OpenAI 账户

+   访问本书的仓库，网址为：[`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)

+   在 VS Code 或 PyCharm 中设置虚拟环境

+   OpenAI API 令牌

如需设置 GitHub Copilot 账户的帮助，请参阅*第三章*。有关设置 OpenAI API 访问和生成令牌的说明，请参阅*第二章*。如果您需要创建 OpenAI 账户或在其 IDE 中设置虚拟环境的帮助，请参阅*附录*以获取详细指南。

# 介绍时间和空间分析

在我们当前的技术周期中，大多数公司都在利用大数据和人工智能来改善他们的业务。例如，YouTube 和 TikTok 平台上的视频每天被观看超过十亿次，这产生了推荐和广告价值。在这些情况下，即使存储或计算效率提高 1%，也可能节省数百万美元。

根据*Lamda Labs*，训练生成式预训练转换器模型*GPT-3*需要大约 700 千兆字节的**随机存取存储器（RAM**）和数千个并行工作的强大 Nvidia GPU，累计计算时间相当于 355 年。在实现这些模型时，即使是微小的低效也可能导致巨大的成本，或者在最坏的情况下，造成瓶颈，阻止模型有效运行。

## 程序的运行时间

程序的运行时间指的是在特定硬件配置下，执行源代码中定义的任务所需的时间。程序的运行时间取决于诸如计算复杂度（完成任务所需的操作数）和硬件（如**中央处理器（CPU）**）等因素。

例如，考虑一个使用递归计算斐波那契数的低效实现：

```py
def fibonacci_recursive(n): if n <= 1: return n return fibonacci_recursive(n - 1) + fibonacci_recursive(n - 2) 
```

在这个实现中，每个斐波那契数的计算涉及两次递归调用：一次是前一个数，另一次是前一个数。这些调用中的每一个又触发了两次额外的递归调用，依此类推，直到满足基本条件`n <= 1`。

为了说明这个实现的运行时间增长有多快，以下是在 MacBook Pro 上使用这个实现记录的运行时间示例，该电脑配备了 M1 芯片：

`fibonacci_recursive(5)`的运行时间为：0.000006 秒

`fibonacci_recursive(35)`的运行时间为：1.7051 秒

`fibonacci_recursive(40)`的运行时间为：19.5045 秒

计算`fibonacci_recursive(100)`预计需要 1500 万亿秒，或大约 475,000 年，这使得它完全不切实际。这种指数增长代表了算法设计中最不希望看到的复杂度之一，因为它无论使用什么硬件都保持低效，正如我们现在将要探讨的。

### 运行时复杂度复习

由于计算机的速度各不相同，因此广泛的做法是使用**大 O 符号**来一般性地衡量运行时复杂度，表示为![大 O 符号](img/B31534_14_001.png)。这种符号描述了运行时间相对于输入数据大小的相对缩放。

例如：

+   在长度为![长度](img/B31534_14_002.png)的无序数组中查找最小数具有![复杂度](img/B31534_14_003.png)的运行时复杂度

+   打印长度为![长度](img/B31534_14_002.png)的数组中所有![组合](img/B31534_14_004.png)的元素具有![复杂度](img/B31534_14_006.png)的运行时复杂度。

使用`fibonacci_recursive`计算第 n 个斐波那契数具有![复杂度](img/B31534_14_007.png)的运行时复杂度。

如果您需要进一步复习大 O 符号或对它不熟悉，我们建议检查本章末尾的**进一步阅读**部分。大 O 符号是开发者在应用设计和日常问题解决中的基本概念。

## 程序的空间消耗

程序在执行过程中消耗的 RAM 反映了其内存空间使用情况。例如，一个拥有 16 **千兆字节 (GB)** RAM 的 MacBook Pro 可以容纳大约 25 亿个 float64 值，其中每个 `float64` 占据 8 字节。

考虑以下效率低下的函数 `get_top_video`，该函数将逗号分隔值 (CSV) 文件读取到内存中的 *Pandas DataFrame* 中，并返回平均观看百分比最高的视频：

```py
def get_top_video(path):
    interactions = pd.read_csv(path)
    avg_ratio = interactions.mean(axis=0, skipna=True) return avg_ratio.idxmax() 
```

输入 CSV 文件可能表示如下矩阵，其中每个单元格表示用户观看特定视频的百分比：

|  | video_1 | video_2 | video_3 | video_4 | video_5 | video_6 | ... |
| --- | --- | --- | --- | --- | --- | --- | --- |
| user_1 |  | 0.5 |  |  |  | 1 |  |
| user_2 | 0.1 |  |  | 0.7 |  | 0.9 |  |

如果输入数据集包含 50,000 个用户（行）和 50,000 个视频（列），这将涉及将 25 亿个单元格加载到内存中。如此大的数据集超过了 16 GB RAM 的限制，导致 **内存不足错误**，并导致函数失败。

### 空间复杂度

为了评估内存使用，开发者通常使用空间复杂度，用大 O 表示法表示，来描述内存使用如何随着数据结构的大小而扩展。例如，在 `get_top_video` 中，对于有 ![](img/B31534_14_009.png) 行和 ![](img/B31534_14_002.png) 列的 CSV 文件，空间复杂度是 ![](img/B31534_14_008.png)，因为该函数将整个数据集加载到内存中。

### 平衡效率权衡

在设计程序时，经常会遇到内存使用和运行效率之间的权衡。例如，**缓存**是将函数的计算输出值等信息存储在 RAM 中而不是重新计算的过程。这可以显著提高重复计算的速度，但也会增加内存消耗。在一个重复调用 `fibonacci_recursive` 函数的程序中，例如 `n=35`，之前运行需要 1.7 秒，缓存结果可以为后续每次调用节省 1.7 秒。

另一个权衡是在 `get_top_video` 中，我们在开始计算之前将整个文件读入内存。可能更实际的做法是从磁盘读取较小的数据批次，并按顺序计算每个批次的累积顶级视频，而不是一次性处理整个数据集。读取和处理大型 CSV 文件的小块数据可能需要更多时间，但有助于避免超过 RAM 限制。

现在我们已经掌握了运行时间和空间效率的重要性，以及如何评估它们的复杂性和涉及的权衡，我们可以继续前进，探索 GenAI 如何在管理和优化程序效率的每个步骤中提供帮助。

# 使用 GitHub Copilot 分析运行时间和内存消耗

分析运行时间和内存使用是一个简单直接的过程。内置的`time`模块对于跟踪运行时间很有用，第三方`memory_profiler`库用于监控内存使用。接下来的两个子章节将描述 GitHub Copilot 如何通过完成我们的实现或从头生成代码来协助这两种情况。在本节的末尾，我们将要求 ChatGPT 使用这些分析作为输入来预测运行时间和内存大小限制。

## 分析运行时间

在 Python 中测量函数的运行时间有助于评估源代码中完成任务所需的时间是否符合可接受的阈值，并识别潜在的改进区域。这可以通过以下脚本实现：

```py
start = time.process_time()
recursive_fibonacci(35)
end = time.process_time() print(f"Time taken: {end – start:.3f} seconds") 
```

通过记录执行前后的时间，我们可以计算运行时间，即这两个时间之间的差值，以计算第 35 个斐波那契数。

在第十五章中，我们将探讨如何使用**装饰器**来记录应用程序性能。现在，我们将简单地使用`start`和`end`时间来测量程序运行时间。

由于分析代码简短且直接，作者们主要使用 GitHub Copilot 来完成此类任务。以下示例演示了 Copilot 如何通过应用如图 14.1 所示的五个 S（提示精确度）来理解我们的文件`profile_runtime.py`的目的：

![图 14.1：Copilot 补全](img/B31534_14_1.png)

图 14.1：Copilot 补全

在这个例子中，我们命名文件为`profile_runtime.py`，并包含了`time`包和`fibonacci_recursive`函数所需的必要导入，为 Copilot 建立一个清晰的上下文。基于这些，Copilot 很可能会识别出我们的目标是分析`fibonacci_recursive`函数，并建议一个完整的运行时分析实现。

或者，我们可以使用聊天、ChatGPT 或 OpenAI API 从头生成分析脚本。例如，我们可以在 Copilot 聊天中使用以下提示：

```py
print the runtime of fibonacci_recursive for n=35 
```

下面是 Copilot 在 PyCharm 中提供的示例实现：

![图 14.2：Copilot 从分析建议中编写完整方法](img/B31534_14_2.png)

图 14.2：Copilot 从分析建议中编写完整方法

这段代码可以直接用来分析函数的运行时间。或者，我们可以进行一些小的修改，例如对运行时间值进行四舍五入以提高可读性。

这里是运行建议的分析脚本的一个输出：

```py
Result: 9227465
Runtime: 1.7093181610107422 seconds 
```

虽然`n=35`时运行时间为 1.7 秒可能看起来合理，但对于更大的输入，如 50 或 100，运行时间变得不切实际。在本章的后面部分，我们将探讨识别和解决这些挑战的技术。

## 分析空间使用情况

使用`memory_profiler`包中的`@profile`装饰器可以实现对程序内存使用的分析。这个轻量级工具监控函数中每一行的内存使用情况。该包应包含在此书仓库的*requirements.txt*文件中，因此它应该已经可以在您的虚拟环境中访问。

例如，为了配置`get_top_video`函数，该函数检索具有最高平均观看百分比的视频，我们可以在函数定义之前添加`@profile`装饰器。对包含 10,000 个用户观看 10,000 个视频观看百分比的文件*interactions_10_000.csv*的函数调用将记录每行的内存消耗：

```py
import pandas as pd from memory_profiler import profile @profile
def get_top_video(path):
    interactions = pd.read_csv(path)
    avg_ratio = interactions.mean(axis=0, skipna=True) return avg_ratio.idxmax()
get_top_video('interactions_10_000.csv') 
```

配置输出提供了诸如行号、总内存使用量、增量内存使用量、每个语句执行的次数以及这些执行的内容等详细信息。为了参考，*图 14.3* 展示了上述代码的输出：

![图 14.3：按行显示内存消耗的配置输出](img/B31534_14_3.png)

图 14.3：按行显示内存消耗的配置输出

文件*interactions_10_000.csv*包含 10,000 x 10,000 个 float64 类型的单元格，每个单元格需要 8 字节，预期的内存使用量大约为：

![](img/B31534_14_011.png)

这与第 7 行记录的内存消耗非常接近，其中将 CSV 文件加载到 Pandas DataFrame 中消耗了 889.7 MB。这包括单元格数据所需的内存以及与 Pandas DataFrame 对象相关的开销，例如列名、行名、元数据和类型。

学习了如何使用 GitHub Copilot 简化创建配置脚本以简化运行时间和空间复杂性的创建后，我们可以继续探索如何使用 Copilot 配置多次运行以及如何使用 ChatGPT 估计我们的函数可以管理的最大输入容量。

# 使用 ChatGPT 分析最大容量

确定函数的最大容量意味着确定超过该容量后由于内存限制或不可接受的运行时间而失败的最大的输入。此类预测的一种策略是针对几个输入大小对其性能进行配置，识别运行时间或空间增长，然后估计函数可以处理的最大容量。GenAI 可以通过自动化不同输入的配置以及将结果用作提示以计算最大容量的辅助数据来协助这一两步过程。

## 在多次运行中配置运行时间

Copilot 可以帮助我们创建类似于单个配置的`fibonacci_recursive`配置循环。例如，如果我们想配置从 10 到 40 的输入的运行时间，步长为 5，我们可以在文件中添加以下导入语句：

```py
import time from fibonacci import fibonacci_recursive 
```

然后在 Copilot 聊天中使用如下提示：

```py
print the runtime of fibonacci_recursive for n=10:41:5 
```

这个提示，连同文件中导入语句的周围上下文，很可能会生成一段代码来分析不同参数的运行时间：

![图 14.4：针对多个斐波那契输入的剖析建议](img/B31534_14_4.png)

图 14.4：针对多个斐波那契输入的剖析建议

我们可以使用生成的代码原样使用或进行轻微调整，例如，将记录的时间四舍五入到四位小数或更改范围的停止值到 41。在运行在 16GHz CPU 的 M1 MacBook Pro 上时，记录了以下运行时间剖析：

```py
Runtime for fibonacci_recursive(10): 0.0000 seconds
Runtime for fibonacci_recursive(15): 0.0002 seconds
Runtime for fibonacci_recursive(20): 0.0013 seconds
Runtime for fibonacci_recursive(25): 0.0150 seconds
Runtime for fibonacci_recursive(30): 0.1571 seconds
Runtime for fibonacci_recursive(35): 1.7051 seconds
Runtime for fibonacci_recursive(40): 19.5045 seconds 
```

此运行时间剖析将被用作 GenAI 应用的输入，以分析函数的复杂度并确定输入大小容量。

## 在多次运行中剖析内存消耗

使用简单的方法，可以通过多次运行`get_top_video`函数来剖析内存消耗：

```py
paths = ['interactions_100.csv', 'interactions_1000.csv', 'interactions_10_000.csv'] for p in paths: print("top video: ", get_top_video(p)) 
```

在这个例子中，文件*interactions_100.csv, interactions_1000.csv*和*interactions_10_000.csv*代表用户-视频交互数据集，行和列的长度与它们文件名中的数字相对应。

在包含文件名后，Copilot 可以通过以下方式协助完成`for`循环，如下所示：

![图 14.5：Copilot 代码补全建议](img/B31534_14_5.png)

图 14.5：Copilot 代码补全建议

生成的代码可以直接使用或稍作修改，例如，通过增强打印语句以包含有关文件大小的信息。

为了参考，运行此代码产生了以下剖析：

![图 14.6：剖析内存使用输出](img/B31534_14_6.png)

图 14.6：剖析内存使用输出

读取 CSV 文件的内存使用量增长如下：

+   100 x 100 矩阵占用 0.6 MB

+   1,000 x 1,000 矩阵占用 29.9 MB

+   10,000 x 10,000 矩阵占用 889 MB

这内存消耗数据可以作为补充信息包含在我们的提示中，以估计函数可以处理的矩阵最大尺寸，正如我们在本章后面所看到的。

## 在运行时间限制内确定最大容量

*GPT-4o1*模型专门设计用于在思维链推理方面表现出色，这使得它在确定运行时间限制下的最大容量方面非常有效。为了利用这一能力，我们可以创建遵循五个 S 的精确提示，包括函数的源代码和相关剖析。这些提示的理想结构可能如下所示：

```py
CONTEXT: You are provided with:
1\. Python function enclosed with {{{ FUNCTION }}} 
2\. Runtime profiling enclosed with {{{ PROFILING }}}. 3\. Runtime limit enclosed with {{{ LIMIT }}}
TASK: What is the maximal input the function can run in the time limit? FUNCTION: {{{ ... }}}
PROFILING: {{{ ... }}}
LIMIT: {{{ ... }}}
MAXIMAL INPUT: 
```

例如，当使用此提示并设置 100 秒的运行时间限制时，ChatGPT 中的*GPTo1-mini*模型提供了以下推理步骤：

1.  **剖析分析**：反复审查了报告的剖析。

1.  **观察**：识别了运行时间的指数增长。

1.  **计算**：在时间限制内计算了最大的输入。

1.  **结论**：确定了最大输入为 43。

这些推理步骤导致最终答案，即结论步骤，如图*图 14.7*所示：

![图 14.7：GPT-4o1-mini 的最大容量结论](img/B31534_14_7.png)

图 14.7：GPT-4o1-mini 的最大容量结论

模型预测`n=43`的运行时间为 78.5 秒，`n=44`为 123 秒。当我们使用我们的脚本测量实际运行时间时，分别为 81.08 秒和 129.07 秒，这表明与最大容量匹配得非常接近，并正确识别了最大容量：

```py
Elapsed time for n=43: 81.08 seconds
Elapsed time for n=44: 129.07 seconds 
```

供您参考，以下是本例中使用的完整提示：

```py
CONTEXT: You are provided with:
1\. Python function enclosed with {{{ FUNCTION }}} 
2\. Runtime profiling enclosed with {{{ PROFILING }}}. 3\. Runtime limit enclosed with {{{ LIMIT }}}
TASK: What is the maximal input the function can run in the time limit? FUNCTION: {{{
def fibonacci_recursive(n):
    if n <= 0:
        return 0
    if n == 1:
        return 1
    return fibonacci_recursive(n - 1) + fibonacci_recursive(n - 2)
}}}
PROFILING: {{{
Runtime for fibonacci_recursive(10): 0.0000 seconds
Runtime for fibonacci_recursive(15): 0.0002 seconds
Runtime for fibonacci_recursive(20): 0.0013 seconds
Runtime for fibonacci_recursive(25): 0.0150 seconds
Runtime for fibonacci_recursive(30): 0.1571 seconds
Runtime for fibonacci_recursive(35): 1.7051 seconds
Runtime for fibonacci_recursive(40): 19.5045 seconds
}}}
LIMIT: {{{ 100 seconds }}}
MAXIMAL INPUT: 
```

在接下来的章节中，我们将探讨如何有目的地收集数据以与 OpenAI API 集成，作为 SDLC 自动化的部分。

## 在内存约束内确定最大容量

与用于在运行时约束下识别最大容量的类似提示结构也可以应用于内存约束：

```py
CONTEXT: You are provided with:
1\. Python function enclosed with {{{ FUNCTION }}} 
2\. RAM usage profiling enclosed with {{{ PROFILING }}}. 3\. RAM usage limit enclosed with {{{ LIMIT }}}
TASK: What is the maximal input the function can run in the RAM limit? FUNCTION: {{{ ... }}}
PROFILING: {{{ ... }}}
LIMIT: {{{ ... }}}
MAXIMAL ROWS / MAXIMAL COLUMNS: 
```

在这里，提示中的提示稍微调整为`MAXIMAL ROWS / MAXIMAL COLUMNS`，以强调输入的二维维度。

例如，当使用此模板在 ChatGPT 的`get_top_video`函数中与*GPT-4o1*模型一起使用，以及从 100 x 100、1,000 x 1,000 和 10,000 x 10,000 大小的稀疏矩阵中记录的结果时，模型生成了以下推理步骤：

1.  **分析分析**：包括对内存使用数据和其缩放行为的理解。

1.  **结论**：估计了 5GB 内存限制下的最大输入。

1.  **最终推荐**：建议 22,000 x 22,000 矩阵大小为最大的可行输入。

这些推理步骤导致最终答案，即最终推荐步骤，如图*图 14.8*所示：

![图 14.8：GPT-4o1-mini 的最大容量推理](img/B31534_14_8.png)

图 14.8：GPT-4o1-mini 的最大容量推理

当执行包含一个 22,000 x 22,000 矩阵的脚本时，记录的内存使用峰值是 4.63 GB，与模型的预测非常接近。

![图 14.9：内存使用低于 5GB](img/B31534_14_9.png)

图 14.9：内存使用低于 5GB

这种内存使用与 ChatGPT 的能力评估相一致，并且低于所需的 5GB RAM 限制。

供参考，以下是生成此输出的完整提示：

```py
CONTEXT: You are provided with:
1\. Python function enclosed with {{{ FUNCTION }}}  
2\. RAM usage profiling enclosed with {{{ PROFILING }}}. 3\. RAM usage limit enclosed with {{{ LIMIT }}}
TASK: What is the maximal input the function can run in the RAM limit? FUNCTION: {{{ def get_top_video(path):
    interactions = pd.read_csv(path)
    avg_ratio = interactions.mean(axis=0, skipna=True)
    return avg_ratio.idxmax() }}}
PROFILING: {{{...}}}
LIMIT: {{{ 5 GB }}}
MAXIMAL ROWS / MAXIMAL COLUMNS: 
```

由于篇幅限制，省略了分析信息，包括终端输出的直接复制粘贴，如图*图 14.6*所示。完整的提示可以在*ch14/code_samples/chatgpt_maximum_input_prompt.txt*中找到。这个提示成功预测了最大输入大小为 22,000 行和 22,000 列。

在这两种情况下，ChatGPT 肯定是在外推输入值以预测运行时间或最大维度。它需要足够的输入值来做出这样的预测，并且可能不如自己计算准确，但这是一个合理的近似。

在本章的下一部分，我们将探讨如何使用 GenAI 和增加具有更好运行时间复杂度的函数（如算法）以及处理块的能力。

# 使用链式提示优化代码

之前的例子展示了 LLMs 的简单编码和估计能力。然而，LLMs 可以做更多。它们可以创建改进算法的代码，甚至平衡特定的运行时间和内存效率目标。

为了有效地增加输入容量，我们将优化提示与最大容量提示的结果**链式**连接。初始提示已经提供了基本细节，例如函数、运行时或内存限制，以及各种输入的剖析。优化提示还应包括以下关键信息：

+   **优化目标**：明确指定主要目标，无论是提高运行时间复杂度、减少内存使用，还是两者兼而有之。尽可能详细地描述期望的方法，例如批处理或提高算法复杂度。

+   **函数文档字符串**：提供对函数目的的简洁描述，以及任何约束或要求。

+   **输入要求**：在运行时或内存约束下定义新的输入目标，例如计算 1,000,000^(th)斐波那契数或处理一个有 100,000 行和 100,000 列的矩阵。

对于更复杂的场景，提供更多细节可能有所帮助，例如之前的优化尝试、对外部函数或资源的依赖、函数调用的频率或并发使用模式，以及可接受的权衡，例如为了减少内存使用而允许更长的运行时间。

此信息将被整合到一个链式提示中，遵循五个 S 原则以确保精确性和清晰度。

## 运行时间优化

让我们考察`fibonacci_recursive`函数的运行时间优化。下面是一个链式提示的示例，基于本章前面提出的最大容量提示。此提示请求一个改进的实现，以更好的运行时间复杂度处理 1,000,000 的输入：

```py
CONTEXT: You are provided with the function's docstring enclosed with {{{ DOCSTRING }}} and the required input enclosed with {{{ REQUIRED_INPUT }}}. TASK: Optimize the function to run in a better time complexity within the runtime limit. DOCSTRING: {{{ """
    Calculate the nth Fibonacci number using a recursive approach. Args:
        n (int): The position in the Fibonacci sequence. Returns:
        int: The nth Fibonacci number. """
}}}
REQUIRED_INPUT = {{{ 1,000,000 }}}
IMPROVED IMPLEMENTATION: 
```

此提示包含一个文档字符串，描述了我们的特定任务，即优化运行时间复杂度以实现目标输入 1,000,000。提供不同的约束，如较小的输入大小，将导致模型输出不同。

一个典型的斐波那契数计算方法具有![](img/B31534_14_003.png)复杂度，然而*GPT-4o1*提出了一种更有效的实现方法，通过快速加倍递归方法实现了![](img/B31534_14_013.png)的运行时间复杂度：

![图 14.10：处理大输入的快速加倍方法](img/B31534_14_10.png)

图 14.10：处理大输入的快速加倍方法

以下是*GPT-4o1*提出的代码：

```py
def fib_pair(n): if n == 0: return (0, 1)
    a, b = fib_pair(n // 2)
    c = a * ((2 * b) - a)
    d = a * a + b * b if n & 1: return (d, c + d) else: return (c, d) 
```

虽然此实现也使用了递归，但它调用![](img/B31534_14_014.png) (![](img/B31534_14_015.png)无余数)来减少函数调用的次数，大约为![](img/B31534_14_016.png)。为了说明其效率，以下是计算第 1,000,000 个斐波那契数的性能比较：

```py
Fast-doubling approach: 0.057893 seconds
Iterative (memoization) approach: 9.175633 seconds 
```

作为另一个基准，使用`fibonacci_fast_doubling`计算第 10,000,000 个斐波那契数耗时 2.26 秒，而迭代方法在 10 分钟内未能完成。

此方法利用了数学恒等式：

![](img/B31534_14_017.png)

![](img/B31534_14_018.png)

其中 ![](img/B31534_14_019.png) 是第 k 个斐波那契数。

使用这些恒等式，一旦![](img/B31534_14_019.png)和![](img/B31534_14_021.png)被计算出来，![](img/B31534_14_022.png)和![](img/B31534_14_023.png)就可以高效地确定。这意味着我们不需要按顺序计算到第 1,000,000 个斐波那契数，而只需关注其一半，显著减少了所需的计算量。

## 空间优化

与运行时优化提示类似，我们可以链式请求优化一个函数以适应 RAM 限制。提示结构保持相似，但它描述了一个内存限制而不是运行时限制，以及一个针对内存使用的优化请求。

例如，考虑以下链式提示，要求对`get_top_video`函数进行优化，以处理在 5GB RAM 限制内的 100,000 行乘以 100,000 列的矩阵：

```py
CONTEXT: You are provided with the function's docstring enclosed with {{{ DOCSTRING }}} and the required input enclosed with {{{ REQUIRED_INPUT }}}. TASK: Optimize the function to run in batches within the RAM limit. DOCSTRING: {{{ """
    Reads a CSV file containing video interactions, calculates the average watch ratio for each video,
    and returns the video with the highest average watch ratio. Args:
        path (str): The file path to the CSV file containing video interactions. Returns:
        str: The identifier of the video with the highest average watch ratio. """
}}}
REQUIRED_INPUT = {{{ 100,000 rows x 100,000 columns matrix}}}
IMPROVED IMPLEMENTATION: 
```

此提示指定了输入矩阵的大小（100,000 行乘以 100,000 列）并基于之前定义的 5GB RAM 限制。

![图 14.11：ChatGPT 基于分块处理的建议](img/B31534_14_11.png)

图 14.11：ChatGPT 基于分块处理的建议

基于这些信息，ChatGPT 建议以 1,000 行为一批处理 CSV 文件，这对于有效处理此类大小的数据是一个合适的解决方案。

在这种情况下，指定输入要求至关重要。对于更大的矩阵，使用 Pandas DataFrame 可能变得不切实际，需要寻找替代方案。相反，对于列数较少的矩阵，较大的列块可能就足够了。

供您参考，以下是 ChatGPT 根据上述提示提供的分块处理矩阵的实现：

```py
def get_top_video(path):
    cumulative_sum = None cumulative_count = None chunksize = 1000
   for chunk in pd.read_csv(path, chunksize=chunksize):
        chunk_sum = chunk.sum(skipna=True)
        chunk_count = chunk.count() if cumulative_sum is None:
            cumulative_sum = chunk_sum
            cumulative_count = chunk_count else:
            cumulative_sum += chunk_sum
            cumulative_count += chunk_count
    average_ratio = cumulative_sum / cumulative_count
    top_video = average_ratio.idxmax() return top_video 
```

当使用 100,000 行和 100,000 列的输入对实现进行性能分析时，分块实现最终以 4,326.1 GB 的内存使用量结束：

![图 14.12：使用分块提高内存利用率](img/B31534_14_12.png)

图 14.12：使用分块提高内存利用率

在第 13 行，我们可以看到矩阵被处理成 100 个块，每个块包含 1,000 列。

提出的解决方案可以进一步细化以满足内存和运行时要求。始终建议对新实现进行测试，以这两个标准来确保解决方案在效率和性能方面都是令人满意的。

## 进一步的运行时间和空间优化

之前的优化主要集中在单 CPU 算法上。GenAI 可以超越这些限制，并推荐额外的技术。例如，可能适合使用线程进行并行化，利用**图形处理单元**（**GPU**），或者采用更高效的文件格式，如稀疏矩阵或*Apache Parquet*。在`get_top_video`函数中，可以通过集成线程将不同视频的处理并行化。通过利用 GPU，可以进一步加速，因为每一列可以独立于其他列进行处理。或者，将文件格式从 CSV 转换为更高效的选项可以提高性能。如*SciPy*中的**压缩稀疏行**（**CSR**）或**压缩稀疏列**（**CSC**）格式非常适合稀疏数据，而像 Apache Parquet 这样的列式存储格式则非常适合处理大型数据集。

# 摘要

在本章中，我们探讨了如何通过分析运行时间和内存使用情况、识别最大容量以及建议优化代码来增加这些容量，从而确保 LLM 可以辅助高效的应用程序。

使用递归斐波那契示例，我们看到了采用更有效的算法如何显著减少运行时间。在`get_top_video`函数中，我们在 RAM 限制下处理大型矩阵，通过分块帮助 GenAI 优化内存使用。GitHub Copilot 协助分析运行时间和内存消耗，并在不同输入上执行分析运行。ChatGPT 估计了在运行时和 RAM 限制下的最大容量。利用链式提示，ChatGPT 展示了大幅改进实现以实现更大容量的能力，并且可以做更多。

在下一章中，我们将进一步探讨如何将 GenAI 集成到 SDLC 中，重点关注日志记录、监控应用程序和错误处理。

# 测验时间

在你进入下一章之前，请确保你能自信地回答以下问题：

**问题 1**：Copilot 如何帮助分析程序的运行时间和内存使用情况？

**答案**：在 Python 中，可以使用内置的`time`模块和第三方`memory-profiler`包来分析运行时间和内存使用情况。Copilot 可以通过完成起始代码或根据精确提示从头生成该功能来协助。

**问题 2**：ChatGPT 如何帮助在运行时或 RAM 限制下识别最大输入？

**答案**：通过精心设计的提示，包括函数的源代码、运行时或 RAM 限制以及分析结果，我们可以利用专为思维链推理设计的*GPT-4o1*模型，来计算在那些限制下可管理的最大输入。

**问题 3**：如何通过链式提示来增加程序输入容量？

**答案**：在确定一个函数可以处理的最大输入而不会成为瓶颈后，链式提示可以包括期望的输入大小和特定的优化请求。*GPT-4o1*可以利用这些信息提出一个遵循运行时和/或内存限制的优化解决方案。

# 进一步阅读

要了解更多关于本章所涉及的主题，请查看以下资源：

+   维基百科，CPU：[`en.wikipedia.org/wiki/Central_processing_unit`](https://en.wikipedia.org/wiki/Central_processing_unit)

+   极客们对内存消耗的理解：[`www.geeksforgeeks.org/how-to-get-current-cpu-and-ram-usage-in-python`](https://www.geeksforgeeks.org/how-to-get-current-cpu-and-ram-usage-in-python)

+   Python 内存分析简介：[`www.datacamp.com/tutorial/memory-profiling-python`](https://www.datacamp.com/tutorial/memory-profiling-python)

+   Big-o Python 包：[`pypi.org/project/big-O-calculator/`](https://pypi.org/project/big-O-calculator/)

+   Lambda Labs 关于 GPT-3 训练成本的介绍：[`lambda.ai/blog/demystifying-gpt-3`](https://lambda.ai/blog/demystifying-gpt-3)

# 免费订阅电子书

新框架、演进的架构、研究发布、生产分析——*AI_Distilled*将噪音过滤成每周简报，供与 LLMs 和 GenAI 系统实际操作的工程师和研究人员阅读。现在订阅，即可获得免费电子书，以及每周的见解，帮助您保持专注并获取信息。

在[`packt.link/TRO5B`](https://packt.link/TRO5B)订阅或扫描下面的二维码。

![白色背景上的二维码 AI 生成的内容可能不正确。](img/B31534_Newsletter_NEW.png)

# 15

# 使用 GenAI 上线：日志记录、监控和错误处理

**大型语言模型（LLMs**）可以极大地加速我们的上线过程，即部署代码到生产环境。但如果提示不当，它们也可能降低代码质量。在本章中，我们将探讨即使遵循五个 S 原则来提示 GenAI 进行日志记录、监控和输入验证，生成的代码也可能变得杂乱，将这些元素与核心功能结合在一起，违反**单一职责原则**。例如，模型有时建议使用`print`语句而不是适当的日志记录，在函数内处理输入验证，或者在不报告其值的情况下递增计数器。这违反了单一职责原则，并降低了整体代码质量。

为了解决这个问题，我们将应用**思维链**（**CoT**）提示工程技术到 GitHub Copilot，以生成良好监控的代码，同时不干扰函数的核心功能，利用**装饰器**作为设计模式。我们还将利用**少样本学习**来引导它遵循编码风格。虽然 GitHub Copilot 适合这些任务，但我们将探讨如何使用 ChatGPT 中的 CoT 和 OpenAI API 中的**微调**实现类似的结果。

本章涵盖的关键主题包括以下内容：

+   介绍日志记录、监控和错误处理

+   利用 GenAI 进行高级编码模式

+   在 ChatGPT 和 OpenAI 中应用逆 CoT

+   将少样本学习和微调作为风格指南

# 技术要求

为了充分利用本章内容，请确保您具备以下条件：

+   一个 GitHub Copilot 账户

+   一个**集成开发环境**（**IDE**）- 要么是 VS Code，要么是 PyCharm

+   一个具有访问 ChatGPT 和 OpenAI API 的 OpenAI 账户

+   访问本书的仓库，可在[`github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI`](https://github.com/PacktPublishing/Supercharged-Coding-with-Gen-AI)找到

+   在 VS Code 或 PyCharm 中设置的虚拟环境

+   一个 OpenAI API 令牌

如需设置 GitHub Copilot 账户的帮助，请参阅*第三章*。有关设置 OpenAI API 访问和生成令牌的说明，请参阅*第二章*。如果您需要创建 OpenAI 账户或在其 IDE 中设置虚拟环境的帮助，请参阅*附录*以获取详细的指导。

# 介绍日志记录、监控和错误处理

当 Python 软件在生产阶段上线并服务于客户时，验证其在实际使用场景中是否持续按预期工作非常重要。如果发现了一些问题，理解这些问题的行为至关重要。因此，对有问题的输入进行日志记录、监控和错误处理是**软件开发生命周期**（**SDLC**）的一个基本方面。这涉及到跟踪内部过程中的关键检查点，通常由记录器执行，这些有助于调试和其他分析。记录性能统计信息，如计数函数调用，通常与性能分析一起使用，以提高性能。最后，处理意外场景，例如接收无效类型的参数，是一个确保代码能够抵御广泛用户输入的过程。这三个方面有助于保持软件质量，最小化意外问题，并在出现问题时简化调试。

在本章中，我们将重点关注这三个基本实践，因为这些通常是任何项目中首次上线活动的首选，并且它们很可能与你的软件相关。随着你的策略扩展到更多的指标和错误处理技术，这些使用 GenAI 工具的标准方法可以很容易地从本章中介绍的内容进行泛化和扩展。

## FizzBuzz 用例

为了探索如何将监控努力整合到我们的代码中，让我们考虑开发一个生成**FizzBuzz**序列的程序，这是一个在*第二章*中引入的编码挑战。作为对这个程序监控努力的一部分，我们希望记录每个函数调用及其参数，维护总函数调用计数器，并确保输入是小于 500 的正整数。

作为起点，可以从函数签名生成一个基本的 FizzBuzz 实现：

```py
def print_fizzbuzz(limit: int) -> None: 
```

*图 15.1* 展示了 GitHub Copilot 在 PyCharm 中建议的实现：

![图 15.1：Copilot 的初始 FizzBuzz 实现](img/B31534_15_1.png)

图 15.1：Copilot 的初始 FizzBuzz 实现

此实现作为引入上线功能的基石。在介绍使用提示工程技术的监控最佳实践之前，我们将首先探讨仅仅通过链式调用日志、监控和错误提升请求如何降低代码质量。为这些任务添加 GenAI 实现会导致函数更长且更复杂。然而，诸如 CoT 和 few-shot 学习等技术可以帮助添加这些功能，同时保持代码的整洁和结构化。

## 日志记录

日志是生成文本记录，充当我们程序执行的日记。例如，在 FizzBuzz 序列的开始，我们可能希望记录调用的参数。虽然使用简单的`print`语句是一个选择，但内置的`logging`库是一个更好的选择，因为它可以写入控制台，同时也提供了更多对输出和日志写入位置的控制，例如文件和远程服务器。它允许对记录进行结构化格式化，并管理日志级别，可以报告所有输出以进行调试，或者根据重要性报告警告的子集。

要使用`logging`库，我们通常使用模块的名称定义一个`logger`实例：

```py
import logging
logger = logging.getLogger(__name__) 
```

这通过使用`__name__`特殊属性（也称为**魔法属性**）将 logger 实例与模块名称关联起来。这种关联使得在该文件中对日志消息进行更好的过滤和定制成为可能。

当使用通用人工智能（GenAI）进行日志记录时，将日志任务单独作为一个提示（prompt）是至关重要的，而不是将其嵌入到实现提示中。这种方法符合之前在书中介绍的五 S 最佳实践之一的**单任务**原则。

例如，当在 VS Code 的**编辑窗口**中使用 Copilot 时，我们可以选择`print_fizzbuzz`实现，并使用以下提示：

```py
#selection log the function arguments 
```

以下是我们使用*3o-mini*模型在*图 15.2*中获得的建议：

![图 15.2：FizzBuzz 的日志建议](img/B31534_15_2.png)

图 15.2：FizzBuzz 的日志建议

在 PyCharm 中，我们可以在选择函数代码后利用内联聊天，并提示以下内容以产生类似的结果：

```py
Log the function arguments 
```

虽然生成的日志语句正确地记录了函数的参数，但它也在函数内部引入了两行不必要的代码杂乱，而这些代码应该专注于打印 FizzBuzz 序列。在章节的后面部分，我们将探讨如何使用提示工程技术来保持代码的整洁。

## 处理意外输入

当我们的程序在运行时接收到意外的输入，例如不正确的参数类型（例如，`float`而不是`int`）或超出我们程序可管理范围的值时，我们希望通过**引发错误**来控制程序的行为，而不是失败或产生不可预测的结果。

例如，在`print_fizzbuzz`函数中，`limit`参数预期是一个正整数，这样我们就可以从 0 打印到该值的`fizz`或`buzz`。一个额外的约束可能是输入应该小于 500，以确保输出适合屏幕。为了通过错误处理强制执行这两个要求，我们可以利用 Copilot。

当在 VS Code 的编辑窗口中使用 Copilot 时，我们可以选择`print_fizzbuzz`代码并使用以下提示：

```py
#selection validate limit type, and that it is in the range [0,500] 
```

在 PyCharm 中，我们可以通过选择`print_fizzbuzz`函数并输入以下提示来使用内联聊天：

```py
validate limit type, and that it is in the range [0,500] 
```

以下是用 VS Code 的 Copilot 和 o3 mini 模型获得的结果：

![图 15.3：VS Code 输出正确处理输入但创建代码杂乱](img/B31534_15_3.png)

图 15.3：VS Code 输出正确处理输入但创建代码杂乱

这个建议验证了参数的类型和范围限制，正如所要求的。然而，就像日志提示一样，它引入了验证函数输入的额外责任。在本章的后面部分，我们将探讨提示工程如何帮助生成高质量的代码。

## 监控

上线过程中的另一个关键方面是跟踪不同函数的使用情况。通过记录指标，我们可以收集有关性能、调用频率和执行率的宝贵统计数据。

一个简单的起点是跟踪我们程序中的函数调用次数。为了使用`print_fizzbuzz`做到这一点，我们可以定义一个全局计数变量`FIZZBUZZ_COUNTER = 0`，并指示 Copilot 在每次成功执行前后增加它。例如，当在 VS Code 的**编辑窗口**中使用 Copilot 时，我们可以选择`print_fizzbuzz`实现，并使用以下提示：

```py
#selection increment FIZZBUZZ_COUNTER after a successful execution. 
```

类似地，在 PyCharm 中，我们可以选择代码并使用内联聊天来提示以下内容：

```py
Increment FIZZBUZZ_COUNTER after a successful execution. 
```

*图 15.4*展示了在 VS Code 中使用 Copilot 和 o3 mini 模型时对这一提示的建议完成：

![图 15.4：VS Code 添加记录使用计数器](img/B31534_15_4.png)

图 15.4：VS Code 添加记录使用计数器

在这一点上，我们的`print_fizzbuzz`函数集成了多个监控组件：日志记录、处理无效输入和计数调用。虽然这些满足了我们的监控需求，但它们导致函数变得冗长且难以阅读。这违反了清洁编码原则，特别是**单一职责原则**，该原则强调函数应专注于单一任务。

使用简单提示创建的 GenAI 代码倾向于在现有方法中生成代码并添加它，这可能导致实现混乱。为了保持代码的清洁和结构化，我们可以利用 CoT 提示。这种方法使我们能够以更高的抽象级别处理监控，正如我们接下来将要探讨的。

# 利用生成式人工智能（GenAI）实现高级编码模式

为了平衡清洁代码原则，如单一职责原则，与上线需求，Pythonic 的方法是使用高级编码模式，如装饰器。而不是在函数内嵌入日志语句，我们将这一职责委托给装饰器模式：

```py
def log_function_args(func: callable): # logging logic here
@log_function_args
def print_fizzbuzz(limit: int) -> None: # main functionality here 
```

在这里，`log_function_args`负责记录函数调用，允许`print_fizzbuzz`专注于处理 FizzBuzz 序列。这种方法确保了更清洁、更模块化的代码，同时为多个函数启用日志记录。

GenAI 应用可能不会建议这种模式，除非我们积极引导它们走向清洁编码实践。如在第*第九章*中介绍，CoT 提示帮助 LLM 通过复杂任务进行推理。我们可以通过使用 CoT 提示并明确编写装饰器调用（例如`@log_function_args`），在实现实际的装饰器函数之前，将模型引导向更好的设计选择。这将导致更清洁、更易于维护的实现。

## 使用装饰器来分离职责

**装饰器**是一种结构化设计模式，它允许在函数调用前后堆叠任务，而不会改变函数的代码。它是一种**闭包**的专用用例，其中函数保留对其相关参数的访问。典型的装饰器实现如下所示：

```py
def sample_decorator(func: callable) -> callable: def wrapper(*args, **kwargs): print("Function is wrapped") return func(*args, **kwargs) return wrapper 
```

常见的用法包括应用`@`注解，如下所示：

```py
@sample_decorator
def foo(*num): return len(nums) 
```

在这里，`sample_decorator`装饰器接受一个函数对象，并返回一个包装函数，该函数接受与原始函数相同的参数，但在执行前会打印`Function is wrapped`。

LLMs can certainly include decorators in their generated code as their training data contains many common decorator implementations. For well-known use cases such as timers, loggers, argument validation, and retry mechanisms, the models can generate decent implementations based on the decorator’s signature when prompted to.

接下来，我们将探讨如何应用逆 CoT 提示来生成所需的实现。

## 装饰器实现的逆 CoT

在*第九章*中，我们探讨了如何定义一个调用低级实现的函数，为 GitHub Copilot 提供强有力的指导。通过逆 CoT，我们采取类似的方法，通过引用尚未定义的函数。我们使用术语*逆*，因为我们希望装饰器在文件中比使用它们的函数出现得更早。为了实现这一点，我们将光标放置在文件较高的位置，允许 Copilot 在现有实现之上生成代码。

作为复习，这里是一个在*第九章*中使用的 CoT 提示示例，用于实现几何平均计算器的变体，其中 Copilot 成功生成了缺失的低级函数：

![图 15.5：GitHub Copilot 驱动的更高层次函数的实现](img/B31534_15_5.png)

图 15.5：GitHub Copilot 驱动的更高层次函数的实现

在这种方法中，函数被分解为具有命名函数，这些函数故意被调用为未定义。Copilot 理解它的角色是生成这些必要的实现。这种做法使得 Copilot 能够实现缺失的函数，生成结构化和可预测的代码。

我们可以在实现上线功能时应用相同的技巧，通过定义装饰器结构并允许 Copilot 生成实现。只需添加对所需装饰器的调用，我们就可以引导 Copilot 生成相应的实现。例如，在我们的 FizzBuzz 用例中，我们可以在我们的函数上叠加三个监控功能：

1.  **验证输入**：定义一个带有参数的装饰器以强制执行输入边界，即`@validate_args_types_and_limits(0, 500)`。

1.  **增加全局计数器**：

1.  `@increment_counter`。

1.  **记录函数调用**：

1.  `@log_function_args`。

For reference, here is how stacking these decorators would appear before Copilot generates their implementations:

![图 15.6：逆 CoT 方法](img/B31534_15_6.png)

图 15.6：逆 CoT 方法

在这里，与 CoT 技术一样，IDE 将正确地将装饰器标记为未定义，并带有红色下划线。在调用装饰器之后，我们将光标移至第 7 行，在第一个装饰器调用之前，按*Enter*三次以为它们的实现留出空间，然后返回第 8 行并输入以下内容：

```py
def l 
```

此提示足以让 Copilot 推断它应该生成第一个装饰器，将 `l` 解释为 `log_function_args` 的引用。将光标向上移动并按 *Enter* 三次就涉及到 **逆 CoT**，但非常有效。如图 15.7 所示，此提示使 Copilot 能够生成完整的日志机制实现，包括函数的参数。

![图 15.7：Copilot 的装饰器实现](img/B31534_15_7.png)

图 15.7：Copilot 的装饰器实现

建议的 `log_function_args` 实现方式正确地将函数名称和参数作为 `info` 级别的日志语句记录。

在初始 `def l` 提示后，按 *Enter* 键两次就足以让 Copilot 生成下一个装饰器 `increment_counter`，如图 15.8 所示：

![图 15.8：Enter 键作为 Copilot 实现下一个装饰器的提示](img/B31534_15_8.png)

图 15.8：Enter 键作为 Copilot 实现下一个装饰器的提示

*Enter* 键作为足够的提示，用于下一个实现。这突出了 Copilot 如何提升我们的工作效率。为了您的参考，以下是 Copilot 建议的 `increment_counter` 实现方式：

```py
def increment_counter(func): def wrapper(*args, **kwargs): global FIZZBUZZ_COUNTER
        FIZZBUZZ_COUNTER += 1 logger.info(f"Function {func.__name__} called {FIZZBUZZ_COUNTER} times") return func(*args, **kwargs) return wrapper 
```

此装饰器在函数调用之前正确地增加了先前初始化的全局变量 `FIZZBUZZ_COUNTER`。如果我们希望在执行后增加它，我们可以使用不同的装饰器调用，例如 `@increment_counter_after_call`。

最后，Copilot 建议的参数验证实现方式有效地使用参数化装饰器管理类型检查和值约束。这种类型的装饰器引入了一个额外的闭包层，允许我们指定参数，例如在本例中的最小和最大限制。

通过调用 `@validate_args_types_and_limits(0, 500)`，我们为 Copilot 提供了一个清晰的提示，表明需要具有给定约束的参数化装饰器。以下是建议的实现方式：

```py
def validate_args_types_and_limits(min_limit: int, max_limit: int): def decorator(func): def wrapper(limit: int): if not isinstance(limit, int): raise TypeError(f"Argument 'limit' must be of type int, got {type(limit)}") if limit < min_limit or limit > max_limit: raise ValueError(f"Argument 'limit' must be between {min_limit} and {max_limit}, got {limit}") return func(limit) return wrapper return decorator 
```

在这里，参数化装饰器 `validate_args_types_and_limits` 确保在执行函数之前，参数位于指定的包含范围内。

为了参考，这里提供了一个调用 `print_fizzbuzz(-15)` 的示例，由于输入为负数，应该会引发一个值错误：

```py
File "supercharge/ch15/application/fizzbuzz_printer.py", line 32, in wrapper
ValueError: Argument 'limit' must be between 0 and 500, got -15 
```

由于输入错误，`validate_args_types_and_limits` 引发了错误，防止了函数使用负数限制被调用。同样，如果我们调用 `print_fizbuzz(3.14)`，我们会收到一个 `TypeError` 错误，表明它处理整数但不处理浮点值。

要查看我们的 `log_function_args` 和 `increment_counter` 装饰器的操作方式，我们将在文件开头添加一个基本的日志配置，捕获名为 `fizzbuzz.log` 的文件中的 `INFO` 级别及以上日志：

```py
logging.basicConfig(level=logging.INFO,
                    filename="fizzbuzz.log") 
```

这确保了日志消息被存储在 `fizzbuzz.log` 中。在大多数软件系统中，`print` 语句不应使用，而应被能够将输出直接导向控制台或文件的日志所替代。

接下来，我们添加两个带有有效输入的函数调用：

```py
print_fizzbuzz(5)
print_fizzbuzz(50) 
```

为参考，`fizzbuzz_printer.py` 的输出显示在图 15.9 中：

![图 15.9：两个函数调用的控制台输出](img/B31534_15_9.png)

图 15.9：两个函数调用的控制台输出

这会产生一个干净的输出，包含 FizzBuzz 结果。同时，`fizzbuzz.log` 日志文件按照指定的格式记录日志消息，如图 15.10 所示：

![图 15.10：包含日志和计数消息的 fizzbuzz.log 输出](img/B31534_15_10.png)

图 15.10：包含日志和计数消息的 fizzbuzz.log 输出

此实现遵循清洁代码原则，将核心功能与监控分离，同时在 Copilot 中利用逆 CoT 提示生成整洁且易于维护的代码。然而，装饰器可以以各种方式风格化。在本章的后面部分，我们将探讨少样本学习如何帮助改进它们的结构以获得更好的结果。

接下来，我们将应用逆 CoT 技术来提示 ChatGPT 和 OpenAI API。

# 在 ChatGPT 和 OpenAI 中应用逆 CoT

GitHub Copilot 是集成上线功能的首选工具，因为它提供了最快的代码补全体验。然而，我们还将演示如何使用 ChatGPT 和 OpenAI API 应用相同的 CoT 提示技术。为了有效地做到这一点，我们将使用本书前面介绍的五 S 最佳实践来构建我们的提示。

## 使用 ChatGPT 监控装饰器

与我们对 GitHub Copilot 的方法类似，我们可以利用 ChatGPT 生成用于监控所需的装饰器。由于我们提交了完整的代码而不是在文件中移动光标，这种方法与标准的 CoT 技术相一致。以下是一个结构化提示的示例，它提供了关于不完整的 Python 实现的上下文，专注于单一任务，具有具体且简短的指令，随后是一个引导提示：

```py
CONTEXT: You are provided with a partial Python script in {{{ FIZZBUZZ_PRINTER }}}, where some of the code is missing. TASK: Implement the decorators with the missing implementation in the code. FIZZBUZZ_PRINTER: {{{
import logging
logger = logging.getLogger(__name__)
FIZZBUZZ_COUNTER = 0
@log_function_args
@increment_counter
@validate_args_types_and_limits(0, 500)
def print_fizzbuzz(limit: int) -> None: ... full code implementation omitted for brevity ... }}}
CODE: 
```

当与 *o3-mini high* 模型（截至 2025 年 4 月对 Plus 订阅者可用）一起在 ChatGPT 中使用时，此提示生成了一个完整的脚本，包括缺失装饰器的完整实现，如下所示：

```py
def log_function_args(func: callable) -> callable:
    def wrapper(*args, **kwargs):
        logger.info(
            f"Calling function '{func.__name__}' with args: {args} and kwargs: {kwargs}"
        return func(*args, **kwargs)
    return wrapper
def increment_counter(func: callable) -> callable:
    def wrapper(*args, **kwargs):
        global FIZZBUZZ_COUNTER
        FIZZBUZZ_COUNTER += 1
        logger.info(f"FIZZBUZZ_COUNTER incremented to {FIZZBUZZ_COUNTER}")
        return func(*args, **kwargs)
    return wrapper
def validate_args_types_and_limits(min_limit: int, max_limit: int):
    def decorator(func: callable) -> callable:
        def wrapper(*args, **kwargs):
            # Use inspect to bind the arguments to the function's signature
            sig = inspect.signature(func)
            bound_args = sig.bind(*args, **kwargs)
            bound_args.apply_defaults()
            # Expecting the argument to be named 'limit'
            if 'limit' not in bound_args.arguments:
                raise ValueError("Missing required argument 'limit'.")
            limit = bound_args.arguments['limit']
            if not isinstance(limit, int):
                raise TypeError("Argument 'limit' must be an integer.")
            if not (min_limit <= limit <= max_limit):
                raise ValueError(f"Argument 'limit' must be between {min_limit} and {max_limit}.")
            return func(*args, **kwargs)
        return wrapper
    return decorator 
```

此实现保留了与 Copilot 生成的装饰器相同的功能，但在风格上有所不同。它包括文档字符串和添加了 `@functools.wraps(func)` 装饰器，这有助于保留原始函数的属性。在本章的后面部分，我们将探讨如何使用少样本学习来引导 ChatGPT 向更理想的实现风格发展。

## 使用 OpenAI API 监控装饰器

使用 OpenAI API 的方法与 ChatGPT 提示结构紧密相似。我们构建了一个系统提示，其中包含上下文和一个单一任务，就像为 ChatGPT 所做的那样。此外，我们还使用了一个用户提示，其中包含了现有的脚本以及代码补全的提示。

系统提示应如下所示：

```py
SURROUND = "You are provided with a partial Python script in {{{ FIZZBUZZ_PRINTER }}}, where some of the code is missing." SINGLE_TASK = "Implement the decorators with the missing implementation in the code." 
```

这些提示组件在 ChatGPT 提示中的作用与上下文和任务定义相同。用户提示应包含不完整的实现，例如，通过从文件中读取代码，如下所示：

```py
def get_user_prompt(script_path: str) -> str: with open(script_path, 'r') as file:
        incomplete_code = file.read() return f"""
 FIZZBUZZ_PRINTER: {{{{{{ {incomplete_code} }}}}}}

 CODE:
 """ 
```

通过提供不完整的脚本以及 `CODE:` 提示，我们可以引导 OpenAI API 生成缺失的装饰器实现。使用这些提示调用 OpenAI API 应该会产生类似于 ChatGPT 和 GitHub Copilot 输出的装饰器实现。完整的脚本可在 `ch15/inverse_cot_openai.py` 中找到。

现在我们已经看到了如何使用 GenAI 工具来实现监控装饰器，下一步是改进它们的风格以更好地满足我们的需求。这可以通过使用少量学习来引导 Copilot 和 ChatGPT，或者通过 OpenAI API GUI 对模型进行微调来实现。我们将在下一节中探讨这两种方法。

# 利用少量学习和微调作为风格指南

虽然由 GenAI 应用程序生成的装饰器提供了所需的功能，但我们可以通过引入的少量学习技术进一步改进它们的风格*第八章*。

例如，我们可能希望包括 `@functools.wraps` 装饰器以保留原始函数的属性，并使用 `extra` 参数强制执行特定的日志风格。这两个目标都可以通过向 Copilot 和 ChatGPT 提供少量示例或添加我们希望微调文件中使用的所需提示输出来实现。

## GitHub Copilot 的少量装饰器风格

如在 *第八章* 中所述，使用 GitHub Copilot 强制执行特定风格需要一些示例，这些示例可以作为风格指南脚本提供。这个少量示例实现了预期的实现。

为了实现这一点，我们可以创建一个 `style_guide_decorator.py` 文件，该文件应被视为另一个非项目文件，通常放置在项目仓库中的 `src` 文件夹之外。

这个风格指南应包括我们希望 Copilot 遵循的所有元素，例如日志消息格式化、类型提示和间距。这些示例引导 Copilot 并减少了链式提示或额外编辑的需求。

在创建装饰器风格指南时，我们建议包括一个 `time_it` 装饰器来记录函数的运行时间。实现应该展示如何使用 `@functools.wraps` 保留装饰函数的属性，为参数和变量提供类型提示，以及使用额外参数的悬挂缩进日志风格：

```py
import logging import time from functools import wraps from typing import Any logger: logging.Logger = logging.getLogger(__name__) def time_it(func: callable) -> callable:
 @wraps(func)
    def wrapper(*args, **kwargs):
        start_time: float = time.time()
        res: Any = func(*args, **kwargs)
        end_time: float = time.time()
        logger.info( "Function called.",
            extra={ "function": func.__name__, "args": args, "kwargs": kwargs, "error": "", "timing": f"{end_time - start_time} sec"}) return res return wrapper 
```

在这种情况下，日志消息将静态文本与`extra`参数结合，从而生成一个结构化的日志消息，更适合大规模日志记录。例如，为了快速识别所有执行时间超过五秒的计时消息，我们可以根据`timing`参数使用条件`timing > 5`来过滤日志。

为了将风格指南纳入会话，我们打开`decorators_style_guide.py`，然后剪切并粘贴整个文件内容到相应位置。这个技巧确保 Copilot 识别文件中的代码作为活动会话的一部分，并在提出建议时纳入其风格。

接下来，我们回到`print_fizzbuzz.py`并重复逆 CoT 过程。这次，Copilot 的建议应该与`style_guide_decorator.py`中定义的风格指南相一致。如图 15.11 所示，Copilot 在其建议实现中包含了`@functools.wraps`装饰器，同时日志缩进和额外参数保持了风格指南中指定的格式：

![图 15.11：使用 GitHub Copilot 风格指南的装饰器实现](img/B31534_15_11.png)

图 15.11：使用 GitHub Copilot 风格指南的装饰器实现

这个实现表明 Copilot 遵循我们偏好的日志风格，使用静态日志消息和额外参数来支持更结构化的日志格式。

接下来，我们将探讨如何在提示 ChatGPT 时应用风格指南。然后，我们将展示如何在与 OpenAI API 一起工作时将其纳入微调方法。

## ChatGPT 中的少样本学习

当使用 ChatGPT 时，我们可以应用类似我们在第八章中探索的装饰器部署的少样本方法。对于这个任务，我们推荐使用 o3-mini 高模型，因为它在复杂编码任务上表现更好。

我们首先通过包含一个参考示例来增强提示的上下文：

```py
CONTEXT: You are provided with a partial Python script enclosed with {{{FIZZBUZZ_PRINTER}}} where some of the code is missing, and examples of a good implementation enclosed with {{{ EXAMPLES }}}. TASK: Implement the decorators with the missing implementation in the code while following the style guide. 
```

对于少样本示例，我们将对输入和输出代码片段进行标记，使用`INCOMPLETE_CODE`表示输入，指示缺少`time_it`装饰器，而`COMPLETE_CODE`表示完整实现的脚本。这种区分清楚地突出了预期的转换：

```py
INCOMPLETE_CODE: {{{ import logging
logger: logging.Logger = logging.getLogger(__name__) @time_it
def my_func(a: int, b: int) -> int: return a + b
}}} 
```

使用这个不完整的代码片段，我们期望模型生成一个遵循特定风格的完整实现的装饰器。为了指导模型，我们将提供所需代码的完整实现，如下所示：

```py
COMPLETE_CODE: {{{ import logging import time from functools import wraps from typing import Any logger: logging.Logger = logging.getLogger(__name__) def time_it(func: callable) -> callable:
 @wraps(func) ...omitted for brevity but using "extra" parameter... @time_it
def my_func(a: int, b: int) -> int: return a + b
}}} 
```

提供这个期望输出的示例有助于指导 ChatGPT 生成预期的实现。以下为提示的结构，为了简洁起见，省略了之前引入的部分：

```py
CONTEXT: You are provided with a partial Python script enclosed with {{{FIZZBUZZ_PRINTER}}} where some of the code is missing, and examples of a good implementation enclosed with {{{ EXAMPLES }}}
TASK: Implement the decorators with the missing implementation in the code while following the style guide. EXAMPLES:
INCOMPLETE_CODE: {{{...omitted for brevity...}}}
COMPLETE_CODE: {{{...omitted for brevity...}}}
FIZZBUZZ_PRINTER: {{{...omitted for brevity...}}}
CODE: 
```

完整的提示可以在本书的仓库中找到，位于`ch15/decorators_few_shot_chatgpt.txt`。作为参考，使用此提示生成的结果与 Copilot 的代码补全非常相似，如图 15.12 所示：

![图 15.12：使用 ChatGPT 进行少样本学习](img/B31534_15_12.png)

图 15.12：使用 ChatGPT 进行少样本学习

在 ChatGPT 的实现中，我们可以看到模型遵循了我们的示例中的风格指南，将`extra`参数与静态日志消息一起使用，并使用`@functools.wraps`装饰器来保留函数的属性。然而，这是一个相对较长的提示，GitHub Copilot 可以更快地生成代码补全。因此，我们建议尽可能使用 Copilot 以实现更高效的流程。

## 利用微调为 OpenAI API

使用 OpenAI，我们既可以应用少样本技术，如 ChatGPT 输入输出示例，也可以通过添加 JSONL 格式的少量训练样本来训练**微调模型**，正如*第十一章*中介绍的那样。这种方法甚至比 GitHub Copilot 几乎瞬间生成的内容需要更长的时间。对于大型项目，如扫描整个存储库以自动实现所有文件的日志记录、监控和错误处理，微调将更加实用。

正如我们在*第十一章*中看到的，由于模型在处理提示与在微调过程中更新权重的方式不同，微调通常需要比少样本学习更多的示例。然而，考虑到我们从*第十一章*中获得的起始微调文件`fine_tuning.jsonl`，它已经建立了首选的日志风格、缩进和间距，一个装饰器可能就足够实现所需的实现。

例如，这里是一个添加到`ch13/fine_tuning.jsonl`中的`time_it`装饰器，其结构采用了 ChatGPT 中使用的系统和用户提示，以及分配了权重`1`的期望助手响应：

```py
{"messages": [{"role": "system", "content": "You are provided with a partial Python script enclosed with {{{ INCOMPLETE_CODE }}} where some of the code is missing. Your task is to implement the decorators with the missing implementation"}, {"role": "user", "content": "INCOMPLETE_CODE: {{{import logging\nimport time\n\nlogger: logging.Logger = logging.getLogger(__name__)\n\n@time_it\ndef my_func(a: int, b: int) -> int:\n    return a + b\n}}}\n COMPLETE_CODE:"}, {"role": "assistant", "content": "...omitted for brevity...", "weight": 1}]} 
```

然后，我们可以通过访问[platform.openai.com](https://platform.openai.com)，选择**仪表板** | **微调**，并上传 JSONL 文件来上传微调文件，如图*图 15.13*所示：

![图 15.13：上传微调的 JSONL 文件](img/B31534_15_13.png)

图 15.13：上传微调的 JSONL 文件

上传完成后，微调模型将被训练，大约需要 15 分钟。完成后，将出现一个**成功**图标，如图*图 15.14*所示：

![图 15.14：成功的微调作业表示模型已完成训练](img/B31534_15_14.png)

图 15.14：成功的微调作业表示模型已完成训练

为了比较微调与基础 GPT-4o mini 模型的优势，我们可以使用**Playground**页面。这使我们能够将微调模型的输出与基线结果进行比较，突出改进之处。一旦微调过程完成，始终建议对关键提示进行验证这些增强。

我们将在左侧选择**gpt-4o-mini-2024-07-18**作为基础模型，并在右侧下拉菜单中选择微调模型，如*图 15.15*所示：

![图 15.15：基础模型和微调模型比较](img/B31534_15_15.png)

图 15.15：基础模型和微调模型比较

这种比较使我们能够评估两个模型的表现。接下来，我们在屏幕两侧添加系统指令，反映 ChatGPT 中使用的周围上下文和单任务方法：

```py
You are provided with a partial Python script in {{{FIZZBUZZ_PRINTER}}}, where some of the code is missing. Your task is to implement the decorators with the missing implementation in the code. 
```

用户消息遵循类似于我们的 ChatGPT 提示的格式：

```py
FIZZBUZZ_PRINTER: {{{ ...omitted for brevity... }}}
CODE: 
```

在这个阶段，我们的提示已准备好运行，当使用微调模型时会产生更精确的结果。与**gpt-4o-mini-2024-07-18**相比，微调模型仅返回具有我们首选日志风格的代码，并包括`@functools.wraps`装饰器，如*图 15.16*所示：

![图 15.16：微调模型和基础模型比较](img/B31534_15_16.png)

图 15.16：微调模型和基础模型比较

在这张图中，我们可以看到助手的响应直接从代码开始，反映了微调示例的影响。此外，首选的日志风格被一致地应用，与提供的样本相一致。

虽然微调有助于保持所需的结构和风格，但它比使用 Copilot 进行代码补全等上线任务需要显著更多的努力。因此，我们建议将 Copilot 作为您此类任务的首选工具。如果您正在构建用于内部使用的自定义 GenAI 应用程序，并且有数十个训练示例，例如扫描整个存储库以获取建议或开发用于服务其他客户的 GenAI 解决方案，那么微调可能是一个可行的选项。然而，Copilot 的少样本学习通常是一种更有效的方法，无需投入时间寻找许多用例即可实现结果。

# 摘要

在本章中，我们探讨了添加日志、监控使用和处理不良输入等上线任务如何给函数引入不必要的复杂性。GenAI 本身并不建议使用装饰器来将这些目标与程序的核心功能分离，这可能导致代码质量较低。

利用 GenAI 完成这些任务最有效的方法是通过 GitHub Copilot 的 CoT 提示。这种方法首先实现核心功能，然后指定装饰器以处理日志记录、指标记录或参数验证的额外要求。

为了确保装饰器实现符合我们期望的风格，我们可以使用 Copilot 和 ChatGPT 的少样本学习或微调 OpenAI API 的模型。这使我们能够实现更理想的结果，最大限度地减少对代码链式编辑的要求。

在本书的最后一章中，我们将总结 15 章的关键要点，并探讨如何利用 GenAI 工具增强我们的编码工作。

# 测验时间

在你进入下一章之前，请确保你能自信地回答以下问题：

**问题 1**：LLMs 是否保证更高的编码标准？

**回答**：不一定。仅仅要求 GenAI 应用增加监控责任可能会导致不希望的建议，例如将监控任务与核心功能合并，而不是正确地分离责任。

**问题 2**：Copilot 的逆 CoT 是什么？

**回答**：这涉及到首先定义高级编码结构，如装饰器，然后将光标向上移动，让 Copilot 完成实现细节。

**问题 3**：我们如何指导 GenAI 应用遵循与我们的内部标准一致的样式指南？

**回答**：我们可以为 Copilot 提供一个样式指南文件，在提示 ChatGPT 时提供一些示例，并在与 OpenAI API 合作时应用微调。

# 进一步阅读

要了解本章涵盖的主题的更多信息，请查看以下资源：

+   Real Python 关于装饰器的文章：[`realpython.com/primer-on-python-decorators/`](https://realpython.com/primer-on-python-decorators/)

+   Python 的日志记录文档：[`docs.python.org/3/howto/logging.html`](https://docs.python.org/3/howto/logging.html)

+   代码度量，维基百科：[`en.wikipedia.org/wiki/Software_metric`](http://en.wikipedia.org/wiki/Software_metric)

+   异常处理，维基百科：[`en.wikipedia.org/wiki/Exception_handling_(programming)`](https://en.wikipedia.org/wiki/Exception_handling_(programming))

|

#### 现在解锁这本书的独家优惠

扫描此二维码或访问[packtpub.com/unlock](http://packtpub.com/unlock)，然后通过书名搜索此书。 | ![白色背景上的二维码 AI 生成的内容可能不正确](img/Split-B-PEN-Unlock-QR.png) |

| *注意：在开始之前，请准备好您的购买发票。* |
| --- |

# 16

# 架构、设计和未来

似乎每次关于人工智能未来发展的讨论都不可避免地要考虑到尼尔斯·玻尔的著名引言：“*预测是非常困难的，尤其是关于未来的预测*。”然而，当谈到人工智能时，我们已经有了一些关于未来会带来什么的想法。也就是说，我们阅读了艾萨克·阿西莫夫和其他作者的各种科幻书籍。我们观看了《终结者》和其他科幻电影和电视剧。甚至不同年代的卡通也体现了不同的未来版本，无论是《杰森一家》、《未来世界》还是各种动漫。我们对未来有什么样的概念；不确定性在于我们到达那里需要多长时间。

随着对 AI 的不断投资及其指数级增长，AI 和 GenAI 领域持续发展，其带来的新能力比大多数从业者预期的要快，更不用说跟上其步伐了。由于 AI 和 GenAI 为编码带来的新能力，软件工程的格局正在发生变化。在我们展望未来并估计未来进步的时间框架之前，回顾过去 10 年中加速转型的重大技术进步是有益的。本章简要回顾了这些主要进步，作为理解接下来发生的事情的概念框架。

本书使读者能够拥抱这些变化，并获得有效使用这些技能的技能，不仅限于编码，还包括一系列软件工程技能。随着我们继续学习，了解这些进步对行业的影响是有用的。这包括对软件工程师及其公司的影响，以及未来可能带来的影响。

在本章中，我们将探讨以下主题：

+   GenAI 的快速崛起

+   更快软件开发的经济效益

+   软件开发者格局的变化

+   GenAI 会改变编程语言吗？

+   GenAI 在软件工程中的未来

# GenAI 的快速崛起

直到 2012 年底，托马斯·达文波特（Thomas Davenport）和 DJ 帕蒂尔（DJ Patil）在他们的《哈佛商业评论》文章中宣布，数据科学是“**21 世纪最性感的工作**”（[`hbr.org/2012/10/data-scientist-the-sexiest-job-of-the-21st-century`](https://hbr.org/2012/10/data-scientist-the-sexiest-job-of-the-21st-century)）。仅仅十多年后，行业的转型速度之快令人瞩目。

在过去十年中的同一时期，神经网络在经历了几次 AI 寒冬之后，终于迎来了第三次复兴。尽管神经网络研究始于 20 世纪 50 年代，但它面临着达到极度炒作的期望的困难，这导致了资金和研究最少期的“AI 寒冬”。到 2012 年，新的神经网络架构已经出现。一种名为**卷积神经网络**（**CNN**）的 AlexNet 在 2012 年以大幅优势赢得**ImageNet 大规模视觉识别挑战赛**（**ILSVRC**）后，引起了计算机视觉社区的广泛关注。这改变了计算机视觉的进程，所有图像理解工作迅速转向 CNN。接下来的几年研究使 CNN 在 2016 年能够像人类一样从图像中提取信息，根据 ILSVRC 竞赛，尽管人类准确率水平仍有争议。

当计算机视觉工作通过 CNN 架构取得进展时，**Transformer 架构**通过 Google 在 2017 年的一篇论文被引入。这篇名为 *Attention Is All You Need* 的论文 ([`arxiv.org/abs/1706.03762`](https://arxiv.org/abs/1706.03762)) 描述了 **注意力机制** 和 Transformer 架构。自那以后，这种架构对神经网络和 AI 领域产生了巨大影响。尽管它为 AI 中的许多不同问题提供了改进的解决方案，但其主要受益者是 **自然语言处理**（**NLP**）这一子领域。这篇论文的工作导致了 **大型语言模型**（**LLMs**）的采用。

LLMs 对公众对 AI 的认知产生了深远的影响，尽管这一技术的早期代际远不如人意。OpenAI 在 2018 年和 2019 年发布了 GPT-1 和 GPT-2，这标志着 LLMs 的一大步。这些模型本质上是在大量文本上训练的预测模型，用于预测下一个单词。Transformer 架构学习了句子中单词之间的关系以预测下一个单词。实证研究表明，随着在更多数据上训练的更大模型，LLMs 的表现显著提高。GPT-3 于 2020 年发布，拥有 1750 亿个参数，相比之下，GPT-2 的参数为 15 亿。GPT-4 于 2023 年 3 月发布，参数量估计达到 1.76 万亿，是 GPT-3 的十倍。

InstructGPT 和 ChatGPT 作为利用底层 GPT LLMs 的新工具被开发出来。InstructGPT 被设计用来生成遵循用户指令的特定任务的文本。这些任务可以是电子邮件、摘要，甚至是代码。InstructGPT 包含基于训练数据的 AI 预测，以及基于人类反馈的 **强化学习** 技术，以调整基于人类反馈机制的下一个单词预测。相比之下，OpenAI 的 **ChatGPT** 在 2022 年 11 月的发布基于 GPT-3.5，可能是第一次普通用户能够与 LLM 互动而无需编程。它专注于与用户的对话和一般对话，但也包括了强化学习方法。这两个工具开发了导致 **提示技术** 领域的许多 LLM 方法。

LLM 和 ChatGPT 方法专注于准确预测跨语言的下一个单词。相同的模型通过在其它类型的数据上训练，开辟了其他研究途径。生物学家发现，在基因组学和蛋白质序列预测中，同样的结果可以应用。化学家正在利用这项技术创造具有特殊性质的新药物和化学物质。当然，这本书是基于将相同的预测技术应用于代码，通过在公共代码库上训练来实现的这一想法。

几年前，人工智能在媒体中很少被讨论。如今，财经新闻似乎聚焦于最近的技术进步及其对市场和更大经济的影响。下一节将讨论一些通用人工智能编码可能带来的经济问题。

# 经济学视角下的快速软件开发

软件开发是技术和数字经济的关键推动力。软件影响着现代社会许多方面，从政府到企业。大多数行业都依赖于软件。软件与全球工人的生产力紧密相连，使其成为关键的经济指标。

软件经济学领域研究并估算软件提供的价值与其开发相关成本。软件平台和工具旨在为使用它们的组织提供增量商业/经济价值。购买**现成商业软件**（**COTS**）、许可软件、定制第三方软件或内部构建的决策基于估算的增量价值主张。

利用通用人工智能，软件工程师可以显著更快地编写高质量的代码。根据本书中描述的技术，编写代码的效率应该会提高，而生成代码的质量应该保持相当高。自动化测试和文档的能力进一步降低了软件开发成本。从财务角度来看，相同劳动力使用通用人工智能将导致软件供应量的增加。目前通用人工智能编码赋能的成本为每月 25 美元或以下，这可以说是物有所值。成本的降低将增加对软件的需求，创造更大的自动化，并为企业增加价值。总有更多的问题需要解决，较低的开发成本障碍将改变软件工程的经济学。为了获得这些好处，软件工程师需要开始使用这项技术，下一节将讨论。

# 通用人工智能会被软件工程师采用吗？

通用人工智能为软件工程师带来的改进效率、速度和能力至少是一次范式转变，但可能是软件开发方式的革命。正如本书所讨论的，当前通用人工智能的能力包括许多软件工程师日常从事的任务。这包括编写代码和测试、生成文档、重构和优化代码。通用人工智能有助于从认知复杂的代码调试任务到不太需要关注的代码风格符合性等任务。

Gartner 预测，到 2027 年，将有 50%的软件工程师使用 AI 驱动的编码工具，这一比例将从 2023 年的 5%增长，当时生成式 AI 正处于炒作周期的顶峰([`www.gartner.com/en/newsroom/press-releases/2023-11-28-gartner-hype-cycle-shows-ai-practices-and-platform-engineering-will-reach-mainstream-adoption-in-software-engineering-in-two-to-five-years`](https://www.gartner.com/en/newsroom/press-releases/2023-11-28-gartner-hype-cycle-shows-ai-practices-and-platform-engineering-will-reach-mainstream-adoption-in-software-engineering-in-two-to-five-years))。在过去的两年里，生成式 AI 工具已经从由于错误众多而仅有边际效用转变为软件工程师和企业认为有价值的广泛工具。在这个短暂的时期内，KPMG 声称生成式 AI 已经成为软件工程师最有价值的编码伙伴([`kpmg.com/us/en/articles/2023/generative-artificial-intelligence.html`](https://kpmg.com/us/en/articles/2023/generative-artificial-intelligence.html))。在未来几年，这些工具将继续进化，并产生更高质量的代码、测试实例、文档字符串和文档。

考虑到生成式 AI 编码提供的改进准确性和整体效率，其影响可能不会在所有级别的开发者中均匀分布。下一节将探讨这些工具可能如何影响不同类别的程序员。

# 软件开发者的格局变化

在当前的市场定价下，生成式 AI 工具通常对所有开发者都是可用的。推测由于这项最近的技术，软件工程师的格局可能会发生怎样的变化，这很有趣。有些人认为，生成式 AI 工具将使竞争更加公平，因为任何开发者都能以更高的效率使用任何语言进行编程。他们认为，初级开发者可能会承担更多角色并增加交付的代码量，而更资深开发者可能会被组织淘汰。另一些人则持相反观点。

生成式 AI 工具的兴起也降低了软件开发门槛。由于包括语法、算法、库、**集成开发环境**（**IDEs**）、编译器消息等，每种语言的编程都有陡峭的学习曲线。在任意语言中打印“hello world”消息通常是第一个成就。如果编写新语言就像阅读一份外国报纸的头条，那么编码 AI 就是一个在请求时展示所有单词含义并解释语法的辅导老师。仅就编码而言，初级开发者可能会迅速在直接编码中变得高效。

工具如 ChatGPT 和 GitHub Copilot 将赋予开发者快速学习和在新编程语言中提高生产力的能力。总有新的语言和框架，所有软件工程师都必须不断学习和应用于项目。这意味着开发者可以更快地掌握新语言和框架，并在更短的时间内变得高效。这不仅对新的语言有影响，也对像 COBOL、FORTRAN 等其他仍在遗留系统中运行的老旧语言有影响，这些将在本节后面描述。

我们认为，格局将转向资深开发者，更多初级开发者可能会被 GenAI 工具取代。如果我们考虑典型的软件工程或计算机科学本科课程，主要的技术课程包括微积分、编程、数据结构、算法，以及可能包括软件工程。更高级的课程将包括网络、编译器、操作系统、大数据、AI、编程语言理论、优化、云计算等等。

初级开发者往往更专注于编写代码、测试和文档，而更资深开发者则关注系统需求、利益相关者、架构、设计和其他需要更多经验的复杂交互。GenAI 的效率明显与初级开发者的技能集重叠，但与资深开发者不重叠。

## 与软件工程知识体系相关的 GenAI

另一种观点是，在软件工程中，GenAI 在有限的编码范围内表现非常出色。IEEE 计算机学会编制了一份**软件工程知识体系**（**SWEBOK**）。当前版本于 2024 年开发，汇集了软件工程职业的集体技能、方法、知识等。它由专家们编纂，旨在达成对核心知识体系的共识。*表 16.1*列出了 SWEBOK 指南中发现的 18 个**知识领域**（**KAs**），可在[`www.computer.org/education/bodies-of-knowledge/software-engineering`](https://www.computer.org/education/bodies-of-knowledge/software-engineering)找到：

| **软件需求** | **软件架构** | **软件设计** |
| --- | --- | --- |
| 软件构建 | 软件测试 | 软件工程运营 |
| 软件维护 | 软件配置管理 | 软件工程管理 |
| 软件工程过程 | 软件工程模型和方法 | 软件质量 |
| 软件安全 | 软件工程专业实践 | 软件工程经济学 |
| 计算基础 | 数学基础 | 工程基础 |

表 16.1：软件工程知识体系（SWEBOK）2024 V4

与 SWEBOK 相比，GenAI 增强了一些流程，但只是整体技能集的一小部分。具体来说，它直接增强了软件构建和软件测试。间接地，它有助于支持软件维护和软件质量 KAs（知识域）。

## 软件工程师的民主化

GenAI 工具将帮助比许多人预期的更广泛的受众。我们讨论了如何帮助初级软件工程师和那些在新语言中提高速度的人获得编程帮助。资深开发者可以利用他们在架构、设计和其他软件系统方面的经验。有一大批前开发者有软件经验，但已经转向计算生物学、金融、商业或管理等领域。

之前离开该领域承担不同职责的前程序员可能会在不久的将来利用 GenAI 工具回归编程。如果他们已经多年没有编程，他们就需要学习新的语言、云计算、新的 IDE 等。通常情况下，他们不太可能投入大量时间学习这些众多的新技能。然而，有了 GenAI，他们现在能够在其特定角色内编写利用自己的专业知识的利基应用。这意味着软件工程的一部分可能会从独立于领域的专业技术技能转变为领域专家的额外技能。也就是说，而不是雇佣那些传统上将他们的技术技能应用于为银行、医疗保健或其他行业编写代码的专家软件工程师，这些行业可能会转向那些不仅能够编程而且有经验的领域实践者。我们已经开始在**机器人流程自动化**（**RPA**）中体验到这一点，那里的领域专家学习了工具并推动了特定的工作流程。在过去的几年里，我们看到类似的领域专家学习提示工程，以利用 LLMs（大型语言模型）在其工作流程管道中。我们在 AI 民主化中也看到了类似的转变，其中领域专家可能会被具有 AI 经验的领域专家所取代。

## 遗留软件和灵活团队

在 GenAI 技术的可解释性和指导帮助下，软件开发必将改变企业对软件以及特别是对遗留系统的处理方式。许多公司和行业依赖着几十年前开发的遗留软件系统，并且仍在运行。这些系统可能已经几十年历史，使用的是公司中只有一两个人曾经学习过的语言。这些软件系统对组织构成了重大风险。它们可能运行在遗留硬件上，但仍然是现有工作流程的一部分。理解这些系统，更不用说重写它们，都因成本过高而难以实现。

GenAI 系统现在可以在代码库上进行训练，并提供理解代码的支持，也许还能使它们能够快速重写。使用类似人类语言翻译的技术，代码可以使用 GenAI 技术高效地重写整个代码库，遵循更近期的文档和测试策略，并消除风险。在人员配置方面，这将减少对具有特定语言能力或对这些遗留系统有经验的开发者的需求。

随着与遗留系统的障碍降低，软件工程师可能获得在更广泛的项目上工作的能力。虽然行业领域的专业知识至关重要，但通过 GenAI，编码实现变得更加容易。

使用 GenAI，程序员可以更快地熟悉新的代码库并变得高效，但这也有其影响。GenAI 提供的速度增加了开发团队的灵活性。开发者可以更快地在项目之间切换，并为新项目做好准备。在敏捷项目开发实践和不断变化的需求下，这无疑是一个积极的成果。然而，这种灵活性可能会导致代码开发的外包增加，因为离岸团队也能快速增加以类似方式处理项目。这不是一个新趋势，许多团队仍然依赖于与客户互动的高级开发者、设计师和业务分析师。

本节重点介绍了参与软件工程的人员以及 GenAI 对这一领域的影响。下一节将讨论基于 GenAI 能力，计算机语言可能发生的潜在变化。

# GenAI 会改变编程语言吗？

软件编写的传统艺术和科学涉及创建一套计算机可以遵循的指令。这种通信目前是通过特定的编程语言进行的。指令通常包括存储和操作数据的各种数据结构的组合。指令可能包括算法，这些算法可以有效地排序、操作或转换数据以增加业务价值。大多数编程语言都可以执行这些操作，但它们的真正力量只有在使用添加的库或包时才能实现，这些库或包可以启用用户界面、网络、数据库交互等等。

我们今天的 GenAI 编码工具专注于编写和修改我们的代码。也就是说，ChatGPT、OpenAI API 和 GitHub Copilot 作为编程助手，从方法签名中猜测特定的编程语言代码行。虽然这加快了我们的方法级编程，但要求开发者了解问题如何分解为多个方法，以及方法之间根据其签名传递信息。

我们可以将使用大型语言模型（LLM）编写文档与使用生成式人工智能（GenAI）编写代码进行类比。ChatGPT 和其他 LLM 在为技术受众、医生或儿童重述文本方面表现出色，这相当于重构代码。要从头开始写一封信，不是一条单独的命令，而是一系列提示，这些提示规划了指令和顺序。同样，我们不会编写整个代码文件，而是必须将其分解成一系列命令，每个命令都可以发展成为代码。在这本书中，我们提供了许多例子来说明，GenAI 通常会编写合理的功能性代码。然而，通过将函数分解成更小的单元，GenAI 将产生更高质量、更易读的代码，这使维护变得更加容易。

生成式人工智能软件开发的下一阶段可能是与计算机进行更自然语言交流的方式。虽然计算机语言强调命令的精确性，但它们需要一种不自然且更正式的结构来传达思想。这需要学习曲线，并且可能会减慢开发速度。自然语言可以加快翻译成计算机可读形式的速度，并使软件的访问性更高。

计算机指令的自然语言的兴起可能需要一些时间，并可能面临一些可以通过伪代码克服的障碍。计算机语言的三个正式步骤是序列、迭代和选择（条件）。这些元素的交互是计算机程序的正式控制流。自然语言可以合理地处理序列和条件流，但迭代循环的概念可能不是语言中常见的部分。伪代码代表了一种相当任意的语法，但很好地捕捉了这三个正式步骤。可以被 LLM 解释以产生正式编程语言的通用伪代码可能进一步赋予更广泛的开发者权力。

# 生成式人工智能在软件工程中的未来

本节首先讨论感觉编码，然后把软件工程的未来分解为两个不同的视角。短期考虑的是未来几年，而长期考虑的是该领域可能在五年或更长时间后可能的样子。

## 感觉编码

感觉编码（Vibe coding）是一种新兴趋势，其中开发者用自然语言描述他们想要完成的事情，而将技术编码方面留给大型语言模型（LLM）。使用 LLM 编写代码无疑是本书的一个主题，而感觉编码本质上将这一点推向了极致。本质上，感觉编码提供了一种快速原型设计的形式，这是整体软件开发过程中的宝贵部分，尤其是在定义需求方面。我们相信软件社区将认识到它的价值。然而，对于大型项目来说，代码质量很重要，因为与软件相关的成本大多集中在维护上，例如添加新功能。许多不愉快的梗描述了“感觉调试”由感觉编码产生的相对低质量代码的困难。我们预计未来将在我们现在所处的位置和感觉编码之间找到平衡。接下来，我们将描述短期和长期的预期。

## 短期

在过去的一年里，通用人工智能市场蓬勃发展，许多开发者现在正在使用这项技术。它作为 VSCode 扩展、JetBrains 产品包括 PyCharm 插件以及其他集成开发环境（IDE）提供，因此易于获取。此外，具有内置通用人工智能功能的新 IDE 已进入市场，包括 Cursor、Windsurf 和 Replit。其他工具，如 AWS CodeWhisperer 和 Tabnine，为多种语言提供代码建议。所有这些都以较低的价格提供，与开发者时间的潜在节省相比。在短期内，所有这些都将提高其准确性，并在更短的时间内创建更好的软件。

## 长期

在许多人采用通用人工智能（GenAI）编码方法并能够有效使用它们之后，技术推动将集中在尝试从正式需求规格说明转移到代码上。在软件开发生命周期中的第一步，需求收集是一个正式的过程，用于理解预期的目标、用户界面、非功能性需求等。在许多组织中，还有更多正式的图表，例如**统一建模语言**（**UML**），用于描述设计。其他还包括来自**Balsamiq**和**Figma**的样本用户界面设计。目前正在努力将这些图表直接自动转换为代码。

通用人工智能尚未解决软件开发流程的其他许多方面。规划、设计、高级集成、DevOps、部署、编排等软件方面受到通用人工智能的影响很小。我们对长期前景感到兴奋，但对我们认为通用人工智能技术将在这些领域取得实质性进展的时间没有意见。

## 人工智能会取代软件工程吗？

软件工程的需求将继续存在两个原因。首先，我们知道 GenAI 在编写部分内容方面比编写完整端到端内容更为有效。对于散文文本，我们并不期望 GenAI 起草完整的报告，但我们可以将其分解为章节和段落，并使用提示工程。一些主要用例是网络搜索和摘要，这在软件工程和改进文本方面有弱相似性，本质上是对代码的重构。使用软件工程，需要了解软件结构和支持架构的知识，以便将代码分解为模块、文件和简洁的方法。即使个别方法可能完全使用 GenAI 制作，对这些任务的人类技能的需求可能还会持续几年。人类将转向架构、设计和集成等角色，并最终仍需对代码进行验证。

第二个原因是，当 GenAI 与广泛可用的代码库一起工作时最为有效，但如果没有这样庞大的示例集，它通常会失败。大多数软件工程师平均每 3-5 年就需要学习一门新语言。当然，其中一些是由于换工作。然而，新的语言、框架以及它们的新版本仍在不断涌现——这些都没有足够大的代码库来训练 GenAI 模型。特定领域的语言是另一个有限的训练数据的良好例子。此外，数据库、网络安全、量子计算等最新技术也需要软件工程师，因为它们各自的代码库仍在编写中。

## 风险和治理

目前，人类对产生的代码最终负责，但使用 GenAI 提出了许多挑战。在运输、银行和医疗保健等高度监管的行业中，AI 的使用将受到重大审查。提供可解释性和理解不同程序员、代理或 AI 创建了代码的不同部分的能力可能会成为标准。需要解决软件的风险、法律责任和伦理考虑，包括责任和保障措施。今天围绕自动驾驶汽车的伦理、道德和法律问题提供了考虑的一些好例子。麻省理工学院的电车问题([`en.wikipedia.org/wiki/Trolley_problem`](https://en.wikipedia.org/wiki/Trolley_problem))和道德机器([`en.wikipedia.org/wiki/Moral_Machine`](https://en.wikipedia.org/wiki/Moral_Machine))提供了更多挑战的例子。

另一个挑战是软件的版权问题。对于常规文本，新闻集团、金融时报、美联社和其他媒体公司已与 OpenAI 协商，以许可其文本。微软和谷歌也与其他内容提供商协商，以扩大其训练集而不违反版权法。对于软件代码，法律不太明确，因为它是一个相对较新的问题，尚未得到解决。GenAI 可能会复制受版权保护的代码是肯定可能的。由于 GenAI 的准确性部分取决于训练集的大小，可能需要更多的代码许可来提高性能。

编程语言的教育和技能评估也必须适应。学校和大学已经教授编程技能数十年。正如拼写和语法检查器是撰写报告的标准做法一样，通用人工智能（GenAI）最终可能不仅被接受，而且成为软件开发的一个必要部分。大学往往更关注语言细微差别和语法，而不是可用的工具集，例如编译器、调试器和代码检查器。然而，忽视 GenAI 将是困难的，因为它将被广泛使用。面试官经常使用 LeetCode 形式的编程问题来筛选候选人，尽管许多问题比行业常见做法更学术化。随着 GenAI 的应用，这种低级编码技能的相关性变得更低，我们预计这些形式的面试问题也会随之演变。

# 摘要

在过去几年中，通过一系列重大技术创新，人工智能（AI）和通用人工智能（GenAI）的能力得到了快速发展。由于 GenAI 在软件工程生产率上的提升且价格低廉，它将增加代码的编写量并降低总体成本。这将改变软件工程师的格局，可能更有利于经验丰富的资深开发者，他们在架构、设计和 SWEBOK 方面有更多经验。它也可能使具有深厚领域经验的专家能够编写更多代码。使用 GenAI 支持，可能重写遗留系统，这将使公司能够以更敏捷的方式跨项目使用软件开发人员。

向往采用 GenAI 进行编码的强烈运动正在兴起，它已经被集成到许多集成开发环境（IDE）中。从长远来看，我们将看到它如何超越编码任务并进入软件工程的更多方面。GenAI 仍然需要向计算机传达命令，自然语言最终可能补充或取代编程语言，但伪代码可能是下一个前沿。在可预见的未来，世界仍然需要软件工程师。仍然有许多问题需要管理，从风险到合规性，但 GenAI 已经到来，并且已经开始加速软件工程。

# 进一步阅读

要了解更多关于本章所涵盖的主题，请查看以下资源：

+   托马斯·达文波特和 DJ Patil。哈佛商业评论。[`hbr.org/2012/10/data-scientist-the-sexiest-job-of-the-21st-century`](https://hbr.org/2012/10/data-scientist-the-sexiest-job-of-the-21st-century)

+   人工智能寒冬：[`www.historyofdatascience.com/ai-winter-the-highs-and-lows-of-artificial-intelligence/`](https://www.historyofdatascience.com/ai-winter-the-highs-and-lows-of-artificial-intelligence/)

+   Alex Krizhevsky，Ilya Sutskever，Geoffrey E. Hinton。*使用深度卷积神经网络进行 ImageNet 分类*。NeurIPS 2012。[`proceedings.neurips.cc/paper_files/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf`](https://proceedings.neurips.cc/paper_files/paper/2012/file/c399862d3b9d6b76c8436e924a68c45b-Paper.pdf)

+   ImageNet 大规模视觉识别挑战。[`arxiv.org/pdf/1409.0575`](https://arxiv.org/pdf/1409.0575)

+   *注意力即一切*。[`en.wikipedia.org/wiki/Attention_Is_All_You_Need`](https://en.wikipedia.org/wiki/Attention_Is_All_You_Need)

+   Gartner 人工智能实践炒作周期。[`www.gartner.com/en/newsroom/press-releases/2023-11-28-gartner-hype-cycle-shows-ai-practices-and-platform-engineering-will-reach-mainstream-adoption-in-software-engineering-in-two-to-five-years`](https://www.gartner.com/en/newsroom/press-releases/2023-11-28-gartner-hype-cycle-shows-ai-practices-and-platform-engineering-will-reach-mainstream-adoption-in-software-engineering-in-two-to-five-years)

+   *生成式人工智能给软件开发带来的惊人力量*。[`kpmg.com/us/en/articles/2023/generative-artificial-intelligence.html`](https://kpmg.com/us/en/articles/2023/generative-artificial-intelligence.html)

+   H. Washizaki 编著，*软件工程知识体系指南（SWEBOK 指南），版本 4.0*，IEEE 计算机协会，2024。[`www.computer.org/education/bodies-of-knowledge/software-engineering`](https://www.computer.org/education/bodies-of-knowledge/software-engineering)

+   道德机器。[`en.wikipedia.org/wiki/Moral_Machine`](https://en.wikipedia.org/wiki/Moral_Machine)

+   拉车问题。[`en.wikipedia.org/wiki/Trolley_problem`](https://en.wikipedia.org/wiki/Trolley_problem)

# 免费订阅电子书

新框架、演进的架构、研究新发现、生产分解——*AI_Distilled* 将噪音过滤成每周简报，供直接与大型语言模型和生成式人工智能系统打交道的工程师和研究人员阅读。现在订阅，即可获得免费电子书，以及每周的洞察力，帮助您保持专注并获取信息。

在 [`packt.link/TRO5B`](https://packt.link/TRO5B) 订阅或扫描下面的二维码。

![白色背景上的二维码  人工智能生成的内容可能不正确。](img/B31534_Newsletter_NEW.png)

# 附录

# 设置 OpenAI 账户

创建 OpenAI 账户的步骤如下：

1.  导航到 [`openai.com/`](https://openai.com/)。在页面左上角，点击 ChatGPT 或 API 平台以开始账户创建过程，如图 *图 1* 所示：

![图 1：从 OpenAI API 访问 ChatGPT 和 API 平台](img/B31534_Appendix_1.png)

图 1：从 OpenAI API 访问 ChatGPT 和 API 平台

1.  每个链接都会带您到一个账户创建页面，您可以使用 Google、Microsoft 或 Apple 等流行的平台进行注册，或使用电子邮件地址进行注册，如图 *图 2* 所示：

![图 2：OpenAI 平台注册页面](img/B31534_Appendix_2.png)

图 2：OpenAI 平台注册页面

1.  要使用电子邮件地址注册，请点击 **注册**。

重要提示

截至 2025 年 8 月，你需要创建两个独立的账户：一个用于 ChatGPT，一个用于访问 API 的 OpenAI 平台。

在下一节中，我们将介绍虚拟环境的设置。

# 创建虚拟环境

Python 中的 **虚拟环境** 是一个隔离的设置，确保依赖项的可重复性，这些依赖项是我们项目所依赖的外部库。

例如，考虑以下代码：

```py
import pandas as pd
df = pd.read_csv('df.csv')
df.to_markdown() 
```

在这里，我们依赖于 Pandas，这是一个可在 [`github.com/pandas-dev/pandas`](https://github.com/pandas-dev/pandas) 找到的第三方和开源库。Pandas 提供了 `read_csv` 函数，它返回一个 `DataFrame`。从 1.0.0 版本开始，该版本只能在 `Python 3.6.1` 或更高版本上运行，`DataFrame` 类还包括 `to_markdown` 方法。如果我们使用 Python 或 Pandas 的早期版本，此代码可能无法运行。

通常，开发者会在名为 `requirements.txt` 的文件中指定他们所需的依赖项。在这本书的仓库中，你可以找到我们在 `requirements.txt` 中使用的外部库的规范，如图 *图 3* 所示：

![图 3：本书的 `requirements.txt` 文件](img/B31534_Appendix_3.png)

图 3：本书的 `requirements.txt` 文件

在本书的后续章节中，当我们深入探讨 **软件开发生命周期 (SDLC)** 功能时，这些项目的需求文件将包括特定的版本，如图 *图 4* 所示：

![图 4：带有版本控制的 `requirements.txt`，来自第十章](img/B31534_Appendix_4.png)

图 4：带有版本控制的 `requirements.txt`，来自 *第十章*

就像在这个图中一样，我们的生产项目也包括特定的版本控制。对于依赖项版本控制解析，我们利用依赖和环境管理工具，如 *pipenv*，它提出了针对特定版本控制的依赖管理。其他开发者可能使用 *Conda*、*poetry* 或其他工具。然而，在这本书中，我们将使用 Python 内置的 *venv* 工具来设置我们的环境。

## 虚拟环境提示

在本书中，我们利用 GenAI 对 SDLC 的每个步骤进行了利用，安装虚拟环境也不例外。这项任务非常适合在 GitHub Copilot 聊天窗口中使用 **代理** 模式，并使用遵循在 *第四章*** 中详细讨论的 **Five S’s** 的提示。

安装我们的依赖项的提示应包括以下组件：

1.  **Python 版本**：应使用哪个版本的 Python 运行此项目，在我们的例子中，是 *Python 3.11*。

1.  **环境工具**：可以是 *venv* 或其替代品。

1.  **需求文件**：默认情况下是放置在项目根目录的 `requirements.txt`。

1.  **环境名称**：常见的做法是将环境命名为 `.venv`。我们也可以通过在项目名称前加上点来定制它，例如 `.supercharged`。

1.  **环境位置**：库代码通常安装在项目根目录。

考虑到这些因素，以下是我们可以在 GitHub Copilot 中使用的示例提示，无论是在 PyCharm 还是 VS Code 中：

```py
CONTEXT: You are provided with:
1\. Python version enclosed with {{{ VERSION }}}
2\. Requirements file path enclosed with {{{ PATH }}}
3\. Environment tool enclosed with {{{ TOOL }}}
4\. Environment name enclosed with {{{ ENV NAME }}}
5\. Location for the environment enclosed with {{{ Location }}}
TASK: Set up a virtual environment using the Python version, requirements file path, using the provided name and location for this project. VERSION: {{{ Python 3.11 }}
PATH: {{{ requirements.txt }}}
TOOL: {{{ venv }}}
ENV NAME: {{{ .supercharged }}}
LOCATION: {{{ project root }}} 
```

为了参考，使用 GitHub Copilot 和底层 *Claude Sonnet 4.0* 的代理模式设置环境、激活它以及安装其依赖项的步骤如下。*图 5* 展示了创建具有我们所需名称的环境并激活它：

![图 5：激活虚拟环境](img/B31534_Appendix_5.png)

图 5：激活虚拟环境

*图 6* 展示了根据 `requirements.txt` 指定的依赖项安装过程：

![图 6：依赖项安装](img/B31534_Appendix_6.png)

图 6：依赖项安装

安装完成后，Copilot 可能会提出一些测试，例如验证包的正确版本，并以如 *图 7* 所示的成功消息结束：

![图 7：成功安装消息](img/B31534_Appendix_7.png)

图 7：成功安装消息

设置完成后，我们可以看到在存储库中添加了 `.supercharged` 文件夹，如 *图 8* 所示：

![图 8：添加到存储库的文件](img/B31534_Appendix_8.png)

图 8：添加到存储库的文件

为了参考，以下是我们可以手动安装虚拟环境的典型三个 shell 命令：

```py
python3.11 -m venv .supercharged
source .supercharged/bin/activate
pip install -r requirements.txt 
```

接下来，我们将看到如何指导 git 忽略依赖项文件。

## 将虚拟环境添加到 .gitignore

由于 `requirements.txt` 已足够在任意机器上复制依赖项，因此无需在存储库中包含实际的环境代码。因此，最佳实践是忽略已安装的依赖项。我们可以通过将已安装的要求路径添加到 `.gitignore` 文件中来实现这一点。我们可以在代理模式下链式添加另一个提示：

```py
Add the environment path to .gitignore file. 
```

如 *图 9* 所示，此提示成功将虚拟环境路径添加到 `.gitignore` 文件中。

![图 9：将路径添加到.gitignore 文件中](img/B31534_Appendix_9.png)

图 9：将路径添加到.gitignore 文件中

如果您为环境命名不同，Copilot 可能会将正确的名称添加到文件中。如果您使用了`.supercharged`或`.venv`，则无需更改，因为这些名称已经存在于我们的文件中。

重要提示

现在您已经成为超级编码者，我们鼓励您帮助您的同事在设置新的虚拟环境时使用这些提示。这些提示可以根据不同的环境工具、环境名称和项目进行调整，从而在代理模式下工作减少出错的机会

# 进一步阅读

要了解更多关于本章所涵盖的主题，请查看以下资源：

+   Venv，内置的虚拟环境：[`docs.python.org/3/library/venv.html`](https://docs.python.org/3/library/venv.html)

+   Pipenv，依赖和环境管理工具：[`pipenv.pypa.io/en/latest/`](https://pipenv.pypa.io/en/latest/)

+   Poetry，依赖和环境管理工具：[`python-poetry.org/docs/dependency-specification/`](https://python-poetry.org/docs/dependency-specification/)

+   Conda，依赖和环境管理工具：[`anaconda.org/anaconda/conda`](https://anaconda.org/anaconda/conda)

![Packt 新标志](img/Packt_Logo_New.png)

[packtpub.com](http://packtpub.com)

订阅我们的在线数字图书馆，全面访问超过 7,000 本书籍和视频，以及领先的行业工具，帮助您规划个人发展并推进职业生涯。如需更多信息，请访问我们的网站。

# 为什么订阅？

+   使用来自超过 4,000 位行业专业人士的实用电子书和视频，减少学习时间，增加编码时间

+   通过为您量身定制的技能计划提高学习效果

+   每月免费获得一本电子书或视频

+   完全可搜索，便于快速访问关键信息

+   复制粘贴、打印和收藏内容

您知道吗？Packt 为每本书都提供了电子书版本，包括 PDF 和 ePub 文件。您可以在[packtpub.com](http://packtpub.com)升级到电子书版本，并且作为印刷书客户，您有权获得电子书副本的折扣。如需了解更多详情，请联系我们`customercare@packtpub.com`。

在[www.packtpub.com](http://www.packtpub.com)，您还可以阅读一系列免费的技术文章，订阅各种免费通讯，并享受 Packt 书籍和电子书的独家折扣和优惠。

# 您可能喜欢的其他书籍

如果您喜欢这本书，您可能会对 Packt 的其他书籍感兴趣：

![9781803238753.jpg](https://packt.link/1803238755)

**构建代理 AI 系统**

Anjanava Biswas，Wrick Talukdar

ISBN：978-1-80323-875-3

+   掌握 GenAI 和代理系统的核心原则

+   理解 AI 代理如何在动态环境中操作、推理和适应

+   使 AI 代理能够分析自己的行为并进行即兴发挥

+   实现人工智能代理可以利用外部工具并规划复杂任务的系统

+   应用方法以增强人工智能的透明度、问责制和可靠性

+   探索跨行业人工智能代理的真实世界应用

![一本带有彩色鸟和文字的封面  AI 生成的可能不正确。](https://packt.link/1837022011)

**LangChain 生成式人工智能 - 第二版**

本·奥法特，列昂尼德·库利金

ISBN: 978-1-83702-201-4

+   使用 LangGraph 设计和实现多代理系统

+   实施在部署前识别问题的测试策略

+   为生产环境部署可观察性和监控解决方案

+   构建具有重新排序能力的代理 RAG 系统

+   使用 LangGraph 和 MCP 架构可扩展、生产就绪的人工智能代理

+   与最新的 LLM 和 Google Gemini、Anthropic、Mistral、DeepSeek 以及 OpenAI 的 o3-mini 等提供商合作

+   设计符合现代道德实践的合规人工智能系统

# Packt 正在寻找像你这样的作者

如果你有兴趣成为 Packt 的作者，请访问 [authors.packtpub.com](http://authors.packtpub.com) 并今天申请。我们已与成千上万的开发者和技术专业人士合作，就像你一样，帮助他们将见解分享给全球技术社区。你可以提交一般申请，申请我们正在招募作者的特定热门话题，或者提交你自己的想法。

# 分享你的想法

现在你已经完成了 *Supercharged Coding with GenAI*，我们很乐意听听你的想法！如果你在亚马逊购买了这本书，请[点击此处直接进入该书的亚马逊评论页面](https://packt.link/r/1836645295)并分享你的反馈或在该购买网站上留下评论。

你的评论对我们和科技社区都很重要，并将帮助我们确保我们提供高质量的内容。

# 加入我们的 Discord 和 Reddit 空间

你不是唯一一个在导航碎片化工具、不断更新和不确定的最佳实践的人。加入一个不断壮大的专业社区，分享那些没有进入文档的见解。

| 通过更新、讨论和作者幕后洞察保持信息畅通。加入我们的 Discord 空间 [`packt.link/z8ivB`](https://packt.link/z8ivB) 或扫描下面的二维码：![一个白色背景上的二维码  AI 生成的可能不正确。](img/B31534_Discord_NEW.png) | 与同行建立联系，分享想法，并讨论真实世界的 GenAI 挑战。在 Reddit 上关注我们 [`packt.link/0rExL`](https://packt.link/0rExL) 或扫描下面的二维码：![一个白色背景上的二维码  AI 生成的可能不正确。](img/B31534_Reddit_NEW.png) |
| --- | --- |

# 目录

符号

__call__ 方法 110

A

人工智能配对程序员 45

人工智能寒冬 6

美国邀请赛数学考试 (AIME) 78

应用程序编程接口 (API) 10, 17

人工智能 (AI) 6, 389

助手提示 19, 107

B

Big-O 表示法 262, 337

C

calculate_distance 函数 250

调用

调用参数，使用 ChatGPT 和 OpenAI 自定义 182, 183

使用 GitHub Copilot 进行代码调试 177-179

使用示例参数创建 175, 176

中央处理器 (CPU) 336

连锁提示，代码优化 351

运行时优化 352-354

空间优化 354-357

连接 209

思维链 (CoT) 209, 241, 361

重构 250, 251

使用 ChatGPT 重构 254, 255

使用 GitHub Copilot 重构 251-253

使用 OpenAI API 重构 254, 255

ChatGPT 9, 154, 155

连接 228-231

用于测试 318-320

用于解释代码 166-168

用于性能重构 258, 259

用于重构思维链 (CoT) 254, 255

用于搜索过时的文档字符串 304-307

ChatGPT 基准 213, 215

ChatGPT 最大容量

分析 343

在内存限制内确定 349-351

在运行时限制内确定 347, 348

分析运行时 344

分析空间使用情况 345, 346

Claude 7

代码分析和重构工具 5

代码库结构

阅读 160, 161

代码补全设计

概述 46, 47

代码优化

使用链式提示 351

代码可读性

提高 247, 248

代码重构 242

限制，使用 IDE 工具 248, 249

代码异味 5

逗号分隔值 (CSV) 338

商业现成产品 (COTS) 392

压缩稀疏列 (CSC) 357

压缩稀疏行 (CSR) 357

计算机编程 4

上下文窗口 151

示例 152

持续集成和持续部署 (CI/CD) 系统 5

持续集成/持续开发 (CI/CD) 管道 300

对比学习 274

卷积神经网络 (CNN) 390

Copilot

连接 236, 237

使用大型语言模型 (LLM) 进行 CoT 推理

为 GitHub Copilot 221-224

使用 ChatGPT 计算几何平均数 225, 226

使用 OpenAI API 计算几何平均数 226, 227

GPT-o 系列 219

使用 217, 219

D

数据驱动测试 321, 322

装饰器 361, 368

使用 368, 369

深度学习 7, 150

依赖代码

调试 183, 184

距离函数

实现 244, 245

Dockerfile 159, 161

文档字符串

生成，用于 Singleton __call__ 方法 112, 113

生成，使用 OpenAI API 110

Google 风格文档字符串 113-116

文档字符串，与 GenAI

编写 300

编写，针对整个文件 302, 304

编写，针对单个方法 300, 301

双下划线 (dunder) 105

E

欧几里得距离 243

评估指标 80

专家系统 6

极限编程 (XP) 10, 243, 322

F

少样本装饰器风格

用于 GitHub Copilot 378, 380

少样本学习 152, 189, 190, 265, 274, 361

代码实现，使用 OpenAI API 200-203

用于代码重构 190, 192

在 ChatGPT 中 381-383

使用，作为风格指南 378

与 OpenAI API 一起工作 199

少样本提示，与 ChatGPT

利用 192

输出改进，通过代码重构 193-195

结构 192

微调 152, 203

使用，对于 OpenAI API 383-387

使用，作为风格指南 378

与提示工程对比 268

FizzBuzz 363

用例 363

Frobenius 范数 243

G

Gemini 7

通用人工智能 390, 391

软件工程师采用 392, 393

用于编码任务 78, 79

用于单元测试 312-317

编程语言 396, 397

创建样本数据 329-331

通用人工智能用于高级编码模式

使用装饰器 368, 369

装饰器实现的逆 CoT 369-374

使用 368

通用人工智能的未来 397

长期 398

风险和治理 399

短期 398

软件工程，需求 398, 399

氛围编码 397

通用人工智能工具包 9

ChatGPT 9

GitHub Copilot 10

OpenAI API 10

生成式人工智能 (GenAI) 3, 17

编码的好处 12

编码的缺点 12, 13

提高软件开发 11

生成式预训练变换器 (GPT) 7, 9

几何平均

分析 59, 60

使用聊天完成进行计算 57

指导性演示 58, 59

几何平均计算

分析 63-65

完成和键盘快捷键 61

指导性演示 61, 62

几何平均范围 210, 211

GitHub Copilot 10, 46, 155, 164, 196

账户，激活 50, 51

聊天功能，使用 54, 56

代码，分析 65, 66

代码，使用 VS Code 中的 Copilot 编辑器窗口分析 67, 68

代码补全设计概述 46, 47

代码补全策略 49

使用 177-179 调试

依赖代码，调试 180, 181

/explain 命令，使用 164, 165

扩展，为 VS Code 安装 53

错误实现，修复 125

免费账户限制 48

导入和标签 118-121

交互模式 54

引导提示结构 117, 118

插件，为 PyCharm 安装 52

精确提示，制作 117

定价 49

设置，在 PyCharm 中 51

设置，在 VS Code 中 51

简短提示，无注释冗余 124, 125

单个任务 121-123

风格指南 196-199

单元测试，评估 126-134

用于分析运行时 339

用于分析空间使用情况 339

用于重构思维链（CoT） 251-253

用于搜索过时的文档字符串 304-307

使用描述性名称说明 123

使用文档字符串说明 123

使用类型提示说明 123

使用单元测试说明 123

在 VS Code Jupyter Notebook 中工作，用于代码分析 69

GitHub Copilot 基线 213

GitHub Copilot 命令

与 296-300 一起工作

GitHub Copilot，提示分析

提示技术，与 PyCharm 聊天应用 135

单个任务，以修复方法实现 135, 136

单个任务，与 VS Code 135

具体简短的提示原则 134, 135

结构化提示原则，带有引导提示 134

周围上下文，与 VS Code 135

Google 风格 295

Google 风格的文档字符串 112-116

分析 116, 117

GPT-3.5 模型 154

GPT-4o 迷你版 209

用于计算二次根 271

GPT-o 系列 219

采用 220

图形处理单元（GPU）357

图形用户界面（GUI）269

H

超文本传输协议（HTTP）19, 161

I

IEBUPDTE 5

ImageNet 大规模视觉识别挑战（ILSVRC）390

实现代码 311

在上下文中学习 189, 190, 265

集成开发环境（IDE）5, 45, 104, 362, 393

交互模式

分析 54

聊天 54

补全 54

装饰器实现的逆 CoT 369-374

与 ChatGPT 的逆 CoT

应用 375

装饰器，监控 375, 377

与 OpenAI 的逆 CoT

应用 375

装饰器，监控 377, 378

J

JSONL 文件

制作，用于微调 273

文件结构，微调 274, 275

策略 275

JSONL 文件，策略

仅代码 276

无注释的代码 277, 278

对比性仅代码 276, 277

对比性无注释 278-280

K

Kite 6

L

L1 范数 243

L2 范数 243

语言模型 (LMs) 7

大型语言模型 (LLMs) 4, 18, 45, 78, 106, 149, 209, 265, 335, 361, 390

ChatGPT，用于解释代码 166-168

代码任务，专业化 268

成本 280, 281

/explain 命令，与 GitHub Copilot 一起使用 164, 166

微调模型，使用 284

微调 267, 268

微调实践 287

微调作业，启动 281-284

微调，使用 OpenAI GUI 280

局限性 153, 154

OpenAI API，用于解释代码 168, 169

输出，比较 285-287

上升 6, 7

使用，用于解释代码 163

代码检查器 5

Llama 7

LLM 输出性能

上下文窗口，添加 151, 152

微调 152

改进 151

提示工程 151

检索增强生成 153

LLMs 专业化 267

示例 267

记录 362-365

长期 398

M

机器学习 (ML) 6

Maestro I 5

魔法属性 364

曼哈顿距离 159-162, 243

对于矩阵 162, 163

内存空间使用 338

效率权衡，平衡 339

空间复杂度 338

米勒定律 295

模型精通 79

监控 362, 366, 367

N

自然语言生成 (NLG) 7

自然语言处理 (NLP) 6, 7, 18, 155, 390

神经网络 6

神经元 7

n-gram 313

非项目文件 169

整个文件，解释 170

解释，使用 ChatGPT 172, 173

解释，带有上下文 171, 172

解释，使用 OpenAI API 174, 175

NumPy/SciPy 风格 295

O

单次学习 152

OpenAI 17

计费、计算 30, 31

项目 API 密钥，获取 22-24

使用，用于性能重构 258, 259

OpenAI 账户

速率限制 31

参考链接 403

设置 403, 404

使用限制 31

OpenAI API 10, 18

正文 19

端点 19

标题 19

历史 231-235

HTTP 方法 19

精确提示，制作 107

提示 256

路由聊天功能，到代码补全 37-41

结构化提示 107, 108

系统提示，包括周围上下文和单一任务 108

通过 RESTful HTTP 请求 19

用于解释代码 168, 169

用于提取 Python 对象属性 104-106

用于生成文档字符串 110

用于重构思维链 (CoT) 254, 255

用于搜索过时的文档字符串 304-307

用户提示，带有具体说明 109

用于生成代码 36

向量化 260, 261

OpenAI API 基准 215-217

OpenAI API 演示平台

进行实验 269-271

使用 GPT-4o mini 计算二次根 271

OpenAI API 请求

成本计算 28

参数分析 32-36

OpenAI 图形用户界面

用于微调大型语言模型 (LLMs) 280

openai Python 包

安装 21

OpenAI API 请求，发送 24-27

OpenAI 标记化器

参考链接 29

过时的文档字符串

搜索，使用 ChatGPT 304-307

搜索，使用 GitHub Copilot 304-307

搜索，使用 OpenAI API 304-307

P

配对程序员 10

参数化装饰器 373

模式匹配 5

PEP 257 295

性能重构

高级功能 261

使用 ChatGPT 258, 259

使用 GenAI 256

使用 GitHub Copilot 256-258

使用 OpenAI 258, 259

精确提示 81

制作，用于 GitHub Copilot 117

生产系统 8

分析运行时间 339-341

使用 GitHub Copilot 339

分析空间使用情况 342

使用 GitHub Copilot 339

程序运行时间 336, 337

运行复杂度，测量 337

LLM 的提示链

ChatGPT，与 228-231 链接

Copilot，链式操作 236, 237

OpenAI API，历史 231-235

使用 227

提示工程 10, 151

用于编码 188, 189

与微调对比 268

提示工程，技术 203, 266

额外方法 206

大规模错误修复 203, 204

思维链（CoT）提示 205, 206

迭代提示 204, 205

基于模板的提示 205

提示实现范围 210

提示技术 391

提示 18

助手提示 19

系统提示 19

用户提示 18

OpenAI 提供的提示样本 94, 95

分析 99-101

思维链提示 101

代码调试 95, 96

指导性演示 97-99

迭代提示 101

ChatGPT 的提示

分析 92- 94

制作 84, 85

引导式演示 87, 88

单个任务 89

具体指令 90-92

结构化 88

周围上下文，添加 89

编码任务的提示，最佳实践 81

短提示 83

每个提示单任务 82

具体指令 83

结构化 81

周围信息 82

概念验证 (POC) 9

提交请求 (PR) 78

PyCharm 5

使用，用于设置 GitHub Copilot 51

PyCharm 图形用户界面

转换，到 CLI 85, 87

Python 对象属性

提取，针对 OpenAI API 104-106

Python 线程 80

Q

二次根

计算器，实现 272, 273

计算，使用 GPT-4o mini 271

R

抛出错误 362

随机存取存储器 (RAM) 336

Reddit 6

重构 241

类型 245, 246

重构任务

性能 246

可读性 246

结构变化 246

回归测试包 330

强化学习 391

从人类反馈中进行强化学习 (RLHF) 154

表现状态传输 (REST) 19

每日请求数 (RPD) 31

每分钟请求数 (RPM) 31

ReSharper 5

RESTful HTTP 请求 17

reStructuredText (reST) 295

检索增强生成 153

检索增强生成 (RAG) 151

Reuters-21578 数据集 142

版本控制系统 5

机器人流程自动化 (RPA) 395

S

单一职责原则 361, 367

单任务原则 364

单例设计模式 104, 110, 111

小型语言模型 149

软件开发 391, 392

工具，演变 4-6

软件开发生命周期 (SDLC) 4-8, 235, 287, 293, 335, 362, 405

软件开发工具 393, 394

历史软件和灵活团队 395, 396

软件工程知识体系 (SWEBOK) 394

软件工程师民主化 395

软件文档 294, 295

软件工程 4

软件工程知识体系 (SWEBOK) 394

软件测试 5

SonarQube 5

Sphinx 风格 295

Spyder 5

Stack Overflow 6

统计方法 142-147

结构化提示 107, 108

系统提示 19, 107

单任务 108

带有周围上下文 108

T

测试代码 311

测试驱动开发 (TDD) 9, 243, 311, 313, 322-325

与 ChatGPT 327，329 合作

在 PyCharm 327 内

在 VS Code 325，326 内

时间和空间分析 336

内存空间使用 338

程序运行时间 336，337

令牌 17，28，29

每分钟令牌数 (TPM) 31

传输器架构 390

Turbo Pascal 5

U

UCI 机器学习仓库 142

非预期输入

处理 365，366

统一标记语言 (UML) 398

unittest 框架 5

单元测试

与 GenAI 312-317 合作

广义逼近定理 150

美国初级数学奥林匹克赛 (USAJMO) 78

美国数学奥林匹克赛 (USAMO) 78

用户提示 18，107

使用特定指令 109

V

向量化计算 256

版本控制系统 5

感觉编码 13，397

虚拟环境 404

添加到 .gitignore 409

创建 404，405

提示 406-408

Visual Studio 5

Visual Studio Code (VS Code) 5

用于设置 GitHub Copilot 51

VS Code Jupyter Notebook 用于代码分析

分析 72，74

GitHub Copilot，与 69 合作

指导性演示 69-71

W

word2vec 模型 149，150

单词级模型

扩展 147-149

Z

零样本跨语言迁移 153

零样本学习 152

Zipf 定律 142
