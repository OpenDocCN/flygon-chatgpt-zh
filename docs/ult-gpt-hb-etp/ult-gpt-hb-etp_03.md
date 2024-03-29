# 第四章：由 GPT 模型启用的架构模式

# 介绍

在我们之前的章节中奠定了基础，我们探讨了我们的 AI 能力框架 CapabilityGPT 在各种企业角色中的变革性影响，现在我们将把焦点转向潜在的解决方案架构。在本章中，我们深入探讨了创建高质量 GPT 驱动系统的高级模式，涵盖了对话和自主解决方案。

在我们深入讨论各个模式之前，我们首先在各自的子章节中介绍**架构模式**的概念。在这里，我们分解了这些模式的核心组件，包括它们的层、工作流程、质量方面和潜在的用例。

有了这个基础，我们将本章的其余部分组织成四个主要部分，每个部分都专注于不同类别的架构模式：

+   **基础对话模式（A）：**这些包括 GPT 驱动对话系统的基本组件，为所有进一步的增强和集成奠定了基础。

+   **与外部工具集成的对话模式（B）：**这些展示了在对话过程中将 GPT 模型与企业应用程序和搜索引擎集成的高级解决方案设计。

+   **具有精细调整模型的对话模式（C）：**这些展示了利用重新训练的模型的特定设计，基于 GPT 技术或开源，以生成更准确和特定领域的响应。

+   **代理模式（D）：**这些深入探讨了专门代理与 GPT 模型的架构集成，重点放在自动化、适应和协作上。

每个部分都提供了对模式的详细审查，包括它们的工作流程和潜在的用例，全面了解如何在各种对话环境、工具集成、协作设置和自动化场景中有效部署 GPT 模型。

我们以选择不同应用需求最合适的架构模式的见解和指南结束本章。

# 结构

在本章中，将涵盖以下主题：

+   架构模式定义

+   基础对话模式

+   与外部工具集成的对话模式

+   具有精细调整模型的对话模式

+   代理模式

+   架构模式的建议

# 架构模式定义

术语**架构模式**指的是在特定上下文中针对重复设计问题的一般可重用解决方案。它提供了一个概要框架，概述了所涉及的子系统或组件、它们的责任以及它们的交互方式。架构模式通过提供经过验证的解决方案、提高开发人员效率和减少潜在的设计风险来促进系统设计。它们包括以下元素：

+   **按层组件**：每个模式在分层系统内运行，以确保关注点的分离和可维护性。每个层都承载执行不同功能的特定组件。一个常见的分层结构包括用户体验层、应用层和 AI 层。这些层内的具体组件因模式而异，但在系统运行中都发挥着关键作用。

+   **工作流程**：工作流程描述了系统运行时发生的操作序列，从用户输入到生成的响应。这还包括任何中间步骤，如预处理、提示生成、响应过滤等，根据特定的架构模式来决定。

+   **企业集成**：这些架构模式构成了更大的组织 IT 景观的一个组成部分。因此，它们必须与现有的企业应用程序、数据库和知识库建立和谐的互动关系。每种模式都详细说明了这种集成的手段和程度，以及它对系统功能的后续影响。

+   **输出质量**：这指的是系统生成的响应的相关性、准确性和可用性。质量可以受到多种因素的影响，例如使用响应过滤器进行质量检查、应用基础和丰富过程以获得更好的上下文，或者使用多个 GPT 模型进行优化响应。每种模式都概述了影响输出质量的机制及其对系统响应准确性和相关性的影响。

+   **性能**：这指的是系统操作的效率和速度。性能可以根据任务复杂性、使用的 GPT 模型数量、应用集成的程度以及执行的任务类型而有所不同。每种模式都详细说明了其性能特征，讨论了影响其计算效率和响应速度的因素。

+   **使用案例**：每种架构模式都设计用于满足特定需求或解决特定问题。使用案例提供了每种模式可能最适合的实际情况的实际示例。这些可以从基本的问答机器人到更复杂的、具有上下文意识的解决方案。

在接下来的章节中，我们将应用这种结构来描述各种 GPT 驱动的架构模式，每种模式都解决了一组独特的需求。最终，您应该对这些模式有全面的了解，以便能够选择最适合您特定需求的模式。

# 基础对话模式

本节深入探讨了四种基于 GPT 模型的对话系统的基础架构模式。每种模式代表了不断增加的复杂程度，提供了不同程度的互动、知识集成和质量控制：

+   **基本对话（A1）：**这种模式描述了利用 GPT 模型的端到端对话解决方案的基本结构。这种解决方案处理用户查询并生成响应，提供了适用于问答交互和基本用户参与活动的简单功能。

+   **基础对话（A2）：**这种模式通过集成知识库扩展了基本的 GPT 驱动解决方案，从而丰富了 GPT 模型的能力，具有特定领域的知识。改进的响应质量和相关性使其适用于需要更加细致、具有上下文意识的交互的情况。

+   **混合主动对话（A3）：**这种模式引入了一个交互式的、由 GPT 驱动的解决方案，旨在不仅响应用户查询，还要生成查询或提供指示。这种额外的互动促进了用户参与，并提供了更动态的对话体验。

+   **质量控制对话（A4）：**这种高级模式提供了一个质量受控的对话解决方案，其中包括一个次要的 GPT 模型作为评论者。这个评论者评估主要模型的响应，促进一个逐步改进响应质量的迭代反馈循环。这是一个适用于生成响应质量至关重要的应用程序的理想模式。

在接下来的子章节中，我们将深入探讨每种模式，提供详细的描述、工作流说明和真实世界的使用案例。

# A1 基本对话

这种模式描述了在企业环境中实现基于 GPT 的聊天机器人的基本架构设置。它利用了 GPT 模型的强大功能，以生成对用户查询有意义的响应，同时保持用户友好的界面（见*图 4.1*）。

![](img/Figure-4.1.jpg)

**图 4.1:** 基本对话

# 用户体验层

这一层主要关注用户如何与解决方案进行交互。它采用标准的聊天机器人用户界面，可以是一个简单的文本框，也可以是一个具有语音和头像功能的更高级用户界面。这一层负责捕捉用户输入（话语）并以用户友好的方式呈现来自 AI 层的响应。

# 应用层

这一层连接了用户体验和 AI 层。它执行将原始用户输入转化为适合 GPT 模型的格式（提示生成）以及根据企业规则和要求过滤生成的响应的关键功能。

+   提示生成器：该组件将用户的话语转化为适合 GPT 模型的提示。首先，它选择与用户输入匹配的预定义提示模板²，然后用输入的细节实例化模板。示例如下：

+   服务代理输入：“一个重要客户不断提出不合理的投诉。今天我们收到了另一份这样的投诉。我们可以拒绝吗，还是因为客户的重要性而需要接受？”

+   GPT 模型的提示：

+   “专家角色：您是一家重视客户满意度和公平政策的公司的客户关系专家。

+   背景：一名服务代理提供了以下信息：“一个重要客户不断提出不合理的投诉。今天我们收到了另一份这样的投诉。我们可以拒绝吗，还是因为客户的重要性而需要接受？”

+   任务规范：

1.  总结投诉中与决策相关的方面。

1.  根据公司标准和过往互动，确定投诉是否合理或不合理。

1.  权衡这个客户的重要性和接受或拒绝投诉的公平性。

+   执行规则：

1.  确保所有决定都符合公司指南和道德标准。

1.  优先考虑与客户的长期关系，同时维护公司的诚信和声誉。

1.  考虑客户过去投诉中的任何模式。

+   输出约束：

1.  在不超过 150 个字的简洁回复中，就是否接受或拒绝投诉做出合理的决定。”

+   响应过滤：每个生成的响应都会经过一系列标准的检查，如适当性、相关性、完整性和连贯性。如果响应通过了这些检查，它将通过用户体验层发送回用户。否则，将显示默认消息。

# AI 层

这种模式的核心是 AI 层，它利用 GPT 模型作为响应生成器。该层接受应用层处理的提示，并利用预先训练的 GPT 模型中嵌入的知识生成响应。

# 模式工作流程

1.  用户通过输入问题或命令与聊天机器人界面进行交互。

1.  应用层接收用户输入并根据提示模板库将其转化为适合 GPT 模型的提示。

1.  AI 层，特别是 GPT 模型，根据给定的提示生成响应。

1.  应用层接收响应并应用过滤器检查是否符合定义的标准。

1.  如果响应通过了过滤器，它将通过用户体验层发送回用户。如果未通过过滤器，将向用户显示默认消息。

# 企业集成

基本对话模式既不与企业应用程序交互，也不利用内部知识库。此外，虽然系统确实考虑了对话历史作为上下文，但它主要依赖用户提供的信息。因此，系统的响应局限于 AI 模型在训练阶段灌输的知识。这样的响应是一般的，缺乏组织特定见解或来自企业应用程序和数据库的实时数据的丰富化，这对许多应用程序构成了相当大的限制。

# 输出质量

这种模式为简单和通用的查询提供了不错的输出质量，这主要归功于先进的 GPT 模型的强大。此外，基本的质量检查也在响应过滤器中实施，有助于保持生成的响应的适当性、相关性和准确性。

# 性能

由于其简约的设计，这种模式在计算性能方面脱颖而出。每次输入用户和 GPT 模型之间只有一次交互，确保快速响应和较低的计算负载。这种简化的方法使系统能够高效处理更大量的用户查询，从而提高了可扩展性。

# 使用案例

考虑到这种模式的基本性质，它适用于简单的问答任务，不需要上下文理解或访问专用知识库。它可以用于简单的常见问题解答机器人、提示-响应系统或基本用户参与活动等场景。它不适用于需要复杂的对话管理、上下文感知响应或访问动态和最新知识库的任务。

# A2 接地对话

这种架构模式通过将 GPT 模型的灵活性与组织现有系统的领域特定知识和数据相结合，增强了基本聊天机器人的能力（见*图 4.2*）。

![](img/Figure-4.2.jpg)

**图 4.2：** 接地对话

# 用户体验层

这一层与 A1 模式相同。

# 应用层

这一层充当用户体验和 AI 层之间的桥梁。它包含以下组件：

+   **企业应用程序和数据库**：这些是企业特定数据的来源，可以通过 API 调用访问。

+   **预处理器**：该组件从企业应用程序和数据库中检索相关数据，并查询知识库，丰富用户的输入。任何必要的质量检查和转换成文本格式也在这里执行。

+   **提示生成器**：该组件从预处理器获取丰富的用户输入，并将其转换为 GPT 模型可以理解和处理的提示格式。

+   **响应过滤器**：该组件评估 GPT 模型的响应是否符合特定标准，如相关性、适当性、完整性和连贯性，就像基本模式一样。如果响应未通过这些检查，将向用户返回默认消息。

# AI 层

这一层对基于 AI 的交互至关重要。它包括两个基本组件：GPT 模型和内部知识库。

+   **知识库**：位于 AI 层内部，与 GPT 模型并列，是领域特定知识的储备库。这个知识库通常以文档数据库³、图数据库⁴或向量数据库⁵的形式存在，提供了一个行业和/或组织特定细节的附加层。

+   **GPT 模型**：它通过利用应用层提供的丰富提示生成连贯且上下文相关的响应。值得注意的是，该模型将其预训练知识应用于用户、企业数据源和知识库的综合输入。

# [模式工作流]

1.  用户与聊天机器人界面进行交互，提供输入或提出问题。

1.  应用程序层的预处理器根据原始用户输入从企业应用程序和数据库中获取任何必要的数据。

1.  然后，预处理器通过知识库搜索与用户输入相关的相关信息。它可以使用传统基于关键词的搜索来直接匹配，或者在基础向量数据库的情况下，依赖于搜索查询和候选文档的向量编码的相似性进行语义搜索，以进行更广泛的、上下文感知的匹配。

1.  预处理器通过数据清洗、规范化、删除个人可识别信息（PII）和将长文本分成可管理的块等任务进一步完善了补充输入，以符合底层 GPT 模型的输入大小限制。

1.  Prompt 生成器将丰富的输入转换为适合 GPT 模型的提示。

1.  AI 层或 GPT 模型根据提示生成回应。

1.  响应过滤器根据预定义的标准检查此响应。

1.  如果响应通过过滤器，则通过用户体验层将其传递回用户。如果失败，将向用户提供默认消息。

# [模式工作流示例]

想象一下，您最近在客厅安装了一个智能灯泡，但它没有开启。寻求快速帮助，您联系制造商的技术支持聊天机器人。

您的交互是：“我的客厅的智能灯泡无法开启。”

以下是模式工作流可能进行的方式，示例中的步骤编号对应于一般工作流程中的步骤：

1.  用户交互：您已经告诉聊天机器人您的智能灯泡问题。

1.  获取必要的数据：立即，预处理器咨询制造商的数据库，确定您拥有的灯泡的确切型号和版本，以及安装日期和任何相关设备。

1.  搜索知识库：使用有关您特定灯泡型号的详细信息，预处理器搜索知识库——数字故障排除手册——寻找针对您灯泡型号量身定制的相关指导。

1.  精炼输入：预处理器确保指令按照易于遵循的顺序排列，剥离任何技术术语，使其用户友好。

1.  提示创建：这是聊天机器人为其主要大脑准备问题或上下文的地方。结合故障排除步骤，提示可能看起来像这样：“鉴于‘ABC 型号’灯泡无法开启，并基于建议检查灯泡的电源来源、验证其与开关的兼容性，并确保应用程序设置正确，您将如何以清晰和富有同情心的方式指导用户完成这些步骤？”

1.  响应生成：有了这个详细的提示，聊天机器人的大脑（GPT 模型）生成了一个连贯而有用的回答，引导您完成这些步骤。

1.  检查响应：响应过滤器评估聊天机器人的答案，确保清晰并击中所有重要的故障排除点。

1.  提供答案：经过验证后，聊天机器人回答：“很抱歉听到您的灯泡出了问题。让我们尝试这些步骤适用于您的‘ABC 型号’：

1.  首先确保灯泡牢固地拧入插座并接收电源。

1.  检查您使用的开关或插座是否与智能设备兼容。

1.  打开相关应用程序，并确保灯泡的设置正确配置。如果在这些步骤之后仍然遇到问题，请与我们的技术团队联系。

# [企业集成]

基于 API 调用的强大企业数据集成是基础对话模式的特点。它还访问知识库，以增强输入的相关领域特定知识。这种级别的集成允许系统利用组织现有 IT 基础设施的资源和功能，通过丰富聊天机器人的响应以组织知识和上下文感知。

# 输出质量

该模式通过将企业知识和数据与提示相结合，增强了输出质量。通过整合企业应用程序、数据库和知识库来补充用户输入，GPT 模型的上下文感知能力和生成更加细致和定制的响应的能力都得到了提高。

为了进一步提高提示的质量，架构采用了诸如数据清洗和规范化等预处理步骤。这些步骤消除了用户输入中的潜在不准确性和不一致性，并标准化数据，确保其以适合 GPT 模型处理的格式呈现。

该模式还包括一个输出过滤过程，原则上类似于基础对话模式（A1）中的过滤过程。然而，由于丰富的提示导致初始响应质量更高，输出过滤器现在可以专注于更具体的质量检查。

# 性能

与基础对话模式（A1）相比，基础对话模式展示了更多的计算复杂性和较低的效率，这是由于包含了额外的预处理步骤和集成。

# 使用案例

该模式适用于需要利用内部领域特定知识以及来自企业应用程序和数据库的数据的更加细致的响应的情景。它适用于希望提供动态、上下文感知响应的企业，比如特定产品或服务的客户支持、内部员工帮助，甚至个性化用户交互。

# A3 混合主动对话

该模式提供了一个具有交互能力的基于 GPT 的聊天机器人的高级配置。它通过系统发起的问题或指令来增强典型的用户驱动交互，以收集信息或协同执行流程（见*图 4.3*）。

![](img/Figure-4.3.jpg)

**图 4.3：** 混合主动对话

# 用户体验层

这一层现在支持使用聊天机器人用户界面进行混合主动对话。

# 应用层

除了之前模式的组件外，这里还引入了两个新组件：

+   **问题/指令过滤器**：这个新组件过滤了 GPT 模型生成的问题或指令，只有符合特定标准的才会传递给用户。

+   **用户输入提供者**：该组件捕获用户对 GPT 生成的问题或指令的响应，并将其反馈到 GPT 模型中。

# AI 层

这一层与基础对话模式（A2）中的情景保持一致，托管着一个 GPT 模型和一个知识库。

# 模式工作流程

1.  用户与聊天机器人界面进行交互，提供输入或提问。

1.  应用层中的预处理器咨询企业数据源和知识库，丰富用户的输入并执行任何其他所需的数据准备任务。

1.  增强的输入被转换为适合 GPT 模型的提示。

1.  GPT 模型可以根据提示为用户生成问题/指令或响应。

1.  GPT 生成的问题/指令经过过滤，如果符合标准，则传递给用户。

1.  用户提供相应的反馈，由用户输入提供者捕获并传递给 GPT 模型。

1.  最后，GPT 模型生成一个响应，然后由响应过滤器进行评估。

1.  如果回复通过了过滤器，它将被传递回用户。如果未通过，将显示默认消息。

# 企业集成

这种模式提供了与基础对话模式（A2）相同水平的企业集成。

# 输出质量

由于 GPT 模型提出的问题导致提示更具上下文，因此与 A2 相比，输出质量更高。

# 性能

每次对话轮的性能与 A2 相同，但由于 GPT 模型提出的额外问题，对话本身更加延长。

# 使用案例

这种架构类型非常适合需要动态、上下文感知的回复和用户输入的复杂互动场景。可能的应用包括高级客户服务、互动用户参与、引导式故障排除和个性化推荐。

# A4 质量控制对话

这种模式概述了一种复杂的聊天机器人架构，通过使用两个 GPT 模型来提高对话质量：一个作为主要的响应生成器，另一个作为评论家。这种配置提供了一个迭代的反馈机制，用于质量控制，以根据 GPT 评论家提供的反馈改进聊天机器人的回复（见*图 4.4*）。

![](img/Figure-4.4.jpg)

**图 4.4：** 质量控制对话

# 用户体验层

用户体验层与基础对话模式（A1）保持一致。

# 应用层

这一层包含与**基础对话**模式（A2）相同类型的组件，但在功能上有一些不同：

+   **提示生成器**：该组件还会根据 GPT 评论家的反馈生成纠正提示。这种功能使得有一个反馈循环，可以逐步改进回复的质量。

+   **响应过滤器**：与**基础对话**模式相比，由于 GPT 评论家提供的详细反馈，过滤标准现在更具体，使得对回复的评估更具上下文敏感和严格。

# 人工智能层

这一层包含两个 GPT 模型：一个作为主要的响应生成器，另一个作为评论家，还有一个知识库。

+   **响应生成器**：这个 GPT 模型根据提示生成回复，利用其预训练知识以及从内部知识库和企业数据源获取的输入。

+   **GPT 评论家**：这个 GPT 模型会对生成的回复进行质量评估。它会评估提示和回复，并就回复的质量提供反馈。为了确保高水准的回复，GPT 评论家会根据更详细的一套标准对每个生成的回复进行检查，包括恰当性、相关性、事实准确性、正确推理和潜在幻觉。评论的性质可能会根据具体的设置而有所不同。如果响应生成器使用的是相同的模型和上下文，那么 GPT 评论家也使用相同的模型和上下文，这可能会导致一种自我批评。在这种情况下，模型本质上会评估自己的输出。然而，如果评论过程中使用了不同的模型或上下文，这将引入一个新的独立审查层次，从而产生一个独立的评论。这有助于提供额外的检查和平衡，以确保生成的回复的质量。过去迭代的回复和反馈也可以包含在未来的提示中，以便响应生成器从过去的错误中学习。

# 模式工作流程

1.  用户与聊天机器人界面进行交互，提供输入或提问。

1.  预处理器使用内部知识库和企业数据源丰富用户输入，并执行必要的数据准备任务。

1.  增强输入被转换成适合 GPT 模型的提示。

1.  GPT 响应生成器根据提示生成响应。

1.  提示和响应被输入到 GPT 评论者中，评论者对响应的质量提供反馈。

1.  检查质量反馈。如果所有标准都得到满足，原始响应被传递回用户。如果没有，会向提示生成器发送更正提示的请求。

1.  更正提示被反馈到 GPT 响应生成器，新的迭代开始。

1.  在评论者提供反馈后，该过程终止，该反馈通过响应过滤器，或者在预定义数量的迭代完成失败后终止。

# 企业集成

这种模式提供了与基础模式（A2）相同水平的企业集成。

# 输出质量

通过企业数据和知识对提示进行基础和丰富是从以前的模式中保留下来的特性，这确保了响应的生成基于企业特定的上下文。

与这种模式独有的是，GPT 评论者审查来自 GPT 响应生成器的响应。它评估提示和生成的响应，提供的反馈被响应过滤器用来改善响应的质量，形成迭代的反馈循环。这个过程有助于确保响应的相关性、连贯性和整体质量，因为它们不断被改进，直到满足预定义的质量标准。

# 性能

与以前的模式相比，质量受控对话模式引入了计算复杂性的显着增加，因为增加了作为评论者的第二个 GPT 模型。这个 GPT 评论者审查了第一个 GPT 模型生成的每个响应，增加了新的计算负载。此外，迭代的反馈循环机制，根据评论者的反馈改善响应的质量，还通过响应生成器增加了额外的处理时间。

# 使用案例

这种模式非常适合需要高质量、上下文感知的响应的场景。反馈循环机制确保响应在满足定义的质量标准之前不断改进。这在客户支持系统、医疗咨询助手、金融咨询服务或任何其他响应质量至关重要的领域中特别有用。

# 与外部工具集成的对话模式

在本节中，我们深入探讨了两种用于 GPT 驱动的聊天机器人的更高级的架构模式。这些模式利用了 OpenAI 的 GPT 模型的强大功能，同时集成了外部工具和引导聊天机器人推理过程的高级方法。

+   **基本工具集成对话（B1）：**在介绍章节的相应部分的延续中（*GPT 模型中的外部工具访问*），第一个模式概述了一个架构，其中一个对话解决方案通过 API 调用与企业应用程序进行交互。这些交互嵌入到整个对话中，并根据用户输入动态触发，从文本生成扩展到执行企业任务，扩展了解决方案的能力。

+   **使用工具引导的思维链对话（B2）：** 第二种模式介绍了一种结构，将思维链（CoT）演示与特定工具的 API 调用集成在一起。这种配置确保了工具操作在解决方案推理过程中的流畅整合，使其能够暂停，使用外部工具执行操作，并根据结果继续对话。这种高级交互模型特别有益于需要在对话过程中进行推理的更复杂任务。

+   **高级工具集成对话（B3）：** 比基本工具集成对话（B1）更进一步，第三种模式将 GPT 模型部署为上下文规划器和响应生成器。虽然 B1 侧重于用户输入触发的与外部工具的直接交互，B3 引入了一个规划层，确定了一系列逻辑操作的顺序。结果是更丰富和更适应性的对话体验，超越了简单的任务执行，转向战略任务编排。

接下来的章节将详细讨论这些模式，讨论它们的各个组成部分、工作流程和潜在用例。

# B1 基本工具集成对话

这种模式概述了一种架构，其中一个启用了 GPT 的聊天机器人参与用户交互，这些交互需要通过 API 执行企业应用程序、数据库和知识库提供的特定功能。这使得聊天机器人能够扩展其能力，不仅仅是生成类似人类的文本，还能够在对话过程中执行外部任务（见*图 4.5*）。

![](img/Figure-4.5.jpg)

**图 4.5：** 基本工具集成对话

# 用户体验层

这一层与**Grounded Conversation**模式（A2）保持不变，为用户交互提供标准的聊天机器人用户界面。

# 应用层

作为用户体验和 AI 层之间的桥梁，这一层包含几个组件：工具 API 规范、企业应用程序和数据库、用户提示生成器、响应过滤器、响应分类、API 调用的提取和执行，以及语音提示生成器。

+   **工具 API 规范**：这个组件保存了对话应用程序可以与之交互的各种工具的 API 规范。规范通常包括这四个元素。

+   **API 名称**：API 名称提供了 API 的摘要。它帮助 GPT 模型将用户指令与此 API 链接，并作为提取和执行组件的入口。名称应该用自然语言清晰而精确，避免与其他 API 名称产生歧义，比如*check_order_status*用于检查后端系统中订单的状态。

+   **参数列表**：API 的参数列表包括输入参数和返回值，每个参数都有参数名称、参数描述、数据类型和默认值。这些信息帮助使用的 GPT 模型正确填充相应位置的参数，并使用适当的格式。对于*check_order_status*示例，参数可能如下：

+   输入参数：

+   **order_id***:* 整数，系统中订单的唯一标识符。这用于查找特定订单并检索其当前状态。

+   返回值：

+   **order_status***:* 字符串，表示订单的当前状态。常见的值可以包括 Pending、Processing、Shipped、Delivered、Canceled 等。

+   **expected_delivery_date***:* 日期（可选），已发货状态的订单的预计交付日期。

+   **reason***:* 字符串（可选），如果订单被取消，这将提供取消的原因。

+   **API 描述**：与 API 名称相比，API 描述包含了更多关于 API 的信息，包括它的功能、工作原理、输入和输出，以及可能引发的任何潜在错误或异常。*check_order_status*的相应示例可能是：*此函数允许检索与特定订单相关的当前状态，通过使用订单的唯一 ID 实现。查询时，系统将回复订单的状态，并可能提供额外的细节，如预计交付日期或订单取消的原因。*

+   使用示例（可选）：为复杂的 API 提供使用示例可以帮助演示 API 的使用方式，而对于简单的 API 可能并不是必要的。对于订单状态检查，一个示例可能是这样的：*用户可以使用 ID“12345678”请求订单的状态。响应可能会告知他们订单已经“发货”，并提供相应的预计交付日期。*

+   **企业应用和数据库**：这些通过 API 调用提供外部工具，可以包括任何功能性后端系统，如人力资源、财务或采购，还可以包括搜索引擎或专门的 ML 模型。

+   **用户提示生成器**：这个组件将用户的输入转换成适合 GPT 模型的提示。

+   **响应分类**：这个组件将 GPT 生成的响应分为两种类型：

+   对用户请求的最终响应或

+   中间响应包含一个功能调用。

如果响应包含一个`**function_call**`字段，则会识别出一个功能调用。

+   **API 调用的提取和执行**：当识别到一个功能调用响应时，这个组件从功能调用字段中提取必要的细节，根据工具 API 规范选择适当的工具，并使用所选的工具执行 API 调用。工具可以是企业应用、数据库或知识库中的任何功能。

+   **语言化提示生成器**：这个组件利用现有的上下文（用户提示和功能调用响应）并添加一个功能提示，其中包含了前一个功能调用的结果转换成文本格式。然后，一个 GPT 模型将这些结果转换成自然语言的用户响应。

+   **响应过滤器**：这个组件检查用户的最终 GPT 响应，以确保其适当性、相关性、完整性和连贯性。

# AI 层

这一层承载了 GPT 模型，这些模型已经在包括特定版本的 GPT-3.5 Turbo 和 GPT-4 在内的对话数据上进行了训练。这些模型可以根据它们收到的提示生成用户响应或功能调用响应。

它还包括一个具有与之前模式相同功能的知识库。

# 模式工作流程

1.  用户与聊天机器人界面进行交互，提供输入或提出问题。

1.  用户的输入被转换成 GPT 模型的初始提示，其中还包括工具 API 规范。

1.  然后将响应分类为用户响应或功能调用响应。

1.  如果是用户响应，它将被转发到响应过滤器，那里会对其进行相关性、准确性和适当性的审查，并将其转发给用户（检查结果为正面）或替换为默认消息（检查结果为负面）。

1.  如果它是一个以定义 API 调用格式的功能调用响应，‘API 调用的提取和执行’组件将执行 API 调用到指定的企业应用、数据库或知识库。

1.  API 调用的结果被用于语言化提示生成器生成一个 GPT 模型的功能提示。

1.  一个 GPT 模型会生成一个用户响应，将 API 调用的结果转换成自然语言。

1.  这个过程会随着每个新的用户提示而重复，直到对话结束。

# 模式工作流程示例

让我们通过一个示例来使用这个模式。在这里，我们将使用用户联系在线书店的聊天机器人询问其订单状态的场景：

您的互动是：“您能告诉我订单编号为 98765432 的订单状态吗？”

以下是聊天机器人模式工作流程的辅助，示例中的步骤编号对应于一般工作流程中的步骤：

1.  用户互动：您通过提供订单编号向聊天机器人询问订单状态。

1.  初始提示创建：提示生成器将您的问题转换为适合 GPT 模型的提示：“用户想要根据工具 API 规范检查订单状态来了解订单编号为 98765432 的订单状态。”

1.  响应分类：GPT 模型解释提示并确定这需要调用书店系统的函数，特别是 check_order_status 函数。

1.  用户或函数调用决策：由于响应表明需要进行函数调用，系统跳过用户响应生成并继续下一步。

1.  API 执行：使用提供的细节，系统从书店系统获取信息。它使用订单编号 98765432 的 check_order_status API 来获取订单的当前状态和其他细节。

1.  口头提示创建：使用书店系统的结果，为 GPT 模型生成一个函数提示，其中包含订单的当前状态和其他细节。

1.  生成用户响应：然后，GPT 模型根据这个提示创建一个连贯的响应，可能是：“您的订单编号为 98765432 的订单已经发货！您可以预计在 2023 年 8 月 28 日之前收到。”

1.  对话继续或结束：聊天机器人将这条消息传递给您。如果您有更多问题，对话将继续，如果您的询问得到满足，对话将结束。

# 企业集成

工具集成对话模式具有显著的企业集成水平。该架构与通过 API 可访问特定功能的企业应用程序和数据库紧密相关。这种设计促进了几乎实时的集成，使聊天机器人能够执行任务、获取数据并根据这些操作生成响应。此外，这种模式还可以通过 API 潜在地访问知识库，扩展了聊天机器人在对话过程中可以获取数据的范围。

# 输出质量

这种模式通过动态地使用后端系统的任务输出来显著提高了输出质量。决定何时调用后端系统是由 GPT 模型根据用户输入而不是像**Grounded pattern**（A2）中的预处理器来进行的。这些任务的结果为 GPT 模型提供了详细和准确的上下文，当它实际用作响应生成器时。

# 性能

这种模式引入了更多的计算复杂性和延迟，因为涉及与企业应用程序和数据库通过 API 进行交互、对响应进行分类和生成口头提示的额外步骤。

# 用例

这种模式在需要根据用户输入与企业应用程序和数据库进行多次交互的流程导向场景中表现出色。它也非常适合需要与企业应用程序和数据库交互以获取或更新用户数据的客户服务机器人。

# B2 链式思维引导对话使用工具

该模式代表了基于 GPT 的聊天机器人的架构，结合了思维链（CoT）演示和通过 API 调用与企业应用程序和数据库的特定功能进行交互。CoT 演示有助于设计更有效的提示，展示逻辑推理链给 GPT 模型，增强其在一系列交互中保持一致的逻辑响应或动作的能力（见*图 4.6*）。

![](img/Figure-4.6.jpg)

**图 4.6:** 使用工具进行思维链引导的对话

# 用户体验层

这一层与**基础对话**模式（A2）中的一样，为用户交互提供了标准的聊天机器人用户界面。

# 应用层

应用层在调解聊天机器人的推理过程和其与企业应用程序和数据库的交互中发挥了关键作用。它包括几个组件：CoT 演示、企业应用程序和数据库、工具 API 规范、初始提示生成器、响应过滤器、响应分类、函数名称/输入提取和 API 调用以及继续提示生成器。

+   **思维链（CoT）演示**：这些是用于增强用户输入的聊天机器人所需思维过程的演示。

+   **企业应用程序和数据库**：这些应用程序和数据库包含了聊天机器人通过 API 调用与之交互的特定工具功能。

+   **工具 API 规范**：该组件保存了企业应用程序和数据库中各种工具的规范，聊天机器人可以与之交互。

+   **初始提示生成器**：该组件将用户的输入与企业应用程序和数据库中的相关工具 API 规范以及匹配的 CoT 演示相结合，转换为 GPT 模型的初始提示，指示在生成工具触发时停止。

+   **响应过滤器**：该组件检查 GPT 模型生成的响应是否符合定义的标准。

+   **响应分类**：该组件将 GPT 生成的响应分类为用户响应或工具调用。

+   **工具名称/输入提取和 API 调用**：当在响应中识别出工具触发时，该组件提取工具名称和输入，执行工具调用，并将结果附加到推理过程中。

+   **继续提示生成器**：该组件通过结合原始提示、中间响应和工具结果生成 GPT 模型的继续提示。

# AI 层

该层承载了知识库和一个负责生成用户提示的中间和最终响应的 GPT 模型。

# 模式工作流程

1.  用户与聊天机器人界面进行交互，提供输入或发出请求。

1.  用户的输入被增强，包括来自企业应用程序和数据库的相关工具 API 规范以及匹配的 CoT 演示。

1.  增强输入被转换为 GPT 模型的初始提示，指示在生成工具触发时停止。

1.  GPT 模型生成中间响应，然后被分类为用户响应或函数调用。

1.  如果响应包含工具触发，将提取工具名称和输入，并在指定的应用程序、数据库或知识库上执行相应的函数调用。

1.  函数调用的结果被附加到推理过程中。

1.  再次调用 GPT，使用继续提示（原始提示+中间响应+工具结果）来继续对话。

1.  步骤 4-7 重复，直到推理过程中的所有使用工具的步骤都已完成。

1.  生成最终响应，由响应过滤器检查，并传递给用户。

# 企业集成

该模式的企业集成等同于**集成工具对话**模式（B1）中的企业集成。

# 输出质量

这种模式的输出质量也与之前的模式相当。

# 性能

由于每次需要执行函数调用时都会重复进行继续提示，因此该模式的性能不如工具集成对话模式。

# 用例

这种模式特别适用于需要逐步推理过程和与外部工具集成的复杂用例。它可以用来创建复杂的聊天机器人，不仅可以回答查询，还可以执行多步任务，解决复杂问题，或者在与外部工具或服务交互时引导用户完成流程。示例包括 IT 支持聊天机器人，复杂软件应用程序的虚拟助手，或培训系统。

# B3 高级工具集成对话

这种进化的架构模式利用了 GPT 模型的两种能力：作为规划者和响应生成器。作为规划者，它将用户输入转换为任务序列，这些任务以协调的方式执行，作为响应生成器，它使用每个任务的输出生成具有上下文的用户响应（参见*图 4.7*）。

![](img/Figure-4.7.jpg)

**图 4.7：** 高级工具集成对话

# 用户体验层

与 B1 模式相比，这保持不变，提供一致的用户-聊天机器人交互界面。

# 应用层

该层使用 B1 模式中的以下组件：

+   工具 API 规范，现在还可以包括有关如何组合多个 API 以完成复杂用户请求的组合说明。

+   API 调用的提取和执行

+   企业应用程序和数据库

+   响应过滤器

此外，它引入了几个与规划相关的组件：

+   **规划提示生成器**：该组件将用户的输入转换为提示，要求 GPT 模型生成计划或任务序列。

+   **计划执行**：一旦 GPT 模型生成了计划，该组件系统地提取并执行序列中的每个任务。

+   **用户响应提示生成器**：它取代了语言提示生成器。该组件将结果编译成新的提示，供 GPT 模型生成全面且易于理解的响应，所有计划中的任务执行完毕后。

# AI 层

该层包括与以前一样的知识库和 GPT 模型扮演两种不同角色：

+   **规划者**：给定一个规划提示，GPT 模型会概述一系列逻辑任务及其相应的 API 调用，以满足用户的请求。

+   **用户响应生成器**：在计划中的所有任务执行完毕并编译结果后，GPT 模型将编译结果并将其制作成用户易于理解的全面响应。

# 模式工作流程

1.  用户与聊天机器人界面进行交互。

1.  规划提示生成器将用户的请求转换为 GPT 模型的规划提示，其中还包括工具 API 规范。

1.  GPT 在其规划者角色中解释规划提示，并为每个任务生成一系列具有 API 调用的任务序列。第一个任务具有完全指定的 API 调用，而后续任务在各自的 API 调用中有占位符。

1.  计划执行组件提取第一个任务的 API 调用并将其发送到 API 调用执行组件，该组件处理并返回 API 调用结果。

1.  计划执行组件更新任务序列中第一个任务的结果，并将其重新提交给 GPT 作为规划者。

1.  GPT 模型保留计划中已执行的任务，并立即重新生成紧随上一个已执行任务的任务序列。

1.  计划执行组件移动到序列中的下一个任务，并将其发送到 API 执行模块，从中再次获取结果。

1.  之后，它更新计划并将其重新提交给 GPT 模型。这个循环会一直持续，直到计划中的所有任务都被执行。

1.  在所有任务完成后，计划执行组件将所有中间和最终结果转发给用户响应提示生成器。

1.  用户响应提示生成器为 GPT 模型制定了一个提示。

1.  GPT 在其响应生成器角色下产生了详细且用户友好的响应。

1.  响应过滤器审核这个最终响应，确保其质量和相关性。

1.  用户收到经过过滤的响应，并在需要时继续交互。

# [模式工作流示例]

让我们想象一下，一个用户想要在当地公园为朋友举办生日派对，并需要一些帮助。

您的互动是：“我想在下周六在中央公园为我的朋友马克举办生日派对。你能帮忙吗？”

这就是这种模式如何发挥作用的方式。由于对计划任务序列的迭代，示例中的步骤编号不同：

1.  用户互动：您向聊天机器人表达了在中央公园为朋友筹划生日派对的意图。

1.  规划提示创建：聊天机器人通过规划提示生成器重新制定您的请求：“为下周六在中央公园举办生日派对生成一个计划。”

1.  GPT 的计划生成：GPT 模型在其规划者角色下解释规划提示，并制定了一个多步任务序列：

+   任务 1：验证下周六中央公园的活动场地是否可用。

+   任务 2：在中央公园预订一个合适的地点。

+   任务 3：列出附近的面包店供制作生日蛋糕。

+   任务 4：推荐本地娱乐或表演者供雇佣。

+   任务 5：提供下周六的天气预报。

1.  计划执行 - 任务 1：系统首先使用活动 API 检查指定日期中央公园的活动场地是否可用。

1.  更新和重新提交：假设公园可用，计划将继续并被重新提交给 GPT 进行下一个序列。

1.  计划执行 - 任务 2：系统然后使用预订 API 预订一个适合生日聚会的中央公园地点。

1.  计划执行 - 任务 3：聊天机器人访问本地目录 API，列出附近几家评价较高的面包店，以便可能的蛋糕订购。

1.  计划执行 - 任务 4：系统利用另一个本地服务 API，提供一些可供雇佣的魔术师、音乐家或派对表演者等娱乐选项。

1.  计划执行 - 任务 5：系统使用天气 API 提供下周六的天气预报，以确保准备工作考虑到可能的雨天或晴天。

1.  编制结果：所有中间结果，即公园的可用性、预订确认、面包店列表、娱乐建议和天气预报，都被整合起来。

1.  用户响应提示创建：生成一个提示，整合所有数据：“将中央公园的可用性、预订、面包店列表、娱乐选项和天气预报的发现转化为连贯的用户响应。”

1.  制作用户响应：GPT 在其用户响应生成器的能力下构建消息：“下周六中央公园有空！我已经为马克的生日预订了一个地点。附近有前 3 家面包店：[面包店名称]。作为娱乐，考虑雇佣[表演者名称]。此外，天气预报显示将是晴天。愉快的筹划！”

1.  响应过滤：检查这个详细的响应是否连贯清晰。

1.  最终用户互动：您将得到详细的计划和资源，可以继续进行准备工作，或者继续交互以获取更具体的细节。

# 企业集成

高级工具集成对话模式展示了更深层次的企业集成。通过利用 GPT 的规划能力，它可以动态交互地构建利用各种企业应用程序和数据库功能的任务序列。这种设计允许自适应交互，确保任务序列和响应根据不断变化的用户输入不断优化。

# 输出质量

这种模式的输出质量明显更高，因为动态规划和迭代执行任务的添加。GPT 模型不仅仅依赖于初始上下文，还可以根据先前任务的结果和用户的响应调整其方法。这种迭代和自适应过程确保对话保持更相关，并且不断优化以最好地满足用户的需求。

# 性能

虽然这种模式在输出质量和企业集成方面带来了显著的好处，但也引入了更多的计算开销。迭代规划、执行和重新规划过程会增加整体响应时间的延迟。

# 用例

鉴于 B3 模式的增强功能，其用例扩展到更复杂和动态的场景：

+   **流程自动化机器人：** 适用于引导用户完成复杂的、多步骤的流程，如入职、故障排除或服务配置。随着每个步骤的完成，机器人可以根据结果调整其引导。

+   **动态查询系统：** 适用于用户请求需要按特定顺序从多个来源获取和处理数据的情况，例如生成跨多个企业应用程序的详细报告。

+   **高级客户服务机器人：** 除了简单的数据检索，这些机器人可以执行更新多个记录、启动流程，然后在单个用户交互中报告结果的任务序列。

+   **交互式教程和引导学习：** 机器人可以根据用户的响应、测试结果或其他标准调整学习路径，确保定制化的学习体验。

+   **集成业务智能工具：** 适用于需要从不同企业工具中获取数据、进行分析和可视化任务序列以生成见解的业务用户。

# C 使用经过微调的模型的对话模式

本节介绍了两种利用 GPT 与经过微调模型潜力的高级模式，用于端到端的对话解决方案。

+   **使用经过微调的模型的对话 (C1):** 这种模式利用 GPT 模型生成训练数据，用于微调商业或开源语言模型。对话解决方案随后利用这个经过微调的模型为用户制定响应，辅以企业知识和数据。

+   **使用两个模型的对话 (C2):** 这种模式同时利用经过微调的模型和预训练的 GPT 模型进行操作。经过微调的模型的输出用于增强具有特定上下文数据的用户输入。这为 GPT 模型提供了更高质量的输入，从而产生更精确和与上下文相关的响应。

包括它们的结构、工作流程和潜在用例在内的这些架构模式的详细描述将在下文中介绍。

# C1 使用经过微调的模型的对话

这种模式概述了一个以 GPT 为驱动的对话解决方案的架构，它利用数据库和 GPT 创建训练数据。这些数据用于微调现有的语言模型，随后处理用户交互（参见*图 4.8*）。

![](img/Figure-4.8.jpg)

**图 4.8:** 使用经过微调的模型的对话

# 用户体验层

这一层相当于**基础对话**模式（A2）。

# 应用层

这一层还包括 A2 模式中的相同组件。

# AI 层

AI 层包括几个关键组件：

+   增强知识库：在运行时用于补充 AI 的知识。

+   预训练语言模型：这是一个通用模型，经过大量数据的训练，可以理解语言，但不专门针对任何特定任务。

+   精细调整的语言模型：利用预训练模型奠定的基础，这个版本在特定数据集上进一步训练或精细调整。这可以用于针对性的任务，比如遵循指示或促进对话，提高其在这些任务中的准确性和相关性。

+   GPT 模型作为训练数据生成器：它利用 GPT 模型的能力生成训练数据，模拟各种场景或对话。用户应注意一个关键的许可规定：从 OpenAI 的服务中得到的输出不得用于与 OpenAI 竞争的模型的创建。值得注意的是，许可条款是动态的，可能会定期更改。有关最新信息，请始终参考 OpenAI 的官方文档或服务条款。

+   用于训练数据生成的数据库：一个精心策划的来源，GPT 模型从中提取和处理信息以生成训练数据。

在考虑精细调整解决方案时，企业今天可以选择利用 OpenAI 提供的商业模型或一些值得注意的开源模型：

+   OpenAI 的商业模型：

+   GPT-3.5 Turbo：OpenAI 提供了 GPT-3.5 Turbo 的精细调整能力。早期评估表明，GPT-3.5 Turbo 的精细调整版本在特定狭窄任务中可以达到与基础 GPT-4 模型相媲美的性能水平。强调安全性，精细调整的训练数据受到 OpenAI 的 Moderation API 的约束，该 API 基于 GPT-4。

+   GPT Base、babbage-002 和 davinci-002：这些模型是 OpenAI 的最新添加，具有 16K 的上下文窗口大小，可用于标准和精细调整应用。

+   开源模型（预训练 1 万亿标记）：

+   MosaicML 的 MPT-30B：一个拥有 300 亿参数的开源模型。它超越了 MPT-7B 和 GPT-3 的能力，具有 8000 个标记的上下文窗口大小。该模型有两个不同的版本：MPT-30B-Instruct，专门用于指令精细调整，以及 MPT-30B-Chat，专为聊天机器人开发而设计。MosaicML 的平台还提供了定制和部署选项。

+   科技创新研究所的 Falcon LLM：这个总部位于阿布扎比的开源模型配备了 400 亿参数，并提供了 2000 个标记的上下文长度。此外，还提供了 Falcon-40B-Instruct 变体，专门设计用于基于指令的精细调整。

+   OpenLLaMA：作为 Meta AI 的 LLaMA 的开源对应物，它提供了 3B、7B 和 13B 参数配置的模型，每个模型都配有 4000 个标记的上下文窗口。与 Meta 的研究专用 LLaMA 相比，OpenLLaMA 是为商业应用而设计的，并支持精细调整。

+   开源模型（预训练 2 万亿标记）：

+   Meta 的 Llama 2：这是一个更近期的发布，Llama 2 有 7B、13B 和 70B 参数的配置。它有 4000 个标记的上下文长度，是其前身 Llama 1 的两倍容量。Llama-2-chat 变体经过进一步的改进，使用了 10 万个公共指令数据集，并受到了超过一百万人类偏好的影响，以增强交互的安全性和实用性。Llama 2 的许可允许商业利用和精细调整。

在选择预训练模型之后，需要对其进行微调以适应特定的企业任务。我们的方法涵盖了数据策划、预处理、使用 GPT 生成训练数据、模型训练和评估，所有这些都以实际例子进行说明。这种方法确保模型能够有效地适应手头的任务：

1.  数据策划：

+   定义：主要步骤涉及收集和策划特定领域的数据库。所选数据应代表特定任务，并为后续步骤提供坚实基础。

+   例子：

+   收集客户支持票据以创建 IT 支持聊天机器人。

+   积累过程日志以帮助预测过程结果。

+   汇总电子邮件历史以开发通信分类器。

+   收集销售交易数据以开发产品推荐系统。

+   整理员工入职的查询和答案，以识别常见问题和回答。

1.  预处理：

+   定义：处理策划数据，使其准备好进行机器学习任务。这涉及数据清理、转换或其他特定领域的操作。

+   例子：

+   清理支持票据以删除任何个人客户信息。

+   结构化和组织过程日志以跟踪执行阶段。

+   根据主题和内容对电子邮件历史进行分类。

+   规范销售交易数据，例如调和产品描述，以应对季节性或促销高峰。

+   整理员工入职的查询和答案，形成全面的数据库。

1.  使用 GPT 模型生成训练数据：

+   定义：利用 GPT 模型根据预处理信息生成标记或结构化数据。

+   例子：

+   模拟 IT 支持对话：通过将客户支持票据输入到 GPT 模型中，生成整个对话，模拟客户查询如何由 IT 支持台处理。

+   预测过程结果：GPT 模型在提供部分执行过程时，生成潜在结果，可用作训练数据。

+   使用 GPT 进行电子邮件分类：通过向 GPT 模型提供电子邮件历史，模型可以生成分类标签，如“投诉”、“查询”或“反馈”。

+   产品推荐模拟：通过 GPT 处理销售数据，我们可以模拟客户购买模式并得出可能的产品推荐。

+   HR 的问题和答案生成：GPT 可以生成与入职流程相关的问题和答案对，形成一个多样化的数据集。

1.  模型微调：

+   定义：使用生成的数据集来训练或微调特定于手头任务的模型。

+   例子：

+   使用模拟的 IT 支持对话训练聊天机器人模型以处理客户互动。

+   使用 GPT 派生的结果训练模型以预测过程结果。

+   训练分类器以根据 GPT 生成的标签对电子邮件进行分类。

+   使用 GPT 模拟客户购买模式来训练推荐引擎。

+   创建标准的问答聊天机器人，找到类似的问题并显示相应的答案，使用 GPT 生成的问答对。

1.  评估和迭代：

+   定义：评估训练模型的性能，并根据需要重复过程以实现最佳结果。

+   例子：

+   将聊天机器人的回答与专家提供的答案进行比较，评估聊天机器人的效果。

+   将过程结果预测的准确性与实际结果进行比较。

+   通过将其与手动标签进行比较，评估电子邮件分类器的准确性。

+   测试推荐引擎的建议与真实客户反馈进行比较。

+   通过将 HR 聊天机器人的答案与 GPT 生成的数据集进行比较，以确保准确性和相关性。

每个步骤都经过精心设计，以确保所选的预训练模型精确适应特定领域的需求，推动高效和准确的结果。

# 模式工作流程

微调后的工作流程与 A2 模式相同。

# 企业集成

这种模式提供了与 A2 模式中一样的企业集成水平。

# 输出质量

与 A2 模式相比，这种模式显示出更高的输出质量。这种改进来自于在微调过程中应用特定领域知识，使系统能够在特定领域内提供更准确和相关的响应。

与 A2 模式一样，它还通过输出过滤过程丰富用户提示的信息来确保生成的响应的相关性和适当性。

# 性能

这种模式在训练阶段主要会产生相当大的计算负载，其中模型会在特定领域的数据上进行微调。虽然对其进行优化的研究仍在进行中，但生成训练数据和微调预训练语言模型的过程仍然需要大量的计算资源，如处理能力、内存和时间。它可能还需要大量的特定领域数据才能达到所需的性能水平。

一旦模型被微调，操作计算成本与涉及将用户话语转换为提示、生成响应和过滤这些响应的其他模式相似。

然而，微调对话模式的一个重要优势是，它通常会导致一个比通用模型更小的模型。这种减小的尺寸可以降低每次推理（响应生成）的计算成本，提高速度，并且可能允许本地部署，消除了通过云平台访问的需要，因此可能减少响应时间。

# 使用案例

这种模式在特定领域相关知识至关重要的场景中特别有用。这些可能包括：

+   **具有丰富示例的高复杂度领域**：生命科学或工程等领域，标准语言模型可能无法提供所需的深度或准确性的输出。特别是在存在大量复杂和专业示例的情况下，微调变得至关重要。

+   **高风险环境**：精度至关重要的情况，因为不准确可能导致重大后果。例如医学诊断、财务预测或法律咨询，错误的解释或建议可能会产生严重后果。

+   **定制化体验和语调**：需要定制化互动或调整以满足不同用户群体的需求，以及努力在模型输出中反映其独特品牌声音的机构。

+   **快速变化的领域**：知识领域迅速发展，不断进行模型重新训练比依赖外部工具或预处理更有优势。例如技术行业频繁的软件更新或新闻机构报道快速发展的事件。

+   **可操纵性、一致性和输出格式化**：对于需要增强对模型行为的控制的企业，比如保持特定语言输出或确保一致的响应格式。这对于代码补全或组成 API 调用等场景至关重要。

+   **高效的提示利用**：微调可以减少对冗长提示的需求，当原始提示及其响应可以从微调数据集中的快捷方式中预测出来时。

# C2 使用两个模型的对话

这种模式详细介绍了一个使用微调模型与预训练模型协同生成用户响应的 GPT 启用对话解决方案的架构 4]（参见*[图 4.9*）。

![](img/Figure-4.9.jpg)

**图 4.9:** 使用两个模型的对话

# 用户体验层

该层利用标准聊天机器人用户界面进行用户交互，可能还增加了语音和头像功能。

# 应用层

应用层包括两个提示生成器、一个响应过滤器以及企业应用和数据库：

+   企业应用和数据库：这些是内部工具和数据源。

+   提示生成器 1：这个组件解释用户的话语，并调用企业应用和数据库的相关 API，将返回的数据整合到微调模型的初始提示中。

+   提示生成器 2：这个组件接受微调模型的输入和输出，如果需要，再次调用企业应用和数据库的必要 API，并为预先训练的 GPT 模型生成最终响应的新提示。

+   响应过滤器：这个组件根据各种标准检查最终响应，以确保它与用户的查询相关且适当。

# AI 层

该层包括一个预先训练的模型、一个微调模型、GPT 作为训练数据生成器、GPT 作为响应生成器以及一个知识库。

微调过程与前一模式中描述的过程相同。

# 模式工作流程

1.  用户交互到初始提示创建：用户向系统传达他们的查询。提示生成器 1 理解这个输入，与后端系统 API 进行联络，吸收必要的数据。这些综合信息形成了一个为微调模型量身定制的初始提示。

1.  微调模型交互：微调模型在其专业领域内进行评估初始提示，并产生简洁而明晰的输出。

1.  预先训练的 GPT 模型的提示：提示生成器 2 将微调模型的输入和输出合并。它可能通过咨询额外的后端 API 进一步增强数据，最终形成一个为预先训练的 GPT 模型设计的全面提示。

1.  生成最终响应：预先训练的 GPT 模型，具有更广泛的理解能力，根据接收到的提示制作全面而有条理的响应。

1.  响应过滤：结果消息经过一定标准的相关性和适当性检查。通过此评估后，将其传递给用户，但未通过检查则显示默认响应。

# 模式工作流程示例

使用这个模式，让我们概述一个示例场景，用户想购买一台笔记本电脑，并根据他们的特定需求寻求最佳选择的建议。

您的交互是：“我正在寻找一台适合图形设计任务的笔记本电脑。我的预算是$1500。你有什么推荐？”

以下是 C2 模式的应用方式，示例中的步骤编号与一般工作流程中的步骤相对应：

1.  用户交互到初始提示创建：在表达您的需求后，提示生成器 1 解释您的查询。它调用后端系统的 API 来获取价格范围内可用的笔记本电脑及其规格。这些信息被整合到一个初始提示中，可能是：“在$1500 内提供适合的笔记本电脑推荐，优先考虑图形设计能力。”

1.  微调模型交互：微调模型专门针对电子产品和用户需求进行培训，可能生成一个简洁的列表：“考虑[Laptop Brand A]，配备[Spec A]，售价$1400，或[Laptop Brand B]，配备[Spec B]，售价$1450。两者都适合图形设计。”

1.  预训练 GPT 模型的提示：Prompt Generator 2 接受来自经过精细调整模型的输入和输出，可能调用额外的后端 API（也许是用户评论或可用性），生成预训练 GPT 模型的提示：“考虑到用户的平面设计需求和 1500 美元的预算，以及推荐的笔记本电脑[Laptop Brand A]，配备[Spec A]，售价 1400 美元和[User Review A]，以及[Laptop Brand B]，配备[Spec B]，售价 1450 美元和[User Review B]，制定一个详细而有说服力的回应。”

1.  生成最终回应：预训练 GPT 模型处理全面的提示，产生一个详细的回复：“根据您的需求和预算，我建议[Laptop Brand A]，配备[Spec A]，非常适合平面设计任务，价格为 1400 美元，远低于您的预算。它得到了用户的高度评价，特别是因为它的[specific feature]。另一个很好的选择是[Laptop Brand B]，售价 1450 美元，提供[Spec B]，也受到平面设计师的积极反馈。两者现在都可以购买。您对哪个感兴趣？”

1.  响应过滤：对这个详细的回应进行审查，以确保它符合适当性和相关性的标准。如果通过，消息将传递给您。如果没有，您可能会看到一个通用的回应，也许是这样的：“抱歉，我无法处理您的请求。请再试一次。”

# 企业集成

在这种模式中，通过将企业应用程序和数据库整合到应用层中，实现了两次企业集成。

应用层中的两个提示生成器旨在直接调用企业应用程序和数据库的相关 API。‘Prompt Generator 1’利用从这些 API 调用返回的数据来为经过精细调整的模型形成初始丰富的提示。同样，‘Prompt Generator 2’可能会从企业应用程序和数据库调用额外的 API，将返回的数据集成到预训练 GPT 模型的新提示中。

# 输出质量

“使用两个模型进行对话”的模式通过利用经过精细调整和预训练模型的独特优势来提高输出质量。它利用了经过精细调整的模型对专业化、上下文感知的响应的能力，以及预训练的 GPT 模型的通用多功能性。这些模型的协同作用促进了适应性和特定上下文的响应生成，可以满足各种对话场景的需求。

就像在**基于事实的对话**模式（A2）中一样，这种架构也包括提示的基础和丰富方面，利用来自企业应用程序和数据库的数据来完善和指导提供给 AI 模型的提示。这种基础过程在这种模式中执行两次，每个模型执行一次，这允许更深入、更复杂地理解用户的意图。

# 性能

“使用两个模型进行对话”的模式的计算需求更高，因为它涉及到每个用户交互的两个独立语言模型。第一个计算负载是模型的精细调整，这是离线完成的，可能会像前一个模式描述的那样在计算上昂贵。

第二个，可能更重要的计算负载是在交互过程中产生的。每个用户提示都要经过两次处理，首先是由经过精细调整的模型处理，然后是由预训练的 GPT 模型处理。这两个步骤都需要 CPU 或 GPU 资源，并需要一定的时间。此外，应用层的处理，比如从企业应用程序和数据库调用 API，可能需要两次，并生成丰富的提示，也会增加计算负载。

# 用例

这种双模型模式在需要专业模型和通用模型共同工作的环境中表现出色。潜在的场景包括：

+   多阶段查询解决方案：在 IT 支持等领域，第一个模型可以根据用户的问题描述快速诊断问题，第二个模型可以提供更用户友好的详细逐步解决方案。

+   数据丰富的产品推荐：在电子商务中，第一个模型可以根据用户偏好识别和列出产品，而第二个模型可以将短列表与用户评论、评级或趋势数据进行交叉参考，以提供更全面的推荐。

+   法律咨询：最初，第一个模型可以根据用户的查询识别相关法律或先例，第二个模型可以用通俗的语言解释它们，确保理解。

+   财务规划：最初，第一个模型可以根据用户的财务状况提供财务概况或策略，第二个模型可以深入研究投资机会、风险和详细预算等具体内容。

+   教育内容创建：第一个模型可以根据课程大纲概述学习模块或教学计划，第二个模型可以开发详细的内容、活动和评估。

# D1 代理模式

在这一部分，我们深入探讨了利用 GPT 集成的专门代理模式，突出它们独特的架构特点和应用功能。重点是自动化、适应性和用户协作：

+   **批量自动化代理（D1）**：该代理首先对数据进行预处理，然后执行两步循环：处理每个增强的数据记录，并通过顺序指令引导 GPT 模型，其中一个指令的结果提供下一个指令的输入，直到序列完全处理。

+   编排代理（D2）：这种模式的核心是编排代理，它无缝地连接用户、GPT 模型、应用程序、数据库和知识库。编排可以通过工作流提示或程序实现。

+   **协作代理（D3）**：这种模式的关键是协作代理，它在动态的合作环境中使多个用户和 GPT 模型保持一致。通过协作存储库，每个 GPT 交互都受到不断发展的上下文的驱动，其中包括多个用户的提示和先前模型的输出。

+   **多代理协作（D4）**：在这种设计中，多个代理共同努力实现给定用户目标。规划代理将目标分解为任务，并相应地推导专家代理配置文件。然后编排代理根据这些配置文件创建和管理专家代理，而专家代理执行其指定的任务以实现用户的目标。

# D1 批量自动化代理

这种模式展示了一个以 GPT 为中心的系统，由批量自动化代理驱动。来自企业应用程序和数据库的数据记录通过知识库进行丰富。然后代理采用双循环机制：迭代每个丰富的记录，并引导 GPT 通过一系列提示。一个提示的结果影响下一个提示。后处理使输出准备好由用户界面显示（参见*图 4.10*）。

![](img/Figure-4.10.jpg)

**图 4.10：** 批量自动化代理

# 用户体验层

显示批处理输出的结果，并通过聊天机器人或 Web 用户界面促进用户交互。

# 应用层

该层由预处理器、企业应用程序和数据库、批量自动化代理和后处理器组成：

+   企业应用程序和数据库：企业应用程序和数据库是原始数据记录的主要来源。

+   预处理器：预处理器执行与对话模式相同的步骤，但这次是针对整个数据记录批处理。

+   批量自动化代理：该代理采用双循环机制：外部循环处理批处理中的每个数据记录，内部循环迭代地将与当前记录相关的一系列丰富提示输入到 GPT 模型中。

+   后处理器：一旦批量自动化代理生成了批量响应，后处理器会将其格式化为用户体验层的显示。

# AI 层

AI 层具有与**扎根对话**模式（A2）相同的功能。

# 模式工作流程

1.  企业应用和数据库提供批量数据记录。

1.  预处理器利用知识库创建丰富的数据记录。

1.  批量自动化代理采用其双循环机制：对于批处理中的每个丰富记录（外部循环），它会处理一系列提示（内部循环）到一个 GPT 模型。

1.  后处理器为最佳显示组织批量输出。

1.  用户体验层可视化格式化输出。

# 模式工作流程示例

想象一家租车公司，希望处理他们每天收到的大量关于汽车租赁和服务的客户评论。目标是对这些评论进行分类，并以分类、总结、用户友好的格式呈现给他们的分店经理。

这里有一个示例工作流程：

1.  源数据收集：公司的租车管理系统和反馈门户作为企业应用和数据库，收集当天的客户评论，汇总成几百条反馈条目的批量。

1.  数据丰富：预处理器接受每个评论并使用内部知识库添加上下文。例如，一条评论说，“汽车的空调坏了”可能会被丰富为：“顾客发现从[具体分店]租来的[汽车型号]的空调有问题。”

1.  双循环数据处理：

+   外部循环：批量自动化代理开始处理每个丰富的评论。

+   内部循环：

+   第一个提示：“根据评论‘[丰富的评论]’，确定其情绪（积极的、中立的、消极的）和主要关注类别（例如，车辆状况、客户服务、定价、预订流程）。”

+   第二个提示：“根据识别的情绪和类别，创建一个适合分店经理审阅的简洁摘要。”

+   （注意：根据系统设计，可以添加进一步提示以提取更细致的信息。）

1.  数据格式化：一旦 GPT 模型处理了所有评论，后处理器会对批量摘要进行结构化。评论按分店、车型和关注类别分组。数据准备好进行最佳可视化，可能通过生成展示经常问题的图表或通过积极反馈排名分店的排行榜来展示。

1.  可视化和用户交互：用户体验层在交互式仪表板上显示这些结构化摘要。分店经理可以深入特定的反馈类别，查看个别评论，或通过集成的聊天机器人提出更详细的问题。

# 企业集成

相当于**扎根对话**模式（A2）的集成级别。

# 输出质量

批量自动化代理的双循环机制在保持连续性和上下文的同时，也带来了一个挑战：错误累积的风险。如果序列中的一个提示生成了不准确或次优的响应，随后的提示可能会基于这个错误，潜在地使不准确性叠加。这强调了确保每个单独提示的精度以维护响应的整体质量的重要性。

# 性能

虽然双循环的特性可能引入复杂性，但批量处理方法旨在提高效率。批量处理本质上具有延迟，直到整个批次完成，但结果是全面的，过程在没有用户参与的情况下自主运行。

# 使用案例

这种架构模式适用于需要高级批量知识驱动自动化的场景。在知识管理领域特别突出，为大量数据的快速处理、分类和表示提供了强大的解决方案。值得注意的应用包括：

+   信息提取：深入研究广泛的文件，挖掘相关的见解，这个功能在研究、法律或新闻等领域尤其有价值。

+   数据转换和质量管理：具有整合不同格式和结构的数据，发现冗余、不一致性的能力，使得可以使用标准分析工具。

+   过程分析：通过检查从不同事件日志中提取的模式，提供有助于完善工作流程的可操作见解。这对于依赖于复杂过程指标的行业特别有益。

+   高级数据挖掘：通过在非结构化数据上使用关联规则挖掘和聚类分析等方法，该架构能够解读传统分析可能忽略的模式和见解。

+   自动标记：通过增强搜索结果和加强推荐，这个功能简化了用户体验，根据内容的性质自动标记内容。

# D2 编排代理

这种架构的核心是编排的工作流程，旨在指导用户-GPT 从开始到结束的互动。编排代理是这个工作流程的核心，集成了用户、GPT 模型、应用程序、数据库和知识库（见*图 4.11*）。

![](img/Figure-4.11.jpg)

**图 4.11：**编排代理

# 用户体验层

这一层是多个用户与系统连接的地方。他们可能使用聊天机器人或 Web 界面。他们提出请求，查看他们的任务，并从 GPT 模型获得回应。

# 应用层

分为三个主要组件，这一层协调任务和互动的流程：

+   编排代理：这个关键组件存在两种变体：

+   基于程序的代理：用于使用适当的编程语言（如 Python 或 Java）编写的静态工作流程，以控制顺序任务执行。

+   基于提示的代理：适用于涉及规划、执行和适应的动态工作流程。它使用与外部工具集成的工作流提示，类似于 B1-B3 架构模式。

+   企业应用和数据库：这些是代理利用的特定企业工具和数据源。

+   信息检索工具：这包括公共工具，如搜索引擎或网站，系统利用这些工具来给后续提示提供上下文。

# AI 层

这一层包括：

+   两种潜在角色中的主 GPT 模型：

+   特定工作流任务的响应生成器（基于程序的编排）：在这种情况下，GPT 模型对脚本化工作流中定义的特定任务进行回应。

+   工作流引擎（基于提示的编排）：在这里，GPT 模型承担更广泛的角色，通过工作流提示管理任务的流程和执行。

+   知识库：该组件提供长期和短期记忆功能，因此超越了它在以前模式中扮演的静态存储库角色：

+   长期记忆：这部分存储各种知识，根据信息的来源和性质进行分类。

+   学习知识：这包括从以前的互动中生成的见解和信息，GPT 模型做出了回应。它形成了一个不断丰富的知识体系，通过监控和分析 GPT 模型过去回应的结果，以促进对时间的更细致理解和改进性能。

+   检索到的知识：这部分存储了在先前操作中从外部资源获取的数据和信息，例如在先前用户互动中搜索的结果。它有助于保留有价值的发现以供将来参考，避免对相同查询进行重复搜索操作，并确保一致的响应。

+   获取的知识：这部分记忆中存放着经常由专业主题专家（SMEs）策划和验证的知识。它代表了随着时间的推移形成的结构化和可靠的信息库，为 GPT 模型的响应提供了坚实的基础，确保输出与企业标准和专家验证相一致。

+   短期记忆：这部分旨在保留与用户、GPT 模型、企业应用程序或搜索工具的中间交互结果，暂时保存数据以便通过回忆最近的交互和计算来促进连贯和适应性的互动。这种记忆是短暂的，在会话结束或预定义的时间后会被清除，以保持数据的相关性和安全性。

+   GPT-Critic：一个辅助 GPT 模型，负责评估主要 GPT 模型的输出的有效性和质量。

# 基于程序的编排代理的模式工作流

1.  用户请求：用户描述他们的预期结果。

1.  工作流选择：根据用户请求选择标准工作流程。例如：

+   具有生成任务的一步搜索

+   语义搜索：从知识库中提取相关知识。

+   生成任务：使用 GPT 模型进行内容创建、摘要或回答查询。

+   具有生成任务的两步搜索：

+   查询制定：在需要特定数据时使用 GPT 模型生成 API 调用或搜索查询。

+   信息检索：从外部来源获取必要的数据。

+   知识表示：将这些数据纳入知识库。

+   语义搜索：从知识库中提取相关知识。

+   生成任务：使用 GPT 模型进行内容创建、摘要或回答查询。

+   一步后端功能执行（类似于 B1 模式）

+   从用户收集信息（可选）：根据需要从用户那里收集补充数据。

+   后端功能调用生成：创建可执行的应用级功能或调用。

+   后端功能调用执行：执行先前生成的应用程序功能调用。

+   后端功能结果翻译：将系统级功能的结果转换为用户友好的输出或格式。

+   多步后端功能执行

+   对每个后端系统重复上一个工作流程的三个步骤：依次执行多个后端进程的功能生成、执行和结果转换步骤。

+   后端功能调用之间可能的用户交互：在各个阶段与用户互动，收集更多信息或完善后续步骤。

+   交互式内容创建

+   从用户收集信息：从用户那里收集内容创建过程所需的数据。

+   基于收集的信息创建内容：根据用户提供的数据开发定制内容。

1.  工作流执行：开始并监督在前一个“工作流选择”步骤中选择的完整步骤序列。

1.  输出评估：利用 GPT-Critic 检查输出的准确性和相关性，确保其符合已建立的标准或用户请求。

1.  结果呈现：以易于理解和用户友好的方式向用户显示工作流的结果。

# 基于程序的编排的工作流示例

想象一个为企业设计的数字平台，用于定位和采购稀有、环保或具有其他独特属性的专业原材料。

一家制造公司正在寻找一种可持续的橡胶，既耐用又对环境影响最小，用于新的系列环保鞋类产品。

以下是一个匹配模式工作流程结构的示例工作流程：

1.  用户请求：制造商的采购经理登录数字平台并指定他们的需求：可持续、耐用的橡胶，最好具有公平贸易或雨林联盟等认证。

1.  工作流程选择：

+   考虑经理的具体要求，系统选择了具有生成任务工作流程的两步搜索。

+   查询制定：使用经理的输入，系统制定针对性的搜索查询，如“具有认证的可持续耐用橡胶供应商”。

+   信息检索：系统利用网络爬虫浏览行业数据库、供应商目录、论坛和相关的可持续发展网站，以确定潜在供应商。

+   知识表示：提取的信息，如供应商档案、他们的认证、客户评价和材料规格，被结构化以便更容易分析。

+   语义搜索：系统评估组织好的数据，优先考虑与制造商标准密切符合的供应商。

+   生成任务：如果没有找到理想的供应商，系统将使用 GPT 模型起草询问或 RFP（提案请求）发送给有前途的供应商或行业联系人。

1.  工作流程执行：

+   基于程序的代理管理操作顺序，确保从网络中获取相关和准确的供应商信息。

1.  输出评估：

+   GPT 评论员审查供应商的入围名单和 RFP，以确认它们符合制造商的规格。

+   如果发现不一致，可能会启动“信息检索”步骤的新迭代，或者修订搜索标准。

1.  结果呈现：

+   买方收到了一份精心筛选的潜在供应商名单，包括所有相关细节，如认证、过往客户评价和联系信息。

+   生成的 RFP 可用，准备好发送给潜在供应商以获得更详细的提案。

+   买方可以选择直接与供应商联系，请求样品，或者发送 RFP 以进行竞争性投标。

# 具有基于提示的编排代理的模式工作流程

1.  用户请求：用户描述他们的预期结果。

1.  工作流程提示模式选择：根据用户请求选择工作流程提示模式。相应模式的示例在[第六章](c06.xhtml)的“自适应业务流程管理”部分中给出。

1.  工作流程提示执行：通过使用 GPT 模型作为工作流引擎执行工作流程。当工作流程需要时，它会生成对 API 函数调用的请求（如 B1 模式中）和用户输入（如 A3 模式中）。编排代理将处理这些请求，并将结果反馀 GPT 模型以继续工作流程。工作流程在达到特定停止条件或用户停止时终止。

1.  输出评估：GPT 评论员检查工作流程的输出，以确保符合规定的标准。

1.  结果呈现：一旦工作流程完成，结果以易于解释的格式展示给用户。

# 具有基于提示的编排的工作流程示例

想象一个电子商务巨头，一个客户最近购买的智能手表屏幕损坏了：

1.  用户请求：客户访问投诉部分并提到：“我收到了我的智能手表订单，但屏幕破裂了。我想要更换或退款。订单号：567890。”

1.  工作流程提示选择：根据投诉的性质，系统选择自适应投诉管理工作流的提示：

+   提示名称：自适应投诉管理工作流程

+   专家角色：“作为一名接受过电子商务自适应投诉管理培训的人工智能，您可以通过确定和执行适当的工作流来自主管理投诉解决。与用户的互动仅用于捕获必要的细节。”

+   背景：“您正在协助一家每天收到大量投诉的电子商务巨头。当前的投诉是：[捕获的投诉槽]。投诉解决步骤包括：

1.  投诉澄清：通过与用户互动了解投诉的具体情况。

1.  工作流设计：自主规划任务以解决投诉。

1.  工作流启动和执行：开始并完成投诉任务，要求用户提供所需的详细信息。

1.  工作流监控：确保解决进展顺利并收集用户反馈。

1.  工作流适应：根据意外情况或偏差修改任务。”

+   目标：有效地引导每个投诉解决阶段，利用沟通、规划和建议等技能。

+   控制和约束：始终尊重隐私，寻求必要的用户输入，澄清决策，并确保输出是可操作的，并遵循最佳实践。

+   指示：从“投诉澄清”开始：请分享有关投诉的更多信息[捕获的投诉槽]，以进行有效的解决过程。

1.  工作流执行：

1.  投诉澄清：系统询问：“您能否提供有关损坏的更多具体信息？包装在送达时是否完好？”用户回答：“包装看起来没问题，但里面的手表损坏了。看起来是质量控制问题。”

1.  工作流设计：根据用户的反馈，系统选择产品更换和质量保证工作流。

+   验证订单。

+   确认保修。

+   发起退货和更换流程。

+   确保更换产品的质量检查。

1.  工作流启动和执行：执行四个工作流步骤：

1.  工作流监控：随着更换产品的发货，用户将收到关于进展的通知。

1.  工作流适应：如果出现延迟或问题，系统将调整工作流，通知用户并提供解决方案。

1.  输出评估：GPT-Critic 评估整个解决过程，确保投诉得到有效解决，并且所有工作流步骤都得到遵守。

1.  结果呈现：客户将得到采取的行动时间表、更换货物的跟踪号码以及在收到货物后提供反馈的界面。他们还将获得一个折扣码，以补偿不便，鼓励未来的购买。

# 企业集成

这种模式由于编排代理的能力可以在整个工作流中嵌入基于 API 的功能，因此提供了先进的企业集成。

# 输出质量

这种模式通过系统地将提示与上下文用户输入、知识、内部和外部数据以及先前的 GPT 输出相结合，系统地提高了输出质量。多个用户的潜在参与提供了一个额外的人类判断层，进一步完善了人工智能的上下文感知输出。GPT-Critic 评估人工智能生成内容的质量，其反馈由编排代理管理，以优化输出质量。

# 性能

这种模式的计算性能与工作流的长度密切相关。然而，对于大多数使用案例来说，长度较短到中等长度的工作流应该足够，平衡了效率和计算需求。

# 使用案例

这种模式的动态能力和健壮的设计使其非常适用于各种应用。在其核心，它旨在管理两种主要类型的工作流：静态（脚本化）和动态（自适应）。

静态工作流是日常运营的基础，其结构明确定义，流程可预测。这类工作流通常是自动化的，并遵循预设脚本：

+   复杂内容创建：

+   报告：将数据点综合成全面的报告，包括图表等可视化呈现。

+   新闻简报：定期整理更新或相关新闻的内容，保持一致的布局。

+   文档：为各种需求生成结构化文档，确保目标受众的清晰度。

+   信息收集：

+   采访：利用模板和协议系统地从个人或团体中提取信息。

+   交互式报告：从企业特定系统或数据库中获取并呈现交互格式的数据，确保数据的完整性和准确性。

+   网站：自动搜索、阅读和总结相关网站内容。

+   标准工作流程：

+   申请：处理和自动化标准申请流程，从请求到批准。

+   批准周期：简化批准请求、提醒和文档工作。

+   库存管理：自动化与库存盘点、重新订货水平和库存估值相关的任务。

虽然这种模式轻松地管理可预测的操作，但它也展示了它在接纳更加复杂和适应性挑战方面的熟练。具有不完整规范、需要即时调整或由不断发展的用户意图和意外情况所决定的任务属于这个领域。这样的动态工作流程需要计划、执行、重新评估和适应的结合：

+   任务导向对话：适应不断发展的用户意图，这些代理设计、修改和部署对话计划，产生多方面的互动。

+   全面研究：将广泛的研究目标分割为子目标，并使用多种资源对每个子目标进行概念化和执行详细的策略。

+   探索性数据分析：代理根据洞察目标制定探索性策略，通过多种数据来源和工具进行迭代。

+   自动故障排除：在理解用户问题后，系统制定诊断计划，可能包括查询特定企业工具，提供引导解决方案，或利用 GPT 进行创新疗法。

+   个性化学习路径：根据学生的抱负定制教育轨迹，精心选择、排序和校准内容，根据他们的进展和反馈。

# D3 协作代理

这种模式的本质围绕着协作代理，作为连接用户与 GPT 模型的动态通道，在自适应协作空间内。通过利用协作存储库，这种设计确保了 GPT 的参与是基于上下文的，并且可以被归档，重新访问或完善（见*图 4.12*）。

![](img/Figure-4.12.jpg)

**图 4.12：** 协作代理

# 用户体验层

通过聊天机器人或 Web UI，用户可以积极参与任何活跃的协作，贡献意见，并根据不断发展的内容共同确定轨迹和结果。

# 应用层

它包括以下内容：

+   企业应用和数据库：这些是在协作过程中使用的工具和数据来源。

+   协作代理：该代理与协作存储库交互，以检索或归档主要提示⁸，协作历史，摘要和结果。

+   协作存储库：关键的存储空间，保存主要提示，深入的协作历史，简洁的协作摘要，以及中间和最终结果。

# AI 层

这一层包括：

+   GPT 作为响应生成器：负责提供与上下文相关的响应。

+   知识库：与之前的 D2 模式一样，具有短期和长期记忆。

+   GPT-Critic：第二个 GPT 模型，确保第一个 GPT 模型的输出符合期望的质量标准。

# 模式工作流程

1.  用户选择启动或参与一个持续的合作。

1.  如果开始一个新的合作，合作代理会从合作存储库中获取与所选场景相对应的主提示。

1.  对于持续的合作，最近的合作历史为舞台。

1.  用户不断添加提示。在每个用户输入之后，合作代理都会将用户的提示和 GPT 的输出结果附加到活动合作历史中。

1.  GPT-Critic 监督并确保 GPT 的回应质量。

1.  在结束合作时，其摘要和结果将存档在合作存储库中。

# 模式工作流示例

想象一家希望改进其车辆维护策略的汽车租赁公司。通过与多个利益相关者（技术人员、车队经理、客户服务代表，甚至客户）合作，他们旨在在使用合作代理进行持续讨论中收集见解、经验和建议。

你的任务是：主持一个关于改进车辆维护流程的合作讨论，考虑到不同的观点、历史讨论和建议。

这是一个与模式工作流匹配的示例工作流：

1.  启动：车队经理决定开始一个名为“改进我们的车辆维护策略”的合作讨论。

1.  合作启动：

+   合作代理从合作存储库中检索有关汽车维护的通用主提示。

+   提示可能会是：“讨论我们公司汽车维护的最佳实践、挑战和改进。”

1.  持续合作参与：

+   当技术人员、客户服务代表和其他利益相关者加入时，他们可以查看正在进行的讨论并做出贡献。

+   例如，一个技术人员可能会添加：“例行检查通常只是肤浅的。我们需要更深入的诊断。”

+   立即，一个从知识库中获取信息的 GPT 模型可能会建议：“考虑实施详细的每两个月一次的诊断和例行检查。这可以发现潜在问题。”

+   合作代理将每个提示和回应附加到活动合作历史中。

1.  用户贡献：

+   一个客户服务代表可能会插话：“客户经常报告夏季空调问题。也许我们可以在旺季之前进行预防性检查？”

+   一个 GPT 模型可能会回应：“夏季前的年度空调服务有助于。此外，考虑在初始租车时教育客户如何最佳使用空调。”

1.  GPT-Critic 对质量进行监督：

+   假设客户提出：“我曾经租过一辆在半路抛锚的车。紧急情况下的策略是什么？”

+   如果 GPT 模型最初提供了一个模糊的答案，比如“汽车应该保养”，GPT-Critic 可能会标记这个答案质量低，促使模型产生更全面的回应。

1.  合作结束和存档：

+   一个星期后，车队经理决定结束讨论。

+   合作代理会自动生成一个摘要：“讨论改进我们的车辆维护策略的要点。”

+   它包括实施每两个月一次的诊断、夏季前的年度空调服务，以及可能针对紧急故障的策略。

+   这个摘要和整个讨论都被存档在合作存储库中以供将来参考。

# 企业集成

这个模式提供了与**基础对话**模式（A2）相同水平的企业集成。

# 输出质量

通过合作存储库的帮助，GPT 模型在一个丰富的背景下运作，这个背景包括来自多个具有不同观点的用户和相应 GPT 输出的输入。GPT-Critic 的角色也有助于通过检查和验证来提高输出的质量。

# 性能

这种模式的效率取决于协作内容的深度和广度。然而，通过协作代理处理任务，利用协作存储库，确保流畅的进展，并且仅在接收到新的协作输入后使用计算资源。

# 使用案例

理想情况下，这种模式适用于跨不同背景的复杂协作努力，主要应用包括：

+   顺序人本工作流程：在产品开发中，这涉及协调团队从构思到生产。协作代理根据先前的输入确保每个阶段的一致性。

+   项目：在活动规划中，代理帮助建立时间表，分配任务，并收集后勤输入。它根据持续更新提出改进建议。

+   销售参与：对于市场进入战略，代理整合市场研究、竞争对手分析和客户画像。

+   供应商评估：在寻找供应商时，代理存储供应商档案和过去的互动。评估者的标准，如成本或交付时间表，将与存储的数据进行匹配，以做出明智的决策。

+   创新框架：在技术创新中，利益相关者在平台上进行头脑风暴。代理提供情境反馈，从过去的会话或外部趋势中获取，协助制定一致和创造性的策略。

# D4 多代理合作

这种模式的本质根植于分布式智能的概念。通过将任务分散在一组专门的代理人之间 5]，这种模式创造了一种更流畅和适应性更强的方式来满足复杂的用户目标。这个动态的代理人合奏团共同利用各种 GPT 模型，确保每个任务都由最合适的专家来处理（见*[图 4.13*）。

![](img/Figure-4.13.jpg)

**图 4.13：** 多代理合作

# 用户体验层

与之前两种模式相似，这一层提供了各种互动可能性。通过聊天机器人界面或 Web 用户界面，用户可以表达复杂的目标，然后由一组合作的代理人来完成，并可能需要与多个用户进一步互动。

# 应用层

这里包括的组件有：

+   代理团队：一群专门的代理人，负责执行不同的角色，以实现用户目标。团队由以下成员组成：

+   规划代理：将用户指定的目标分解为可行动的任务，并确定适合每个任务的理想专家代理配置文件。

+   编排代理：根据代理配置文件启动专家代理创建过程，启动任务序列，激活第一个专家代理，并逐步完成任务。该代理还监督专家代理之间的通信，确保与用户、知识库和其他企业工具的无缝互动。

+   专家代理：动态创建，这些代理具备执行特定任务所需的精确技能，以实现整体用户目标。

+   企业应用和数据库：这与 D2 模式中的情况相同。

+   信息检索工具：这与 D2 模式中的情况相同。

与 D2 模式类似，值得注意的是在这种架构中有两种不同类型的代理团队。虽然图表中展示了基于程序的代理团队，但还存在另一种构造 - 基于提示的代理团队。基于提示的代理团队的复杂性和应用将在《第五章，高级 GPT 提示工程技术》和专门讨论多代理提示的附录 1 中进行探讨。

# AI 层

以下元素对这一层至关重要：

+   知识库：类似于 D2，存储着瞬时和持久的信息。

+   在不同角色中实例化的 GPT 模型：

+   GPT 作为规划者：与规划代理对齐，将用户目标转化为一系列任务。

+   GPT 作为指挥者：驱动着编排代理，管理专家代理之间任务的排序和委派。

+   GPT 作为专家：为每个专家代理提供领域特定的知识和专业知识，以执行其指定的任务。

# 模式工作流

1.  用户表达了他们希望实现的详细目标。

1.  规划代理处理这个目标，将其转化为一系列可执行任务，并为每个任务确定理想的专家代理配置文件。

1.  对于每个任务，编排代理创建相应的专家代理。

1.  任务排序完成后，编排代理激活第一个专家代理并委派相应的任务。

1.  专家代理执行分配给它的任务。

1.  任务完成后，编排代理移动到下一个任务，激活下一个排队的专家代理。

1.  这个顺序会被认真遵循，直到所有任务得到解决。

1.  在整个过程中，编排代理确保专家代理之间以及它们与其他涉及实体（如用户、知识库或数据库）之间的顺畅沟通。

# 企业集成

这种模式提供了与 D2 模式中一样的高级企业集成，因为所有代理都可以通过 API 访问功能来执行他们的任务。

# 输出质量

当最终专家代理评估所有先前专家代理的性能时，D4 的输出质量与 D2 的输出质量非常相似。虽然通过为每个涉及的代理（包括规划、编排和专家代理）实施质量评估有潜力提高输出质量，但必须注意，这种增强可能会以性能下降为代价。

# 性能

性能受到参与的代理数量以及他们之间和用户和企业应用程序之间的互动程度的显着影响。随着代理数量的增加，或者互动变得更频繁和复杂，系统的响应速度和效率可能会相应受到影响。

# 使用案例

在 D2 模式的基础能力上构建，并通过多代理合作的复杂性加以增强，这种 D4 模式能够熟练处理各种应用，如以下使用案例所示：

+   全面的研究：

+   规划代理：理解总体研究目标，并将其分成有针对性的研究领域或问题。

+   编排代理：在专家代理之间协调，为它们分配特定的研究领域或任务，并确保无缝整合它们的发现。

+   专家代理：深入其分配的领域，挖掘数据，参考学术文章，并交叉参考研究结果。每个代理可能专门研究各种研究方法或来源。

+   探索性数据分析：

+   规划代理：根据期望的见解和结果定义数据探索的目标。

+   编排代理：组织数据流，确保它以有序的方式在专家代理之间移动并整合他们的分析。

+   专家代理：每个代理可以专注于特定的数据集或分析技术。例如，一个代理可能处理统计分析，而另一个专注于可视化或预测建模。

+   自动故障排除：

+   规划代理：识别报告的问题并定义诊断步骤。

+   编排代理：管理故障排除过程，确保每个步骤都被执行，收集所需数据，并提供反馈。

+   专家代理：专门处理问题的不同方面。一个可能处理与软件相关的问题，另一个可能是硬件诊断，另一个可能专注于用户体验或界面问题。

+   个性化学习路径：

+   规划代理：评估学习者当前的知识水平、偏好和长期教育目标。

+   编排代理：组织课程表，安排课程，并确保内容流与学习者的进展相一致。

+   专家代理：专注于不同学科或学习方法。例如，一个人可以处理数学，而另一个人处理文学。其他人可能专注于经验性学习、多媒体内容或实践项目。

+   软件开发协助：

+   规划代理：解释需求并将其分解为特性或任务。

+   编排代理：管理依赖关系和工作流程。

+   专家代理：建议代码片段，运行测试，调试问题，甚至帮助部署策略。

+   咨询任务：

+   规划代理：确定客户需求并将其分解为可操作的见解或任务。

+   编排代理：安排会议，管理时间表，并确保交付物得到满足。

+   专家代理：深入具体细节，无论是市场研究、财务建模还是战略规划，利用最佳工具和资源完成每项任务。

# 架构模式建议

通过深入研究各种 GPT 驱动的架构模式的细微差别和复杂性，我们准备提出一系列精心策划的建议。这些见解来自全面的描述和评估，旨在指导您选择最适合您特定需求的架构：

+   **高级对话体验**：**基于实际情况的对话**（A2）与企业系统集成，增加了上下文深度。**混合主动对话**（A3）促进双向互动，引导用户行动和查询，而**质量控制对话**（A4）确保所有回应在显示给用户之前都经过第二个 GPT 模型的检查。

+   **工具驱动对话**：**集成工具对话**（B1）利用 GPT 模型通过 API 与外部应用程序和数据库无缝交互。**基于思维链引导的工具对话**（B2）通过推理演示丰富了这一点。与此同时，**高级工具集成对话**（B3）利用基于对话上下文的动态任务规划优化与企业工具的交互。

+   **专业对话**：**使用精细调校模型的对话**（C1）采用精细调校的语言模型生成精确的回应，非常适合复杂领域和高风险环境。与此同时，**使用两个模型的对话**（C2）结合了精细调校模型的特定性和预训练的 GPT 模型的广度，确保深入用户互动嵌入到多样的对话场景中。

+   **高级自动化**：对于复杂的自动化需求，模式**批量自动化代理**（D1）、**编排代理**（D2）和**多代理协作**（D4）脱颖而出。D1 强调批量数据处理，而 D2 利用顺序编排实现无缝互动。D4 特别适用于需要高度动态适应性和任务特定专业知识的环境。

+   **协助协作**：对于深度协作环境，模式**协作代理**（D3）和**多代理协作**（D4）表现突出。D3 在强调持续以人为中心互动的情况下表现出色，GPT 管理和增强整个协作过程。另一方面，D4 强调人类和任务特定代理共同工作的情景，结合各自的优势以获得最佳结果。

我们对 GPT 驱动的架构模式的探索揭示了多种解决方案，每种都有其固有的优点。您的组织或项目的正确选择取决于您的具体需求和限制。将此分析作为参考，指导您选择最符合您目标的架构模式。

# 结论

当我们在 GPT 驱动的架构模式的多样景观中航行时，这些系统可以如何在改善用户互动、增强协作场景和推进自动化流程方面发挥重要作用变得明显。通过提供多样化的模式谱，每个模式都针对特定的用例和需求定制，我们可以释放 AI 能力的全部潜力，开发未来高效、适应性强、协作性强且提供丰富用户体验的对话系统和工作流程。

既然我们已经确定了 GPT 在各种架构模式中的多功能性和适应性，现在是时候深入了解高级 GPT 提示工程技术的世界了。这些技术将深入了解如何引导 GPT 模型实现期望的结果，特别是在复杂的企业场景中。让我们现在将焦点转向这些结构化提示方法，以进一步释放 GPT 在高级 AI 应用中的广泛潜力。

# 关键点

1.  GPT 驱动架构的多功能性：架构模式是多功能的，可以将 GPT 模型部署到各种对话上下文、工具集成和自动化场景中，证明了它们在增强用户参与和简化信息检索方面的重要性。

1.  分层系统方法：在架构模式中使用分层系统方法确保解耦和可维护性，从而导致更可持续的系统生命周期。

1.  质量和性能的权衡：每种模式都提供了独特的输出质量、性能和企业集成的混合，提供了一系列选择，以满足不同的需求和用例。

1.  企业集成：与企业应用程序和数据库的无缝集成，如工具集成对话和其他模式中所见，可以显著扩展 GPT 驱动系统的能力。

1.  响应的精确性和广度：在特定知识与更广泛理解之间取得平衡，一些架构展示了模型微调在提供准确和全面响应方面的重要性。

1.  高级自动化：GPT 集成架构还展示了在各种自动化场景中的多功能性：内容的批处理、信息工作流编排以及使用多代理系统执行项目。

1.  协作卓越：GPT 模型可以用于促进协作环境中的自适应互动，实现人类中心互动和多代理合作的独特融合，共同实现复杂目标。

____________________

¹ 代理是一种设计用于执行特定任务的软件组件，通常是自主地与其他代理、系统或用户进行交互。

² 提示模板主要是预填的提示模式，用于控制 GPT 模型，并在*[第五章，高级 GPT 提示工程技术](c05.xhtml)*中介绍。模板可以基于规则、机器学习模型或通过选择提示向 GPT 模型选择。

³ 文档数据库，也称为文档导向数据库或文档存储，是一种设计用于存储、检索和管理半结构化信息的非关系型数据库，例如带有元数据的文本，通常以 JSON（JavaScript 对象表示）或 XML（可扩展标记语言）等标准格式存储。

⁴ 图数据库，通常称为图导向数据库或图引擎，也是一种非关系型数据库，用于捕获、处理和管理以网络模型化的数据，强调节点、边和属性，从而能够映射、访问和分析复杂的相互连接和依赖关系。

⁵ 向量数据库是一种专门优化用于存储和查询高维向量数据的数据库系统，通常表示文档、查询或兴趣配置文件，常用于 AI 应用程序中的任务，如相似性搜索或推荐。

⁶ 在 GPT 模型（如 ChatGPT）的背景下，“思维链（CoT）”指的是模型在一系列句子或交流中保持连贯推理的能力。CoT 演示就是这样一种推理链的示例。

⁷ 这种架构模式的实现在[第九章](c09.xhtml)中以 Java 编程语言为例进行了说明。

⁸ 主提示定义了给定协作场景的协作手册。主提示在*[第六章，设计基于提示的智能助手](c06.xhtml)*中有详细介绍。
