# 8 自定义 LLMs 及其输出

## 加入我们在 Discord 上的书籍社区

[`packt.link/EarlyAccessCommunity`](https://packt.link/EarlyAccessCommunity)

![自动生成的二维码描述](img/file54.png)

本章介绍了改进大型语言模型（LLMs）在复杂推理和问题解决任务等特定场景中的可靠性和性能的技术和最佳实践。通常，将模型调整到特定任务或确保模型输出符合我们期望的过程称为调节。在本章中，我们将讨论微调和提示作为调节方法。微调涉及在特定任务或数据集上对预训练基础模型进行训练，这些任务或数据集与所需应用相关。这个过程使模型能够适应并变得更准确和上下文对齐以用于预期的用例。同样，在推断时提供额外的输入或上下文，大型语言模型（LLMs）可以生成适合特定任务或风格的文本。提示设计对于释放 LLM 推理能力、未来模型和提示技术的潜力以及这些原则和技术对于与大型语言模型一起工作的研究人员和从业者来说是非常重要的工具包。了解 LLMs 如何逐个标记生成文本有助于创建更好的推理提示。提示仍然是一门经验艺术 - 经常需要尝试各种变化来看看哪种方法有效。但是一些提示工程的见解可以在模型和任务之间转移。我们将讨论 LangChain 中的工具，以实现高级提示工程策略，如少样本学习、动态示例选择和链式推理。在整个章节中，我们将使用 LLMs 进行微调和提示，您可以在书籍的 Github 存储库的`notebooks`目录中找到。主要章节包括：

+   调节和对齐

+   微调

+   提示工程

让我们从讨论调节和对齐开始，为什么它很重要，以及我们如何实现它。

## 调节和对齐

在生成式人工智能模型的背景下，对齐是指确保这些模型的输出与人类价值观、意图或期望结果一致。它涉及引导模型的行为与在特定背景下被认为是道德、适当或相关的内容保持一致。对齐的概念对于避免生成可能带有偏见、有害或偏离预期目的的输出至关重要。解决对齐问题需要仔细关注训练数据中存在的偏见，通过涉及人类审阅者的迭代反馈循环，在训练/微调阶段完善客观函数，利用用户反馈，并在部署过程中进行持续监控以确保持续对齐。有几个原因可能会希望对大型语言模型进行条件化。首先是控制输出的内容和风格。例如，根据特定关键词或属性（如正式程度）进行条件化可以产生更相关和高质量的文本。条件化还包括安全措施，以防止生成恶意或有害内容。例如，避免生成误导性信息、不当建议或潜在危险的指令，或者更一般地将模型与某些价值观保持一致。对大型语言模型进行条件化的潜在好处是多方面的。通过提供更具体和相关的输入，我们可以获得符合我们需求的输出。例如，在客户支持聊天机器人中，通过将用户查询作为条件，使其生成能够准确解决他们关注的回复。条件化还有助于通过将模型的创造力限制在特定范围内来控制有偏见或不当的输出。此外，通过对大型语言模型进行条件化，我们可以使它们更易控制和适应。我们可以根据我们的要求对其进行微调和塑造其行为，并创建在特定领域（如法律咨询或技术写作）可靠的人工智能系统。然而，也需要考虑潜在的缺点。过度对模型进行条件化可能导致过拟合，使其过于依赖特定输入，并在不同情境下难以生成创造性或多样化的输出。此外，应当负责任地利用条件化，因为大型语言模型有放大训练数据中存在偏见的倾向。在对这些模型进行条件化时，必须小心不要加剧与偏见或有争议话题相关的问题。

> **对齐的好处** 包括：

+   增强用户体验：对齐模型生成与用户查询或提示相关的输出。

+   建立信任：确保道德行为有助于在用户/客户之间建立信任。

+   品牌声誉：通过与关于品牌一致性和所需语气/风格指南的业务目标保持一致。

+   缓解有害影响：与安全、保密和隐私考虑的对齐有助于防止生成有害或恶意内容。

    > **潜在的缺点** 包括：

+   挑战平衡：在极端对齐（过于保守）和创造自由（过于宽松）之间取得平衡可能很困难。

+   自动化指标的局限性：定量评估指标可能无法完全捕捉对齐细微差别。

+   主观性：对齐判断往往是主观的，需要仔细考虑并就期望的价值观和指导方针达成共识。

在多样化数据上预训练大型模型以学习模式和语言理解，结果是得到一个具有广泛理解各种主题但缺乏特定性或与任何特定背景相关性的基础模型。虽然像 GPT-4 这样的基础模型能够在各种主题上生成令人印象深刻的文本，但对其进行调节可以增强其在任务相关性、特定性和连贯性方面的能力，并使其输出更相关和主题相关。没有调节，这些模型往往会生成与期望背景不完全吻合的文本。通过调节它们，我们可以引导语言模型生成更与给定输入或指令相关的输出。调节的主要优势在于它允许引导模型而无需进行大量的重新训练。它还能够实现交互式控制和在不同模式之间切换。调节可以发生在模型开发周期的不同阶段——从微调到在各种背景下生成输出。有几种实现大型语言模型对齐的选项。一种方法是在微调过程中进行调节，通过在反映所需输出的数据集上训练模型。这使模型能够专门化，但需要访问相关的训练数据。另一种选择是在推断时动态调节模型，通过提供条件输入以及主要提示。这更加灵活，但在部署过程中引入了一些复杂性。在接下来的部分中，我将总结关于对齐的关键方法，如微调和提示工程，讨论其基本原理，并检查它们的相对优缺点。

### 对齐方法

随着像 GPT-3 这样的大型预训练语言模型的出现，人们对将这些模型调整为下游任务的技术越来越感兴趣。这个过程被称为微调。微调允许预训练模型根据预训练期间获得的广泛语言知识定制特定应用程序。调整预训练神经网络的想法起源于 2010 年代初的计算机视觉研究。在自然语言处理领域，Howard 和 Ruder（2018）展示了微调预训练的上下文表示（如 ELMo 和 ULMFit）在下游任务上的有效性。开创性的 BERT 模型（Devlin 等人，2019）将微调预训练的 transformers 确立为自然语言处理中的事实标准。微调的必要性源于预训练语言模型的设计目的是对一般语言知识进行建模，而不是特定的下游任务。只有在适应特定应用程序时，它们的能力才会显现出来。微调允许更新预训练权重以适应目标数据集和目标。这使得可以从一般模型中进行知识转移，同时为专门任务定制它。已经提出了几种用于对齐的方法，效率和效率之间存在权衡，值得更深入地研究每种对齐方法的细节。**全面微调**在微调期间更新预训练语言模型的所有参数。该模型在下游任务上端到端地进行训练，允许全局更新权重以最大化目标性能。FFT 在各种任务中始终取得强大的结果，但需要大量的计算资源和大型数据集以避免过拟合或遗忘。在**适配器调整**中，额外的可训练适配器层通常是瓶颈层插入到预训练模型中，同时保持原始权重冻结。只有新添加的适配器层在下游任务上进行训练。这使得调整参数高效，因为只有一小部分权重被更新。然而，由于预训练权重保持不变，适配器调整存在低拟合任务的风险。适配器的插入点和容量影响整体有效性。**前缀调整**：这在 LM 的每一层前面添加可训练向量，在微调期间进行优化，而基本权重保持冻结。前缀允许向模型注入归纳偏见。与适配器相比，前缀调整的内存占用较小，但效果没有那么好。前缀的长度和初始化影响有效性。在**提示调整**中，输入文本附加了可训练提示标记，这些标记提供软提示以诱导 LM 产生所需的行为。例如，可以提供任务描述作为提示来引导模型。只有添加的提示标记在训练期间进行更新，而预训练权重保持冻结。性能受提示工程的影响很大。正在探索自动提示方法。**低秩适应（LoRA）**向冻结的 LM 权重添加成对的低秩可训练权重矩阵。例如，对于每个权重 W，添加低秩矩阵 B 和 A，使得前向传���使用 W + BA。只有 B 和 A 被训练，基本 W 保持冻结。LoRA 以更高的参数效率实现了合理的效果。秩 r 的选择影响权衡。LoRA 使得在有限硬件上调整巨大 LM 成为可能。确保输出正确对齐的另一种方法是通过**人工监督**方法，如人机协同系统。这些系统涉及提供反馈并在必要时进行更正的人类审阅者。人类参与有助于使生成的输出与人类设定的期望值或指导原则保持一致。以下是总结引导生成 AI 输出的不同技术的表格：

| **阶段** | **技术** | **示例** |
| --- | --- | --- |
| 训练 | 预训练 | 在多样数据上训练 |
|  | 目标函数 | 训练目标的精心设计 |
|  | 架构和训练过程 | 优化模型结构和训练 |
| 微调 | 专业化 | 在特定数据集/任务上训练 |
| 推理时条件 | 动态输入 | 前缀，控制代码，上下文示例 |
| 人类监督 | 人类参与 | 人类审查和反馈 |

图 8.1：引导生成式人工智能输出。

结合这些技术为开发人员提供了更多对生成式人工智能系统行为和输出的控制。最终目标是确保人类价值在训练到部署的所有阶段都被纳入，以创建负责任和一致的人工智能系统。此外，在预训练目标函数中的精心设计选择也会影响语言模型最初学习的行为和模式。通过将道德考虑因素纳入这些目标函数中，开发人员可以影响大型语言模型的初始学习过程。我们可以区分一些微调方法，如在线和离线。InstructGPT 被认为是一个改变游戏规则的因素，因为它展示了通过引入强化学习从人类反馈（RLHF）可以显著改进语言模型，如 GPT-3。让我们谈谈 InstructGPT 为何具有如此变革性影响的原因。

#### 强化学习与人类反馈

在他们 2022 年 3 月的论文中，OpenAI 的欧阳等人展示了使用强化学习从人类反馈（RLHF）与近端策略优化（PPO）来调整大型语言模型如 GPT-3 与人类偏好一致。强化学习从人类反馈（RLHF）是一种在线方法，通过人类偏好对语言模型进行微调。它有三个主要步骤：

1.  监督预训练：首先通过标准监督学习对语言模型进行训练，使用人类演示。

1.  奖励模型训练：通过人类对语言模型输出的评分来训练奖励模型以估计奖励。

1.  RL 微调：通过强化学习对语言模型进行微调，以最大化来自奖励模型的预期奖励，使用类似 PPO 的算法。

主要变化 RLHF 允许通过学习奖励模型将微妙的人类判断纳入语言模型训练中。因此，人类反馈可以引导和改进语言模型的能力，超越标准监督微调。这种新模型可以用于遵循以自然语言给出的指令，并且可以以比 GPT-3 更准确和相关的方式回答问题。尽管参数少 100 倍，InstructGPT 在用户偏好、真实性和减少伤害方面优于 GPT-3。从 2022 年 3 月开始，OpenAI 开始发布 GPT-3.5 系列模型，这是 GPT-3 的升级版本，包括与 RLHF 微调。这些模型的用户立即注意到了微调的三个优点：

1.  可操纵性：模型遵循指令的能力（指令微调）

1.  可靠的输出格式化：这对于 API 调用/函数调用等方面变得重要。

1.  自定义语调：这使得可以根据任务和受众适当地调整输出风格。

InstructGPT 通过将人类反馈的强化学习方法纳入传统微调方法之外的新途径，开辟了改进语言模型的新途径。尽管 RL 训练可能不稳定且计算成本高昂，但其成功激发了进一步研究，以完善 RLHF 技术，减少对齐的数据需求，并为各种应用开发更强大和更易访问的模型。

#### 离线方法

离线方法通过直接利用人类反馈来规避在线 RL 的复杂性。我们可以区分基于排名和基于语言的方法：

+   基于排名：人类对 LM 输出的排名用于定义微调的优化目标，避免完全使用 RL。这包括 Preference Ranking Optimization（PRO；宋等，2023）和 Direct Preference Optimization（DPO；拉法洛夫等，2023）等方法。

+   基于语言：人类反馈以自然语言形式提供，并通过标准监督学习利用。例如，Hindsight 链（CoH；刘等，2023）将所有类型的反馈转换为句子，并用于微调模型，利用语言模型的语言理解能力。

直接偏好优化（DPO）是一种简单而有效的方法，用于训练语言模型以符合人类偏好，无需明确学习奖励模型或使用强化学习。虽然它优化的目标与现有的 RLHF 方法相同，但实现起来要简单得多，更稳定，并且取得了强大的实证表现。Meta 的研究人员在论文“*LIMA：对齐的少即是多*”中，通过在精细训练 LLaMa 模型时最小化仅有 1,000 个精心策划的提示的监督损失，简化了对齐。基于与 DaVinci003（GPT-3.5）的输出相比较时的有利人类偏好，他们得出结论，精细训练只有极小的重要性。他们将此称为表面对齐假设。离线方法提供更稳定和高效的调整。然而，它们受到静态人类反馈的限制。最近的方法尝试将离线和在线学习结合起来。虽然 DPO 和带有 PPO 的 RLHF 旨在将 LLM 与人类偏好对齐，但它们在复杂性、数据需求和实现细节方面存在差异。DPO 提供简单性，但通过直接优化概率比实现强大的性能。另一方面，在 InstructGPT 中，带有 PPO 的 RLHF 引入了更多复杂性，但通过奖励建模和强化学习优化允许通过微妙的对齐。

#### 低秩适应

LLM 在自然语言处理领域取得了令人印象深刻的成果，现在也被用于其他领域，如计算机视觉和音频。然而，随着这些模型变得更大，训练它们在消费者硬件上变得困难，并且为每个特定任务部署它们变得昂贵。有一些方法可以降低计算、内存和存储成本，同时提高在低数据和领域外情况下的性能。低秩适应（LoRA）冻结了预训练模型的权重，并在 Transformer 架构的每一层中引入可训练的秩分解矩阵，以减少可训练参数的数量。LoRA 在各种语言模型（RoBERTa、DeBERTa、GPT-2 和 GPT-3）上实现了与微调相当或更好的模型质量，同时具有更少的可训练参数和更高的训练吞吐量。QLORA 方法是 LoRA 的扩展，通过将梯度反向传播通过冻结的 4 位量化模型到可学习的低秩适配器，实现了对大型模型的高效微调。这使得可以在单个 GPU 上微调一个 65B 参数模型。QLORA 模型通过引入新的数据类型和优化器等创新，实现了在 Vicuna 上 ChatGPT 性能的 99%。特别是，QLORA 将微调一个 65B 参数模型的内存需求从>780GB 降低到<48GB，而不影响运行时或预测性能。

> **量化**是指减少神经网络中权重和激活的数值精度的技术，如大型语言模型（LLMs）。量化的主要目的是减少大型模型的内存占用和计算需求。
> 
> > 有关 LLM 量化的一些关键要点：

+   它涉及使用比标准单精度浮点（FP32）更少的位数来表示权重和激活。例如，权重可以量化为 8 位整数。

+   这可以将模型大小缩小多达 4 倍，并提高专用硬件的吞吐量。

+   量化通常对模型准确性影响较小，尤其是在重新训练时。

+   常见的量化方法包括标量、向量和乘积量化，它们将权重分别或分组量化。

+   通过估计激活的分布并适当分组，激活也可以被量化。

+   量化感知训练在训练过程中调整权重以最小化量化损失。

+   像 BERT 和 GPT-3 这样的 LLMs 已经证明通过微调可以很好地使用 4-8 位量化。

参数高效微调（PEFT）方法使每个任务可以使用小的检查点，使模型更具可移植性。这些小的训练权重可以添加到 LLM 之上，使得同一模型可以用于多个任务而无需替换整个模型。在下一节中，我们将讨论在推理时对大型语言模型（LLMs）进行条件化的方法。

#### 推理时的条件化

一种常用的方法是**推理时的条件化**（输出生成阶段），在这里特定的输入或条件会动态提供以指导输出生成过程。在某些情况下，LLM 微调可能并不总是可行或有益的：

1.  有限的微调服务：一些模型只能通过缺乏或受限的微调能力的 API 访问。

1.  数据不足：在某些情况下，针对特定下游任务或相关应用领域缺乏微调数据。

1.  动态数据：应用程序中频繁更改数据的情况，例如新闻相关平台，可能难以频繁微调模型，导致潜在的缺点。

1.  上下文敏感应用：动态和特定上下文的应用，如个性化聊天机器人，无法根据个人用户数据进行微调。

对于推理时的条件化，通常我们在文本生成过程的开头提供一个文本提示或指示。这个提示可以是几句话甚至一个单词，作为所需输出的明确指示。一些常见的动态推理时条件化技术包括：

+   提示调整：为预期行为提供自然语言指导。对提示设计敏感。

+   前缀调整：在 LLM 层前添加可训练向量。

+   限制标记：强制包含/排除某些词语。

+   元数据：提供高级信息，如流派、目标受众等。

提示可以促进生成符合特定主题、风格甚至模仿特定作者写作风格的文本。这些技术包括在推理时提供上下文信息，例如在上下文学习或检索增强中。提示调整的一个例子是在提示前加上前缀，比如“写一个适合儿童的故事...”这样的指示。例如，在聊天机器人应用中，通过使用用户消息来调节模型，帮助其生成个性化且与当前对话相关的回复。更多的例子包括在提示前加上相关文档以帮助 LLMs 完成写作任务（例如新闻报道、维基百科页面、公司文件），或者在提示 LLM 之前检索并加上用户特定数据（财务记录、健康数据、电子邮件）以确保个性化答案。通过在运行时将 LLM 输出与上下文信息相结合，这些方法可以引导模型而不依赖于传统的微调过程。通常演示是推理任务指令的一部分，其中提供少量示例以诱导期望的行为。强大的 LLMs，如 GPT-3，可以通过提示技术解决任务而无需进一步训练。在这种方法中，要解决的问题被呈现给模型作为文本提示，可能还包括一些类似问题及其解决方案的文本示例。模型必须通过推理提供提示的完成。**零样本提示**不涉及已解决的示例，而少量样本提示包括少量类似（问题，解决方案）对的示例。已经证明提示可以轻松控制像 GPT-3 这样的大型冻结模型，并且可以在不进行大量微调的情况下引导模型行为。提示使模型能够在新知识上进行条件化，但需要精心设计提示以获得最佳结果。这将是我们在本章讨论的内容之一。在前缀调整中，连续的任务特定向量在推理时被训练并提供给模型。类似的想法已经被提出用于适配器方法，如参数高效的迁移学习（PELT）或梯子侧调整（LST）。在推理时进行条件化也可以发生在采样过程中，例如基于语法的采样，其中输出可以被限制为与某些明确定义的模式兼容，比如编程语言语法。

#### 结论

完全微调始终能取得强大的结果，但通常需要大量资源，并且在功效和效率之间存在权衡。像适配器、提示和 LoRA 这样的方法通过稀疏性或冻结减轻了这种负担，但可能效果较差。最佳方法取决于约束和目标。未来改进的技术针对大型语言模型量身定制，可以推动功效和效率的边界。最近的工作将离线和在线学习相结合以提高稳定性。整合世界知识和可控生成仍然是开放挑战。基于提示的技术允许对 LLM 进行灵活的条件设定，以诱导所需行为而无需进行密集训练。谨慎的提示设计、优化和评估是有效控制 LLM 的关键。基于提示的技术允许以灵活、低资源的方式对 LLM 进行特定行为或知识的条件设定。

### 评估

对齐是通过像 HUMAN 这样的对齐基准和像 FLAN 这样的泛化测试来评估的。有一些核心基准具有很高的可区分性，可以准确评估模型的优势和劣势，例如：

+   英语知识：MMLU

+   中文知识：C-Eval

+   推理：GSM8k / BBH（算法）

+   编码：HumanEval / MBPP

在平衡这些方向之后，可以追求像 MATH（高难度推理）和对话等额外的基准。特别有趣的评估在数学或推理方面，预计泛化能力会非常强。 MATH 基准展示了高水平的难度，而 GPT-4 根据提示方法实现了不同的得分。 结果范围从通过少量评估进行天真提示到 PPO + 基于过程的奖励建模。 如果微调仅涉及对话数据，可能会对现有能力（如 MMLU 或 BBH）产生负面影响。 提示工程至关重要，因为偏见和查询难度会影响评估。 还有像困惑度（衡量模型预测数据的能力）或 BLEU 分数（捕捉生成文本与参考文本之间的相似性）这样的定量指标。 这些指标提供了粗略的估计，但可能无法完全捕捉语义含义或与更高级目标的对齐。其他指标包括通过人类评估的用户偏好评分，成对偏好，利用预训练奖励模型进行在线小/中型模型或自动化 LLM 评估（例如 GPT-4）。 人类评估有时可能存在问题，因为人类可能会受到主观标准的影响，例如回应中的权威语气而不是实际准确性。 进行评估，让用户根据事先设定的具体标准评估生成文本的质量、相关性和适当性，可以提供更细致入微的见解。 微调的目的不仅仅是改善给定提示集上的用户偏好。 其主要目的是通过减少不良输出（如非法、有害、滥用、虚假或欺骗性内容）的发生来解决 AI 安全问题。 关注减轻风险行为对确保 AI 系统的安全性和可靠性至关重要。 仅基于用户偏好评估和比较模型，而不考虑它们可能造成的潜在危害，可能会误导，并优先考虑比较安全的替代方案。 总之，评估 LLM 的对齐性需要仔细选择基准，考虑可区分性，并结合自动评估方法和人类判断。 注意提示工程和特定评估方面的关注是必要的，以确保对模型性能进行准确评估。在接下来的部分中，我们将使用 PEFT 和量化对一个小型开源 LLM（OpenLLaMa）进行微调，用于问答，并将其部署在 HuggingFace 上。

## 微调

正如我们在本章第一节中讨论的那样，LLM 的模型微调的目标是优化模型，使其生成的输出比原始基础模型更具体于任务和上下文。 在我们可能想要应用这种方法的众多任务和场景中，包括以下几种：

+   软件开发

+   文档分类

+   问答

+   信息检索

+   客户支持

在本节中，我们将为问答模型进行微调。这个步骤不是特定于 LangChain 的，但我们将指出一些自定义内容，LangChain 可以参与其中。出于性能原因，我们将在 Google Colab 上运行这个步骤，而不是通常的本地环境。

> **Google Colab** 是一个计算环境，提供不同的硬件加速计算任务的手段，如张量处理单元（TPUs）和图形处理单元（GPUs）。这些在免费和专业版中都可用。对于本节任务的目的，免费版完全足够。您可以在此网址登��到 Colab 环境：[`colab.research.google.com/`](https://colab.research.google.com/)

请确保您在 Google Colab 机器的顶部菜单中设置为 TPU 或 GPU，以确保您有足够的资源来运行此操作，并且训练不会花费太长时间。我们将在 Google Colab 环境中安装所有所需的库 - 我添加了我使用的这些库的版本，以便使我们的微调可重复进行：

+   peft：参数高效微调（PEFT；版本 0.5.0）

+   trl：近端策略优化（0.6.0）

+   bitsandbytes：k 位优化器和矩阵乘法例程，用于量化（0.41.1）

+   accelerate：使用多 GPU、TPU、混合精度训练和使用 PyTorch 模型（0.22.0）

+   transformers：HuggingFace transformers 库，支持 JAX、PyTorch 和 TensorFlow（4.32.0）

+   datasets：社区驱动的开源数据集库（2.14.4）

+   sentencepiece：用于快速标记化的 Python 封装（0.1.99）

+   wandb：用于监控 Weights and Biases 上训练进度的工具（0.15.8）

+   langchain 用于在训练后将模型加载回作为 langchain llm（0.0.273）

我们可以通过 Colab 笔记本安装这些库，如下所示：

```
!pip install -U accelerate bitsandbytes datasets transformers peft trl sentencepiece wandb langchain
```

为了从 HuggingFace 下载和训练模型，我们需要在平台上进行身份验证。请注意，如果您想稍后将您的模型推送到 HuggingFace，您需要在 HuggingFace 上生成一个具有写入权限的新 API 令牌：[`huggingface.co/settings/tokens`](https://huggingface.co/settings/tokens)

![图 8.3：在 HuggingFace 上创建一个新的具有写入权限的 API 令牌。](img/file55.png)

图 8.3：在 HuggingFace 上创建一个新的具有写入权限的 API 令牌。

我们可以像这样从笔记本进行身份验证：

```
import notebook_login
notebook_login()
```

在提示时，粘贴您的 HuggingFace 访问令牌。

> 在我们开始之前，请注意：在执行代码时，您需要登录不同的服务，因此请确保在运行笔记本时要注意！

Weights and Biases（W&B）是一个 MLOps 平台，可以帮助开发人员从头到尾监控和记录 ML 训练工作流程。正如前面提到的，我们将使用 W&B 来了解训练的效果如何，特别是模型是否随着时间的推移而改进。对于 W&B，我们需要为项目命名；或者，我们可以使用 wandb 的 `init()` 方法：

```
import os
os.environ["WANDB_PROJECT"] = "finetuning"
```

为了与 W&B 进行身份验证，您需要在他们这里创建一个免费帐户：[`www.wandb.ai`](https://www.wandb.ai) 您可以在授权页面上找到您的 API 密钥：[`wandb.ai/authorize`](https://wandb.ai/authorize)同样，我们需要粘贴我们的 API 令牌。如果之前的训练仍然处于活动状态 - 这可能是从笔记本的上一次执行中，如果您再次运行第二次 - 让我们确保我们开始一个新的！这将确保我们在 W&B 上获得新的报告和仪表板：

```
if wandb.run is not None:
    wandb.finish()
```

接下来，我们需要选择一个数据集进行优化。我们可以使用许多不同的数据集，适用于编码、叙述、工具使用、SQL 生成、小学数学问题（GSM8k）或许多其他任务。HuggingFace 提供了丰富的数据集，可以在此网址查看：[`huggingface.co/datasets`](https://huggingface.co/datasets)这些数据集涵盖了许多不同的，甚至是最为专业的任务。我们也可以自定义我们自己的数据集。例如，我们可以使用 langchain 来设置训练数据。有许多可用的过滤方法可以帮助减少数据集中的冗余。在本章中展示数据收集作为一个实用的步骤可能会很吸引人。然而，由于复杂性，我将其排除在本书的范围之外。从网络数据中过滤出质量可能会更加困难，但有许多可能性。对于代码模型，我们可以应用代码验证技术来对段落进行评分作为质量过滤器。如果代码来自 Github，我们可以按星级或按存储库所有者的星级进行过滤。对于自然语言文本，质量过滤并不是一件简单的事情。搜索引擎排名可以作为一个流行度过滤器，因为它通常基于用户与内容的互动。此外，知识蒸馏技术可以通过事实密度和准确性进行调整作为一个过滤器。在这个步骤中，我们正在使用 Squad V2 数据集进行问答性能的微调。您可以在 HuggingFace 上查看详细的数据集描述：[`huggingface.co/spaces/evaluate-metric/squad_v2`](https://huggingface.co/spaces/evaluate-metric/squad_v2)

```
from datasets import load_dataset
dataset_name = "squad_v2" 
dataset = load_dataset(dataset_name, split="train")
eval_dataset = load_dataset(dataset_name, split="validation") 
```

我们同时采用训练和验证拆分。Squad V2 数据集有一个部分应该用于训练，另一个部分用于验证，正如我们可以在`load_dataset(dataset_name)`的输出中看到的：

```
DatasetDict({
    train: Dataset({
        features: ['id', 'title', 'context', 'question', 'answers'],
        num_rows: 130319
    })
    validation: Dataset({
        features: ['id', 'title', 'context', 'question', 'answers'],
        num_rows: 11873
    })
}) 
```

我们将使用验证拆分进行早停。早停将允许我们在验证错误开始恶化时停止训练。Squad V2 数据集由各种特征组成，我们可以在这里看到：

```
{'id': Value(dtype='string', id=None), 
 'title': Value(dtype='string', id=None), 
 'context': Value(dtype='string', id=None), 
 'question': Value(dtype='string', id=None), 
 'answers': Sequence(feature={'text': Value(dtype='string', id=None), 
 'answer_start': Value(dtype='int32', id=None)}, length=-1, id=None)}
```

训练中的基本思想是用一个问题提示模型，并将答案与数据集进行比较。我们希望有一个小型模型，可以在本地以合理的标记速率运行。LLaMa-2 模型需要使用您的电子邮件地址签署许可协议并得到确认（公平地说，这可能非常快），因为它受到商业使用的限制。像 OpenLLaMa 这样的 LLaMa 衍生产品在 HF 排行榜上表现相当不错：[`huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard`](https://huggingface.co/spaces/HuggingFaceH4/open_llm_leaderboard)OpenLLaMa 版本 1 不能用于编码任务，因为分词器的原因。因此，让我们使用 v2！我们将使用一个 30 亿参数的模型，即使在较旧的硬件上也能使用：

```
model_id = "openlm-research/open_llama_3b_v2" 
new_model_name = f"openllama-3b-peft-{dataset_name}"
```

我们甚至可以使用更小的模型，比如`EleutherAI/gpt-neo-125m`，这样可以在资源使用和性能之间取得很好的折衷。让我们加载模型：

```
import torch
from transformers import AutoModelForCausalLM, BitsAndBytesConfig
bnb_config = BitsAndBytesConfig(
    load_in_4bit=True,
    bnb_4bit_quant_type="nf4",
    bnb_4bit_compute_dtype=torch.float16,
)
device_map="auto"
base_model = AutoModelForCausalLM.from_pretrained(
    model_id,
    quantization_config=bnb_config,
    device_map="auto",
    trust_remote_code=True,
)
base_model.config.use_cache = False
```

Bits and Bytes 配置使我们能够将模型量化为 8、4、3 甚至 2 位，从而加速推理并减少内存占用，而不会在性能方面产生大的成本。我们将在谷歌云盘上存储模型检查点；您需要确认登录到您的谷歌账户：

```
from google.colab import drive
drive.mount('/content/gdrive')
```

我们需要通过谷歌进行身份验证才能使其工作。我们可以将模型检查点和日志的输出目录设置为我们的谷歌云盘：

```
output_dir = "/content/gdrive/My Drive/results"
```

如果您不想使用谷歌云盘，只需将其设置为计算机上的一个目录。对于训练，我们需要设置一个分词器：

```
from transformers import AutoTokenizer
tokenizer = AutoTokenizer.from_pretrained(model_id, trust_remote_code=True)
tokenizer.pad_token = tokenizer.eos_token
tokenizer.padding_side = "right"
```

现在我们将定义我们的训练配置。我们将设置 LORA 和其他训练参数：

```
from transformers import TrainingArguments, EarlyStoppingCallback
from peft import LoraConfig
# More info: https://github.com/huggingface/transformers/pull/24906
base_model.config.pretraining_tp = 1
peft_config = LoraConfig(
    lora_alpha=16,
    lora_dropout=0.1,
    r=64,
    bias="none",
    task_type="CAUSAL_LM",
)
training_args = TrainingArguments(
    output_dir=output_dir, 
    per_device_train_batch_size=4,
    gradient_accumulation_steps=4,
    learning_rate=2e-4,
    logging_steps=10,
    max_steps=2000,
    num_train_epochs=100,
    evaluation_strategy="steps",
    eval_steps=5,
    save_total_limit=5 
    push_to_hub=False, 
    load_best_model_at_end=True,
    report_to="wandb"
)
```

有一些参数需要解释一下。`push_to_hub`参数意味着我们可以在训练过程中定期将模型检查点推送到 HuggingSpace Hub。为了使其工作，你需要设置 HuggingSpace 身份验证（如上所述，需要写入权限）。如果我们选择这个选项，作为`output_dir`我们可以使用`new_model_name`。这将是模型在 HuggingFace 上可用的存储库名称：[`huggingface.co/models`](https://huggingface.co/models)或者，如我在这里所做的，我们可以将模型保存在本地或云端，例如谷歌云盘的一个目录。我将`max_steps`和`num_train_epochs`设置得非常高，因为我注意到训练仍然可以在许多步骤后改进。我们使用早停和较高数量的最大训练步数使模型收敛到更高的性能。对于早停，我们需要将`evaluation_strategy`设置为`"steps"`，并且`load_best_model_at_end=True`。`eval_steps`是两次评估之间的更新步数。`save_total_limit=5`意味着只保存最后 5 个模型。最后，`report_to="wandb"`意味着我们将发送训练统计数据、一些模型元数据和硬件信息到 W&B，我们可以在那里查看每次运行的图表和仪表板。然后训���可以使用我们的配置：

```
from trl import SFTTrainer
trainer = SFTTrainer(
    model=base_model,
    train_dataset=dataset,
    eval_dataset=eval_dataset,
    peft_config=peft_config,
    dataset_text_field="question",  # this depends on the dataset!
    max_seq_length=512,
    tokenizer=tokenizer,
    args=training_args,
    callbacks=[EarlyStoppingCallback(early_stopping_patience=200)]
)
trainer.train()
```

训练可能需要相当长的时间，即使在 TPU 设备上运行。评估和早停会大大减慢训练速度。如果禁用早停，可以使训练速度更快。我们应该在训练过程中看到一些统计数据，但最好显示性能图表，这样我们可以在 W&B 上看到：

![图 8.4：随时间（步数）的微调训练损失。](img/file56.png)

图 8.4：随时间（步数）的微调训练损失。

训练完成后，我们可以将最终检查点保存在磁盘上以便重新加载：

```
trainer.model.save_pretrained(
    os.path.join(output_dir, "final_checkpoint"),
)
```

现在，我们可以与朋友分享我们的最终模型，以炫耀我们通过手动推送到 HuggingFace 所取得的性能：

```
trainer.model.push_to_hub(
    repo_id=new_model_name
)
```

现在，我们可以使用我们的 HuggingFace 用户名和存储库名称（新模型名称）的组合来加载模型。让我们快速展示如何在 LangChain 中使用这个模型。通常，peft 模型存储为适配器，而不是完整模型，因此加载方式有点不同：

```
from peft import PeftModel, PeftConfig
from transformers import AutoModelForCausalLM, AutoTokenizer, pipeline
from langchain.llms import HuggingFacePipeline
model_id = 'openlm-research/open_llama_3b_v2'
config = PeftConfig.from_pretrained("benji1a/openllama-3b-peft-squad_v2")
model = AutoModelForCausalLM.from_pretrained(model_id)
model = PeftModel.from_pretrained(model, "benji1a/openllama-3b-peft-squad_v2")
tokenizer = AutoTokenizer.from_pretrained(model_id, trust_remote_code=True)
tokenizer.pad_token = tokenizer.eos_token
pipe = pipeline(
    "text-generation",
    model=model,
    tokenizer=tokenizer,
    max_length=256
)
llm = HuggingFacePipeline(pipeline=pipe)
```

到目前为止，我们在 Google Colab 上完成了所有工作，但我们也可以在本地执行，只需注意你需要安装 huggingface peft 库！到目前为止，我们已经展示了如何对开源 LLM 进行微调和部署。一些商业模型也可以根据自定义数据进行微调。例如，OpenAI 的 GPT-3.5 和 Google 的 PaLM 模型都提供了这种能力。这已经与一些 Python 库集成。使用 Scikit-LLM 库，在任何情况下这只是几行代码：对文本分类进行 PaLM 模型的微调可以这样完成：

```
from skllm.models.palm import PaLMClassifier
clf = PaLMClassifier(n_update_steps=100)
clf.fit(X_train, y_train) # y_train is a list of labels
labels = clf.predict(X_test)
```

同样，你可以这样对 GPT-3.5 模型进行文本分类的微调：

```
from skllm.models.gpt import GPTClassifier
clf = GPTClassifier(
        base_model = "gpt-3.5-turbo-0613",
        n_epochs = None, # int or None. When None, will be determined automatically by OpenAI
        default_label = "Random", # optional
)
clf.fit(X_train, y_train) # y_train is a list of labels
labels = clf.predict(X_test)
```

有趣的是，在 OpenAI 提供的微调中，所有输入都会通过一个调节系统，以确保输入与安全标准兼容。这结束了微调。在极端情况下，LLMs 可以在没有任何任务特定调整的情况下部署和查询。通过提示，我们可以实现少样本学习甚至零样本学习，正如我们将在下一节讨论的那样。

## 提示工程

提示对于引导大型语言模型（LLMs）的行为非常重要，因为它们可以在不进行昂贵的重新训练的情况下将模型输出与人类意图对齐。精心设计的提示可以使 LLMs 适用于原始训练之外的各种任务。提示充当指示，向 LLM 展示所需的输入-输出映射。下图显示了提示不同语言模型的几个示例（来源：“预训练、提示和预测 - 自然语言处理中提示方法的系统调查”由刘等人，2021 年）：

![图 8.5：提示示例，特别是填空形式的知识探测和摘要。](img/file57.png)

图 8.5：提示示例，特别是填空形式的知识探测和摘要。

提示工程，也称为上下文学习，是指通过精心设计的提示技术引导大型语言模型（LLM）的行为，而无需更改模型权重。其目标是使模型输出与给定任务的人类意图对齐。通过设计良好的提示模板，模型可以取得强大的结果，有时可与微调相媲美。但是好的提示看起来是什么样的呢？

### 提示的结构

提示由三个主要组成部分组成：

+   描述任务要求、目标和输入/输出格式的指令

+   展示所需输入-输出对的示例

+   模型必须对其进行操作以生成输出的输入

说明清楚任务给模型解释。示例提供了不同输入应该如何映射到输出的多样演示。输入是模型必须概括的内容。基本提示方法包括仅使用输入文本的零-shot 提示，以及使用几个演示示例显示所需的输入-输出对的少-shot 提示。研究人员已经确定了像多数标签偏见和最近性偏见这样的偏见，这些偏见导致了少-shot 性能的变化。通过示例选择、排序和格式化的仔细提示设计可以帮助减轻这些问题。更高级的提示技术包括指令提示，其中任务要求被明确描述而不仅仅是演示。自一致性抽样生成多个输出并选择与示例最匹配的输出。思维链 (CoT) 提示生成导致最终输出的明确推理步骤。这对于复杂的推理任务特别有益。CoT 提示可以手动编写，也可以通过增强-修剪-选择等方法自动生成。这张表简要概述了几种提示方法与微调的比较：

| **技术** | **方法** | **关键思想** | **结果** |
| --- | --- | --- | --- |
| 微调 | 在通过提示生成的解释数据集上进行微调 | 提高模型的推理能力 | 在常识 QA 数据集上达到 73%的准确率 |
| 零-shot 提示 | 简单地将任务文本输入模型并要求结果。 | 文本："我敢打赌视频游戏比电影更有趣。"<br>- 情感： |  |
| 思维链 (CoT) | 在响应前加上"让我们一步一步地思考" | 在回答之前给模型推理的空间 | 在数学数据集上将准确率提高了四倍 |
| 少-shot 提示 | 提供少量演示，包括输入和期望的输出，以帮助模型理解 | 显示所需的推理格式 | 在小学数学上将准确率提高了三倍 |
| 由浅入深提示 | 逐步提示模型解决更简单的子任务。"要解决{问题}，我们首先需要解决：" | 将问题分解成较小的部分 | 在某些任务上，将准确率从 16%提高到 99.7% |
| 选择-推理提示 | 交替选择和推理提示 | 引导模型进行推理步骤 | 提高了长推理任务的表现 |
| 自一致性 | 从多个样本中选择最频繁的答案 | 增加冗余性 | 在各项基准测试中获得了 1-24 个百分点的提升 |
| 验证器 | 训练单独的模型来评估响应 | 过滤掉不正确的响应 | 将小学数学准确率提高了约 20 个百分点 |

图 8.6：LLM 的提示技术。

一些提示技术结合外部信息检索，在生成输出之前为 LLM 提供缺失的上下文。对于开放领域的问答，可以通过搜索引擎检索相关段落并纳入提示中。对于封闭书籍问答，具有证据-问题-答案格式的少样本示例比问题-答案格式效果更好。有不同的技术可以提高大型语言模型（LLMs）在复杂推理任务中的可靠性：

1.  提示和解释：在回答之前，提示模型逐步解释其推理过程，使用类似“让我们逐步思考”（如 CoT 中）的提示显著提高推理任务的准确性。

1.  提供推理链的少样本示例有助于展示所需的格式，并指导 LLMs 生成连贯的解释。

1.  交替选择和推理提示：利用专门的选择提示（缩小答案空间）和推理提示（生成最终响应）的组合，与仅使用通用推理提示相比，可以获得更好的结果。

1.  问题分解：将复杂问题分解为较小的子任务或组件，使用从最少到最多的提示方法有助于提高可靠性，因为这样可以实现更有结构和可管理的问题解决过程。

1.  采样多个响应：在生成过程中从 LLMs 中采样多个响应，并选择最常见的答案，可以增加一致性，减少对单一输出的依赖。特别是训练单独的验证器模型，评估 LLMs 生成的候选响应，有助于过滤出不正确或不可靠的答案，提高整体可靠性。

最后，通过提示生成的解释数据集对 LLMs 进行微调可以增强它们在推理任务中的性能和可靠性。

> **少样本学习**向 LLM 提供与任务相关的少量输入-输出示例，而无需明确说明。这使模型能够纯粹从演示中推断出意图和目标。精心选择、排序和格式化的示例可以极大地提高模型的推理能力。然而，少样本学习可能容易受到偏见和试验间的变异性影响。添加明确的说明可以使意图对模型更加透明，并提高鲁棒性。总的来说，提示结合了指令和示例的优势，以最大程度地引导 LLM 完成手头任务。

自动提示调整等方法不是手工设计提示，而是通过直接优化嵌入空间上的前缀标记来学习最佳提示。目标是在给定输入的情况下增加期望输出的可能性。总的来说，提示工程是一个活跃的研究领域，用于使大型预训练 LLM 与人类意图在各种任务上保持一致。精心设计的提示可以引导模型而无需昂贵的重新训练。在本节中，我们将介绍之前提到的一些（但不是全部）技术。让我们讨论 LangChain 提供的用 Python 创建提示模板的工具！

### 模板化

提示是我们提供给语言模型的指令和示例，以引导它们的行为。提示模板化指的是创建可配置不同参数的提示的可重用模板。LangChain 提供了用 Python 创建提示模板的工具。模板允许使用变量输入动态生成提示。我们可以创建一个基本的提示模板如下：

```
from langchain import PromptTemplate
prompt = PromptTemplate("Tell me a {adjective} joke about {topic}")
```

这个模板有两个输入变量 - {形容词} 和 {主题}。我们可以用值格式化这些变量：

```
prompt.format(adjective="funny", topic="chickens")
# Output: "Tell me a funny joke about chickens"
```

模板格式默认为 Python f-strings，但也支持 Jinja2。提示模板可以组合成管道，其中一个模板的输出作为下一个模板的输入。这样可以实现模块化重用。

#### 聊天提示模板

对于对话代理，我们需要聊天提示模板：

```
from langchain.prompts import ChatPromptTemplate 
template = ChatPromptTemplate.from_messages([
  ("human", "Hello, how are you?"),
  ("ai", "I am doing great, thanks!"),
  ("human", "{user_input}"),
])
template.format_messages(user_input="What is your name?")
```

这将格式化一系列聊天消息而不是一个字符串。这对考虑对话历史非常有用。我们在第五章中看过不同的记忆方法。在这种情况下，这些方法同样相关，以确保模型输出相关且切题。提示模板化可以实现可重用、可配置的提示。LangChain 提供了一个 Python API，方便地创建模板并动态格式化它们。模板可以组合成管道以实现模块化。高级提示工程可以进一步优化提示。

### 高级提示工程

LangChain 提供了工具，以实现像少样本学习、动态示例选择和链式推理等高级提示工程策略。

#### 少样本学习

`FewShotPromptTemplate`允许向模型展示任务的几个示例以引导它，而无需明确的指令。例如：

```
from langchain.prompts import FewShotPromptTemplate, PromptTemplate 
example_prompt = PromptTemplate("{input} -> {output}")
examples = [
  {"input": "2+2", "output": "4"},
  {"input": "3+3", "output": "6"}
]
prompt = FewShotPromptTemplate(
  examples=examples,
  example_prompt=example_prompt
)
```

模型必须仅从示例中推断出该做什么。

#### 动态示例选择

为了选择针对每个输入量身定制的示例，`FewShotPromptTemplate`可以接受一个`ExampleSelector`而不是硬编码的示例：

```
from langchain.prompts import SemanticSimilarityExampleSelector
selector = SemanticSimilarityExampleSelector(...) 
prompt = FewShotPromptTemplate(
   example_selector=selector,
   example_prompt=example_prompt
)
```

`SemanticSimilarityExampleSelector`等`ExampleSelector`实现可以自动找到每个输入最相关的示例。

#### 链式推理

当要求 LLM 通过一个问题进行推理时，通常更有效的做法是在陈述最终答案之前让它解释其推理过程。例如：

```
from langchain.prompts import PromptTemplate
reasoning_prompt = "Explain your reasoning step-by-step. Finally, state the answer: {question}"
prompt = PromptTemplate(
  reasoning_prompt=reasoning_prompt,
  input_variables=["questions"]
)
```

这鼓励 LLM 首先通过逻辑方式思考问题，而不是仅仅猜测答案，然后试图在之后证明。这被称为**零射链思维**。要求 LLM 解释其思维过程与其核心能力非常契合。**少射链思维**提示是一个少射提示，其中推理作为示例解决方案的一部分进行解释，旨在鼓励 LLM 在做出决定之前解释其推理。已经证明这种提示可以导致更准确的结果，然而，这种性能提升发现与模型的大小成正比，而在较小的模型中，改进似乎是微不足道的，甚至是负面的。在**思维树（ToT）**提示中，我们生成多个解决问题的步骤或方法，然后使用 AI 模型对这些步骤进行批判。批判将基于模型对解决方案适应问题的判断。让我们通过使用 LangChain 实现 ToT 的更详细示例来走一遍。首先，我们将使用`PromptTemplates`定义我们的 4 个链组件。我们需要一个解决方案模板，一个评估模板，一个推理模板和一个排名模板。让我们首先生成解决方案：

```
solutions_template = """
Generate {num_solutions} distinct solutions for {problem}. Consider factors like {factors}.
Solutions:
"""
solutions_prompt = PromptTemplate(
   template=solutions_template,
   input_variables=["problem", "factors", "num_solutions"]
)
```

让我们要求 LLM 评估这些解决方案：

```
evaluation_template = """
Evaluate each solution in {solutions} by analyzing pros, cons, feasibility, and probability of success.
Evaluations:
"""
evaluation_prompt = PromptTemplate(
  template=evaluation_template,
  input_variables=["solutions"]  
)
```

现在我们将对它们进行更多的推理：

```
reasoning_template = """
For the most promising solutions in {evaluations}, explain scenarios, implementation strategies, partnerships needed, and handling potential obstacles. 
Enhanced Reasoning: 
"""
reasoning_prompt = PromptTemplate(
  template=reasoning_template,
  input_variables=["evaluations"]
)
```

最后，根据我们迄今为止的推理，我们可以对这些解决方案进行排名：

```
ranking_template = """
Based on the evaluations and reasoning, rank the solutions in {enhanced_reasoning} from most to least promising.
Ranked Solutions:
"""
ranking_prompt = PromptTemplate(
  template=ranking_template, 
  input_variables=["enhanced_reasoning"]
)
```

接下来，我们在将所有内容放在一起之前从这些模板中创建链：

```
chain1 = LLMChain(
   llm=SomeLLM(),
   prompt=solutions_prompt,
   output_key="solutions"  
)
chain2 = LLMChain(
   llm=SomeLLM(),
   prompt=evaluation_prompt,
   output_key="evaluations"
)
```

最后，我们将这些链连接成一个`SequentialChain`：

```
tot_chain = SequentialChain(
   chains=[chain1, chain2, chain3, chain4],
   input_variables=["problem", "factors", "num_solutions"], 
   output_variables=["ranked_solutions"]
)
tot_chain.run(
   problem="Prompt engineering",
   factors="Requirements for high task performance, low token use, and few calls to the LLM",
   num_solutions=3
)
```

这使我们能够在推理过程的每个阶段利用 LLM。ToT 方法有助于通过促进探索来避免死胡同。这些技术共同增强了大型语言模型在复杂任务上的推理能力的准确性、一致性和可靠性，提供更清晰的指导，通过有针对性的数据微调，采用问题分解策略，融合多样的抽样方法，整合验证机制，并采用概率建模框架。提示设计对于释放 LLM 的推理能力、模型和提示技术未来进展的潜力以及这些原则和技术对于与大型语言模型一起工作的研究人员和从业者来说都是非常重要的。让我们总结一下！

## 摘要

在第一章中，我们讨论了生成模型的基本原理，特别是 LLMs 及其训练。我们主要关注预训练步骤，通常是调整模型以适应单词和更广泛文本段之间的相关性。对齐是评估模型输出与期望之间的关系，而调节是确保输出符合期望的过程。调节允许引导生成式 AI 以提高安全性和质量，但这并不是一个完整的解决方案。在本章中，重点是调节，特别是通过微调和提示。在微调中，语言模型被训练在许多任务示例上，这些任务被制定为自然语言指令，以及适当的回应。通常这是通过强化学习与人类反馈（RLHF）来完成的，其中包括在人类生成的数据集上进行训练（提示，回应）对，然后通过人类反馈进行强化学习，然而，已经开发出其他技术，已经显示出具有较低资源占用的竞争性结果。在本章的第一个示例中，我们实现了一个用于问答的小型开源模型的微调。有许多技术可以提高 LLMs 在复杂推理任务中的可靠性，包括逐步提示，备选选择和推理提示，问题分解，多个响应的采样，以及使用单独的验证器模型。这些方法已经显示出在推理任务中提高准确性和一致性。我们已经讨论并比较了几种技术。LangChain 提供了解锁高级提示策略的构建模块，如少样本学习，动态示例选择和链式推理分解，正如我们在示例中展示的那样。精心设计的提示工程是将语言模型与复杂目标对齐的关键。通过分解问题并添加冗余性可以提高推理的可靠性。我们在本章中讨论的原则和技术为与 LLMs 一起工作的专家提供了工具包。我们可以期待模型训练和提示技术的未来进展。随着这些方法和 LLMs 的持续发展，它们很可能会变得更加有效和有用，适用于更广泛的应用领域。让我们看看你是否记得本章的一些关键要点！

## 问题

请看看你是否能够凭记忆回答这些问题。如果你对任何问题不确定，我建议你回到本章的相应部分查看：

1.  在 LLMs 的背景下，什么是对齐？

1.  有哪些不同的调节方法，我们如何区分它们？

1.  调节与调节有什么关系？

1.  什么是指令调整，它的重要性是什么？

1.  什么是量化？

1.  有哪些微调的方法？

1.  什么是少样本学习？

1.  什么是思维链提示？

1.  解释一下思维树提示！
