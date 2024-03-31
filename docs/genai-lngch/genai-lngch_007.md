# 6 开发软件

## 加入我们在 Discord 上的书籍社区

[`packt.link/EarlyAccessCommunity`](https://packt.link/EarlyAccessCommunity)

![自动生成的二维码描述](img/file42.png)

虽然这本书是关于将生成式人工智能，特别是大型语言模型（LLMs）集成到软件应用程序中，但在本章中，我们将讨论如何利用 LLMs 来帮助软件开发。这是一个重要的主题，软件开发被几家咨询公司如 KPMG 和麦肯锡的报告所强调，是受生成式人工智能影响最大的领域之一。我们首先讨论 LLMs 如何帮助编码任务，并概述我们在自动化软件工程师方面取得了多大进展。我们还将讨论许多最新进展和新模型。然后，我们将尝试几种模型，定性评估生成的代码。接下来，我们将实现一个完全自动化的软件开发任务代理。我们将讨论设计选择，并展示我们在 LangChain 中仅用几行 Python 代码实现的代理实现的一些结果。这种方法有许多可能的扩展，我们也将讨论。在整个章节中，我们将探讨软件开发的不同方法，您可以在书籍的 Github 存储库中的`software_development`目录中找到。主要部分包括：

+   软件开发和人工智能

+   使用 LLMs 编写代码

+   自动化软件开发

我们将从使用人工智能进行软件开发的最新技术概述开始本章。

## 软件开发和人工智能

强大的 AI 系统如 ChatGPT 的出现引发了人们对将 AI 作为辅助软件开发人员的工具的极大兴趣。根据 KPMG 在 2023 年 6 月发布的一份报告，大约 25%的软件开发任务可以自动化处理。同月的麦肯锡报告强调了软件开发作为一个领域，在这个领域，生成式 AI 可以在成本降低和效率提升方面产生重大影响。利用人工智能来辅助编程的想法并不新鲜，但随着计算和人工智能的进步，这一想法迅速发展。正如我们将看到的那样，这两个领域是相互交织在一起的。20 世纪 50 年代和 60 年代早期的语言和编译器设计工作旨在使软件编写更加容易。1955 年，由 Grace Hopper 在雷明顿兰德公司设计的数据处理语言**FLOW-MATIC**（又称：**商业语言版本 0**）从类似英语的语句中生成代码。同样，20 世纪 60 年代在达特茅斯学院创建的**BASIC**（**初学者通用符号指令代码**）等编程语言旨在使在解释环境中编写软件更加容易。其他努力进一步简化和标准化了编程语法和接口。20 世纪 70 年代初由 J. Paul Morrison 发明的**基于流程的编程**（**FBP**）范式允许将应用程序定义为连接的黑盒进程，通过消息传递交换数据。视觉低代码或无代码平台也遵循了相同的模式，其中 LabVIEW 等流行的支持者被广泛用于电子工程中的系统设计，而 KNIME 提取、转换、加载工具则用于数据科学。20 世纪 80 年代出现的**专家系统**是最早尝试通过 AI 自动编码的努力之一。作为一种狭义 AI 形式，它们专注于编码领域知识和规则以提供指导。这些规则将以非常特定的语法制定，并在规则引擎中执行。这些编码了编程任务的最佳实践，如调试，尽管它们的实用性受到了对细致的基于规则的编程的需求的限制。对于软件开发，从命令行编辑器如 ed（1969 年），到 vim 和 emacs（20 世纪 70 年代），再到今天的集成开发环境（IDEs）如 Visual Studio（1997 年首次发布）和 PyCharm（自 2010 年以来），这些工具帮助开发人员编写代码，导航复杂项目，重构，进行高亮显示，设置和运行测试。IDE 还集成并提供来自代码验证工具的反馈，其中一些工具自 20 世纪 70 年代以来就存在。著名的 Lint 由贝尔实验室的 Stephen Curtis Johnson 于 1978 年编写，可以标记错误，风格错误和可疑结构。许多工具应用形式方法；然而，机器学习已经应用了包括遗传编程和基于神经网络的方法在内的方法至少 20 年。在本章中，我们将看到使用深度神经网络，特别是 transformers 来分析代码的进展。这将我们带到了当今，模型已经被训练出根据自然语言描述（在编码助手或聊天机器人中）或一些代码输入（完成）生成完整或部分程序的能力。

### 当今

DeepMind 的研究人员分别在《自然》和《科学》杂志上发表了两篇论文，这些论文代表了使用人工智能来改变基础计算的重要里程碑，特别是使用强化学习来发现优化算法。2022 年 10 月，他们发布了由他们的模型**AlphaTensor**发现的用于矩阵乘法问题的算法，这可以加速深度学习模型所需的这种基本计算，也适用于许多其他应用。**AlphaDev**发现了集成到广泛使用的 C++库中的新型排序算法，提高了数百万开发人员的性能。它还泛化了其能力，发现了一种比现在每天使用数十亿次的哈希算法快 30%的算法。这些发现展示了 AlphaDev 超越人类优化算法并解锁在更高编程级别难以实现的优化的能力。他们的模型**AlphaCode**于 2022 年 2 月发表的一篇论文中展示了一个由人工智能驱动的编码引擎，以与普通程序员相当的速度创建计算机程序。他们报告了在不同数据集上的结果，包括 HumanEval 等，我们将在下一节中介绍。DeepMind 的研究人员强调了大规模抽样候选算法池和选择的过滤步骤。该模型被誉为突破性成就；然而，他们方法的实用性和可扩展性尚不清楚。如今，像 ChatGPT 和微软的 Copilot 这样的新代码 LLM 是非常受欢迎的生成式人工智能模型，拥有数百万用户和显著的提高生产力的能力。LLM 可以处理与编程相关的不同任务，例如：

1.  代码补全：此任务涉及根据周围代码预测下一个代码元素。它通常用于集成开发环境（IDE）中，以帮助开发人员编写代码。

1.  代码摘要/文档：此任务旨在为给定的源代码块生成自然语言摘要或文档。这个摘要帮助开发人员理解代码的目的和功能，而无需阅读实际代码。

1.  代码搜索：代码搜索的目标是根据给定的自然语言查询找到最相关的代码片段。这项任务涉及学习查询和代码片段的联合嵌入，以返回代码片段的预期排名顺序。在文本中提到的实验中，神经代码搜索专注于这一点。

1.  Bug 查找/修复：AI 系统可以减少手动调试工作量，增强软件的可靠性和安全性。许多程序员很难找到代码中的错误和漏洞，尽管存在着代码验证工具的典型模式。作为替代方案，LLMs 可以发现代码中的问题，并在提示时进行修正。因此，这些系统可以减少手动调试工作量，帮助提高软件的可靠性和安全性。

1.  测试生成：类似于代码补全，LLMs 可以生成单元测试（参见 Bei Chen 等人，2022 年）和其他类型的测试，增强代码库的可维护性。

AI 编程助手将早期系统的互动性与尖端自然语言处理相结合。开发人员可以用简单的英语查询错误或描述所需的功能，接收生成的代码或调试提示。然而，围绕代码质量、安全性和过度依赖仍存在风险。在保持人类监督的同时找到计算机增强的正确平衡是一个持续的挑战。让我们看看目前用于编码的 AI 系统的性能，特别是代码 LLMs。

### 代码 LLMs

出现了许多 AI 模型，每个模型都有其优势和劣势，它们不断竞争以改进并提供更好的结果。这种比较应该概述一些最大和最受欢迎的模型：

| **模型** | **读取文件** | **运行代码** | **标记** |
| --- | --- | --- | --- |
| ChatGPT; GPT 3.5/4 | 否 | 否 | 最多 32k |
| ChatGPT: 代码解释器 | 是 | 是 | 最多 32k |
| 克劳德 2 | 是 | 否 | 100k |
| 巴德 | 否 | 是 | 1k |
| 必应 | 是 | 否 | 32k |

图 6.1：软件开发的公共聊天界面。

尽管这种竞争通过提供更广泛的选择范围使用户受益，但这也意味着仅依赖 ChatGPT 可能不再是最佳选择。用户现在面临选择为每个特定任务选择最合适的模型的决定。最新的浪潮利用机器学习和神经网络实现更灵活的智能。强大的预训练模型如 GPT-3 可以实现上下文感知、对话支持。深度学习方法还赋予了 bug 检测、修复建议、自动化测试工具和代码搜索更多的能力。微软的 GitHub Copilot 基于 OpenAI 的 Codex，利用开源代码实时建议完整的代码块。根据 2023 年 6 月的 Github 报告，开发人员接受 AI 助手的建议约占 30%，这表明该工具可以提供有用的建议，经验不足的开发人员受益最多。

> **Codex** 是由 OpenAI 开发的模型。它能够解析自然语言并生成代码，为 GitHub Copilot 提供动力。作为 GPT-3 模型的后代，它已经在 GitHub 上公开可用的代码上进行了微调，来自 5400 万个 GitHub 仓库的 159GB Python 代码，用于编程应用。

为了说明在创建软件方面取得的进展，让我们看一下基准测试中的定量结果：Codex 论文中介绍的**HumanEval 数据集**（“*评估基于代码训练的大型语言模型*”，2021 年）旨在测试大型语言模型根据其签名和文档字符串完成函数的能力。它评估了从文档字符串合成程序的功能正确性。该数据集包括 164 个编程问题，涵盖语言理解、算法和简单数学等各个方面。其中一些问题与简单的软件面试问题相当。HumanEval 上的一个常见指标是 pass@k（pass@1）- 这指的是在为每个问题生成 k 个代码样本时的正确样本比例。以下表总结了 AI 模型在 HumanEval 任务上的进展（来源：苏里亚·古纳塞卡等人，“*只需教科书*”，2023 年；[`arxiv.org/pdf/2306.11644.pdf`](https://arxiv.org/pdf/2306.11644.pdf)）：

![图 6.2：编码任务基准上的模型比较（HumanEval 和 MBPP）。性能指标是自报告的。此表仅包括模型，而不包括其他方法，例如推理策略。Llama2 在 HumanEval 上的自报告性能为 29.9%。](img/file43.png)

图 6.2：编码任务基准上的模型比较（HumanEval 和 MBPP）。性能指标是自报告的。此表仅包括模型，而不包括其他方法，例如推理策略。Llama2 在 HumanEval 上的自报告性能为 29.9%。

请注意，大多数 LLM 模型训练中使用的数据包括一定量的源代码。例如，由 EleutherAI 的 GPT-Neo 策划的 Pile 数据集，用于训练 GPT 模型的开源替代品，GPT-Neo，包括来自 Github 约 11%的代码（102.18GB）。Pile 被用于 Meta 的 Llama、Yandex 的 YaLM 100B 等许多模型的训练。尽管 HumanEval 已广泛用作代码 LLM 的基准测试，但还有许多编程基准测试。以下是一个给 Codex 的高级计算机科学测试的示例问题和回应：

![图 6.3：CS2 考试中的一个问题（左）和 Codex 的回应（来源“我的 AI 想知道这会不会出现在考试中：测试 OpenAI 的 Codex 对 CS2 编程练习的影响”詹姆斯·芬尼-安斯利等人，2023 年）。](img/file44.png)

图 6.3：CS2 考试中的一个问题（左）和 Codex 的回应（来源“我的 AI 想知道这会不会出现在考试中：测试 OpenAI 的 Codex 对 CS2 编程练习的影响”詹姆斯·芬尼-安斯利等人，2023 年）。

有许多有趣的研究揭示了人工智能帮助软件开发人员的能力，或者扩展了这种能力，如下表所总结的：

| **作者** | **出版日期** | **结论** | **任务** | **分析的模型/策略** |
| --- | --- | --- | --- | --- |
| Abdullah Al Ishtiaq 和其他人 | 2021 年 4 月 | 像 BERT 这样的预训练语言模型可以通过改进语义理解来增强代码搜索。 | 代码搜索 | BERT |
| Mark Chen 等人（OpenAI） | 2021 年 7 月 | 对 Codex 进行代码生成评估，显示了推进程序合成的潜力。 | 代码生成 | Codex |
| Ankita Sontakke 和其他人 | 2022 年 3 月 | 即使是最先进的模型也会产生质量低劣的代码摘要，表明它们可能不理解代码。 | 代码摘要 | Transformer 模型 |
| Bei Chen 等人（微软） | 2022 年 7 月 | CODE-T 利用 LLM 自动生成测试用例，减少人力投入，提高代码评估。它在 HumanEval pass@1 中达到了 65.8%。 | 代码生成，测试 | CODET |
| Eric Zelikman 等人（斯坦福大学） | 2022 年 12 月 | Parsel 框架使 LLM 能够分解问题并利用优势，提高了在分层推理上的表现。 | 程序合成，规划 | Codex |
| James Finnie-Ansley 和其他人 | 2023 年 1 月 | Codex 在高级 CS2 编程考试中表现优异，超过大多数学生。 | CS2 编程 | Codex |
| Yue Liu 和其他人 | 2023 年 2 月 | 现有的自动代码生成在鲁棒性和可靠性方面存在局限性。 | 代码生成 | 5 个 NMT 模型 |
| Mingyang Geng 和其他人 | 2023 年 2 月 | 两阶段方法显著提高了代码摘要的有效性。 | 代码摘要 | LLM + 强化学习 |
| Noah Shinn 等人 | 2023 年 3 月 | Reflexion 通过口头反思实现试错学习，实现了 91% 的 HumanEval pass@1。 | 编码，推理 | Reflexion |
| Haoye Tian 和其他人 | 2023 年 4 月 | ChatGPT 在编程辅助方面表现出潜力，但在鲁棒性、泛化性和注意力持久性方面存在局限。 | 代码生成，程序修复，代码摘要 | ChatGPT |
| Chuqin Geng 和其他人 | 2023 年 4 月 | ChatGPT 在入门编程教育中展示出令人印象深刻的能力，但作为学生只能获得 B- 的成绩。 | 入门函数式编程课程 | ChatGPT |
| Xinyun Chen 和其他人 | 2023 年 4 月 | 自我调试技术使语言模型能够识别和纠正生成代码中的错误。 | 代码生成 | Self-Debugging |
| Masum Hasan 和其他人 | 2023 年 4 月 | 将文本转换为中间形式语言使得从描述中更有效地生成应用程序代码成为可能。 | 应用程序代码生成 | Seq2seq 网络 |
| Anis Koubaa 和其他人 | 2023 年 5 月 | ChatGPT 在复杂编程问题上表现不佳，尚不适合完全自动化编程。它的表现远远不如人类程序员。 | 编程问题解决 | ChatGPT |
| Wei Ma 和其他人 | 2023 年 5 月 | ChatGPT 理解代码语法，但在分析动态代码行为方面受限。 | 复杂代码分析 | ChatGPT |
| Raymond Li 等人（BigCode） | 2023 年 5 月 | 推出了由 1 万亿 GitHub 令牌训练的 15.5B 参数 StarCoder，实现了 40%的 HumanEval pass@1 | 代码生成，多种语言 | StarCoder |
| Amos Azaria 和其他人 | 2023 年 6 月 | ChatGPT 存在错误和局限性，因此输出应该经过独立验证。最好由精通领域的专家使用。 | 通用功能和限制 | ChatGPT |
| Adam Hörnemalm | 2023 年 6 月 | ChatGPT 提高了编码和规划的效率，但在沟通方面存在困难。开发人员希望有更多集成的工具。 | 软件开发 | ChatGPT |
| Suriya Gunasekar 等人（微软） | 2023 年 6 月 | 高质量的数据使较小的模型能够匹配较大的模型，改变了缩放定律 | 代码生成 | Phi-1 |

图 6.2：用于编程任务的人工智能文献综述。出版日期主要指的是预印本发布日期。

这只是研究的一个小子集，但希望这有助于揭示该领域的一些发展。最近的研究探讨了 ChatGPT 如何支持程序员的日常工作活动，如编码、沟通和规划。其他研究描述了新模型（如 Codex、StarCoder 或 Phi-1）或规划或推理执行这些模型的方法。最近，微软研究院的 Suriya Gunasekar 等人在 2023 年发表的论文“*只需教科书*”介绍了 phi-1，这是一个基于 Transformer 的 1.3B 参数语言模型用于代码。该论文展示了高质量数据如何使较小的模型能够匹配较大的模型进行代码任务。作者从 The Stack 和 StackOverflow 的 3 TB 代码语料库开始。一个大型语言模型（LLM）对其进行过滤，选择了 6B 高质量标记。另外，GPT-3.5 生成了 1B 标记，模仿教科书风格。一个小的 1.3B 参数模型 phi-1 在这些过滤数据上进行了训练。然后，phi-1 在 GPT-3.5 合成的练习上进行微调。结果显示，phi-1 在 HumanEval 和 MBPP 等基准测试中与其大小超过 10 倍的模型的性能相匹配或超过。核心结论是高质量数据显著影响模型性能，可能改变缩放规律。数据质量应优先于蛮力缩放。作者通过使用较小的 LLM 来选择数据，而不是昂贵的完整评估，降低了成本。递归地过滤和在选定数据上重新训练可能会带来进一步的改进。重要的是要意识到，在短代码片段中，任务规范直接转换为代码，必须按照特定任务的顺序发出正确的 API 调用，而生成完整程序则依赖于对任务、背后的概念以及如何完成任务的深入理解和推理。然而，推理策略对于短代码片段也能产生很大的影响，正如 Noah Shinn 等人在 2023 年发表的论文“*反思：语言代理与口头强化学习*”所示。作者提出了一个名为 Reflexion 的框架，使 LLM 代理（在 LangChain 中实现）能够通过口头强化的试错学习快速有效地学习。代理人口头反思任务反馈信号，并将其反思文本存储在一个情节性记忆缓冲区中，这有助于代理人在随后的试验中做出更好的决策。作者展示了 Reflexion 在改善顺序决策、编码和语言推理等各种任务中决策制定的有效性。Reflexion 有潜力在特定任务中胜过以往的最先进模型，如其在 HumanEval 编码基准测试中的 91% pass@1 准确率所示，这超过了以往任何已发布的方法，包括 GPT-4 的 67%（由 OpenAI 报告）。  

### 展望

展望未来，多模态人工智能的进步可能会进一步发展编程工具。能够处理代码、文档、图像等的系统可以实现更自然的工作流程。人工智能作为编程伙伴的未来光明，但需要人类创造力和计算机增强生产力的深思熟虑协调。虽然有前景，但有效利用人工智能编程助手需要通过研讨会建立标准，为任务创建有用的提示和预提示。专注的培训确保生成的代码得到正确验证。将人工智能整合到现有环境中而不是独立的浏览器可以提高开发者体验。随着研究的继续进行，人工智能编程助手提供了增加生产力的机会，如果能够深思熟虑地实施并了解其局限性。在预训练阶段出现了法律和伦理问题，特别是涉及使用内容创建者数据训练模型的权利。版权法和公平使用豁免在与机器学习模型使用受版权保护数据相关的讨论中备受争议。例如，自由软件基金会对 Copilot 和 Codex 生成的代码片段可能侵犯版权提出了担忧。他们质疑在公共存储库上进行训练是否属于公平使用，开发者如何识别侵权代码，机器学习模型的性质是否为可修改源代码或训练数据的编译，以及机器学习模型的可版权性。此外，GitHub 的一项内部研究发现，少部分生成的代码直接复制了训练数据，包括错误的版权声明。OpenAI 认识到围绕这些版权问题的法律不确定性，并呼吁权威解决。这种情况被比作了关于 Google Books 中文本片段公平使用的 Authors Guild, Inc. v. Google, Inc.法庭案例。理想情况下，我们希望能够在不依赖收费云服务的情况下完成这一切，并且不会被迫放弃我们的数据所有权。然而，外包人工智能非常方便，因此我们只需实现提示和如何与客户发出调用的策略。许多开源模型在编码任务上取得了令人瞩目的进展，并且在其开发过程中具有完全透明和开放的优势。它们大多是在发布了宽松许可证下的代码上进行训练的，因此不会带来与其他商业产品相同的法律问题。这些系统对编码本身以及软件开发周围生态系统产生了更广泛的影响。例如，ChatGPT 的出现导致了程序员流行的 Stack Overflow 问答论坛的大量流量下降。在最初阻止使用大型语言模型（LLMs）生成的任何贡献后，Stack Overflow 推出了 Overflow AI，为 Stack 产品带来了增强的搜索、知识吸收和其他人工智能功能。新的语义搜索将使用 Stack 的知识库提供智能、对话式的结果。像 Codex 和 ChatGPT 这样的大型语言模型在解决常见问题的代码生成方面表现出色，但在新问题和长提示方面表现不佳。最重要的是，ChatGPT 在理解语法方面表现良好，但在分析动态代码行为方面存在局限性。在编程教育中，人工智能模型超越了许多学生，但仍有很大的改进空间，然而，它们尚未达到能够取代程序员和人类智慧的水平。仔细审查是必要的，因为错误可能会发生，专家监督至关重要。编码中人工智能工具的潜力令人鼓舞，但在稳健性、泛化性、注意力跨度和真正的语义理解方面仍存在挑战。需要进一步发展以确保可靠和透明的人工智能编程工具，可以增强开发者，使他们能够更快地编写代码并减少错误。在接下来的部分中，我们将看到如何使用 LLMs 生成软件代码以及如何从 LangChain 内部执行这些代码。

## 使用 LLMs 编写代码

让我们从应用模型来为我们编写代码开始。我们可以使用一些公开可用的模型来生成代码。我之前列举了一些示例，比如 ChatGPT 或 Bard。从 LangChain，我们可以调用 OpenAI 的 LLMs，PaLM 的 code-bison，或者通过 Replicate、HuggingFace Hub 等多种开源模型，或者通过本地模型，比如 Llama.cpp、GPT4All 或 HuggingFace Pipeline 集成。让我们来看看 StarCoder。这个截图展示了模型在 HuggingFace Spaces 上的游乐场：

![图 6.3：StarCoder 模型游乐场。我们可以在 StarCoder、StarCoderPlus、StarCoderBase 之间进行选择。此处可访问 https://huggingface.co/spaces/bigcode/bigcode-playground](img/file45.png)

图 6.3：StarCoder 模型游乐场。我们可以在 StarCoder、StarCoderPlus、StarCoderBase 之间进行选择。此处可访问 https://huggingface.co/spaces/bigcode/bigcode-playground

请注意，正如描述所说，StarCoder 模型没有经过指令调整，这意味着我们不能给它任务去执行。我们不能说“编写一个包含…”，但我们可以要求它完成一个文本，就像截图中展示的那样，我们用“`# dataclass of customer including an alphanumeric id, a name, and a birthday`”提示模型 – 让我们试试这个！我们可以切换温度、最大新标记、top-n 和重复惩罚的设置。对于任何非平凡的事情，我们需要调整最大新标记的设置。我得到了这段代码，为我们的假想客户提供了一个有用的数据模型：

```
@dataclass(frozen=True)  # frozen means that the class cannot be modified after creation. This is useful for storing data in databases or other persistent storages (e.g., files).
class Customer:
    cust_id : str = field()   # this defines how to create instances from the class; it's called "field" because we're creating fields within our object/instance
    firstname : str = ""      # these are default values if no value was provided when instantiating objects using this class
    lastname : str = ""       # note that there can only ever exist one instance variable per line - you'll get errors otherwise!
    def __post_init__(self):
        """This method runs automatically once upon instantiation"""
        self._validate_cust_id()    # validate input before saving anything into memory
        self.__set_fullname__()     # set full name based on given inputs
    @property        # getter function used by Python interpreter whenever trying to access property directly instead of through. notation e.g.: myobj.firstname vs just myobj.firstname()
    def fullname(self)->str:
        return f"{self.lastname}, {self.firstname}"
    ## private methods below here
    ### validation functions go here
    def _validate_cust_id(self):
        assert len(self.cust_id)==8, \
            ValueError("Customer ID must have exactly eight characters")
        try:
            int(self.cust_id[0]) == True
        except Exception as err:
            raise TypeError('First character of CustID should be numeric') from None
    #### setter functions go here
    def __set_fullname__(self):
        '''sets the customers' full name'''
        names = [x.strip().title() for x in re.split("[\W]+", self.firstname)] + [''] * max((1,-len([y.strip().title() for y in re.split("[\W]+", self.lastname)])) )
        print(names)
        self.firstname=' '.join(filter(None,[n[:3]for n in reversed(names)])+[''])
        self.lastname =''.join([' '*(4-len(l))+' '+ l[-2:]if not l=='I' else '' for l in filter(None,[n[:-2].upper()+','*bool(re.search('[aeiou]',n))+n[-2:].upper() for n in reversed(names)])]).rstrip(',') 
```

这里缺少了导入部分，通常应该在注释提示之前，所以我不能因此责怪模型，我们需要在顶部添加这两行：

```
import re
from dataclasses import dataclass, field
```

当我们按原样运行时，这不会引发错误，这令人印象深刻，但是，当我们更详细地查看时，有一些事情并不理想，甚至是错误的。乍一看，我个人不喜欢注释风格和缺乏文档字符串。代码中留下了一些`print()`语句；通常这是为了调试目的而做的。这不应该出现在生产代码中。将空字符串作为`firstname`和`lastname`的默认值可能并不理想。我希望客户 ID 是基于哈希函数分配的 - 我不明白为什么 ID 应该在验证属性的验证函数中强制为 8 个字符。这段代码还有更多问题影响其正确性和可读性，但代码中还有一些更为关键的问题，包括尝试编写只读属性。在数据类中的`firstname`和`lastname` - 在数据类中，`frozen=True`意味着属性在创建后无法更改。使用非标准语法中的正则表达式从`firstname`和`lastname`创建变量名的逻辑至少是奇怪的 - 且不正确。姓氏在这个过程中被丢弃。对反转名称的过滤也是非常可疑的。我就说到这里。这给了我们一些好的想法和一个开始的结构，但这不是生产代码。它甚至不起作用。您可以在书的 Github 存储库中看到这段代码作为`customer.py`。让我们再试一次。也许我们一开始就走错了。我们以初学者预期的错误语法开始了一个代码片段，并期望能够运行的代码。这是不现实的。让我们再试一次，并从一个更符合标准的提示开始：

```
"""Customer data model.
Here we implement our data model for customers, a dataclass with
fields firstname, lastname, customer_id (a hash).
"""
```

我们得到了以下结果：

```
@dataclass(frozen=True)  # frozen means that the object cannot be modified after creation!
class Customer:
    """A class representing one single customer."""
    firstname: str = ""
    lastname: str = ""
    id_: int = field(default=-1024, init=False)

    def __post_init__(self):
        self.__hash__()

    @property    
    def fullname(self)->str: 
        return f"{self.firstname} {self.lastname}"    

    def __eq__(self, other:"Customer")->bool:        
        if isinstance(other, type(self)):
            return all([
                getattr(self, attr)==getattr(other,attr) 
                for attr in ["firstname", "lastname"]])            
        else: 
            raise TypeError("Cannot compare different types")        

    def __lt__(self, other:"Customer"):  
        try:            
            assert len({type(x) for x in [self, other]})==1             

            if not hasattr(self,"fullname"):                
                setattr(self, 'fullname',f'{self.firstname}{self.lastname}')

            if not hasattr(other,'fullname'):               
                setattr(other, 'fullname',f'{other.firstname}{other.lastname}')
            return self.fullname < other.fullname

        except AssertionError as e:  
            print('Error:',e )

    def __repr__(self):    
        return f"Customer('{self.firstname}', '{self.lastname}','{hex(abs(self._customer_id))[-6:]})"   

    def __hash__(self):       
        hsh = abs(hash((self.firstname+self.lastname))) % ((sys.maxsize + 1)*2)+ sys.maxsize*3      
        self.id_=hsh         

        return hsh
```

很高兴看到客户 ID 像预期的那样使用哈希创建。有一些用于比较两个不同客户对象的样板代码。然而，再次出现了问题，与之前类似的问题。首先，缺少导入，我不明白我们的提示之后会在文件开头找到一个模块文档字符串，然后导入会紧随其后。其次，又一次尝试在类初始化后设置一个应该是冻结的属性。修复这两个问题后，我们得到了我们的第一个`Customer()`，然后出现了一个问题，客户 ID 被引用为错误的名称。修复这个问题后，我们可以初始化我们的客户，查看属性，并比较一个客户和另一个客户。我可以看到这种方法开始对编写样板代码变得有用。您可以在书的 Github 存储库中看到这段代码作为`customer2.py`。让我们尝试一个指令调整模型，这样我们就可以给它任务！StarChat，基于 StarCoder，可以在 HuggingFace 的[`huggingface.co/spaces/HuggingFaceH4/starchat-playground`](https://huggingface.co/spaces/HuggingFaceH4/starchat-playground)下找到。此屏幕截图显示了 StarChat 的示例：

![图 6.4：StarChat 在 Python 中实现计算素数的函数。请注意，截图中并非所有代码都可见。](img/file46.png)

图 6.4：StarChat 在 Python 中实现计算素数的函数。请注意，截图中并非所有代码都可见。

您可以在 Github 上找到完整的代码清单。对于这个在第一年计算机科学课程中应该很有名的例子，不需要导入任何内容。算法的实现很简单。它立即执行并给出预期的结果。在 LangChain 中，我们可以像这样使用`HuggingFaceHub`集成：

```
from langchain import HuggingFaceHub
llm = HuggingFaceHub(
    task="text-generation",
    repo_id="HuggingFaceH4/starchat-alpha",
    model_kwargs={
        "temperature": 0.5,
        "max_length": 1000
    }
)
print(llm(text))
```

截至 2023 年 8 月，这个 LangChain 集成存在一些超时问题 - 希望这很快就会得到解决。我们不打算在这里使用它。正如之前提到的，Llama2 并不是编码的最佳模型之一，通过率约为 29，但是，我们可以在 HuggingFace 聊天中尝试一下：

![图 6.5：HuggingFace 聊天与 Llama2 在 https://huggingface.co/chat/](img/file47.png)

图 6.5：HuggingFace 聊天与 Llama2 在 https://huggingface.co/chat/

请注意，这只是输出的开始。Llama2 找到了一个很好的实现，解释也很到位。干得好，StarCoder 和 Llama2！ - 或者，这太容易了？有很多方法可以获得代码完成或生成。我们甚至可以尝试一个小型本地模型：

```
from transformers import AutoModelForCausalLM, AutoTokenizer, pipeline
checkpoint = "Salesforce/codegen-350M-mono"
model = AutoModelForCausalLM.from_pretrained(checkpoint)
tokenizer = AutoTokenizer.from_pretrained(checkpoint)
pipe = pipeline(
    task="text-generation",
    model=model,
    tokenizer=tokenizer,
    max_new_tokens=500
)
text = """
def calculate_primes(n):
    \"\"\"Create a list of consecutive integers from 2 up to N.
    For example:
    >>> calculate_primes(20)
    Output: [2, 3, 5, 7, 11, 13, 17, 19]
    \"\"\"
"""
```

CodeGen 是 Salesforce AI Research 的一个模型。 CodeGen 350 Mono 在 HumanEval 中的通过率为 12.76%。截至 2023 年 7 月，发布了新版本的 CodeGen，只有 6B 参数，非常具有竞争力，性能达到 26.13%。这个最后的模型是在包含 C、C++、Go、Java、Javascript 和 Python 的 BigQuery 数据集上训练的，以及包含 5.5TB Python 代码的 BigPython 数据集。另一个有趣的小型模型是微软的 CodeBERT（2020），这是一个用于程序合成的模型，已经在 Ruby、Javascript、Go、Python、Java 和 PHP 上进行了训练和测试。由于这个模型是在 HumanEval 基准发布之前发布的，因此基准的性能统计数据不是初始出版物的一部分。我们现在可以直接从流水线中获取输出，就像这样：

```
completion = pipe(text)
print(completion[0]["generated_text"])
```

或者，我们可以通过 LangChain 集成来包装这个流水线：

```
llm = HuggingFacePipeline(pipeline=pipe)
llm(text)
```

这有点啰嗦。还有更方便的构造方法`HuggingFacePipeline.from_model_id()`。我得到了类似于 StarCoder 输出的东西。我不得不添加一个`import math`，但这个函数有效。我们可以在 LangChain 代理中使用这个管道，但请注意，这个模型没有经过指导，所以你不能给它任务，只能完成任务。你也可以使用所有这些模型进行代码嵌入。其他经过指导并可用于聊天的模型，可以充当您的技术助手，帮助提供建议，文档和解释现有代码，或将代码翻译成其他编程语言 - 对于最后一个任务，它们需要在这些语言中经过足够的样本训练。请注意，这里采取的方法有点天真。例如，我们可以采集更多样本并在它们之间进行选择，就像我们讨论过的一些论文中那样。现在让我们尝试为代码开发实现一个反馈循环，其中我们验证并运行代码，并根据反馈进行更改。

## 自动化软件开发

现在我们将编写一个完全自动化的代理，它将为我们编写代码并根据反馈修复任何问题。在 LangChain 中，我们有几个用于执行代码的集成，比如`LLMMathChain`，它执行 Python 代码来解决数学问题，以及`BashChain`，它执行 Bash 终端命令，可以帮助处理系统管理任务。然而，这些是用于通过代码解决问题而不是创建软件。不过，这种方法可能效果很好。

```
from langchain.llms.openai import OpenAI
from langchain.agents import load_tools, initialize_agent, AgentType
llm = OpenAI()
tools = load_tools(["python_repl"])
agent = initialize_agent(tools, llm, agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION, verbose=True)
result = agent("What are the prime numbers until 20?")
print(result)
```

我们可以看到在 OpenAI 的 LLM 和 Python 解释器之间，质数计算是如何在内部很好地处理的：

```
Entering new AgentExecutor chain...
I need to find a way to check if a number is prime
Action: Python_REPL
Action Input: 
def is_prime(n):
    for i in range(2, n):
        if n % i == 0:
            return False
    return True
Observation: 
Thought: I need to loop through the numbers to check if they are prime
Action: Python_REPL
Action Input: 
prime_numbers = []
for i in range(2, 21):
    if is_prime(i):
        prime_numbers.append(i)
Observation:
Thought: I now know the prime numbers until 20
Final Answer: 2, 3, 5, 7, 11, 13, 17, 19
Finished chain.
{'input': 'What are the prime numbers until 20?', 'output': '2, 3, 5, 7, 11, 13, 17, 19'}
```

我们已经得出了关于质数的正确答案，然而，目前还不太清楚这种方法在构建软件产品方面的可扩展性，其中涉及模块、抽象、关注点分离和可维护代码。目前有一些有趣的实现方法。MetaGPT 库通过代理模拟来处理这个问题，其中不同的代理代表公司或 IT 部门中的工作角色：

```
from metagpt.software_company import SoftwareCompany
from metagpt.roles import ProjectManager, ProductManager, Architect, Engineer
async def startup(idea: str, investment: float = 3.0, n_round: int = 5):
    """Run a startup. Be a boss."""
    company = SoftwareCompany()
    company.hire([ProductManager(), Architect(), ProjectManager(), Engineer()])
    company.invest(investment)
    company.start_project(idea)
    await company.run(n_round=n_round)
```

这是一个非常鼓舞人心的代理模拟用例。Andreas Kirsch 的 llm-strategy 库使用装饰器模式为数据类生成代码。自动软件开发的其他示例包括 AutoGPT 和 BabyGPT，尽管这些通常会陷入循环或因失败而停止。像这样的简单规划和反馈循环可以在 LangChain 中使用 ZeroShot 代理和规划器实现。Paolo Rechia 的 Code-It 项目和 AntonOsika 的 Gpt-Engineer 都遵循这样的模式，如 Code-It 的图表所示：

![图 6.6：Code-It 控制流（来源：https://github.com/ChuloAI/code-it）](img/file48.jpg)

图 6.6：Code-It 控制流（来源：https://github.com/ChuloAI/code-it）。

这些步骤中的许多都包括发送给 LLMs 的具体提示，指示其拆分项目或设置环境。通过使用所有工具实现完整的反馈循环是非常令人印象深刻的。在 LangChain 中，我们可以以不同的方式实现相对简单的反馈循环，例如使用`PlanAndExecute`链，`ZeroShotAgent`或`BabyAGI`。让我们选择`PlanAndExecute`！主要思想是设置一个链并执行它，目的是编写软件，就像这样：

```
llm = OpenAI()
planner = load_chat_planner(llm)
executor = load_agent_executor(
    llm,
    tools,
    verbose=True,
)
agent_executor = PlanAndExecute(
    planner=planner,
    executor=executor,
    verbose=True,
    handle_parsing_errors="Check your output and make sure it conforms!",
    return_intermediate_steps=True
)
agent_executor.run("Write a tetris game in python!")
```

我在这里省略了导入部分，但你可以在书籍的 Github 仓库中找到完整的实现。其他选项也可以在那里找到。这还有一些其他要点，但根据我们给出的指示，这已经可以编写一些代码了。我们需要的一件事是为语言模型提供清晰的指令，以便以某种形式编写 Python 代码：

```
DEV_PROMPT = (
    "You are a software engineer who writes Python code given tasks or objectives. "
    "Come up with a python code for this task: {task}"
    "Please use PEP8 syntax and comments!"
)
software_prompt = PromptTemplate.from_template(DEV_PROMPT)
software_llm = LLMChain(
    llm=OpenAI(
        temperature=0,
        max_tokens=1000
    ),
    prompt=software_prompt
)
```

我们需要确保选择一个能够生成代码的模型。我们已经讨论了我们可以选择的模型。我选择了一个较长的上下文，这样我们就不会在函数中间被切断，以及一个较低的温度，这样它就不会变得太疯狂。然而，单独使用这个模型无法将其存储到文件中，也无法对其进行有意义的操作，并根据执行的反馈进行操作。我们需要想出代码然后测试它，看看它是否有效。让我们看看我们如何实现这一点 - 这是传递给代理执行器的`tools`参数，让我们看看这是如何定义的！

```
software_dev = PythonDeveloper(llm_chain=software_llm)
code_tool = Tool.from_function(
    func=software_dev.run,
    name="PythonREPL",
    description=(
        "You are a software engineer who writes Python code given a function description or task."
    ),
    args_schema=PythonExecutorInput
)
```

`PythonDeveloper` 类包含了关于接受任何形式任务并将其转换为代码的所有逻辑。我不会在这里详细介绍，但主要思想在这里：

```
class PythonDeveloper():
    """Execution environment for Python code."""
    def __init__(
            self,
            llm_chain: Chain,
    ):
        self. llm_chain = llm_chain
    def write_code(self, task: str) -> str:
        return self.llm_chain.run(task)
    def run(
            self,
            task: str,
    ) -> str:
        """Generate and Execute Python code."""
        code = self.write_code(task)
        try:
            return self.execute_code(code, "main.py")
        except Exception as ex:
            return str(ex)
    def execute_code(self, code: str, filename: str) -> str:
        """Execute a python code."""
        try:
            with set_directory(Path(self.path)):
                ns = dict(__file__=filename, __name__="__main__")
                function = compile(code, "<>", "exec")
                with redirect_stdout(io.StringIO()) as f:
                    exec(function, ns)
                    return f.getvalue()
```

我再次略过了一些部分。这里的错误处理非常简单。在 Github 上的实现中，我们可以区分我们遇到的不同类型的错误，比如这些：

+   `ModuleNotFoundError`: 这意味着代码尝试使用我们未安装的包。我已经实现了安装这些包的逻辑。

+   `NameError`: 使用不存在的变量名。

+   `SyntaxError`: 代码经常不关闭括号或根本不是代码。

+   `FileNotFoundError`: 代码依赖不存在的文件。我发现有几次代码试图显示虚构的图像。

+   `SystemExit`: 如果发生更严重的情况导致 Python 崩溃。

我已经实现了为`ModuleNotFoundError`安装包的逻辑，并为其中一些问题提供了更清晰的消息。在缺少图像的情况下，我们可以添加一个生成图像模型来创建这些图像。将所有这些作为丰富的反馈返回给代码生成，会产生越来越具体的输出，例如：

```
Write a basic tetris game in Python with no syntax errors, properly closed strings, brackets, parentheses, quotes, commas, colons, semi-colons, and braces, no other potential syntax errors, and including the necessary imports for the game
```

Python 代码本身被编译并在子目录中执行，我们重定向 Python 执行的输出以捕获它 - 这两者都被实现为 Python 上下文。请谨慎在您的系统上执行代码，因为其中一些方法对安全性非常敏感，因为它们缺乏沙盒环境，尽管存在诸如 codebox-api、RestrictedPython、pychroot 或 setuptools 的 DirectorySandbox 等工具和框架，仅举几例供 Python 使用。所以让我们设置工具：

```
ddg_search = DuckDuckGoSearchResults()
tools = [
    codetool,
    Tool(
        name="DDGSearch",
        func=ddg_search.run,
        description=(
            "Useful for research and understanding background of objectives. "
            "Input: an objective. "
            "Output: background information about the objective. "
        )
    )
]
```

通过进行互联网搜索，确保我们正在实现与我们目标相关的内容是绝对值得的。我看过一些实现了石头、剪刀、布而不是俄罗斯方块的例子。我们可以定义额外的工具，比如将任务分解为函数的计划工具。你可以在仓库中看到这一点。每次以实现俄罗斯方块为目标来运行我们的代理执行器时，结果都会有些不同。我看到了几次搜索需求和游戏机制，以及几次生成和运行代码。pygame 库已安装。最终的代码片段并不是最终产品，但它会弹出一个窗口：

```
# This code is written in PEP8 syntax and includes comments to explain the code
# Import the necessary modules
import pygame
import sys
# Initialize pygame
pygame.init()
# Set the window size
window_width = 800
window_height = 600
# Create the window
window = pygame.display.set_mode((window_width, window_height))
# Set the window title
pygame.display.set_caption('My Game')
# Set the background color
background_color = (255, 255, 255)
# Main game loop
while True:
    # Check for events
    for event in pygame.event.get():
        # Quit if the user closes the window
        if event.type == pygame.QUIT:
            pygame.quit()
            sys.exit()
    # Fill the background with the background color
    window.fill(background_color)
    # Update the display
    pygame.display.update()
```

就语法而言，代码并不算太糟糕 - 我想提示可能有所帮助。然而，就功能而言，它与俄罗斯方块相去甚远。这种用于软件开发的全自动代理的实现仍然相当实验性。它也非常简单和基础，仅包括约 340 行 Python 代码，包括导入部分，你可以在 Github 上找到。我认为一个更好的方法可能是将所有功能分解为函数，并维护一个要调用的函数列表，这可以在所有后续代码生成中使用。我们也可以尝试测试驱动的开发方法，或者让人类给出反馈，而不是完全自动化的过程。然而，我们方法的一个优点是很容易调试，因为所有步骤，包括搜索和生成的代码，都写入了实现的日志文件中。让我们总结一下！

## 总结

在本章中，我们讨论了用于源代码的 LLMs，以及它们如何帮助开发软件。有很多领域可以从 LLMs 中受益，主要是作为编码助手。我们应用了一些模型来使用天真的方法生成代码，并对其进行了定性评估。我们看到建议的解决方案表面上看起来是正确的，但实际上并没有执行任务，或者充满了错误。这可能会特别影响初学者，并且可能对安全性和可靠性产生重大影响。在之前的章节中，我们看到 LLMs 被用作目标驱动的代理与外部环境进行交互。在编码中，编译器错误、代码执行的结果可以用来提供反馈，正如我们所见。或者，我们可以使用人类反馈或实施测试。让我们看看你是否记得本章的一些关键要点！

## 问题

请看看你是否能够从记忆中找到这些问题的答案。如果你对任何问题不确定，我建议你回到本章的相应部分查看：

1.  LLMs 可以如何帮助软件开发？

1.  如何衡量代码 LLM 在编码任务上的表现？

1.  有哪些代码 LLM 模型可用，包括开源和闭源？

1.  Reflexion 策略是如何工作的？

1.  我们有哪些选项可用于建立写代码的反馈循环？

1.  你认为生成式人工智能对软件开发有什么影响？
