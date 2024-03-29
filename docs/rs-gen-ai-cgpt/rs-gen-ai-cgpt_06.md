# 第七章：ChatGPT 技术概述：介绍

# 介绍

人工智能或机器学习提供了跨多种形式的自动化监督和无监督学习，无论是文本、图像还是语音，可能是跨不同类型，如数值数据、上下文数据、基于特征的数据、基于模式的数据。自然语言处理（NLP）一直是人工智能领域的一个子领域，它仅占据了几乎五分之一的市场份额和解决方案数量，专注于计算机与人类语言之间的互动。

# 自然语言处理简介

NLP 使用计算技术使计算机能够理解、解释和生成人类语言。它是人工智能的重要组成部分之一，涉及语言任务并自动化分析和从任何短语中获取有意义的上下文的过程。这些任务包括情感分析、上下文映射、聊天机器人、内容预测、字幕、答案生成、机器翻译、内容分类等，并且在银行业、金融业、客户服务、健康和医疗、教育以及几乎所有其他实体中使用。近年来，NLP 取得了重大进展，这要归功于大型数据集、强大的计算资源和先进的机器学习算法。凭借其处理和理解人类语言的能力，NLP 正在帮助弥合人类和机器之间的差距，并使我们与技术的互动更直观和自然。

# NLP 的发展

根据斯坦福大学的说法，对 NLP 的第一个需求始于二战期间的紧急翻译。回到 20 世纪 50 年代，研究人员开始探索使用计算机理解和生成人类语言的可能性。1950 年，艾伦·图灵提出了“图灵测试”，这是机器智能的一个基准，涉及计算机进行与人类无法区分的对话的能力。这导致了早期 NLP 系统的开发，例如 20 世纪 60 年代开发的“ELIZA”程序，模拟了计算机和人类治疗师之间的对话。

在 20 世纪 70 年代，研究人员开始开发更先进的 NLP 算法，如“SHRDLU”程序，它可以理解自然语言命令并在模拟环境中操作虚拟对象。在 20 世纪 80 年代和 90 年代，研究人员专注于开发用于语言处理的统计模型，这使计算机能够从大量的人类语言数据集中学习。

在 20 世纪 2000 年代和 2010 年代，NLP 在深度学习算法的发展和维基百科、社交媒体数据等大型数据集的可用性方面取得了重大进展。这些进展导致了更复杂的 NLP 应用程序的开发，如语音助手、聊天机器人和机器翻译。

在上个十年的后半段，自然语言处理（NLP）继续取得进展，研究人员在深度学习、迁移学习和预训练等领域取得了重大进展。

NLP 中最重要的发展之一是大型预训练语言模型的出现，如 BERT（双向编码器表示来自变压器）、GPT-2（生成式预训练变压器 2）和 GPT-3。这些模型经过大量文本数据的训练，可以执行各种 NLP 任务，包括文本分类、问答和语言生成。它们使研究人员能够在各种 NLP 基准测试中取得最先进的结果。

NLP 方面的另一个重要发展是迁移学习的使用，其中模型首先在大型数据集上进行预训练，然后针对特定任务进行微调。这种方法已被用于在各种 NLP 任务上实现高性能，包括情感分析、命名实体识别和文本分类。

除了这些进展，研究人员还专注于改进 NLP 模型的鲁棒性和公平性。这包括开发方法来检测和减轻语言数据和模型中的偏见，并确保 NLP 应用对来自不同语言和文化背景的人们是可访问的。

总的来说，NLP 方面的这些进展为开发更复杂和准确的基于语言的应用程序打开了新的可能性，从聊天机器人到虚拟助手，可能会对许多行业产生深远的影响。从那时起，LUNAR-科学定性数据，ELIZA-第一个聊天机器人，从今天的复杂模型和用例，如智能 Alexa，对话机器人是 Siri，具有高级复杂的神经网络后端。在 ChatGPT 的背景下，这是一个现代先进的 NLP 架构，能够以更接近人类感知和解释的定量和定性准确性和精度执行非常高级的任务。在此期间，从 Word2Vec 模型到今天的 ChatGPT，通过神经网络、LSTM 模型、编码器-解码器、注意力模型、Transformer 模型、Google 的 BERT、imageBERT 等，这个过程的改进逐渐而持续地发展。

# GPT 和 ChatGPT

谈到**生成式预训练变压器**（GPT），它是一个复杂的神经网络架构，支撑着 ChatGPT 的第 3.5 版 GPT 系列（称为 InstructGPT），是他们最新的开发。由 Google 于 2017 年创建的 Transformers 模型是这个 GPT 模型的基础和初步元素。它基于首次在论文“**注意力就是你所需要的**”中提出的基于注意力的模型的直觉。

# GPT 系列由 OpenAI 提供

在 2019 年至 2022 年期间，整个 GPT 系列通过 OpenAI 进行了许多技术模型和超参数的调整，并且他们一直在改进许多微观层面的变化。整个 GPT-3 模型包括大约 1750 亿个参数，这是谷歌在 2018 年推出的语言模型 BERT 的 50 倍，尽管在 NLP 研究中有一些装载较重的语言模型，如 NVIDIA 的 Megatron-NLG，具有 5300 亿个参数，由 560 个 DGX A100 服务器组成，每个服务器包含八个 A100 80GB GPU，能够自动完成短语和陈述。谷歌的 PaLM 扩展到了 5400 亿个参数，是另一个例子，这是一个高度多任务的 NLP 模型，训练在世界上最大的 TPU 上，拥有 6144 个芯片。谷歌还推出了 LaMDA；与传统模型经常提供的基于任务的回复相反，该模型可以以自由形式产生对话聊天，也有大约 1370 亿个参数。 *Dr Alan D. Thompson*博客系列的以下气泡图解释了语言模型中大参数最近发展的估计：

![](img/Figure-7.1.jpg)

**图 7.1：** *具有大参数的领先 NLP 模型[来源：Lifearchitect.ai]*

# 需要记住的要点

+   自然语言处理（NLP）一直是人工智能领域的一个子领域，它只占据了几乎五分之一的市场份额和解决方案数量，专注于计算机与人类语言之间的交互。

+   NLP 使用计算技术使计算机能够理解、解释和生成人类语言。

+   近年来，由于大型数据集、强大的计算资源和先进的机器学习算法的可用性，自然语言处理取得了重大进展。

+   凭借其处理和理解人类语言的能力，自然语言处理正在帮助弥合人类和机器之间的差距，并使我们与技术的互动更直观和自然。

+   在 2000 年代和 2010 年代，随着深度学习算法的发展和维基百科、社交媒体数据等大型数据集的可用性，自然语言处理取得了重大进展。

+   在上个十年的后半段，自然语言处理（NLP）继续取得进展，研究人员在深度学习、迁移学习和预训练等领域取得了重大进展。

+   这些模型是在大量文本数据上训练的，可以执行各种自然语言处理任务，包括文本分类、问答和语言生成。

+   除了这些进展之外，研究人员还专注于改进自然语言处理模型的健壮性和公平性。

+   这包括开发方法来检测和减轻语言数据和模型中的偏见，并确保自然语言处理应用对来自不同语言和文化背景的人们是可访问的。

+   总的来说，自然语言处理的这些进展为开发更复杂和准确的基于语言的应用打开了新的可能性，从聊天机器人到虚拟助手，可能会对许多行业产生深远的影响。

# 加入我们书籍的 Discord 空间

加入书籍的 Discord Workspace，获取最新更新、优惠、全球科技动态、新发布和作者交流的信息：

[**https://discord.bpbonline.com**](https://discord.bpbonline.com)

![](img/dis.jpg)
