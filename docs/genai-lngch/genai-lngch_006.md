# 5 构建类似 ChatGPT 的聊天机器人

## 加入我们在 Discord 上的书籍社区

[`packt.link/EarlyAccessCommunity`](https://packt.link/EarlyAccessCommunity)

![自动生成的二维码描述](img/file35.png)

在本章中，我们将讨论聊天机器人，它们是什么，能做什么，以及如何实现它们。我们将从讨论聊天机器人的演变和当前的最新技术状态开始。了解和增强当前聊天机器人和大型语言模型（LLMs）的能力对于它们在不同领域的安全有效使用具有实际意义，包括像医学和法律这样受监管的领域。积极沟通，重要的是为了满足客户需求，需要在技术方面实现上下文和记忆的机制。本章的重点是检索机制，包括向量存储以提高响应的准确性和聊天机器人对可用信息和当前对话的忠实度。我们将介绍现代聊天机器人的基础知识，如检索增强语言模型（RALMs），我们在 LangChain 中实现它们所需的技术背景。我们将详细讨论加载文档和信息的方法，包括向量存储和嵌入。我们还将讨论关于记忆的更具体的方法，这些方法涉及维护正在进行对话的知识和状态。最后，我们从声誉和法律的角度讨论另一个重要主题：审查。让我们确保我们的回复不是无礼的、不宽容的，也不违背组织的精神。LangChain 允许您通过一个审查链传递任何文本，以检查是否包含有害内容。在整个章节中，我们将使用 Streamlit 中的界面实现一个聊天机器人，您可以在书的 Github 存储库中的`chat_with_retrieval`目录中找到。主要章节包括：

+   什么是聊天机器人？

+   检索和向量

+   实现一个聊天机器人

+   不要说蠢话！

我们将通过介绍聊天机器人和技术的最新状态来开始本章。

## 什么是聊天机器人？

**聊天机器人**是一种人工智能程序，可以与用户聊天、提供信息和支持、预订事物以及执行各种其他任务。它用于与用户进行强大的互动，并可用于不同行业和不同目的。聊天机器人有益处，因为它们可以自动化任务、提供即时响应，并为用户提供个性化体验。它们可用于客户支持、潜在客户生成、销售、信息检索等。聊天机器人可以节省时间、提高效率、增强客户体验，并简化业务流程。聊天机器人通过利用自然语言处理（NLP）和机器学习算法工作。它们分析用户输入，理解其意图，并生成适当的回应。它们可以设计为与基于文本的消息平台或基于语音的应用程序一起工作。在客户服务中使用聊天机器人的一些用例包括提供全天候支持、处理常见问题、协助产品推荐、处理订单和付款以及解决简单客户问题。聊天机器人的一些更多用例包括：

+   预约安排：聊天机器人可以帮助用户安排约会、预订餐厅、管理日历。

+   信息检索：聊天机器人可以为用户提供特定信息，如天气更新、新闻文章或股票价格。

+   虚拟助手：聊天机器人可以充当个人助手，帮助用户设置提醒、发送消息或打电话。

+   语言学习：聊天机器人可以通过提供互动对话和语言练习来协助语言学习。

+   心理健康支持：聊天机器人可以提供情感支持，提供资源，并进行治疗性对话以用于心理健康目的。

+   教育：在教育环境中，虚拟助手被探索为虚拟导师，帮助学生学习和评估他们的知识，回答问题，并提供个性化学习体验。

+   人力资源和招聘：聊天机器人可以通过筛选候选人、安排面试和提供有关职位空缺的信息来协助招聘流程。

+   娱乐：聊天机器人可以让用户参与互动游戏、测验和故事体验。

+   法律：聊天机器人可以用于提供基本法律信息、回答常见法律问题、协助法律研究，并帮助用户导航法律流程。它们还可以帮助准备文件，如起草合同或创建法律表格。

+   医学：聊天机器人可以协助检查症状，提供基本医疗建议，并提供心理健康支持。它们可以通过向医疗专业人员提供相关信息和建议来改善临床决策。

这只是一些例子，聊天机器人的用例在各行各业不断扩展。任何领域的聊天技术都有潜力使信息更易获取，并为寻求帮助的个人提供初步支持。

### 什么是最先进的技术？

图灵测试，以英国计算机科学家、密码分析家和数学家艾伦·图灵命名，是人工智能（AI）领域的一种探究方法，用于确定计算机是否能够像人类一样思考。尽管关于图灵测试的相关性以及基于该测试的竞赛的有效性存在很多争论，但该测试仍然作为讨论和研究人工智能的哲学起点。随着我们在人工智能领域的不断进步，以及对人类大脑功能的更好理解和映射，图灵测试仍然是定义智能的基础，并且是关于我们应该期望技术达到何种程度才能被视为思考机器的辩论基准。图灵提出，如果计算机能够在特定条件下模仿人类的反应，那么可以说计算机具有人工智能。最初的图灵测试需要三个终端，每个终端都与其他两个物理上分开。一个终端由计算机操作，而另外两个由人类操作。在测试过程中，一个人充当提问者，而第二个人和计算机则充当回答者。提问者在特定主题领域内询问回答者，使用指定的格式和语境。在预设的时间长度或问题数量之后，提问者被要求决定哪个回答者是人类，哪个是计算机。自测试形成以来，许多人工智能已经能够通过测试；其中最早的之一是约瑟夫·韦伊岑鲍姆的 ELIZA。1966 年，他发表了一篇关于他的聊天机器人 ELIZA 的文章，“ELIZA - 用于研究人与机器之间自然语言交流的计算机程序。”ELIZA 是最早创建的聊天机器人之一，模拟了心理治疗师的角色。出于幽默的目的展示技术的局限性，这个聊天机器人采用简单的规则和模糊的开放式问题，以在对话中给人一种共情理解的印象，这种讽刺性的转折通常被视为人工智能的里程碑。然而，ELIZA 的知识有限，只能在特定领域的话题中进行对话。它也无法进行长时间的对话或从讨论中学习。多年来，图灵测试一直受到批评，特别是因为在历史上，提问的性质必须受限，以便计算机展现类似人类的智能。多年来，只有当提问者制定查询时，计算机才能获得高分，因此查询必须有“是”或“否”答案，或者涉及狭窄的知识领域。当问题是开放式的，需要对话回答时，计算机程序成功愚弄提问者的可能性较小。此外，像 ELIZA 这样的程序可以通过操纵它不完全理解的符号来通过图灵测试。哲学家约翰·西尔尔认为，这并不能确定与人类相媲美的智能。对许多研究人员来说，计算机是否能通过图灵测试已经变得无关紧要。与其专注于如何说服某人他们正在与人类交谈而不是与计算机程序交谈，真正的焦点应该是如何使人机交互更��观和高效。例如，通过使用对话界面。1972 年，另一个重要的聊天机器人 PARRY 被开发出来，它扮演了一个患有精神分裂症的患者。它有一个明确定义的个性，其回应基于一套假设系统，情绪反应是由用户话语的变化触发的。在 1979 年的一项实验中，五名精神科医生对 PARRY 进行了测试，他们必须确定他们正在互动的患者是计算机程序还是真正的精神分裂病患者。结果各异，有些精神科医生给出了正确的诊断，而其他人给出了错误的诊断。尽管图灵测试的几种变体通常更适用于我们对人工智能的当前理解，但测试的原始格式至今仍在使用。例如，自 1990 年以来，Loebner 奖每年颁发给由评委会投票选出的最像人类的计算机程序。比赛遵循图灵测试的标准规则。奖项的批评者经常将其视为更多关于宣传而非真正测试机器是否能够思考。IBM 沃森是 IBM 开发的一种认知计算系统，利用自然语言处理、��器学习和其他人工智能技术来回答自然语言中的复杂问题。它通过摄取和处理大量结构化和非结构化数据，包括文本、图像和视频。IBM 沃森在 2011 年参加智力竞赛节目 Jeopardy！并击败了两位前冠军时变得著名。沃森已应用于各个领域，包括医疗保健、金融、客户服务和研究。在医疗保健领域，沃森已被用于协助医生诊断和治疗疾病、分析医疗记录和进行研究。它还被应用于烹饪领域，Chef Watson 应用程序帮助厨师创作独特和创新的食谱。2018 年，Google Duplex 成功地在 7000 人面前通过电话与理发师预约。接待员完全不知道他们正在与真正的人类交谈。一些人认为这是现代图灵测试的通过，尽管并不依赖于艾伦·图灵设计的测试真正格式。由 OpenAI 开发的 ChatGPT 是一种语言模型，使用深度学习技术生成类似人类的回应。它于 2022 年 11 月 30 日推出，建立在 OpenAI 专有的一系列基础 GPT 模型之上，包括 GPT-3.5 和 GPT-4。ChatGPT 允许用户与 AI 进行连贯、自然和引人入胜的对话，调整和引导对话朝着他们期望的长度、格式、风格、详细程度和使用的语言发展。ChatGPT 被认为是一项重大突破，因为它代表了对话式人工智能领域的重大进步。由于其能够生成上下文相关的回应，并理解和回应各种主题和问题，一些人认为这个聊天机器人有最好的机会在真正的测试中击败任何我们今天拥有的技术。但是，即使具有先进的文本生成能力，它也可能被诱使回答荒谬的问题，因此在图灵测试的条件下可能会遇到困难。总的来说，ChatGPT 的能力和用户友好的界面使其成为对话式人工智能领域的重大进步，为与 AI 系统的互动和个性化互动提供了新的可能性。

> 以下是一些聊天机器人的例子：

+   ELIZA：ELIZA 是最早的聊天机器人之一，于 1960 年代开发，使用模式匹配模拟与用户的对话。

+   Siri：Siri 是由苹果开发的一款流行的基于语音的聊天机器人。它集成在苹果设备中，可以执行任务，回答问题并提供信息。

+   Alexa：Alexa 是亚马逊开发的智能个人助理。它可以响应语音命令，播放音乐，提供天气更新，并控制智能家居设备。

+   Google Assistant：Google Assistant 是由谷歌开发的聊天机器人。它可以回答问题，提供建议，并根据用户命令执行任务。

+   Mitsuku：Mitsuku 是一款多次赢得 Loebner 奖图灵测试的聊天机器人。它以能够进行自然和类似人类对话的能力而闻名。

> 这些只是一些例子，各行业和应用中还有许多其他聊天机器人可用。

使用图灵测试及其衍生物的一个担忧是，它侧重于模仿和欺骗，而更有意义的测试应强调开发者专注于创造有用和有趣的功能，而不仅仅是执行技巧。使用基准和学术/专业考试提供了对 AI 系统性能的更具体评估。该领域研究人员目前的目标是为测试人工智能（AI）系统的能力提供更好的基准，特别是大型语言模型（LLMs）如 GPT-4。他们旨在了解 LLMs 的极限并确定可能失败的领域。先进的 AI 系统，包括 GPT-4，在与语言处理相关的任务上表现出色，但在简单的视觉逻辑难题上表现不佳。LLMs 可以根据统计相关性生成合理的下一个词，但可能缺乏推理或对抽象概念的理解。研究人员对 LLMs 的能力有不同的看法，有些人将它们的成就归因于有限的推理能力。对 LLMs 进行测试并了解它们的能力具有实际意义。它可以帮助在医学和法律等现实领域中安全有效地应用 LLMs。通过确定 LLMs 的优势和劣势，研究人员可以确定如何最好地利用它们。ChatGPT 的训练使其在处理幻觉方面比以前更好，这意味着它不太可能生成荒谬或无关的回应。然而，重要的是要注意，ChatGPT 仍然可以自信地提供不准确的信息，因此用户应谨慎并验证提供的信息。上下文和记忆在确保聊天机器人的对话提供准确信息和准确反映先前互动的响应方面发挥着重要作用，从而使用户能够更忠实地与其互动。我们现在将更详细地讨论这一点。

### 上下文和记忆

上下文和记忆是聊天机器人设计中重要的方面。它们使聊天机器人能够保持对话上下文，回应多个查询，并存储和访问长期记忆。它们是调整聊天机器人响应准确性和忠实度的重要因素。在聊天机器人中，记忆和上下文的重要性可以与人与人之间对话中记忆和理解的重要性相比。在没有回忆过去交流或理解或了解更广泛背景的对话中，可能会导致不连贯和造成误解，从而导致不满意的对话体验。**上下文理解**极大地影响聊天机器人响应的准确性。它指的是聊天机器人理解整个对话以及一些相关背景而不仅仅是用户最后一条消息的能力。了解上下文的聊天机器人可以保持对话的整体视角，使对话流程更加自然和类似人类。**记忆保持**直接影响聊天机器人性能的忠实度，这涉及识别和记住以前对话中的事实以供将来使用的一致性。这个特性增强了用户的个性化体验。例如，如果用户说：“给我看看最便宜的航班”，然后接着说：“那个地区的酒店怎么样？”如果没有前面消息的上下文，聊天机器人就不知道用户指的是哪个地区。在一个相反的情况下，一个具有上下文意识的聊天机器人会理解用户在谈论与航班目的地相同地区的住宿。缺乏记忆会导致对话中的不一致性（缺乏忠实度）。例如，如果用户在一次对话中用名字标识自己，而机器人在下一次对话中忘记了这些信息，就会导致不自然和不个性化的互动。记忆和上下文对于使聊天机器人交互更加高效、准确、亲切和令人满意至关重要。没有这些元素，机器人可能会显得不足、僵硬，并且无法与人类对话伙伴建立联系。因此，这些特征对于计算机和人类之间复杂而令人满意的互动至关重要。具有 LLMs 的聊天机器人的一个新方面是它们不仅可以回应意图，而且可以更智能地与用户进行对话。这被称为主动。

### 有意识 vs 主动

在语言模型或聊天机器人的背景下，**主动**指的是系统在没有明确提示的情况下启动操作或提供信息的能力。它涉及根据先前的互动或情境线索来预测用户的需求或偏好。另一方面，**有意**意味着聊天机器人被设计为理解和满足用户的意图或请求，并根据这些意图和期望的结果采取特定行动或提供相关响应。主动型聊天机器人很有用，因为它可以与客户建立联系，改善他们的体验，创造更好的客户旅程。这可以通过节省时间和精力来增强用户体验，并且通过在问题出现之前迅速有效地解决客户查询的潜在问题或问题来提高客户满意度。主动沟通对企业的成功至关重要，因为它提高了客户终身价值（CLV）并降低了运营成本。通过积极地预测客户的需求并主动提供信息，企业可以控制沟通并以有利的方式构建对话。这建立了信任、客户忠诚度，并增强了组织的声誉。此外，主动沟通通过在客户提问之前解决客户查询并减少支持电话的数量来帮助提高组织的生产力。在技术方面，这种能力可以通过上下文和记忆以及推理机制来实现。这是本章的重点。在下一节中，我们将讨论现代聊天机器人的基础知识，如检索增强语言模型（RALMs）以及我们需要实现它们的技术背景。

## 检索和向量

在第四章中，我们讨论了检索增强生成（RAG），旨在通过利用外部知识增强生成过程，并确保生成的文本准确且上下文适当。在本章中，我们将进一步讨论如何结合检索和生成技术来提高生成文本的质量和相关性。特别地，我们将讨论检索增强语言模型（RALMs），这是 RAG 的一个具体实现或应用，指的是在生成过程中受到基础语料库中相关文档的约束的语言模型，这些文档是一组书面文本。在检索中，利用语义过滤和向量存储来从大量文档语料库中预先过滤相关信息，并将该信息纳入生成过程。这种检索包括文档的向量存储。

> **检索增强语言模型**（**RALMs**）是将检索组件纳入以提升性能的语言模型。传统语言模型根据输入提示生成文本，但 RALMs 更进一步，通过从大量文档中检索相关信息并将该信息用于生成更准确和上下文相关的响应。

RALMs 的好处包括：

1.  改进的性能：通过整合主动检索，LM 可以访问外部来源的相关信息，从而增强其生成准确和信息丰富响应的能力。

1.  避免输入长度限制：检索增强 LM 丢弃先前检索到的文档，仅使用当前步骤检索到的文档来调节下一代。这有助于防止达到 LM 的输入长度限制，使其能够处理更长更复杂的查询或任务。

更详细地说，检索增强 LM 的工作机制包括以下步骤：

1.  检索：RALMs 从大型语料库中搜索相关文档或段落。LM 根据查询和当前上下文的基于向量的相似性搜索从外部来源检索相关信息。

1.  调节：检索到的信息用于调节 LLM 的下一代。这意味着 LM 将检索到的信息整合到其语言模型中，以生成更准确和上下文适当的响应。

1.  迭代过程：检索和调节步骤是迭代执行的，每一步都建立在前一步的基础上。这种迭代过程允许 LLM 通过从外部来源整合相关信息逐渐改善其理解和生成能力。

检索到的信息可以以不同方式使用。它可以作为语言模型的附加上下文，帮助其生成更准确和上下文适当的响应。它还可以用于为生成的文本中的特定问题提供事实信息或回答特定问题。检索增强生成有两种主要策略：

1.  单次检索增强生成：这种策略涉及使用用户输入作为检索的查询，并一次性生成完整答案。检索到的文档与用户输入连接在一起，并用作语言模型的输入进行生成。

1.  主动检索增强生成：这种策略涉及在生成过程中积极决定何时以及检索什么内容。在生成的每一步中，根据用户输入和先前生成的输出，制定一个检索查询。然后使用检索到的文档作为语言模型的输入进行生成。这种策略允许检索和生成交错进行，使模型能够根据需要动态检索信息。

在主动检索增强生成框架中，有两种前瞻性方法称为 FLARE（前瞻性主动检索增强生成）：

+   带检索指令的 FLARE：该方法在生成答案时提示语言模型生成检索查询。它使用鼓励检索的指令，如“[搜索（查询）]”，来表达对额外信息的需求。

+   直接 FLARE：该方法直接使用语言模型的生成作为搜索查询。它迭代生成下一个句子以了解未来的主题，并且如果存在不确定的标记，则检索相关文档以重新生成下一个句子。

与传统方法不同，传统方法只检索一次信息然后用于生成，FLARE 遵循迭代过程。它涉及使用即将到来的句子的预测作为查询来检索相关文档。这使系统能够在初始生成的信心较低时重新生成句子。RALMs 在问题回答、对话系统和信息检索等任务中表现出有希望的结果。它们可以通过利用外部知识源提供更准确和信息丰富的响应。此外，通过在特定领域或任务上对其进行培训，可以进一步提高它们在专业应用中的实用性。总的来说，通过整合检索，RALMs 可以利用文档语料库中存在的大量知识，使它们在各种自然语言处理任务中更加强大和有用。RALMs 利用主动检索来增强其性能，并克服处理复杂查询或任务的限制。LangChain 实现了一个由不同构建模块组成的工具链，用于构建检索系统。这包括数据加载器、文档转换器、嵌入模型、向量存储和检索器。它们之间的关系在这里的图表中有所说明（来源：LangChain 文档）：

![图 5.1：向量存储和数据加载器。](img/file36.jpg)

图 5.1：向量存储和数据加载器。

在 LangChain 中，我们首先通过数据加载器加载文档。然后我们可以对它们进行转换，将这些文档传递给一个向量存储作为嵌入。然后我们可以查询向量存储或与向量存储相关的检索器。LangChain 中的检索器可以将加载和向量存储包装成一个步骤。在本章中，我们将大多数跳过转换，但是你会在数据加载器、嵌入、存储机制和检索器的示例中找到解释。由于我们正在讨论向量存储，我们需要讨论向量搜索，这是一种根据它们与查询向量的相似性来搜索和检索向量（或嵌入）的技术。它通常用于推荐系统、图像和文本搜索以及异常检测等应用中。我们将更深入地了解 RALMs 背后的基础知识，并且我们将从现在开始介绍嵌入。一旦你理解了嵌入，你就能够构建从搜索引擎到聊天机器人的一切。

### 嵌入

嵌入是内容的数值表示，以便机器可以处理和理解。这个过程的本质是将一个对象，比如一幅图像或一段文本，转换为一个向量，尽可能地封装其语义内容，同时丢弃不相关的细节。一个嵌入将一个内容片段，比如一个单词、句子或图像，映射到一个多维向量空间中。两个嵌入之间的距离表示相应概念（原始内容）之间的语义相似性。

> **嵌入**是由机器学习模型生成的数据对象的表示，以表示。它们可以将单词或句子表示为数值向量（浮点数列表）。至于 OpenAI 语言嵌入模型，嵌入是一个包含 1,536 个浮点数的向量，代表文本。这些数字来自一个捕捉语义内容的复杂语言模型。
> 
> > 举个例子 - 比如我们有单词猫和狗 - 这些可以在一个空间中与词汇表中的所有其他单词一起用数字表示。如果空间是三维的，那么这些可以是向量，比如猫的[0.5, 0.2, -0.1]和狗的[0.8, -0.3, 0.6]。这些向量编码了这些概念与其他单词的关系信息。粗略地说，我们期望猫和狗的概念与动物的概念更接近（更相似），而不是计算机或嵌入。

嵌入可以使用不同的方法创建。对于文本，一种简单的方法是**词袋**方法，其中每个单词由其在文本中出现的次数表示。这种方法在 scikit-learn 库中被实现为`CountVectorizer`，在**word2vec**出现之前很受欢迎。Word2vec 大致上通过预测句子中的单词来学习嵌入，忽略了线性模型中单词顺序的其他周围单词。嵌入的一般概念在这张图中有所说明（来源：“解释类比：理解词嵌入” by Carl Allen and Timothy Hospedales, 2019; https://arxiv.org/abs/1901.09813）：

![图 5.2：Word2Vec 单词嵌入在 3D 空间中。我们可以使用这些向量进行简单的向量运算，例如 king 的向量减去 man 的向量再加上 woman 的向量会得到一个更接近 queen 的向量。](img/file37.png)

图 5.2：Word2Vec 单词嵌入在 3D 空间中。我们可以使用这些向量进行简单的向量运算，例如 king 的向量减去 man 的向量再加上 woman 的向量会得到一个更接近 queen 的向量。

至于图像，嵌入可以来自特征提取阶段，例如边缘检测、纹理分析和颜色组成。这些特征可以在不同的窗口大小上提取，使表示既具有尺度不变性又具有平移不变性（**尺度空间表示**）。如今，通常情况下，**卷积神经网络**（**CNNs**）会在大型数据集（如 ImageNet）上进行预训练，以学习图像属性的良好表示。由于卷积层在输入图像上应用一系列滤波器（或卷积核）以生成特征图，从概念上讲，这类似于尺度空间。当一个预训练的 CNN 在新图像上运行时，它可以输出一个嵌入向量。如今，对于大多数领域，包括文本和图像，嵌入通常来自**基于 transformer 的模型**，这些模型考虑了句子和段落中单词的上下文和顺序。根据模型架构，尤其是参数数量，这些模型可以捕捉非常复杂的关系。所有这些模型都是在大型数据集上训练的，以建立概念及其关系。这些嵌入可以用于各种任务。通过将数据对象表示为数值向量，我们可以对它们执行数学运算并测量它们的相似性，或将它们用作其他机器学习模型的输入。通过计算嵌入之间的距离，我们可以执行搜索和相似性评分等任务，或对对象进行分类，例如按主题或类别。例如，我们可以通过检查产品评论的嵌入是否更接近积极或消极的概念来执行简单的情感分类器。

> **嵌入之间的距离度量标准**
> 
> > 在向量相似度计算中使用了不同的距离度量标准，例如：

+   **余弦距离**是一种相似度度量，计算向量空间中两个向量之间夹角的余弦。它的范围从-1 到 1，其中 1 表示相同的向量，0 表示正交向量，-1 表示完全相反的向量。

+   **欧氏距离**：它衡量向量空间中两个向量之间的直线距离。它的范围从 0 到无穷大，其中 0 表示相同的向量，较大的值表示越不相似的向量。

+   **点积**：它衡量两个向量的大小乘积和它们之间夹角的余弦。它的范围从-∞到∞，其中正值表示指向相同方向的向量，0 表示正交向量，负值表示指向相反方向的向量。

在 LangChain 中，您可以通过`OpenAIEmbeddings`类的`embed_query()`方法获取嵌入。这里是一个示例代码片段：

```
from langchain.embeddings.openai import OpenAIEmbeddings  
embeddings = OpenAIEmbeddings()  
text = "This is a sample query."  
query_result = embeddings.embed_query(text)  
print(query_result)
print(len(query_result))
```

此代码将单个字符串输入传递给`embed_query`方法，并检索相应的文本嵌入。结果存储在`query_result`变量中。可以使用`len()`函数获取嵌入的长度（维度数）。我假设您已经按照第三章“在 LangChain 中入门”的建议将 API 密钥设置为环境变量。您还可以使用`embed_documents()`方法获取多个文档输入的嵌入。这里是一个示例：

```
from langchain.embeddings.openai import OpenAIEmbeddings  
words = ["cat", "dog", "computer", "animal"]
embeddings = OpenAIEmbeddings()
doc_vectors = embeddings.embed_documents(words)
```

在这种情况下，`embed_documents()`方法用于检索多个文本输入的嵌入。结果存储在`doc_vectors`变量中。我们本可以检索长文档的嵌入 - 相反，我们只检索了单词的向量。我们还可以在这些嵌入之间进行算术运算，例如计算它们之间的距离：

```
from scipy.spatial.distance import pdist, squareform
import pandas as pd
X = np.array(doc_vectors)
dists = squareform(pdist(X))
```

这给我们了单词之间的欧氏距离作为一个方阵。让我们来绘制它们：

```
import pandas as pd
df = pd.DataFrame(
    data=dists,
    index=words,
    columns=words
)
df.style.background_gradient(cmap='coolwarm')
```

距离图应该看起来像这样：

![图 5.3：单词 cat，dog，computer，animal 的嵌入之间的欧氏距离。](img/file38.png)

图 5.3：单词 cat，dog，computer，animal 的嵌入之间的欧氏距离。

我们可以确认：猫和狗确实比计算机更接近动物。这里可能会有很多问题，例如，狗是否比猫更像动物，或者为什么狗和猫距离计算机仅比距离动物稍远。尽管这些问题在某些应用中可能很重要，但让我们记住这只是一个简单的例子。在这些示例中，我们使用了 OpenAI 的嵌入 - 在接下来的示例中，我们将使用 Huggingface 提供的模型的嵌入。LangChain 中有一些集成和工具可以帮助这个过程，其中一些我们将在本章后面遇到。此外，LangChain 提供了一个`FakeEmbeddings`类，可用于在不实际调用嵌入提供者的情况下测试您的流程。在本章的背景下，我们将用它们来检索相关信息（语义搜索）。然而，我们仍然需要讨论这些嵌入如何集成到应用程序和更广泛系统中，这就是向量存储的作用所在。

### 我们如何存储嵌入？

如前所述，在向量搜索中，每个数据点都被表示为高维空间中的一个向量。这些向量捕捉了数据点的特征或特性。目标是找到与给定查询向量最相似的向量。在向量搜索中，数据集中的每个数据对象都被分配一个向量嵌入。这些嵌入是一组数字，可以用作高维空间中的坐标。可以使用诸如余弦相似度或欧氏距离之类的距离度量来计算向量之间的距离。为了执行向量搜索，将查询向量（表示搜索查询）与集合中的每个向量进行比较。计算查询向量与集合中每个向量之间的距离，并认为距离较小的对象更类似于查询。为了高效执行向量搜索，使用向量存储机制，如向量数据库。

> **向量搜索**是指在其他存储的向量中搜索与给定查询向量相似的向量的过程，例如在向量数据库中，基于它们与给定查询向量的相似性。向量搜索通常用于各种应用程序，如推荐系统、图像和文本搜索以及基于相似性的检索。向量搜索的目标是以高效和准确地检索与查询向量最相似的向量，通常使用诸如点积或余弦相似度之类的相似性度量。

向量存储是指用于存储向量嵌入的机制，也与它们如何检索相关。向量存储可以是专门设计用于高效存储和检索向量嵌入的独立解决方案。另一方面，向量数据库是专为管理向量嵌入而构建的，并提供了与使用独立向量索引（如 FAISS）相比的几个优势。让我们更深入地探讨一些这些概念。这方面有三个层次：

1.  索引

1.  向量库

1.  向量数据库

这些组件共同用于创建、操作、存储和高效检索向量嵌入。索引将向量组织起来以优化检索，将它们结构化，以便可以快速检索向量。有不同的算法，如 k-d 树或 Annoy 用于此目的。向量库提供了用于向量操作的函数，如点积和向量索引。最后，像 Milvus 或 Pinecone 这样的向量数据库旨在存储、管理和检索大量向量集。它们使用索引机制来促进对这些向量的高效相似性搜索。让我们依次看看这些。LangChain 中还有第四个级别，即检索器，我们将在最后讨论。

### 向量索引

在向量嵌入的上下文中，索引是一种组织数据以优化其检索和/或存储的方法。这类似于传统数据库系统中的概念，其中索引允许更快地访问数据记录。对于向量嵌入，索引旨在结构化向量 - 粗略地说 - 使相似的向量存储在一起，从而实现快速的接近或相似性搜索。在这种情况下应用的典型算法是 K 维树（k-d 树），但许多其他算法如 Ball Trees、Annoy 和 FAISS 经常被实现，特别是对于传统方法可能难以处理的高维向量。

> **K-最近邻** (**KNN**) 是一种简单直观的用于分类和回归任务的算法。在 KNN 中，算法通过查看训练数据集中的 k 个最近邻来确定数据点的类别或值。
> 
> > 这是 KNN 的工作原理：

+   选择 k 的值：确定在进行预测时将考虑的最近邻居（k）的数量。

+   计算距离：计算您想要分类的数据点与训练数据集中所有其他数据点之间的距离。最常用的距离度量是欧氏距离，但也可以使用其他度量标准，如曼哈顿距离。

+   找到 k 个最近邻居：选择与您想要分类的数据点距离最近的 k 个数据点。

+   确定多数类别：对于分类任务，在 k 个最近邻中计算每个类别中数据点的数量。具有最高计数的类别成为数据点的预测类别。对于回归任务，取 k 个最近邻的值的平均值。

+   进行预测：一旦确定了多数类或平均值，将其分配为数据点的预测类别或值。

> 值得注意的是，KNN 是一种惰性学习算法，这意味着在训练阶段不会显式构建模型。相反，它存储整个训练数据集，并在预测时进行计算。

作为 KNN 的替代方案，还有几种常用于相似性搜索索引的其他算法。其中一些包括：

1.  产品量化（PQ）：PQ 是一种将向量空间划分为较小子空间并分别量化每个子空间的技术。这降低了向量的维度，并允许高效的存储和搜索。PQ 以其快速的搜索速度而闻名，但可能会牺牲一些准确性。

1.  局部敏感哈希（LSH）：这是一种基于哈希的方法，将相似的数据点映射到相同的哈希桶中。它对高维数据高效，但可能存在更高的误报和漏报概率。

1.  分层可导航小世界（HNSW）：HNSW 是一种基于图的索引算法，它构建了一个分层图结构来组织向量。它利用随机化和贪婪搜索的组合来构建可导航网络，从而实现高效的最近邻搜索。HNSW 以其高搜索准确性和可扩展性而闻名。

PQ 的示例包括 KD 树和 Ball 树。在 KD 树中，构建了一个基于二叉树结构，根据其特征值对数据点进行分区。对于低维数据而言，这是高效的，但随着维度的增加，效果会减弱。Ball 树：一种将数据点分区为嵌套超球体的树结构。适用于高维数据，但对于低维数据可能比 KD 树慢。除了 HNSW 和 KNN，还有其他基于图的方法，如图神经网络（GNN）和图卷积网络（GCN），利用图结构进行相似性搜索。Annoy（近似最近邻居 Oh Yeah）算法使用随机投影树来索引向量。它构建了一个二叉树结构，其中每个节点表示一个随机超平面。Annoy 易于使用，并提供快速的近似最近邻搜索。这些索引算法在搜索速度、准确性和内存使用方面有不同的权衡。算法的选择取决于应用程序的具体要求和向量数据的特征。

### 向量库

**向量库**，如 Facebook（Meta）Faiss 或 Spotify Annoy，提供了处理向量数据的功能。在向量搜索的背景下，向量库专门设计用于存储和执行向量嵌入的相似性搜索。这些库使用近似最近邻（ANN）算法来高效搜索向量并找到最相似的向量。它们通常提供不同的 ANN 算法实现，如聚类或基于树的方法，并允许用户为各种应用执行向量相似性搜索。以下是一些用于向量存储的开源库的快速概述，显示它们随时间的 Github 星标的流行度（来源：star-history.com）：

![图 5.4：几个流行的开源向量库的星标历史。](img/file39.png)

图 5.4：几个流行的开源向量库的星标历史。

你可以看到 faiss 在 Github 上受到了很多用户的关注。Annoy 排名第二。其他库尚未获得同样的流行度。让我们快速浏览一下这些：

+   FAISS（Facebook AI Similarity Search）是由 Meta（之前是 Facebook）开发的库，提供了高效的相似性搜索和密集向量的聚类。它提供各种索引算法，包括 PQ、LSH 和 HNSW。FAISS 广泛用于大规模向量搜索任务，并支持 CPU 和 GPU 加速。

+   Annoy 是由 Spotify 维护和开发的用于高维空间中近似最近邻搜索的 C++库，实现了 Annoy 算法。它旨在高效且可扩展，适用于大规模向量数据。它使用随机投影树的森林。

+   hnswlib 是使用 Hierarchical Navigable Small World（HNSW）算法进行近似最近邻搜索的 C++库。它为高维向量数据提供快速且内存高效的索引和搜索功能。

+   nmslib（Non-Metric Space Library）是一个提供非度量空间中高效相似性搜索的开源库。它支持各种索引算法，如 HNSW、SW-graph 和 SPTAG。

+   Microsoft 的 SPTAG 实现了分布式近似最近邻搜索（ANN）。它带有 kd 树和相对邻域图（SPTAG-KDT）以及平衡的 k 均值树和相对邻域图（SPTAG-BKT）。

nmslib 和 hnswlib 都由在亚马逊担任高级研究科学家的 Leo Boytsov 和 Yury Malkov 维护。还有很多其他库。你可以在[`github.com/erikbern/ann-benchmarks`](https://github.com/erikbern/ann-benchmarks)上查看概述。

### 向量数据库

**向量数据库**是一种专门设计用于处理向量嵌入的数据库类型，使得搜索和查询数据对象变得更加容易。它提供了额外的功能，如数据管理、元数据存储和过滤，以及可扩展性。虽然向量存储专注于存储和检索向量嵌入，但向量数据库提供了更全面的解决方案，用于管理和查询向量数据。向量数据库特别适用于涉及大量数据并需要跨各种类型的向量化数据进行灵活和高效搜索的应用程序，如文本、图像、音频、视频等。

> **向量数据库**可用于存储和提供机器学习模型及其对应的嵌入。主要应用是**相似性搜索**（又称：**语义搜索**），通过高效地搜索大量文本、图像或视频，根据向量表示识别与查询匹配的对象。这在文档搜索、逆向图像搜索和推荐系统等应用中特别有用。
> 
> > 向量数据库的其他用例随着技术的发展不断扩展，然而，一些常见的向量数据库用例包括：

+   异常检测：向量数据库可用于通过比较数据点的向量嵌入来检测大型数据集中的异常。这在欺诈检测、网络安全或监控系统中识别异常模式或行为至关重要。

+   个性化：向量数据库可用于通过基于用户偏好或行为找到相似向量来创建个性化推荐系统。

+   自然语言处理（NLP）：向量数据库广泛用于 NLP 任务，如情感分析、文本分类和语义搜索。通过将文本表示为向量嵌入，比较和分析文本数据变得更加容易。

这些数据库很受欢迎，因为它们针对可扩展性进行了优化，并且能够在高维向量空间中表示和检索数据。传统数据库并不设计用于高效处理大维向量，比如用于表示图像或文本嵌入的向量。向量数据库的特点包括：

1.  高效检索相似向量：向量数据库擅长在高维空间中查找接近的嵌入或相似点。这使它们非常适合逆向图像搜索或基于相似性的推荐任务。

1.  针对特定任务专门设计：向量数据库旨在执行特定任务，如查找接近的嵌入。它们不是通用数据库，而是专门设计用于高效处理大量向量数据。

1.  支持高维空间：向量数据库可以处理具有数千维的向量，允许对数据进行复杂的表示。这对于自然语言处理或图像识别等任务至关重要。

1.  实现高级搜索功能：使用矢量数据库，可以构建强大的搜索引擎，可以搜索相似的矢量或嵌入。这为内容推荐系统或语义搜索等应用程序开辟了新的可能性。

总的来说，矢量数据库为处理大维度矢量数据提供了专业和高效的解决方案，使得类似搜索和高级搜索功能成为可能。目前，开源软件和数据库市场蓬勃发展，原因有几点。首先，人工智能（AI）和数据管理对企业至关重要，导致对高级数据库解决方案的需求量大。在数据库市场上，新类型的数据库不断涌现并创建新的市场类别的历史悠久。这些市场创造者通常主导行业，吸引风险投资家（VCs）的大量投资。例如，MongoDB、Cockroach、Neo4J 和 Influx 都是成功公司的例子，它们推出了创新的数据库技术并获得了可观的市场份额。流行的 Postgres 有一个用于高效矢量搜索的扩展：pg_embedding。使用分层可导航小世界（HNSW）提供了一个更快、更高效的替代方案，比 IVFFlat 索引更好。风险投资家正在积极寻找下一个突破性的数据库类型，而 Chroma 和 Marqo 等矢量数据库有可能成为下一个大事件。这创造了一个竞争激烈的格局，公司可以筹集大量资金来开发和扩展其产品。此表列出了一些矢量数据库的示例：

| **数据库提供商** | **描述** | **商业模式** | **首次发布** | **许可证** | **索引** | **组织** |
| --- | --- | --- | --- | --- | --- | --- |
| Chroma | 商业开源嵌入式存储 | （部分开放）SaaS 模式 | 2022 | Apache-2.0 | HNSW | Chroma Inc |
| Qdrant | 具有扩展过滤支持的托管/自托管矢量搜索引擎和数据库 | （部分开放）SaaS 模式 | 2021 | Apache 2.0 | HNSW | Qdrant Solutions GmbH |
| Milvus | 用于可扩展相似性搜索的矢量数据库 | （部分开放）SaaS | 2019 | BSD | IVF, HNSW, PQ 等 | Zilliz |
| Weaviate | 云原生矢量数据库，存储对象和矢量 | 开放式 SaaS | 2018 年作为传统图数据库启动，2019 年首次发布 | BSD | 支持 CRUD 的自定义 HNSW 算法 | SeMI Technologies |
| Pinecone | 使用来自 AI 模型的嵌入进行快速和可扩展的应用程序 | SaaS | 2019 年首次发布 | 专有 | 基于 Faiss 构建 | Pinecone Systems Inc |
| Vespa | 商业开源矢量数据库，支持矢量搜索、词法搜索和搜索 | 开放式 SaaS | 最初是一个网络搜索引擎（alltheweb），于 2003 年被雅虎收购，后来于 2017 年开源为 Vespa | Apache 2.0 | HNSW, BM25 | 雅虎 |
| Marqo | 云原生商业开源搜索和分析引擎 | 开放 SaaS | 2022 | Apache 2.0 | HNSW | S2Search Australia Pty Ltd |

图 5.5：向量数据库。

我特意为每个搜索引擎突出了以下几个方面：

+   价值主张。是什么独特的特点使整个向量搜索引擎脱颖而出？

+   商业模式。此引擎的一般类型：向量数据库，大数据平台。托管/自托管。

+   索引。这个搜索引擎采用了什么算法方法来进行相似性/向量搜索，并提供了什么独特的功能？

+   许可证：是开源还是闭源？

我省略了其他方面，例如对分片或内存处理的支持。有许多向量数据库提供商。我省略了许多解决方案，如 FaissDB 或 Hasty.ai，并专注于一些集成在 LangChain 中的解决方案。对于开源数据库，Github 星标历史记录可以很好地反映它们的受欢迎程度和吸引力。这是随时间变化的情况（来源：star-history.com）：

![图 5.6：Github 上开源向量数据库的星标历史。](img/file40.png)

图 5.6：Github 上开源向量数据库的星标历史。

你可以看到 milvus 非常受欢迎，然而其他库如 qdrant、weviate 和 chroma 也在迎头赶上。在 LangChain 中，可以使用`vectorstores`模块实现向量存储。该模块提供了用于存储和查询向量的各种类和方法。LangChain 中的一个向量存储实现示例是 Chroma 向量存储。让我们看两个关于此的例子！

#### Chroma

这个向量存储经过优化，用于使用 Chroma 作为后端存储和查询向量。Chroma 接管了基于角度相似性对向量进行编码和比较。要在 LangChain 中使用 Chroma，您需要按照以下步骤操作：

1.  导入必要的模块：

```
from langchain.vectorstores import Chroma  
from langchain.embeddings import OpenAIEmbeddings
```

1.  创建 Chroma 的实例，并提供文档（拆分）和嵌入方法：

```
vectorstore = Chroma.from_documents(documents=docs, embedding=OpenAIEmbeddings())
```

文档（或在第四章中看到的拆分）将被嵌入并存储在 Chroma 向量数据库中。我们将在本章的另一部分讨论文档加载器。我们可以使用其他嵌入集成，或者我们可以像这样提供嵌入：

```
vector_store = Chroma()
# Add vectors to the vector store:
vector_store.add_vectors(vectors)
```

在这里，`vectors`是您想要存储的数字向量（嵌入）列表。我们可以查询向量存储以检索相似向量：

```
similar_vectors = vector_store.query(query_vector, k)
```

在这里，`query_vector`是您想要找到相似向量的向量，`k`是您想要检索的相似向量的数量。

#### Pinecone

这里是将 Pinecone 与 LangChain 集成的步骤：

1.  首先安装 Pinecone Python 客户端库。您可以通过在终端中运行以下命令来执行此操作：`pip install pinecone`。

1.  在您的 Python 应用程序中导入 Pinecone：`import pinecone`。

1.  连接到 Pinecone：要连接到 Pinecone 服务，您需要提供您的 API 密钥。您可以通过在 Pinecone 网站上注册来获取 API 密钥。获得 API 密钥后，将其传递给 pinecone 包装器或将其设置为环境变量：

```
pinecone.init()
```

1.  创建搜索索引如下：

```
Docsearch = Pinecone.from_texts([“dog”, “cat”], embeddings)
```

嵌入可以是`OpenAIEmbeddings`，例如。

1.  现在我们可以通过相似性找到查询的最相似文档：

```
docs = docsearch.similarity_search(“terrier”, include_metadata=True)
```

然后，我们可以再次查询这些文档，或者在*第四章*，*问答*中使用。在 LangChain 中，我们可以通过集成的文档加载器从许多来源和各种格式加载我们的文档。您可以使用 LangChain 集成中心浏览和选择适合您数据源的适当加载器。选择加载器后，您可以使用指定的加载器加载文档。让我们简要地看一下 LangChain 中的文档加载器！

### 文档加载器

文档加载器用于从源加载数据作为**Document**对象，其中包含文本和相关元数据。有不同类型的集成可用，例如用于加载简单`.txt`文件的文档加载器（`TextLoader`），加载网页的文本内容（`WebBaseLoader`），Arxiv 文章（`ArxivLoader`）或加载 YouTube 视频的转录（`YoutubeLoader`）。对于网页，`Diffbot`集成提供了内容的清晰提取。其他集成用于图像，例如提供图像标题（`ImageCaptionLoader`）。文档加载器具有一个`load()`方法，从配置的源加载数据并将其作为文档返回。它们还可以具有一个`lazy_load()`方法，根据需要将数据加载到内存中。以下是用于从文本文件加载数据的文档加载器示例：

```
from langchain.document_loaders import TextLoader
loader = TextLoader(file_path="path/to/file.txt")
documents = loader.load()
```

`documents`变量将包含加载的文档，可以用于进一步处理。每个文档包含`page_content`（文档的文本内容）和`metadata`（相关元数据，如源 URL 或标题）。类似地，我们可以从维基百科加载文档：

```
from langchain.document_loaders import WikipediaLoader
loader = WikipediaLoader("LangChain")
documents = loader.load()
```

需要注意的是，文档加载器的具体实现可能会因所使用的编程语言或框架而有所不同。在 LangChain 中，代理或链中的向量检索是通过检索器完成的，这些检索器访问向量存储。现在让我们看看这是如何工作的。

### LangChain 中的检索器

LangChain 中的检索器是一种组件类型，用于从给定索引中搜索和检索信息。在 LangChain 的上下文中，一种主要类型的检索器是`vectorstore`检索器。这种类型的检索器利用向量存储作为后端，例如 Chroma，用于索引和搜索嵌入。检索器在文档问答中扮演着至关重要的角色，因为它们负责根据给定的查询检索相关信息。以下是一些检索器的示例：

+   BM25 检索器：此检索器使用 BM25 算法根据与给定查询的相关性对文档进行排名。这是一种考虑词项频率和文档长度的流行信息检索算法。

+   TF-IDF 检索器：此检索器使用 TF-IDF（词项频率-逆文档频率）算法根据文档集合中术语的重要性对文档进行排名。它为在集合中罕见但在特定文档中频繁出现的术语分配更高的权重。

+   稠密检索器：此检索器使用稠密嵌入来检索文档。它将文档和查询编码为稠密向量，并使用余弦相似度或其他距离度量计算它们之间的相似性。

+   kNN 检索器：这利用了著名的 k 最近邻算法，根据与给定查询的相似性来检索相关文档。

这些只是 LangChain 中可用的检索器的几个示例。每个检索器都有其优点和缺点，选择检索器取决于具体的用例和要求。例如，要使用 kNN 检索器，您需要创建一个检索器的新实例，并为其提供一个文本列表。以下是如何使用来自 OpenAI 的嵌入创建 kNN 检索器的示例：

```
from langchain.retrievers import KNNRetriever  
from langchain.embeddings import OpenAIEmbeddings  
words = ["cat", "dog", "computer", "animal"]
retriever = KNNRetriever.from_texts(words, OpenAIEmbeddings())
```

创建检索器后，您可以通过调用`get_relevant_documents()`方法并传递查询字符串来使用它来检索相关文档。检索器将返回与查询最相关的文档列表。以下是如何使用 kNN 检索器的示例：

```
result = retriever.get_relevant_documents("dog")  
print(result)
```

这将输出与查询相关的文档列表。每个文档包含页面内容和元数据：

```
[Document(page_content='dog', metadata={}),
 Document(page_content='animal', metadata={}),
 Document(page_content='cat', metadata={}),
 Document(page_content='computer', metadata={})]
```

在 LangChain 中有一些更专业的检索器，例如来自 Arxiv、Pubmed 或 Wikipedia 的检索器。例如，**Arxiv 检索器**的目的是从 Arxiv.org 存档中检索科学文章。这是一个工具，允许用户搜索和下载各个领域的学术文章，如物理学、数学、计算机科学等。Arxiv 检索器的功能包括指定要下载的文档的最大数量，根据查询检索相关文档，以及访问检索文档的元数据信息。**Wikipedia 检索器**允许用户从 Wikipedia 网站检索 Wikipedia 页面或文档。Wikipedia 检索器的目的是为用户提供方便访问 Wikipedia 上大量信息的途径，并使用户能够从中提取特定信息或知识。**PubMed 检索器**是 LangChain 中的一个组件，帮助将生物医学文献检索整合到其语言模型应用中。PubMed 包含来自各种来源的数百万篇生物医学文献引用。在 LangChain 中，`PubMedRetriever`类用于与 PubMed 数据库交互，并根据给定的查询检索相关文档。该类的`get_relevant_documents()`方法接受查询作为输入，并返回来自 PubMed 的相关文档列表。以下是如何在 LangChain 中使用 PubMed 检索器的示例：

```
from langchain.retrievers import PubMedRetriever  
retriever = PubMedRetriever()  
documents = retriever.get_relevant_documents("COVID")
for document in documents:
    print(document.metadata["title"])
```

在这个例子中，使用查询“COVID”调用了`get_relevant_documents()`方法。该方法然后从 PubMed 中检索与查询相关的文档，并将它们作为列表返回。我得到了以下标题作为打印输出：

```
The COVID-19 pandemic highlights the need for a psychological support in systemic sclerosis patients.
Host genetic polymorphisms involved in long-term symptoms of COVID-19.
Association Between COVID-19 Vaccination and Mortality after Major Operations.
```

可以通过创建一个继承自`BaseRetriever`抽象类的类来在 LangChain 中实现自定义检索器。该类应该实现`get_relevant_documents()`方法，该方法接受查询字符串作为输入，并返回相关文档列表。以下是实现检索器的示例：

```
from langchain.retriever import BaseRetriever  
from langchain.schema import Document  
class MyRetriever(BaseRetriever):  
    def get_relevant_documents(self, query: str) -> List[Document]:  
        # Implement your retrieval logic here  
        # Retrieve and process documents based on the query  
        # Return a list of relevant documents  
        relevant_documents = []  
        # Your retrieval logic goes here…  
        return relevant_documents
```

您可以自定义此方法以执行您需要的任何检索操作，例如查询数据库或搜索索引文档。一旦您实现了您的检索器类，您可以创建一个实例并调用`get_relevant_documents()`方法根据查询检索相关文档。让我们实现一个带有检索器的聊天机器人！

## 实现一个聊天机器人！

现在我们将实现一个聊天机器人。我们将从第四章问答模板开始。与上一章类似，我们假设您已经按照第三章*开始使用 LangChain*中的说明安装了必要的库和 API 密钥。要在 LangChain 中实现一个简单的聊天机器人，您可以按照以下步骤进行：

1.  加载文档

1.  创建一个向量存储

1.  设置一个具有从向量存储中检索的聊天机器人

我们将通过几种格式进行概括，并通过 Streamlit 在 Web 浏览器中提供接口。您可以将您的文档放入其中并开始提问。在生产环境中，对于企业部署以进行客户参与，您可以想象这些文档已经加载进去，您的向量存储可以保持静态。让我们从文档阅读器开始。如前所述，我们希望能够阅读不同格式的文档：

```
from typing import Any
from langchain.document_loaders import (
  PyPDFLoader, TextLoader, 
  UnstructuredWordDocumentLoader, 
  UnstructuredEPubLoader
)
class EpubReader(UnstructuredEPubLoader):
    def __init__(self, file_path: str | list[str], ** kwargs: Any):
        super().__init__(file_path, **kwargs, mode="elements", strategy="fast")
class DocumentLoaderException(Exception):
    pass
class DocumentLoader(object):
    """Loads in a document with a supported extension."""
    supported_extentions = {
        ".pdf": PyPDFLoader,
        ".txt": TextLoader,
        ".epub": EpubReader,
        ".docx": UnstructuredWordDocumentLoader,
        ".doc": UnstructuredWordDocumentLoader
    }
```

这为我们提供了读取 PDF、文本、EPUB 和带有不同扩展名的 Word 文档的接口。现在我们将实现加载器逻辑。

```
import logging
import pathlib
from langchain.schema import Document
def load_document(temp_filepath: str) -> list[Document]:
    """Load a file and return it as a list of documents."""
    ext = pathlib.Path(temp_filepath).suffix
    loader = DocumentLoader.supported_extentions.get(ext)
    if not loader:
        raise DocumentLoaderException(
            f"Invalid extension type {ext}, cannot load this type of file"
        )
    loader = loader(temp_filepath)
    docs = loader.load()
    logging.info(docs)
    return docs
```

目前这个版本处理不了很多错误，但如果需要的话可以进行扩展。现在我们可以将这个加载器从界面中提供，并将其连接到向量存储。

```
from langchain.embeddings import HuggingFaceEmbeddings 
from langchain.text_splitter import RecursiveCharacterTextSplitter
from langchain.vectorstores import DocArrayInMemorySearch
from langchain.schema import Document, BaseRetriever
def configure_retriever(docs: list[Document]) -> BaseRetriever:
    """Retriever to use."""
    # Split each document documents:
    text_splitter = RecursiveCharacterTextSplitter(chunk_size=1500, chunk_overlap=200)
    splits = text_splitter.split_documents(docs)
    # Create embeddings and store in vectordb:
    embeddings = HuggingFaceEmbeddings(model_name="all-MiniLM-L6-v2")
    # Single call to the huggingface model with all texts:
    vectordb = DocArrayInMemorySearch.from_documents(splits, embeddings)
    # Define retriever:
    return vectordb.as_retriever(search_type="mmr", search_kwargs={"k": 2, "fetch_k": 4})
```

DocArray 是一个提供高级 API 用于表示和操作多模态数据的 Python 包。它提供各种功能，如高级索引、全面的序列化协议、统一的 Python 接口等。此外，它为自然语言处理、计算机视觉和音频处理等任务提供了高效和直观的多模态数据处理。我们可以使用不同的距离度量标准（如余弦和欧氏距离）初始化内存中的 DocArray 向量存储，余弦是默认值。对于检索器，我们有两个主要选项：

1.  相似性搜索：我们可以根据相似性检索文档，或者

1.  最大边际相关性（MMR）：我们可以在检索过程中应用基于多样性的文档重新排序，以获得覆盖到目前为止检索到的文档的不同结果。

在相似度搜索中，我们可以设置相似度分数阈值。我们选择了 MMR，这应该能给我们更好的生成。我们将参数`k`设置为 2，这意味着我们可以从检索中获取 2 个文档。检索可以通过**上下文压缩**来改进，这是一种技术，其中检索到的文档被压缩，无关信息被过滤掉。上下文压缩不是直接返回完整的文档，而是利用给定查询的上下文提取并返回只有相关信息。这有助于降低处理成本，并提高检索系统中响应的质量。基础压缩器负责根据给定查询的上下文压缩单个文档的内容。它使用语言模型，如 GPT-3，执行压缩。压缩器可以过滤掉无关信息，只返回文档的相关部分。基础检索器是根据查询检索文档的文档存储系统。它可以是任何检索系统，如搜索引擎或数据库。当向上下文压缩检索器发出查询时，它首先将查询传递给基础检索器以检索相关文档。然后，它使用基础压缩器根据查询的上下文压缩这些文档的内容。最后，只包含相关信息的压缩文档作为响应返回。我们有几种上下文压缩的选项：

1.  `LLMChainExtractor` – 这会遍历返回的文档，并从每个文档中提取相关内容。

1.  `LLMChainFilter` – 这稍微简单一些；它只过滤相关文档（而不是文档内容）。

1.  `EmbeddingsFilter` – 这应用基于嵌入的文档和查询的相似性过滤器。

前两个压缩器需要调用 LLM，这意味着它可能会很慢且成本高昂。因此，`EmbeddingsFilter`可以是一个更高效的替代方案。我们可以在最后使用一个简单的开关语句集成压缩（替换返回语句）：

```
if not use_compression:
    return retriever
embeddings_filter = EmbeddingsFilter(
  embeddings=embeddings, similarity_threshold=0.76
)
return ContextualCompressionRetriever(
  base_compressor=embeddings_filter,
  base_retriever=retriever
)
```

对于我们选择的压缩器`EmbeddingsFilter`，我们需要包括两个额外的导入：

```
from langchain.retrievers.document_compressors import EmbeddingsFilter
from langchain.retrievers import ContextualCompressionRetriever
```

我们可以通过`configure_qa_chain()`将`use_compression`参数传递给`configure_retriever()`方法（此处未显示）。现在我们有了创建检索器的机制。我们可以设置聊天链：

```
from langchain.chains import ConversationalRetrievalChain
from langchain.chains.base import Chain
from langchain.chat_models import ChatOpenAI
from langchain.memory import ConversationBufferMemory
def configure_chain(retriever: BaseRetriever) -> Chain:
    """Configure chain with a retriever."""
    # Setup memory for contextual conversation
    memory = ConversationBufferMemory(memory_key="chat_history", return_messages=True)
    # Setup LLM and QA chain; set temperature low to keep hallucinations in check
    llm = ChatOpenAI(
        model_name="gpt-3.5-turbo", temperature=0, streaming=True
    )
    # Passing in a max_tokens_limit amount automatically
    # truncates the tokens when prompting your llm!
    return ConversationalRetrievalChain.from_llm(
        llm, retriever=retriever, memory=memory, verbose=True, max_tokens_limit=4000
    )
```

检索逻辑的最后一件事是获取文档并将其传递给检索器设置：

```
import os
import tempfile
def configure_qa_chain(uploaded_files):
    """Read documents, configure retriever, and the chain."""
    docs = []
    temp_dir = tempfile.TemporaryDirectory()
    for file in uploaded_files:
        temp_filepath = os.path.join(temp_dir.name, file.name)
        with open(temp_filepath, "wb") as f:
            f.write(file.getvalue())
        docs.extend(load_document(temp_filepath))
    retriever = configure_retriever(docs=docs)
    return configure_chain(retriever=retriever)
```

现在我们已经有了聊天机器人的逻辑，我们需要设置界面。如前所述，我们将再次使用 streamlit：

```
import streamlit as st
from langchain.callbacks import StreamlitCallbackHandler
st.set_page_config(page_title="LangChain: Chat with Documents", page_icon="🦜")
st.title("🦜 LangChain: Chat with Documents")
uploaded_files = st.sidebar.file_uploader(
    label="Upload files",
    type=list(DocumentLoader.supported_extentions.keys()),
    accept_multiple_files=True
)
if not uploaded_files:
    st.info("Please upload documents to continue.")
    st.stop()
qa_chain = configure_qa_chain(uploaded_files)
assistant = st.chat_message("assistant")
user_query = st.chat_input(placeholder="Ask me anything!")
if user_query:
    stream_handler = StreamlitCallbackHandler(assistant)
    response = qa_chain.run(user_query, callbacks=[stream_handler])
    st.markdown(response)
```

这使我们可以通过可视界面使用检索功能的聊天机器人，根据需要插入自定义文档，并提出问题。

![图 5.7：带有不同格式文档加载器的聊天机器人界面。](img/file41.png)

图 5.7：带有不同格式文档加载器的聊天机器人界面。

您可以在 Github 上查看完整的实现。您可以尝试与聊天机器人互动，看看它是如何工作的，以及当它不工作时。需要注意的是，LangChain 对输入大小和成本有限制。您可能需要考虑解决方案来处理更大的知识库或优化 API 使用的成本。此外，与使用商业解决方案相比，微调模型或在内部托管 LLM 可能更复杂且不够准确。我们将在*第八章*，*条件和微调*，以及*第九章*，*LLM 在生产中的应用*中看到这些用例。让我们看看 LangChain 中可用的记忆机制。

### 记忆机制

记忆是 LangChain 框架中的一个组件，允许聊天机器人和语言模型记住先前的互动和信息。在诸如聊天机器人之类的应用中，它是必不可少的，因为它使系统能够在对话中保持上下文和连续性。我们在聊天机器人中需要记忆来：

1.  记住先前的互动：记忆使聊天机器人能够保留与用户交换的先前消息的信息。这有助于理解用户的查询并提供相关的响应。

1.  保持上下文：通过回顾先前的互动，聊天机器人可以在对话中保持上下文和连续性。这使得与用户进行更自然和连贯的对话成为可能。

1.  提取知识：记忆使系统能够从一系列聊天消息中提取知识和见解。然后可以使用这些信息来提高聊天机器人的性能和准确性。

总之，记忆对于聊天机器人至关重要，通过记住和建立在过去互动的基础上，创造出更加个性化和类似人类的对话体验。以下是一个在 Python 中演示如何使用 LangChain 记忆功能的实际示例。

```
from langchain.memory import ConversationBufferMemory
from langchain.chains import ConversationChain
# Creating a conversation chain with memory
memory = ConversationBufferMemory()
chain = ConversationChain(memory=memory)
# User inputs a message
user_input = "Hi, how are you?"
# Processing the user input in the conversation chain
response = chain.predict(input=user_input)
# Printing the response
print(response)
# User inputs another message
user_input = "What's the weather like today?"
# Processing the user input in the conversation chain
response = chain.predict(input=user_input)
# Printing the response
print(response)
# Printing the conversation history stored in memory
print(memory.chat_memory.messages)
```

在这个示例中，我们使用 ConversationBufferMemory 创建了一个带有记忆的对话链，它是一个简单的包装器，将消息存储在一个变量中。用户的输入使用对话链的`predict()`方法进行处理。对话链保留了先前互动的记忆，使其能够提供具有上下文意识的响应。与从链中单独构建记忆不同，我们可以简化：

```
conversation = ConversationChain(
    llm=llm, 
    verbose=True, 
    memory=ConversationBufferMemory()
)
```

我们将 verbose 设置为 True，以便查看提示。处理用户输入后，我们打印对话链生成的响应。此外，我们使用`memory.chat_memory.messages`打印存储在内存中的对话历史。`save_context()`方法用于存储输入和输出。您可以使用`load_memory_variables()`方法查看存储的内容。为了将历史记录作为消息列表获取，将`return_messages`参数设置为`True`。我们将在本节中看到这方面的示例。`ConversationBufferWindowMemory`是 LangChain 提供的一种内存类型，用于跟踪对话随时间的交互。与保留所有先前交互的`ConversationBufferMemory`不同，`ConversationBufferWindowMemory`仅保留最后的 K 个交互，其中 K 是指定的窗口大小。以下是在 LangChain 中如何使用`ConversationBufferWindowMemory`的简单示例：

```
from langchain.memory import ConversationBufferWindowMemory
memory = ConversationBufferWindowMemory(k=1)
```

在此示例中，窗口大小设置为 1，这意味着只有最后一个交互将存储在内存中。我们可以使用`save_context()`方法保存每个交互的上下文。它接受两个参数：user_input 和 model_output。这些代表给定交互的用户输入和相应模型的输出。

```
memory.save_context({"input": "hi"}, {"output": "whats up"})
memory.save_context({"input": "not much you"}, {"output": "not much"})
```

我们可以使用`memory.load_memory_variables({})`查看消息。在 LangChain 中，我们可以集成知识图谱以增强语言模型的能力，并使其在文本生成和推理过程中利用结构化知识。

> **知识图谱**是一种结构化的知识表示模型，以实体、属性和关系的形式组织信息。它将知识表示为图形，其中实体表示为节点，实体之间的关系表示为边。
> 
> > 知识图谱的著名例子包括 Wikidata，它从维基百科中捕获结构化信息，以及谷歌的知识图谱，为搜索结果提供丰富的上下文信息。

在知识图谱中，实体可以是世界上的任何概念、对象或事物，属性描述这些实体的属性或特征。关系捕获实体之间的连接和关联，提供上下文信息并实现语义推理。LangChain 中有用于检索知识图谱的功能，但 LangChain 还提供内存组件，根据我们的对话消息自动创建知识图谱。实例化`ConversationKGMemory`类，并将您的语言模型（LLM）实例作为 llm 参数传递：

```
from langchain.memory import ConversationKGMemory
from langchain.llms import OpenAI
llm = OpenAI(temperature=0)
memory = ConversationKGMemory(llm=llm)
```

随着对话的进行，我们可以使用`ConversationKGMemory`的`save_context()`函数将知识图中的相关信息保存到记忆中。我们还可以自定义 LangChain 中的对话记忆，这涉及修改用于 AI 和人类消息的前缀，以及更新提示模板以反映这些更改。要自定义对话记忆，您可以按照以下步骤操作：

1.  从 LangChain 导入必要的类和模块：

```
from langchain.llms import OpenAI
from langchain.chains import ConversationChain
from langchain.memory import ConversationBufferMemory
from langchain.prompts.prompt import PromptTemplate
llm = OpenAI(temperature=0)
```

1.  定义一个包含自定义前缀的新提示模板。您可以通过创建一个带有所需模板字符串的`PromptTemplate`对象来实现这一点。

```
template = """The following is a friendly conversation between a human and an AI. The AI is talkative and provides lots of specific details from its context. If the AI does not know the answer to a question, it truthfully says it does not know.
Current conversation:
{history}
Human: {input}
AI Assistant:"""
PROMPT = PromptTemplate(input_variables=["history", "input"], template=template)
conversation = ConversationChain(
    prompt=PROMPT,
    llm=llm,
    verbose=True,
    memory=ConversationBufferMemory(ai_prefix="AI Assistant"),
)
```

在这个示例中，AI 前缀被设置为 AI 助手，而不是默认的 AI。`ConversationSummaryMemory`是 LangChain 中一种生成对话摘要的记忆类型，随着对话的进行而生成对话摘要。它不是存储所有消息的逐字记录，而是压缩信息，提供对话的摘要版本。这在对话链很长的情况下特别有用，其中包含所有先前消息可能超过令牌限制。要使用`ConversationSummaryMemory`，首先创建一个实例，将语言模型（llm）作为参数传递。然后，使用`save_context()`方法保存交互上下文，其中包括用户输入和 AI 输出。要检索摘要的对话历史记录，使用`load_memory_variables()`方法。示例：

```
from langchain.memory import ConversationSummaryMemory
from langchain.llms import OpenAI
# Initialize the summary memory and the language model
memory = ConversationSummaryMemory(llm=OpenAI(temperature=0))
# Save the context of an interaction
memory.save_context({"input": "hi"}, {"output": "whats up"})
# Load the summarized memory
memory.load_memory_variables({})
```

LangChain 还允许使用 CombinedMemory 类结合多种记忆策略。当您想要保留对话历史的不同方面时，这将非常有用。例如，一个记忆可以用于存储完整的对话记录和

```
from langchain.llms import OpenAI
from langchain.prompts import PromptTemplate
from langchain.chains import ConversationChain
from langchain.memory import ConversationBufferMemory, CombinedMemory, ConversationSummaryMemory
# Initialize language model (with desired temperature parameter)
llm = OpenAI(temperature=0)
# Define Conversation Buffer Memory (for retaining all past messages)
conv_memory = ConversationBufferMemory(memory_key="chat_history_lines", input_key="input")
# Define Conversation Summary Memory (for summarizing conversation)
summary_memory = ConversationSummaryMemory(llm=llm, input_key="input")
# Combine both memory types
memory = CombinedMemory(memories=[conv_memory, summary_memory])
# Define Prompt Template
_DEFAULT_TEMPLATE = """The following is a friendly conversation between a human and an AI. The AI is talkative and provides lots of specific details from its context. If the AI does not know the answer to a question, it truthfully says it does not know.
Summary of conversation:
{history}
Current conversation:
{chat_history_lines}
Human: {input}
AI:"""
PROMPT = PromptTemplate(input_variables=["history", "input", "chat_history_lines"], template=_DEFAULT_TEMPLATE)
# Initialize the Conversation Chain
conversation = ConversationChain(llm=llm, verbose=True, memory=memory, prompt=PROMPT)
# Start the conversation
conversation.run("Hi!")
```

在这个例子中，我们首先实例化语言模型和我们使用的不同类型的记忆 - `ConversationBufferMemory` 用于保留完整的对话历史，`ConversationSummaryMemory` 用于创建对话摘要。然后我们使用 CombinedMemory 组合这些记忆。我们还定义了一个适应我们记忆使用的提示模板，最后，我们通过提供语言模型、记忆和提示来创建和运行`ConversationChain`。`ConversationSummaryBufferMemory` 用于在内存中保留最近的交互缓冲，并将旧的交互编译成摘要，而不是完全清除它们。清除交互的阈值是由令牌长度而不是交互数量确定的。要使用这个功能，记忆缓冲需要用 LLM 模型和`max_token_limit`实例化。`ConversationSummaryBufferMemory` 提供了一个名为`predict_new_summary()`的方法，可以直接用来生成对话摘要。Zep 是一个设计用于存储、总结、嵌入、索引和丰富聊天机器人或 AI 应用历史的记忆存储和搜索引擎。它为开发人员提供了一个简单且低延迟的 API 来访问和操作存储的数据。使用 Zep 的一个实际例子是将其集成为聊天机器人或 AI 应用的长期记忆。通过使用`ZepMemory`类，开发人员可以使用 Zep 服务器 URL、API 密钥和用户的唯一会话标识符初始化一个`ZepMemory`实例。这使得聊天机器人或 AI 应用能够存储和检索聊天历史或其他相关信息。例如，在 Python 中，你可以初始化一个 ZepMemory 实例如下：

```
from langchain.memory import ZepMemory  
# Set this to your Zep server URL  
ZEP_API_URL = "http://localhost:8000"  
ZEP_API_KEY = "<your JWT token>"  # optional  
session_id = str(uuid4())  # This is a unique identifier for the user  
# Set up ZepMemory instance  
memory = ZepMemory(  
    session_id=session_id,  
    url=ZEP_API_URL,  
    api_key=ZEP_API_KEY,  
    memory_key="chat_history",  
)
```

一旦记忆被设置好，你可以在你的聊天机器人链中使用它，或者与你的 AI 代理一起使用它来存储和检索聊天历史或其他相关信息。总的来说，Zep 简化了持久化、搜索和丰富聊天机器人或 AI 应用历史的过程，使开发人员能够专注于开发他们的 AI 应用，而不是构建记忆基础设施。

## 不要说任何愚蠢的话！

在聊天机器人中，审查的作用是确保机器人的回应和对话是适当的、道德的和尊重的。它涉及实施机制来过滤出冒犯性或不当内容，以及阻止用户的滥用行为。在审查的背景下，宪法指的是一套规范或规则，用于管理聊天机器人的行为和回应。它概述了聊天机器人应遵守的标准和原则，例如避免冒犯性语言、促进尊重互动和维护道德标准。宪法作为确保聊天机器人在期望的边界内运作并提供积极用户体验的框架。在聊天机器人中进行审查和拥有宪法对于为用户创建一个安全、尊重和包容的环境、保护品牌声誉以及遵守法律义务至关重要。在聊天机器人中进行审查和拥有宪法之所以重要有几个原因：

1.  确保道德行为：聊天机器人有与各种用户互动的潜力，包括脆弱的个人。审查有助于确保机器人的回应是道德的、尊重的，不会宣扬有害或冒犯性内容。

1.  保护用户免受不当内容：审查有助于防止不当或冒犯性语言、仇恨言论或可能对用户有害或冒犯性的内容的传播。它为用户与聊天机器人互动创造了一个安全和包容的环境。

1.  维护品牌声誉：聊天机器人通常代表一个品牌或组织。通过实施审查，开发人员可以确保机器人的回应与品牌的价值观一致，并保持良好声誉。

1.  预防滥用行为：审查可以阻止用户参与滥用或不当行为。通过实施规则和后果，例如示例中提到的“两次警告”规则，开发人员可以阻止用户使用挑衅性语言或参与滥用行为。

1.  法律合规：根据司法管辖区的不同，可能存在对内容进行审查并确保其符合法律法规的法律要求。拥有一部宪法或一套准则可以帮助开发人员遵守这些法律要求。

您可以将审查链添加到 LLMChain 中，以确保语言模型生成的输出不会有害。如果传入审查链的内容被认为有害，有不同的处理方式。您可以选择在链中抛出错误并在应用程序中处理，或者您可以向用户返回一条消息，解释该文本是有害的。具体的处理方法取决于您的应用程序需求。在 LangChain 中，首先，您将创建一个`OpenAIModerationChain`类的实例，这是 LangChain 提供的预构建审查链。该链专门设计用于检测和过滤有害内容。

```
from langchain.chains import OpenAIModerationChain  
moderation_chain = OpenAIModerationChain()
```

接下来，您将创建一个 LLMChain 类的实例，代表您的语言模型链。这是您定义提示并与语言模型交互的地方。

```
from langchain.chains import LLMChain  
llm_chain = LLMChain(model_name="gpt-3.5-turbo")
```

要将审查链附加到语言模型链，您可以使用`SequentialChain`类。这个类允许您以顺序方式将多个链链接在一起。

```
from langchain.chains import SequentialChain  
chain = SequentialChain([llm_chain, moderation_chain])
```

现在，当您想使用语言模型生成文本时，您需要先将输入文本通过审查链，然后再通过语言模型链。

```
input_text = "Can you generate a story for me?"  
output = chain.generate(input_text)
```

审查链将评估输入文本并过滤掉任何有害内容。如果输入文本被认为有害，审查链可以选择抛出错误或返回一条消息指示该文本不被允许。我在 Github 的聊天机器人应用程序中添加了一个审查示例。此外，护栏可用于定义语言模型在特定话题上的行为，防止其参与不受欢迎话题的讨论，引导对话沿着预定义路径进行，强制执行特定语言风格，提取结构化数据等。

> 在大型语言模型的背景下，**护栏**（简称**rails**）指的是控制模型输出的特定方式。它们提供了一种添加可编程约束和指导方针的方法，以确保语言模型的输出符合所需标准。

以下是几种使用护栏的方式：

+   控制话题：护栏允许您定义语言模型或聊天机器人在特定话题上的行为。您可以防止其参与关于政治等不受欢迎或敏感话题的讨论。

+   预定义对话路径：护栏使您能够为对话定义一个预定义路径。这确保了语言模型或聊天机器人遵循特定流程并提供一致的回应。

+   语言风格：护栏允许您指定语言模型或聊天机器人应该使用的语言风格。这确保了输出符合您期望的语气、形式或特定语言要求。

+   结构化数据提取：护栏可用于从对话中提取结构化数据。这对于捕获特定信息或根据用户输入执行操作非常有用。

总的来说，护栏为大型语言模型和聊天机器人添加可编程规则和约束提供了一种方式，使它们在与用户的交互中更加可信、安全和安全。通过将审查链附加到您的语言模型链中，您可以确保生成的文本经过审查，可以安全地在您的应用程序中使用。

## 总结

在第四章中，我们讨论了检索增强生成（RAG），其中涉及利用外部工具或知识资源，如文档语料库。在那一章中，我们关注了过程。在本章中，重点是与基于 RALMs 构建聊天机器人相关的方法，更具体地说，是利用外部工具检索相关信息，这些信息可以并入内容生成中。本章的主要部分包括聊天机器人简介，检索和向量机制，实现聊天机器人，记忆机制以及适当响应的重要性。本章以聊天机器人概述开始。我们讨论了聊天机器人和语言处理模型（LLMs）的演变和当前状态，强调了当前技术能力的实际影响和增强。然后，我们讨论了积极沟通的重要性以及为上下文、记忆和推理所需的技术实现。我们探讨了包括向量存储在内的检索机制，旨在提高聊天机器人响应的准确性。我们详细介绍了加载文档和信息的方法，包括向量存储和嵌入。此外，我们讨论了用于维护知识和进行中对话状态的记忆机制。本章以审查讨论结束，强调确保响应尊重和符合组织价值观的重要性。我们在本章中实现了一个聊天机器人，探讨了本章讨论的一些功能，并可作为研究记忆和上下文、言论审查等问题的起点，但也可用于探讨幻觉或其他问题。在第九章中，我们将讨论如何在您的文档上训练 LLMs，这是另一种在数据上调整模型的方式！让我们看看您是否记得本章的一些关键要点！

## 问题

请看看你是否能够从记忆中回答这些问题。如果对任何问题不确定，建议您回到本章的相应部分查看：

1.  请列出 5 个不同的聊天机器人！

1.  在开发聊天机器人中有哪些重要方面？

1.  RALMs 代表什么？

1.  什么是嵌入？

1.  什么是向量搜索？

1.  什么是向量数据库？

1.  请列出 5 个不同的向量数据库！

1.  LangChain 中的检索器是什么？

1.  什么是记忆，LangChain 中的记忆选项是什么？

1.  什么是审查，什么是宪法，它们是如何工作的？
