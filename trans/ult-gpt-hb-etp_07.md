# 第八章：LangChain：Python 的 GPT 实现框架

# 介绍

本章讨论了在 Python 中使用 ChatGPT 的*gpt-3.5-turbo*等大型语言模型（LLMs），并介绍了一种名为 LangChain [12]的开创性框架。LangChain 通过其专门设计的组件，为与 LLMs 合作而量身定制，允许实现 CapabilityGPT 框架中的所有 18 种能力。它通过允许将预先学习的模型知识与实时信息相结合，提高了与大型语言模型合作的可靠性。借助 LangChain，LLMs 可以与数据库、API、云平台和其他基于 API 的资源等各种实体进行交互，从而实现特定目标。因此，LangChain 简化和流畅了开发全面应用的过程。

本章对构成该框架的不同组件进行了解释。这些组件包括模式、模型、数据处理、链、内存处理和代理。通过探索这些组件中的每一个，读者将全面了解 LangChain 作为一个整体的功能。为了进一步增进他们的理解，我们还将通过三个示例用例提供这些组件如何被利用的实际演示。这些演示将包括 Python 代码片段和每个步骤的详细解释。

第一个用例探讨了 LangChain 如何使法律专家受益，并通过利用 GPT 模型系列中 LLM 的创建和转换能力来增强他们的生产力和成功。我们将提供一个实际的例子，演示语义搜索在帮助律师找到相关先前案例方面的应用。这使他们能够有效地为即将到来的审判做准备，最终提高他们在法庭上的表现。

在第二个用例中，我们探讨了 LangChain 如何实现从各种文本数据源无缝检索数据。具体来说，我们提供了一种解决方案，允许自动化专家参与有关控制器的聊天对话。简单解释一下，控制器本质上是一种管理过程以实现和维持期望参数的设备。例如，在温度控制系统中，恒温器通过监测当前温度并调整加热或冷却设备以保持设定温度来充当控制器。

该解决方案利用了 CapabilityGPT 框架中描述的基本能力，如问答、沟通和摘要。这次对话所需的信息以 PDF 格式提供，其中包括控制器手册。LangChain 简化了浏览和利用这些信息的过程。

我们提出的最后一个例子集中在实时价格检查，这可以通过使企业及时了解并保持竞争力而极大地使其受益。本章深入探讨了 LangChain 代理如何结合 LLM 的推理能力和工具的执行能力，并提供准确和最新的价格信息。在这个例子中，代理将利用各种 GPT 功能，如规划、评估、问答、摘要和沟通。这使企业能够做出符合当前市场条件的明智决策，最终提高其竞争力和成功。

通过本章的学习，读者将全面了解 LangChain 的工作原理及其潜在应用。这些知识将为进一步的自学打下基础，读者可以深入研究技术方面并探索更高级的用例。无论您是希望优化业务运营的商业领袖，对最新人工智能技术感兴趣的 IT 专业人士，还是渴望探索可能性的人工智能爱好者，本章都将为您提供导航 LangChain 世界所需的知识。

# 结构

在本章中，将涵盖以下主题：

+   介绍 LangChain

+   LangChain 的组成部分：

+   模式

+   模型

+   数据处理

+   链

+   内存处理

+   代理

+   示例 1：律师的准备助手

+   示例 2：通过控制器手册进行聊天

+   示例 3：使用代理进行当前价格检查

# 介绍 LangChain：释放大型语言模型的潜力

LLM 的强大源自于它们在大量数据上的训练，除其他因素外。然而，重要的是要理解，LLM 通常不是最新的。这是因为它们是在特定数据集上训练的，这些数据集可能不包括最新信息。尽管经过大量数据的训练，LLM 在某些领域的专业知识上仍可能存在困难。

此外，由于其令牌限制（最大令牌限制决定了模型可以处理的输入范围和生成的输出范围），它们在处理大量文本时存在限制。在某些情况下，开发应用程序可能需要根据预算和要求使用不同的 LLM。这就是像 LangChain 这样的综合框架可以发挥作用的地方，因为它提供了适应各种需求和预算的解决方案。

LangChain 框架是一个基于 Python 的工具，可以实现充分利用大型语言模型的能力来创建应用程序。它提供了开发复杂应用程序所需的所有组件。

LangChain 不仅仅是语言模型的简单接口。它不仅允许我们利用不同的语言模型，还与各种实体进行交互，如数据库、API、云平台和其他基于 API 的资源。这些交互扩展了语言模型的能力，并实现了高级应用程序的创建。

LangChain 的主要支柱是组件、用例特定链和代理。

+   **组件**

在复杂应用中使用大型语言模型涉及使用特定概念。这些概念包括为提示创建模板，利用各种工具，访问数据源并处理数据，管理内存等。在 LangChain 中，这些概念被称为组件。组件是使使用这些功能更容易的类或函数。它们已经构建好，准备供开发人员使用。这些组件旨在易于实现，无论您是将 LangChain 用于整个项目还是仅用于其中的某些部分。

+   **用例特定链**

链以结构化的方式实现了上述组件的无缝集成。它们特别设计用于在特定场景中最大化性能。将组件链接在一起的概念既简单又有影响力。它极大地简化了复杂应用程序的实现，从而提高了调试、维护和应用程序整体增强的便利性。

+   **代理**

该框架旨在能够以代理方式工作。在日常生活中，代理是帮助实现特定目标的人或事物。在 LangChain 中，代理可以被视为将任务分解为较小步骤的 LLM。然后，它使用各种工具和其他 LLM 来实现任务的主要目标。

为开发人员设置应用程序可能是一个复杂和耗时的任务。然而，通过使用组件、链和代理，这个过程变得更加简单和快速。通过利用这些工具，开发人员能够节省宝贵的时间和精力，从而更多地专注于应用程序的实际开发和定制。这将提高生产率并加快上市时间。

# LangChain 的组件

要有效地利用 LangChain，熟悉其主要元素至关重要。本节旨在全面介绍这些组件，为理解 LangChain 的工作提供坚实的基础。

# 模式

让我们讨论在使用 LangChain 时会遇到的基本数据类型。这些包括文本、聊天消息、示例和文档。在语言模型的世界中，文本是主要的交流方式。LangChain 作为 LLMs 和各种实体之间的桥梁，专门设计为优先考虑基于文本的界面。

随着聊天界面的流行，某些模型提供商开始提供专门的 API，期望聊天消息而不是纯文本。聊天消息数据类型由两部分组成——内容字段，通常是文本本身，以及与之关联的用户。目前，LangChain 支持系统、人类和 AI 等用户，引入了不同类型的聊天消息，即系统聊天消息（用于主提示）、人类聊天消息和 AI 聊天消息。这种格式目前适用于 GPT-3.5-turbo 和 GPT-4 系列的所有语言模型。

我们可能使用的另一种数据类型是示例。它是表示函数输入和预期输出的输入和输出对。示例经常被纳入提示中，以更好地引导 LLM 提供的答案。

最后，LangChain 利用文档。文档包括称为页面内容的非结构化数据，以及描述其属性的元数据。

# 模型 I/O

LangChain 的核心围绕着其模型展开，这些模型作为整个框架的基础。这些模型为互动提供了必要的元素和构建模块。在讨论与模型的工作时，我们将分为三个部分：模型、提示和输出解析器。

# 语言模型

LangChain 提供两种类型的模型：语言模型和聊天模型。语言模型接受原始输入并输出一个字符串，而聊天模型接受标记为系统、AI 和用户的聊天消息列表作为输入，并生成另一个标记为 AI 的聊天消息。系统角色通过提供高级指令和上下文来引导模型的行为，从而构建整个互动。AI 角色与用户互动，回答查询。最后，用户角色代表与模型互动的个体，给出指示并参与对话。语言模型和聊天模型都有自己的接口。

如果您的应用程序需要与语言模型和聊天模型一起工作，LangChain 开发了一个名为基础语言模型的解决方案。这个接口允许您无缝地集成模型。此外，如果您想为自己的 LLM 创建自定义包装器，或者使用 LangChain 不支持的包装器，也支持这个选项。

如果您想在生成响应时向用户显示响应，而不是等待整个答案生成并一次性发送，您可以使用特殊的流式类。但请注意，流式响应仅受到某些模型的支持。

# 提示

有效的结构化提示是释放 GPT 模型巨大潜力的关键。为了适应不同的用例，我们可以采用一系列提示模式，例如指令提示、指令序列提示、查询提示、请求提示、合作提示或其他在之前的*[第五章，高级提示工程技术](c05.xhtml)*中提到的特殊提示。

为了简化创建提示并有效管理它们的不同部分的过程，LangChain 引入了提示模板。这些模板作为一种结构化的方式来一致地生成提示。它们本质上是接受一组参数的字符串，然后由模型用于处理。目前，在 LangChain 中，这些字符串可以使用两种语法来组成：f-strings 和 Jinja。

如果您决定使用聊天模型，应该使用专门的聊天提示模板。这些模板针对聊天模型输入进行了优化，并与原始字符串不同，原始字符串直接传递给语言模型。在聊天消息中，每条消息都与一个角色相关联：系统、用户或 AI。此外，还有少量提示模板，允许在我们的提示中包含示例。如果默认提示模板不符合您的特定需求，您还可以创建自定义提示模板。例如，您可能希望创建一个具有针对您语言模型的动态指令的提示模板。在这种情况下，自定义提示模板提供了灵活性和定制选项。

# 输出解析器

无论我们是在处理语言模型还是聊天模型，它们都会生成文本作为输出。为了以所需格式组织或结构化这些输出，我们使用输出解析器。这些输出解析器使我们能够以各种格式获取输出，例如逗号分隔列表、日期时间、枚举或 JSON。

如果您希望输出多个自定义文本字段，可以利用结构化输出解析器。另一个选择是使用更强大的 Pydantic（JSON）解析器。但是，它需要具有足够容量的 LLM 来生成格式良好的 JSON。值得注意的是，在某些模型系列中，一些模型擅长生成 JSON，而其他模型可能表现不佳。例如，像*text-davinci-003*、*gpt-3.5-turbo*或*gpt-4*这样的模型可以一致地生成结构良好的 JSON，而*text-curie-001*在这方面的熟练程度显著降低。

此外，还有一个可用的自动修复解析器。如果初始结果不正确或包含错误，它会自动调用另一个解析器。

# 数据连接

使用独立的 LLM 的主要挑战之一是它们只能访问它们专门训练过的数据。为了克服这一限制并使它们能够使用最新信息，我们必须将它们连接到其他数据源。幸运的是，LangChain 提供了有效的组件，可以轻松地与各种数据源进行交互（详细探讨了用于访问企业特定数据源的 A2-A4 架构模式，请参阅*[第四章，由 GPT 模型启用的架构模式](c04.xhtml)*）。

# 数据加载器

与外部数据源一起工作的一个重要方面是使用数据加载器。这些加载器的重要任务是将不同类型的数据加载到称为文档的特定结构中。文档包含文本和与之相关的元数据。已经创建了几个加载器来处理各种数据源。这些加载器使得从文本文件、CSV 文件、JSON 文件、GitBooks、Azure Blob 容器、YouTube 转录等加载数据变得方便。使用这些加载器极大地简化了数据加载过程。

# 数据转换器

一旦成功将数据导入文档对象，您可以开始转换过程，以满足应用程序的需求。一种常见的转换类型是将文档分成称为块的较小部分，这些块与您选择的 LLM 的上下文窗口对齐。例如，如果您打算使用 4 个块作为上下文，并分配 2000 个标记用于上下文，您可能希望将您的文档分成每个 500 个标记的块。对于英文文本，1 个标记大约是 4 个字符或 0.75 个单词。

此外，您还可以选择自动提取与每个块相关的特征或元数据。然后可以利用这些提取的细节来执行各种任务，如分类或摘要。

# 文本嵌入模型

嵌入意味着将文本表示为矢量，这是在转换文档时我们可以考虑的另一种方法。LangChain 中这种方法的实现是简单而高效的。LangChain 提供了一个标准接口，可以与各种嵌入模型提供商一起使用。

需要注意的是，不同的嵌入提供商可能采用不同的嵌入查询和文档的技术。为了解决这个问题，LangChain 采用了类似的方法，并为嵌入每个方法提供了不同的方法。通过这样做，LangChain 确保了在与各种嵌入提供商合作时的兼容性和灵活性，使用户能够无缝地将他们喜欢的嵌入技术集成到他们的工作流程中。

# 矢量存储

在大量非结构化文本中搜索特定信息是 LangChain 的常见用例。为了解决这个任务，一个方法是首先将非结构化文本分解成文档类型的块。然后将这些文档转换为数字列表（矢量）并存储在一个称为矢量存储的特殊数据库中。

为了找到所需的信息，查询也被转换为矢量表示，并与矢量存储中的每个矢量进行比较。选择过程涉及识别与查询最相似的文档。相似性是利用余弦相似度或欧氏距离等度量来计算的。余弦相似度通过测量两个矢量之间的夹角的余弦来确定两个矢量之间的相似性，而欧氏距离则计算空间中两点之间的直线距离。

矢量存储作为一个数据库，可以存储文档的矢量表示和它们的元数据。LangChain 的特殊之处在于它与各种开源矢量存储的兼容性，以及它与不同付费矢量存储提供商的集成能力。

# 检索器

一旦我们的相似性搜索完成，我们可以利用检索器来检索与查询相关的文档。检索器功能使我们能够根据相似性搜索结果有效地检索相关文档。

# 链

前面提到的功能可以被视为提供便利的附加功能，但 LangChain 的真正优势在于其链。虽然单独使用语言模型适用于简单的应用程序，但在开发更复杂的应用程序时，使用多个 LLM 或 LLM 和其他组件的组合是必不可少的。LangChain 通过引入链来简化这个过程。

有各种类型的链。它们特别设计用于快速实现特定用例，这就是它们在复杂性上的差异所在。最基本的类型是 LLM 链，它由提示模板和语言模型组成。这个链的目的是将给定的输入值格式化为提示，使用准备好的提示执行 LLM，最后返回输出。

另一个常用的链是简单顺序链。在这种类型中，初始调用后会对同一个或不同的语言模型进行一系列调用。当一个调用的输出需要作为另一个调用的输入时，这是特别有用的（参见*[第四章，由 GPT 模型实现的架构模式](c04.xhtml)*中的 C2、D1 和 D2 模式）。

检索问答链是另一种流行的类型，它涉及接受一个问题，使用检索器检索相关文档，然后将这些文档作为上下文提供给 LLM 来回答问题。还有 SQL 数据库链，专门用于回答 SQL 数据库上的问题，以及摘要链，用于对多个文档进行摘要。

这只是一些例子，但还有许多其他可能性。此外，用户可以通过对 Chain 类进行子类化来创建自己定制的链。

# 内存

默认情况下，大型语言模型被设计为无状态的。这意味着每个接收到的查询都是独立处理的，不考虑先前的查询或对话。然而，在某些应用程序中，比如虚拟助手，有必要访问对话的上下文，以更好地理解用户的意图并提供与先前查询相关的响应。为了更好地理解这一点，让我们来探讨以下对话：

*用户: 大脑的估计计算能力是多少？*

*AI: 大脑的计算能力极其复杂，难以精确量化，但一些粗略估计表明它可能在 10^18 到 10^26 浮点运算每秒（FLOPS）的范围内。*

*用户: 为什么难以量化？*

*AI: “难以量化”的说法是用来描述情况的常见短语，其中…*

如果用户询问大脑的估计计算能力，AI 模型可能会根据现有知识提供一个一般性答案。然而，当用户跟进提问时，AI 可能会在没有访问先前交互的情况下难以理解引用。

示例中的问题与指代消解有关。指代消解涉及识别句子中指代同一事物的词语。在这种情况下，“it”和“computing power”就是这样的词语。语言模型的缺乏记忆和状态的无关性导致了无关的答案。为了解决这个问题，必须管理完整对话或至少部分对话的记忆是至关重要的。LangChain 提供了一些方法来协助解决这个问题。这些方法提供了一系列针对不同类型交互的选择。在传递数据时，考虑每次调用的令牌限制是很重要的，因为可能会有包含的信息量的限制。例如，如果预计交互会很简短，整个对话可以传递给下一个提示，或者如果预计交互会很长，可以使用摘要版本。所有这些方法使模型能够根据上下文理解并回应对话，从而提高其能力。

# 代理

有时，为了为用户服务，我们需要根据不可预测的输入来确定行动。这就是代理变得有用的地方。代理充当一个有用的助手，不仅代表我们执行任务，还考虑需要执行哪些子任务以及以何种顺序执行。

在 LangChain 中，代理可以被视为将任务分解为较小步骤的 LLMs。它们利用各种工具和其他 LLMs 来实现任务的最终目标。

代理的第一个组成部分是编排代理，简单来说就是“经理”LLM。这个 LLM 处理所有认知过程，包括制定步骤、分析输出、必要时调整计划，并确定下一步行动。

此外，代理还可以使用工具。这些工具可以从简单的计算器到其他 LLM、SERP（搜索引擎结果页面）API 或 JsonGetValueTool 等更高级的工具。还有包含多个相同类别工具的综合工具包，如 Zapier Toolkit、OpenAPI Agent Toolkit 或 JSON Agent Toolkit。每个工具都附有描述性文本标签，由“经理”LLM 用于了解该工具是否适用于即将到来的步骤。

总之，一个代理包括一个“经理”LLM，它决定完成任务所需的子动作，然后使用一系列工具和工具包来执行每个步骤。

有两种类型的代理如下：

+   **行动代理**：这些代理根据所有先前工具的输出在每个时间步骤上做出决策。它们非常适合高效处理小任务。

+   计划和执行代理：相比之下，计划和执行代理事先制定整个行动计划，并在执行过程中不改变计划。这种类型的代理非常适合有效地处理复杂任务。

还可以通过允许计划和执行代理利用行动代理来结合这两种类型。这种混合方法使代理能够从两种代理类型的优势中受益。

# 【示例】

LangChain 提供了一系列出色的工具，大大加快了开发过程。通过利用链和代理等各种组件，整个过程变得更加简单和快速，节省时间和精力。这使个人能够专注于理解需求并实际构建所需的解决方案。使用 LangChain 时，有许多优势可以获得。它允许充分利用所有**C**apabilityGPT 的优势-简化操作、节省成本、改善决策等等。为了充分理解 LangChain 的潜力，让我们通过探索现实世界的例子来深入了解其组成部分。

# 【示例 1：律师的准备助手】

现在，让我们探讨 LangChain 在创建一个帮助律师进行审前准备的应用程序的实际用例。为了有效准备，律师通常需要研究过去的案例。然而，要找到与他们目前正在处理的案件类似的相关案例可能是具有挑战性的。我们的目标是开发一个能够根据律师对他们特定需求的描述来检索包含过去案例的文件的应用程序。

例如，应用程序应能够列出所有与诽谤或经济损失有关的案件。仅依靠简单的关键词搜索可能无法产生准确的结果。

为了克服这一局限性，我们将采用一种更先进的方法，称为语义搜索。在下面的例子中，我们将演示一种流行的方法，该方法从嵌入文档和律师的查询开始。文本嵌入是文本的数值表示，使机器能够理解和处理自然语言。它们将单词或短语转换为一系列数字（向量），具有语义相似性的项目具有相似的值。

在语义搜索中，这使系统能够根据语义相似性而不仅仅是关键词匹配来将用户的查询与相关文档进行匹配。通过使用文本嵌入，系统可以理解微妙的含义，并提高搜索结果的相关性，提供更高效和有效的搜索体验。

因此，一旦我们嵌入了所有文档（转换为数字列表，即向量）并存储在向量存储中，我们嵌入查询并计算查询与每个文档之间的语义接近度。我们将使用的度量标准称为余弦相似度，它是两个向量之间的夹角的余弦。具有最高余弦相似度的文档将成为我们的搜索结果。

尽管如此，为了说明这个应用程序的功能，我们首先需要生成一组我们可以使用的样本民事案件。

# 内容生成

使用语言模型或 LangChain 的模型组件中的聊天模型可以生成案例。在这种情况下，我们将使用 OpenAI 的 GPT-3 家族*text-003-davinci*模型*的语言模型。为了有效地演示输出解析器的使用，我们将采用一个两步的方法。最初，我们将创建一个表示每个案例各种内容的不同名称列表。

随后，使用相同的模型，我们将为民事案件生成内容并将其保存在一个 docx 文件中。

# 生成名称列表

让我们从一些有用的导入和函数定义开始：

`from LangChain import PromptTemplate`

`from LangChain.llms import OpenAI`

`from LangChain.chains import LLMChain`

`from LangChain.output_parsers import CommaSeparatedListOutputParser`

`import os`

从 docx 导入文档

`from typing import List`

`def generate_civil_cases_names() -> List[str]:`

在这种特殊情况下，我们的目标是在单个请求期间保持在 Open AI 模型令牌限制内创建大约 60-80 个民事案件的名称。为了实现这一目标，我们将利用 Python f-string。我们将包括一个名为`**number_of_cases**`的变量，以便在需要修改指定生成案例数量的数量时使用。

`generate_civil_cases_names_template = “””`

`你是一名律师和法律专家。生成{number_of_cases}个民事案件名称。\n{format_instructions}`

`“””`

为了以列表格式实现所需的输出，我们可以利用 LangChain 的列表解析器。这个解析器旨在返回一个逗号分隔的项目列表。然而，为了获得正确的输出，有两个重要的步骤需要遵循：

**步骤 1：为提示定义格式说明**

第一步涉及调用`**ComaSeparatedListOutputParser()**`类对象。这个对象将允许我们访问`**get_format_instructions**`方法。通过在对象上调用这个方法，我们可以检索包含格式说明的字符串，稍后将其合并到我们的提示中：

`output_parser = CommaSeparatedListOutputParser()`

`format_instructions = output_parser.get_format_instructions()`

**步骤 2：格式化实际输出**

一旦我们获得了输出，我们将继续格式化从模型获得的文本。

让我们讨论一下提示的创建。要使用提示，我们必须创建`**PromptTemplate**`类的一个实例。这涉及指定模板、输入变量和部分变量以及格式说明的指令：

`prompt = PromptTemplate(`

`template=generate_civil_cases_names_template,`

`input_variables=[“number_of_cases”],`

`partial_variables={“format_instructions”: format_instructions},`

`)`

为了继续，定义一个模型是至关重要的。为了我们的目的，我们利用了一个 Open AI 模型，尽管 LangChain 支持许多其他备选方案。OpenAI 类对象中的标准模型是`**text-davinci-003**`。`**temperature**`和`**max_tokens**`是控制模型输出的参数。`**Temperature**`确定生成文本的随机性，而`**max_tokens**`是在提示和完成之间生成的最大标记数。

`model = OpenAI(temperature=0.9, max_tokens=4000)`

下一步是将输入传递给模型：

`_input = prompt.format(number_of_cases=”80”)`

`输出 = 模型（_ 输入）`

最后，我们解析输出以获得民事案件流程的*列表*对象：

`processes_list = output_parser.parse(output)`

`return list_of_processes`

现在我们有了一系列民事案件名称，我们将生成内容。

# 生成民事案件内容

首先，让我们为我们的民事案件创建一个目录：

`def 生成民事案件（processes_list）：`

`if not os.path.exists(“civil_cases”):`

`os.makedirs(“civil_cases”)`

我们希望以可重复的方式生成每个民事案件，这就是为什么我们再次使用提示模板。我们使用了一个包含变量`**civil_case_name**`的 Python f-string，它将在每次迭代中更改：

`generate_civil_case_template = “””`

`你是一名律师和法律专家。生成民事案件内容：{civil_case_name}。包括标题，当事人的全名，背景，主张，证据，法律问题和程序状态。`

`“””`

当我们有简单的用例时，单独使用 LLMs 就可以了。但是，随着应用变得更加复杂，链式 LLMs 可能会派上用场。让我们看看如何实现一个简单的`**LLMChain**`，它接受一个提示模板，用用户输入进行格式化，并从 LLM 返回一个响应。

`llm = OpenAI(温度=0.9，最大标记=4000)`

`提示 = PromptTemplate(`

`input_variables=[“civil_case_name”],`

`template=generate_civil_case_template,`

`)`

`chain = LLMChain(llm=llm, prompt=prompt)`

我们在循环中调用链，以生成并保存民事案件：

`对于 i, process in enumerate(list_of_processes, start=1):`

`legal_process_content = chain.run(process)`

`doc = Document()`

`doc.add_paragraph(legal_process_content)`

`doc.save(f”civil_cases/civil_case_{i}.docx”)`

以下是完整的代码供参考：

`从 LangChain 导入 PromptTemplate`

`from LangChain.llms import OpenAI`

`from LangChain.chains import LLMChain`

`从 LangChain.output_parsers 导入 CommaSeparatedListOutputParser`

`导入 os`

`from docx import Document`

`from typing import List`

`def 生成民事案件名称（）-> List[str]：`

`generate_civil_cases_names_template = “””`

`你是一名律师和法律专家。生成 {number_of_cases} 民事案件名称。\n{format_instructions}`

`“””`

``output_parser = CommaSeparatedListOutputParser()`

`format_instructions = output_parser.get_format_instructions()`

`提示 = PromptTemplate(`

`template=generate_civil_cases_names_template,`

`input_variables=[“number_of_cases”],`

`partial_variables={“format_instructions”: format_instructions},`

`)`

`模型 = OpenAI(温度=0.9，最大标记=4000)`

`_ 输入 = prompt.format(number_of_cases=”80”)`

`输出 = 模型（_ 输入）`

`processes_list = output_parser.parse(output)`

``return list_of_processes`

`def 生成民事案件（processes_list）：`

`if not os.path.exists(“civil_cases”):`

`os.makedirs(“civil_cases”)`

``generate_civil_case_template = “””`

`你是一名律师和法律专家。生成民事案件内容：{civil_case_name}。包括标题，当事人的全名，背景，主张，证据，法律问题和程序状态。`

`“””`

`llm = OpenAI(温度=0.9，最大标记=4000)`

`提示 = PromptTemplate(`

`input_variables=[“civil_case_name”],`

`template=generate_civil_case_template,`

`)`

`chain = LLMChain(llm=llm, prompt=prompt)`

`对于 i, process in enumerate(list_of_processes, start=1):`

`legal_process_content = chain.run(process)`

`doc = Document()`

`doc.add_paragraph(legal_process_content)`

`doc.save(f”civil_cases/civil_case_{i}.docx”)`

`if __name__ == “__main__”:`

`process_names = generate_civil_cases_names()`

`generate_civil_cases(process_names)`

代码从介绍*generate_civil_cases_names*函数开始。这个函数利用 LangChain 的`**PromptTemplate**`和`**OpenAI**`模型生成一个案例名称列表。为了确保正确的格式，输出然后通过`**output_parser**`进行处理。接下来，我们有`**generate_civil_cases**`函数，它将生成的案例名称列表作为参数。在这个函数内部，`**LLMChain**`被用来通过迭代过程为每个案例单独生成内容。生成的案例将被用作后续语义搜索部分的输入。

# 语义搜索

现在我们有了一个民事案件数据库，我们希望我们的应用能够进行语义搜索，以返回所有对于一名准备审判的律师相关的案件。

这个想法是获取所有的民事案件，然后使用一个模型将它们转换为向量表示（嵌入）并将它们存储在一个特殊的向量数据库 - 向量存储中。例如，一旦律师输入一个查询，比如*我在寻找有关财务损失的案例*，接下来将执行以下步骤：

1.  将查询转换为向量表示 - 嵌入查询

1.  在嵌入查询和嵌入民事案件之间进行相似性检查

1.  从数据库中检索相关向量

# 嵌入民事案件并将其存储在 Pinecone 向量存储中

让我们开始导入所需的库和模块：

`from LangChain.document_loaders import DirectoryLoader`

`from LangChain.vectorstores import Pinecone`

`from LangChain.embeddings import OpenAIEmbeddings`

`import pinecone`

`import os`

我们将使用 Open AI 嵌入模型嵌入文档，然后将它们存储在 Pinecone 向量存储中。

首先要做的是加载民事案件。为此，`**DirectoryLoader**`类对象将加载指定目录中的所有文件。请注意，默认情况下，*DirectoryLoader*使用`**UnstructuredLoader**`类来加载文档。如果您需要加载不同（结构化）类型的文档，可以使用不同的加载器类。例如，如果您想加载 Python 源代码文件，可以使用*PythonLoader*类：

`def embed_and_store_documents():`

`loader = DirectoryLoader(“civil_cases”, glob=”*.docx”)`

`documents = loader.load()`

让我们定义嵌入模型：

`embeddings_model = OpenAIEmbeddings()`

现在，让我们深入了解 Pinecone 的功能。Pinecone 充当向量数据库，使我们能够有效地存储嵌入数据并发送查询。在使用 Pinecone 之前，我们需要创建一个索引，这个索引作为我们数据的容器。

在创建 Pinecone 索引时，我们必须指定我们想要使用的相似性度量，比如余弦相似度。这个度量有助于根据向量空间中它们与查询的接近程度来找到最相关的向量。此外，我们需要定义我们正在处理的向量的维度。在我们将使用的 OpenAI 的嵌入模型*text-embedding-ada-002*的情况下，输出向量的维度为 1536。

创建索引后，我们可以通过将 API 密钥和环境名称添加到环境变量中来继续进行。这一步确保我们的 Pinecone 客户端具有必要的授权来访问数据库。此外，我们需要提供我们创建的索引的名称。这些信息使我们能够有效地初始化 Pinecone 客户端，提供与向量存储的无缝交互。

`pinecone.init(`

`api_key=os.environ[‘PINECONE_API_KEY’], environment=os.environ[‘PINECONE_ENV’]`

`)

`index_name = “legal-documents-search”`

最后，通过这一行代码，所有文档都将被嵌入并存储在 Pinecone 中。这些 ready-to-use 的部分是 LangChain 的巨大力量：

`Pinecone.from_documents(`

`documents, embeddings_model, index_name=index_name`

`)

这是完整的代码供参考：

`from LangChain.document_loaders import DirectoryLoader`

`from LangChain.vectorstores import Pinecone`

`from LangChain.embeddings import OpenAIEmbeddings`

`import pinecone`

`import os`

`def embed_and_store_documents():`

`loader = DirectoryLoader(“civil_cases”, glob=”*.docx”)`

`documents = loader.load()`

`embeddings_model = OpenAIEmbeddings()`

`pinecone.init(`

`api_key=os.environ[‘PINECONE_API_KEY’], environment=os.environ[‘PINECONE_ENV’]`

`)`

`index_name = “legal-documents-search”`

`Pinecone.from_documents(`

`documents, embeddings_model, index_name=index_name`

`)`

`if __name__ == “__main__”:`

`embed_and_store_documents()`

代码片段首先通过使用`**DirectoryLoader**`加载民事案件。这个加载器从指定的目录中检索所有具有指定扩展名的文件。然后，我们定义嵌入模型并初始化 Pinecone 客户端。最后一步是使用客户端将加载的文件进行嵌入并存储在 Pinecone 向量存储中。

# 相似性搜索和检索相关数据

最后一部分是检索相关数据。首先，我们要嵌入律师提出的查询并进行相似性搜索。一旦找到最接近的结果，我们希望将民事案例文件的名称返回给用户。让我们从必要的导入开始：

`from LangChain.vectorstores import Pinecone`

`from LangChain.embeddings import OpenAIEmbeddings`

`from LangChain.embeddings.openai import OpenAIEmbeddings`

`import pinecone`

`import os`

为了嵌入律师的查询，我们将再次使用 Open AI 的嵌入模型：

`def retrieve_relevant_cases(query):`

`embeddings_model = OpenAIEmbeddings()`

现在我们有了一个包含我们的民事案件的现有索引，我们可以使用`**from_existing_index**`方法创建一个`**docsearch**`对象，用于相似性检查：

`index_name = “legal-documents-search”`

`pinecone.init(`

`api_key=os.environ[“PINECONE_API_KEY”], environment=os.environ[“PINECONE_ENV”]`

`)`

`docsearch = Pinecone.from_existing_index(index_name, embeddings_model)`

如果我们将查询如“关于财务损失的案例”传递给*docsearch*对象调用*similarty_search*方法，将会发生以下情况：查询将使用*OpenAIEmbeddings*对象中定义的默认模型进行嵌入，执行相似性搜索并返回所有相关文件：

`docs = docsearch.similarity_search(query)`

最后，由于我们正在寻找特定的文件，我们希望返回存储在元数据中的这些文件的名称：

`sources = [doc.metadata[“source”] for doc in docs]`

这是检索相关民事案例的完整代码：

`from LangChain.vectorstores import Pinecone`

`from LangChain.embeddings import OpenAIEmbeddings`

`from LangChain.embeddings.openai import OpenAIEmbeddings`

`import pinecone`

`import os`

`def retrieve_relevant_cases(query):`

`embeddings_model = OpenAIEmbeddings()`

`index_name = “legal-documents-search”`

`pinecone.init(`

`api_key=os.environ[“PINECONE_API_KEY”], environment=os.environ[“PINECONE_ENV”]`

`)`

`docsearch = Pinecone.from_existing_index(index_name, embeddings_model)`

`docs = docsearch.similarity_search(query)`

`sources = [doc.metadata[“source”] for doc in docs]`

`return sources`

`if __name__ == “__main__”:`

`print(retrieve_relevant_cases(“Cases about financial loss”))`

代码片段包括一个名为`**retrieve_relevant_cases**`的函数，旨在获取适当的案例。首先，我们定义嵌入模型、索引名称并初始化 Pinecone 客户端。接下来，我们创建一个用于进行相似性搜索的*docsearch*对象。最后，我们从返回的文件的元数据中提取案例的名称。

# 示例 2：自动化专家的内部知识 QA-在特定控制器手册上聊天

在企业环境中利用 LLM 的一个常见场景是从各种类型的文本文档中提取数据，如产品规格、使用文档、网页、演示文稿和内部文档。在这些情况下的主要挑战是处理大量数据以及不同术语用于指代同一事物的不一致性。简单的关键词搜索通常是不够的，理解用户问题的语义含义变得至关重要。为了解决这个问题，LangChain 提供了一系列组件，具有有效的策略来解决语义搜索。

为了说明 LangChain 的功能，让我们考虑一个例子，我们开发一个工具，用于自动化专家加快搜索文档的过程。这个工具将作为一个聊天机制，允许专家询问关于特定控制器的问题。提醒一下，控制器是管理过程以实现和维持期望参数的设备。例如，在巧克力制造工厂中，可编程逻辑控制器（PLC）通过监控和控制各种设备和过程来维持特定的生产参数，如温度、压力和速度，确保最佳运行和产品质量。这类控制器的文档可能非常广泛，包含大量内容。

目标是为自动化专家提供一个聊天界面，使他们能够快速访问设计和编程所需的信息。

# 将手册分块并加载到 Pinecone 向量存储器

让我们探讨使用 LangChain 进行实现的技术方面。控制器手册是一份 40 页的 PDF 文档，所以我们的初始任务是加载文档。由于整个文档太长而无法输入到我们的提示中，我们必须制定一种策略将文档分成可管理的部分。首先，让我们考虑一些有用的导入：

`from LangChain.text_splitter import RecursiveCharacterTextSplitter`

`from LangChain.vectorstores import Pinecone`

`from LangChain.embeddings import OpenAIEmbeddings`

`from LangChain.document_loaders import PyPDFLoader`

`import pinecone`

`Import os`

加载手册是我们的下一步。为了实现这一目标，我们可以利用`**PyPDFLoader**`类，这个类可以方便地加载文档并将其保存为*Document*对象：

`def embed_and_store_documents():`

`loader = PyPDFLoader(“Manual_MT655333.pdf”)`

`manual = loader.load_and_split()`

现在我们已经加载了 PDF 文件，我们需要将其分成较小的部分。在 LangChain 中，有一个名为*RecursiveCharacterTextSplitter*的文本分割器类，可以帮助我们完成这个任务。分割器根据特定字符拆分文本，这些字符列在下面：[“\n”, “\r”, “ “, „“]。采用这种方法的原因是尽可能保持整个段落在一起。这增加了获取强语义相关文本块的机会。

分块大小指的是每个部分的最大大小，由长度函数测量。重叠指示了每个相邻部分之间共享多少标记。长度函数确定了如何计算各部分的长度。默认情况下，它计算字符数，但通常使用标记计数。`**add_start_index**`参数确定是否应在元数据中包括每个部分在原始文档中的起始位置。

`text_splitter = RecursiveCharacterTextSplitter(`

`chunk_size=500,`

`chunk_overlap=30,`

`length_function=len,`

`add_start_index=True,`

`)`

为了将文档分成较小的部分，我们可以利用`**text_splitter**`对象及其`**split_documents**`方法：

`documents = text_splitter.split_documents(documents=manual)`

完成此步骤后，我们继续嵌入这些块并将它们发布到 Pinecone 向量存储中：

embeddings_model = OpenAIEmbeddings（）

pinecone.init（

api_key = os.environ [‘PINECONE_API_KEY’]，environment = os.environ [‘PINECONE_ENV’]

）

index_name = ‘mt655333-manual’

Pinecone.from_documents（documents，embeddings_model，index_name = index_name）

以下是分块、嵌入和推送向 Pinecone 的完整代码：

从 LangChain.text_splitter 导入 RecursiveCharacterTextSplitter

从 LangChain.vectorstores 导入 Pinecone

从 LangChain.embeddings 导入 OpenAIEmbeddings

从 LangChain.document_loaders 导入 PyPDFLoader

导入 pinecone

导入 os

def embed_and_store_documents（）：

加载器= PyPDFLoader（“Manual_MT655333.pdf”）

manual = loader.load_and_split（）

text_splitter = RecursiveCharacterTextSplitter（

chunk_size = 500，

chunk_overlap = 30，

length_function = len，

add_start_index = True，

）

documents = text_splitter.split_documents（documents = manual）

``embeddings_model = OpenAIEmbeddings（）

pinecone.init（

api_key = os.environ [‘PINECONE_API_KEY’]，环境= os.environ [‘PINECONE_ENV’]

）

index_name = ‘mt655333-manual’

Pinecone.from_documents（documents，embeddings_model，index_name = index_name）

if __name__ == ‘__main__’：

embed_and_store_documents（）

上述代码片段使用**PyPDFLoader**加载控制器手册。之后，它利用**RecursiveCharacterTextSplitter**将文档分割成较小的块。随后，它嵌入这些块并使用 Pinecone 客户端将它们放入向量存储中。这使我们能够为下一步准备文档，该步骤涉及在手册上执行相似性搜索。

# [在控制器手册上聊天-用于相似性搜索的对话检索链]（toc.xhtml＃s455a）

现在让我们探讨一种聊天机制的实现，该机制允许自动化专家询问有关控制器的信息。为了确保对话流畅，我们必须解决后续查询可能与先前查询相关的事实。为了处理这一点，我们需要有效地管理对话的记忆。为了检索相关数据块并有效处理聊天历史记录，我们将使用**ConversationalRetrievalQAchain**。使用这个类，我们将处理先前的交互并将它们整合到当前的聊天中。

从 LangChain.embeddings.openai 导入 OpenAIEmbeddings

从 LangChain.llms 导入 OpenAI

从 LangChain.chat_models 导入 ChatOpenAI

从 LangChain.chains 导入 ConversationalRetrievalChain

从 LangChain.vectorstores 导入 Pinecone

导入 pinecone

导入 os

pinecone.init（

api_key = os.environ [“PINECONE_API_KEY”]，环境= os.environ [“PINECONE_ENV”]

）

def retrieve_controllers_info（query，chat_history）：

embeddings_model = OpenAIEmbeddings（）

index_name = “mt655333-manual”

docsearch = Pinecone.from_existing_index（index_name，embeddings_model）

通过在**ConversationalRetrievalChain**类上使用**from_llm**方法创建以下链：

qa = ConversationalRetrievalChain.from_llm（

OpenAI（temperature = 0），

docsearch.as_retriever（），

return_source_documents = True，

condense_question_llm = ChatOpenAI（temperature = 0，model =”gpt-3.5-turbo”），

）

return qa（{“question”：query，“chat_history”：chat_history}）

为了获取生成答案所使用的源文档的信息，我们包括一个名为“return_source_documents”的额外参数，并将其设置为“True”。最后一个参数“condense_question_llm”负责将聊天历史和查询合并为单个查询向量。这使我们能够使用不同的模型来压缩问题并回答它。可以根据特定任务的性能或使用成本选择模型。该链生成一个包含答案和聊天历史的元组。聊天历史是一个包含查询及其对应答案的元组列表。

# 内存处理

最后一步是测试链。重要的是要注意，在这种情况下，我们必须在聊天会话期间管理内存。在每个会话开始时，我们将内存设置为空列表。当每个查询发送到聊天助手时，我们将其添加到一个包含查询及其对应答案的元组中，添加到聊天历史列表中：

如果 __name__ ==“__main__”：

chat_history=[]

查询=“MT65533 支持自动调谐吗？”

结果=检索控制器信息（查询，聊天记录）

打印（result[“answer”]）

打印（result[“source_documents”]）

chat_history.append（（query，result[“answer”]））

查询=“到底是哪些方法？”

result=检索控制器信息（query，chat_history）

打印（result[“answer”]）

打印（result[“source_documents”]）

以下对话是前面的后端应用程序的结果。此外，根据设计，人们可能希望添加由“docsearch”对象返回的手册的相关片段。

自动化专家：MT65533 支持自动调谐吗？

*AI：是的，MT655333 控制器支持自动调谐技术，以自动确定最佳控制参数。*

自动化专家：到底是哪些方法？

*AI：MT65533 控制器支持自动调谐方法，如继电器反馈、Ziegler-Nichols 前向控制、自适应控制和模糊逻辑控制。*

以下是完整的代码供参考：

从 LangChain.embeddings.openai 导入 OpenAIEmbeddings

从 LangChain.llms 导入 OpenAI

从 LangChain.chat_models 导入 ChatOpenAI

从 LangChain.chains 导入 ConversationalRetrievalChain

从 LangChain.vectorstores 导入 Pinecone

导入 pinecone

导入 os

pinecone.init（

api_key=os.environ[“PINECONE_API_KEY”]，environment=os.environ[“PINECONE_ENV”]

）

def retrieve_controllers_info（query，chat_history）：

embeddings_model=OpenAIEmbeddings（）

index_name=“mt655333-manual”

docsearch=Pinecone.from_existing_index（index_name，embeddings_model）

qa=从 llm 创建对话检索链（

OpenAI（temperature=0），

docsearch.as_retriever（），

return_source_documents=True，

condense_question_llm=ChatOpenAI（temperature=0，model=”gpt-3.5-turbo”），

）

返回 qa（{“question”：query，“chat_history”：chat_history}）

如果 __name__ ==“__main__”：

chat_history=[]

查询=“MT65533 支持自动调谐吗？”

result=检索控制器信息（query，chat_history）

打印（result[“answer”]）

打印（result[“source_documents”]）

chat_history.append（（查询，result[“answer”]））

查询=“到底是哪些方法？”

result=检索控制器信息（query，chat_history）

打印（result[“answer”]）

打印（result[“source_documents”]）

这段代码从初始化 Pinecone 客户端开始，然后定义了“retrieve_controllers_info”函数。此函数接受*query*和*chat_history*作为输入参数，并利用“ConversationalRetrievalChain”在向量存储中执行相似性搜索并生成答案。在主函数中，通过将*query*和*chat_history*传递给“retrieve_controllers_info”函数来测试解决方案。对话记忆的管理由开发人员自行决定。

# 示例 3：使用 LangChain 代理进行市场研究

以下示例说明了如何利用 LangChain 的代理进行市场调研。这个过程包括理解任务，制定执行策略和实施具体行动。

在这个例子中，我们将使用 LangChain 的代理组件。我们将赋予我们的代理能力，利用 SERP API 作为搜索引擎。SERP API 本质上是开发人员可以利用的工具，用于访问和提取搜索引擎结果页面的数据。代理将利用 Open AI 模型来规划所有必要的步骤。它将确定要搜索的相关数据，验证 API 输出的准确性，并编译结果以向用户提供答案。

由于 LangChain 提供了所有必要的工具，因此实现这个功能将是简单和不复杂的。让我们首先导入必要的模块和库：

从 LangChain.agents 导入 load_tools

从 LangChain.agents 导入 initialize_agent

从 LangChain.agents 导入 AgentType

从 LangChain.llms 导入 OpenAI

导入 os

为了使用 SERP API，我们需要注册并获取**serp_api_key**：

serpapi_api_key = os.environ[‘SERPAPI_API_KEY’]

llm = OpenAI(temperature=0)

我们正在为代理配备 SERP API 和 LLM。这些工具使代理能够生成准确和全面的答案：

tools = load_tools([“serpapi”], llm=llm)

现在我们已经准备好工具列表，让我们使用**zero-shot-react-agent**。这种类型的代理使用*ReAct* [13]范式来确定基于工具描述的最合适的工具。*ReAct*得名于*reasoning*和*acting*这两个词的组合。这个框架利用推理组件来识别需要执行的任务并评估观察结果。然后它利用执行组件来执行任务。*ReAct*是一个将推理和行动与语言模型相结合，用于解决各种语言推理和决策任务的通用范式。

agent = initialize_agent(tools, llm, agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION, verbose=True)

要开始，我们首先需要初始化代理。我们通过提供一组工具和推理 LLM 来实现这一点，并指定*ReAct*代理类型。此外，我们可以设置 verbose 参数，以确定代理是否应该提供其行动的逐步描述。一旦代理被初始化，我们就可以要求它解决一个问题：

agent.run(“当前最好的兰博基尼车型的价格是多少？”)

这是完整的代码供参考：

从 LangChain.agents 导入 load_tools

从 LangChain.agents 导入 initialize_agent

从 LangChain.agents 导入 AgentType

从 LangChain.llms 导入 OpenAI

导入 os

serpapi_api_key = os.environ[“SERPAPI_API_KEY”]

llm = OpenAI(temperature=0)

tools = load_tools([“serpapi”], llm=llm)

agent = initialize_agent(

tools，llm，agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION，verbose=True

）

agent.run(“当前最好的兰博基尼车型的价格是多少？”)

在初始化代理并装备它的工具后，我们通过使用查询*最新兰博基尼车型的价格是多少？*来运行它。代理然后开始思考并执行一系列动作。由于我们在初始化过程中先前设置了 verbose 参数，这些步骤将显示为输出：

进入新的 AgentExecutor 链…

我应该查找当前最好的兰博基尼车型

动作：搜索

动作输入：“当前最好的兰博基尼车型”

观察：当前兰博基尼车型阵容中最好的是·兰博基尼 Huracán Evo RWD / STO·兰博基尼 Aventador SVJ·兰博基尼 Urus·兰博基尼 Sián·很棒…

思考：我应该查找兰博基尼 Huracán Evo RWD / STO 的价格

动作：搜索

动作输入：“兰博基尼 Huracán Evo RWD / STO 价格”

`观察：当兰博基尼 Huracan STO 轿车推出时，价格为 327,838 美元，不包括税费和交付费，到 2023 年款约为 33.5 万美元。应该...`

`想法：我现在知道最终答案`

`最终答案：兰博基尼 Huracán Evo RWD / STO 的价格约为 2023 年款约为 33.5 万美元。`

`> 链完成。`

确定顶级兰博基尼车型的价格是代理要执行的任务。代理开始通过识别所请求的兰博基尼车型来进行任务，该车型被描述为“最佳”。

一旦确定了车型，代理就使用 SERP API 来进行彻底的搜索，以获取有关其价格和相关数据的具体信息。它不断评估从 API 收到的输出，仔细分析以确定缺失的信息。为了得出正确的答案，代理依靠推理和执行能力的结合。这就是 LangChain 代理如此强大的原因。它们有能力使用工具，并配备有 LLMs，使它们能够得出结论。通过遵循这种系统化的方法，代理能够准确可靠地确定顶级兰博基尼车型的价格。这展示了 LangChain 代理的令人印象深刻的能力，使它们成为各种用例的有价值的工具。其他一些例子包括利用代理创建个性化的动态定价策略，基于历史和市场数据为个别股票生成风险评估，或者通过分析与特定行业相关的新闻文章和社交媒体帖子来识别市场趋势。

# 结论

LangChain 框架是一个强大的基于 Python 的工具，可以释放大型语言模型在应用程序开发中的全部潜力。该框架提供了一套全面的组件，赋予开发人员创建复杂应用程序的能力。通过利用组件、链和代理的使用，开发过程变得更加流畅和高效。这导致了大幅的工作量节约、提高的质量、标准化和可读性，最终导致了组织生产力的提高和更快的上市时间。LangChain 是一个可以彻底改变企业和专业人士利用大型语言模型所有能力的工具。

随着我们结束对 LangChain 的章节，我们已经看到这个基于 Python 的框架在开发基于 GPT 的应用程序方面表现出色。在我们开始下一章之际，我们将深入探讨“predictive-powers”，这是一个特别设计用于构建利用 LLMs 能力的解决方案的杰出的基于 Java 的库 - 这是我们在生成式人工智能领域激动人心旅程的延续。

# 要点

+   LangChain 是一个基于 Python 的框架，允许开发人员创建最大化大型语言模型潜力的应用程序。它可以与多个供应商的 LLMs 一起使用，包括 OpenAI，以及定制的模型。

+   使用 LangChain 有助于提高质量、标准化和可读性。凭借其即用型组件，开发全面应用程序的过程变得简化和流畅。

+   通过将预先学习的知识与实时或领域信息相结合，LangChain 增强了与 LLMs 合作的能力和可靠性。

+   该框架包括模式、模型、数据处理、链、内存处理和代理等组件，赋予开发人员更快的工作能力。

+   链是一种可立即使用的类，允许堆叠命令。它们有助于提高开发人员的效率。

+   代理在需要独立推理、规划和执行操作的任务中非常有价值，这使得创建自主和强大的应用程序成为可能。````````````````
