# 9 生产中的生成式人工智能

## 加入我们的书籍社区Discord

[https://packt.link/EarlyAccessCommunity](https://packt.link/EarlyAccessCommunity)

![自动生成的二维码描述](../media/file58.png)

在本书中，我们已经讨论了模型、代理和LLM应用程序以及不同的用例，但是在确保性能和监管要求时，模型和应用程序需要大规模部署，最终需要进行监控时，许多问题变得重要。在本章中，我们将讨论评估和可观察性，总结涵盖操作化人工智能和决策模型的治理和生命周期管理的广泛主题，包括生成式人工智能模型。虽然离线评估在受控环境中提供了对模型能力的初步理解，但在生产中的可观察性提供了对其在实时环境中性能的持续洞察。在模型生命周期的不同阶段，两者都至关重要，并相互补充，以确保大型语言模型的最佳运行和结果。我们将讨论一些工具，以及为每种情况提供示例。我们还将讨论围绕LLMs构建的模型和应用程序的部署，概述可用工具和使用Fast API和Ray Serve进行部署的示例。在本章中，我们将使用LLMs进行...，您可以在书的GitHub存储库中找到[https://github.com/benman1/generative_ai_with_langchain](https://github.com/benman1/generative_ai_with_langchain)。本章的主要部分包括：

+   介绍

+   如何评估您的LLM应用程序？

+   如何部署您的LLM应用程序？

+   如何观察您的LLM应用程序？

让我们首先介绍MLOps对LLMs和其他生成模型的意义和内容。

## 介绍

正如我们在本书中讨论的那样，由于其生成类似人类文本的能力，LLMs近年来引起了广泛关注。从创意写作到对话聊天机器人，这些生成式人工智能模型在各行各业都有多样化的应用。然而，将这些复杂的神经网络系统从研究转化为实际部署面临着重大挑战。本章探讨了负责任地将生成式人工智能投入生产的实际考虑和最佳实践。我们讨论了推理和服务的计算要求，优化技术，以及围绕数据质量、偏见和透明度的关键问题。当扩展到成千上万的用户时，架构和基础设施决策可能会成败一事。同时，保持严格的测试、审计和道德保障对于可信赖的部署至关重要。在生产中部署由模型和代理组成的应用程序及其工具会带来几个关键挑战，需要解决以确保其有效和安全的使用：

+   **数据质量和偏见**：训练数据可能引入偏见，反映在模型输出中。仔细的数据筛选和监控模型输出至关重要。

+   **伦理/合规考虑**：LLMs可能生成有害、偏见或误导性内容。必须建立审查流程和安全指南以防止滥用。遵守专业行业如医疗保健中的HIPAA等法规。

+   **资源需求**：LLMs需要大量计算资源进行训练和服务。高效的基础设施对于成本效益的规模化部署至关重要。

+   **漂移或性能下降**：模型需要持续监控以检测数据漂移或随时间性能下降等问题。

+   **缺乏可解释性**：LLMs通常是黑匣子，使其行为和决策不透明。解释性工具对于透明度至关重要。

将经过训练的LLM从研究转化为实际生产中涉及许多复杂挑战，如可扩展性、监控和意外行为。负责地部署能力强大但不可靠的模型需要围绕可扩展性、可解释性、测试和监控进行认真规划。微调、安全干预和防御性设计等技术使开发出的应用程序既有益又无害、诚实。通过慎重准备，生成式人工智能有巨大潜力造福从医学到教育等各行各业。以下几种关键模式可以帮助解决上述挑战：

+   **评估**：坚实的基准数据集和指标对于衡量模型能力、回归和与目标的一致性至关重要。指标应根据任务仔细选择。

+   **检索增强**：检索外部知识提供有用的背景信息，以减少幻觉并添加超出预训练数据的最新信息。

+   **微调**：在任务特定数据上进一步调整LLMs可以提高目标用例的性能。像适配器模块这样的技术可以减少开销。

+   **缓存**：存储模型输出可以显著降低重复查询的延迟和成本。但缓存有效性需要仔细考虑。

+   **防护栏**：通过语法和语义验证模型输出确保可靠性。指导技术直接塑造输出结构。

+   **防御性用户体验**：设计以预期不准确性，如限制声明、归因和收集丰富的用户反馈。

+   **监控**：持续跟踪指标、模型行为和用户满意度可提供对模型问题和业务影响的洞察。

在第5章中，我们已经涵盖了类似宪法AI这样的安全对齐技术，用于减轻生成有害输出等风险。此外，LLMs有可能生成有害或误导性内容。建立道德准则和审查流程以防止误传信息、仇恨言论或任何其他有害输出是至关重要的。人类审阅员在评估和过滤生成内容方面可以发挥关键作用，以确保符合道德标准。不仅出于法律、道德和声誉原因，还为了保持性能，我们需要持续评估模型性能和输出，以便检测数据漂移或能力丧失等问题。我们将讨论解释模型行为和决策的技术。提高高风险领域的透明度。由于LLMs或生成式AI模型的规模和复杂性，部署需要大量的计算资源。这包括高性能硬件，如GPU或TPU，以处理涉及的大量计算。由于其资源密集性质，扩展大型语言模型或生成式AI模型可能具有挑战性。随着模型规模的增加，训练和推断的计算要求也呈指数增长。分布式技术，如数据并行或模型并行，通常用于在多台机器或GPU之间分配工作负载。这可以加快训练和推断时间。扩展还涉及管理与这些模型相关的大量数据的存储和检索。需要高效的数据存储和检索系统来处理庞大的模型大小。部署还涉及考虑优化推断速度和延迟的问题。可以采用模型压缩、量化或硬件特定优化等技术来确保高效部署。我们在*第8章*中讨论了其中一些内容。LLMs或生成式AI模型通常被认为是黑盒，这意味着很难理解它们是如何做出决策或生成输出的。解释性技术旨在提供对这些模型内部运作的洞察。这可能涉及注意力可视化、特征重要性分析或为模型输出生成解释等方法。在透明度和问责制重要的领域，如医疗保健、金融或法律系统中，解释性至关重要。正如我们在*第8章*中讨论的，大型语言模型可以在特定任务或领域上进行微调，以提高在特定用例上的性能。迁移学习允许模型利用预训练知识并将其调整到新任务。在领域特定数据上进行迁移学习和微调可以解锁新的用例，同时需要额外的谨慎。通过深思熟虑的规划和准备，生成式AI承诺将各行业从创意写作到客户服务进行转型。但在这些系统继续渗透各个领域的同时，深思熟虑地应对这些系统的复杂性仍然至关重要。本章旨在为团队提供一个实用指南，以填补我们迄今为止遗漏的部分，旨在构建有影响力和负责任的生成式AI应用程序。我们提到了数据筛选、模型开发、基础设施、���控和透明度的策略。在我们继续讨论之前，我们需要谈谈术语问题。

### 术语

**MLOps** 是一个关注在生产环境中可靠高效地部署和维护机器学习模型的范式。它将DevOps的实践与机器学习结合起来，将算法从实验系统过渡到生产系统。MLOps旨在增加自动化，提高生产模型的质量，并解决业务和监管要求。**LLMOps** 是MLOps的一个专门子类别。它指的是为产品的一部分对大型语言模型进行微调和操作所需的操作能力和基础设施。虽然它可能与MLOps的概念并没有明显不同，但区别在于与处理、改进和部署像GPT-3这样拥有1750亿参数的大型语言模型相关的具体要求。术语**LMOps**比LLMOps更具包容性，因为它涵盖了各种类型的语言模型，包括大型语言模型和较小的生成模型。这个术语承认了语言模型及其在操作环境中的相关性的不断扩大。**FOMO（基础模型编排）**专门解决了在使用基础模型时面临的挑战。它强调了管理多步骤流程、与外部资源集成以及协调涉及这些模型的工作流程的需求。术语**ModelOps**侧重于AI和决策模型在部署时的治理和生命周期管理。更广泛地说，**AgentOps**涉及对LLMs和其他AI代理的操作管理，确保它们的适当行为，管理它们的环境和资源访问，并促进代理之间的互动，同时解决与意外结果和不兼容目标相关的问题。虽然FOMO强调了专门处理基础模型时面临的独特挑战，但LMOps提供了对超出基础模型范围的更广泛语言模型的更具包容性和全面覆盖。LMOps承认了语言模型在各种操作用例中的多功能性和日益重要性，同时仍属于更广泛的MLOps范畴。最后，AgentOps明确强调了由具有一定启发式的生成模型组成的代理的互动性质，并包括工具。所有这些非常专业化的术语的出现突显了该领域的快速发展；然而，它们的长期普及尚不清楚。MLOps是一个在行业中广泛使用、得到认可和采用的已建立术语。因此，在本章的其余部分，我们将坚持使用MLOps。在将任何代理或模型投入生产之前，我们应该首先评估其输出，因此我们应该从这开始。我们将重点关注LangChain提供的评估方法。

## 如何评估您的LLM应用程序？

评估LLMs作为独立实体或与代理链结合的重要性在于确保它们正常运行并产生可靠结果，这是机器学习生命周期的一个组成部分。 评估过程确定模型在效率、可靠性和效率方面的性能。 评估大型语言模型的目标是了解它们的优势和劣势，提高准确性和效率，减少错误，从而最大限度地提高它们在解决实际问题中的有用性。 这个评估过程通常在开发阶段离线进行。 离线评估在受控测试条件下提供了模型性能的初步见解，并包括超参数调整、与同行模型或已建立标准的基准测试等方面。 它们为部署之前对模型进行改进提供了必要的第一步。评估提供了关于LLM能够生成相关、准确和有用输出的见解。 在LangChain中，有各种评估LLMs输出的方法，包括比较链输出、成对字符串比较、字符串距离和嵌入距离。 评估结果可用于根据输出的比较确定首选模型。 还可以计算置信区间和p值来评估评估结果的可靠性。 LangChain提供了几种工具来评估大型语言模型的输出。 一个常见的方法是使用`PairwiseStringEvaluator`比较不同模型或提示的输出。 这促使评估模型在相同输入下选择两个模型输出之间的首选输出，并汇总结果以确定整体首选模型。其他评估器允许根据特定标准（如正确性、相关性和简洁性）评估模型输出。 `CriteriaEvalChain`可以根据自定义或预定义原则对输出进行评分，而无需参考标签。 还可以通过指定不同的聊天模型（如ChatGPT）来配置评估模型。让我们使用`PairwiseStringEvaluator`比较不同提示或LLMs的输出，这促使LLM在给定特定输入时选择首选输出。

### 比较两个输出

此评估需要一个评估器、一个输入数据集以及两个或更多的LLMs、链条或代理程序进行比较。 评估将汇总结果以确定首选模型。评估过程涉及几个步骤：

1.  创建评估器：使用`load_evaluator()`函数加载评估器，指定评估器类型（在本例中为`pairwise_string`）。

1.  选择数据集：使用`load_dataset()`函数加载输入数据集。

1.  定义要比较的模型：使用必要的配置初始化要比较的LLMs、链条或代理程序。 这涉及初始化语言模型以及任何其他所需的工具或代理程序。

1.  生成响应：为每个模型生成输出，然后再对其进行评估。这通常是批量进行的，以提高效率。

1.  评估对：通过比较不同模型的输出来评估结果，针对每个输入。通常使用随机选择顺序来减少位置偏见。

这里有一个来自成对字符串比较文档的示例：

```
from langchain.evaluation import load_evaluator
evaluator = load_evaluator("labeled_pairwise_string")
evaluator.evaluate_string_pairs(
    prediction="there are three dogs",
    prediction_b="4",
    input="how many dogs are in the park?",
    reference="four",
)
```

评估器的输出应如下所示：

```
 {'reasoning': 'Both responses are relevant to the question asked, as they both provide a numerical answer to the question about the number of dogs in the park. However, Response A is incorrect according to the reference answer, which states that there are four dogs. Response B, on the other hand, is correct as it matches the reference answer. Neither response demonstrates depth of thought, as they both simply provide a numerical answer without any additional information or context. \n\nBased on these criteria, Response B is the better response.\n',
     'value': 'B',
     'score': 0}
```

评估结果包括一个介于0和1之间的分数，表示代理的有效性，有时还包括概述评估过程并证明分数的推理。在这个根据参考的示例中，基于输入，两个结果都事实上是不正确的。我们可以删除参考并让LLM判断输出，但这可能是危险的，因为指定的内容也可能是不正确的。

### 根据标准进行比较

LangChain为不同的评估标准提供了几个预定义的评估器。这些评估器可以用于根据特定的规则或标准集来评估输出。一些常见的标准包括简洁性、相关性、正确性、连贯性、实用性和争议性。`CriteriaEvalChain`允许您根据自定义或预定义的标准评估模型输出。它提供了一种验证LLM或Chain的输出是否符合一组定义的标准的方法。您可以使用这个评估器来评估正确性、相关性、简洁性和生成输出的其他方面。`CriteriaEvalChain`可以配置为使用或不使用参考标签。没有参考标签时，评估器依赖于LLM的预测答案，并根据指定的标准对其进行评分。有了参考标签，评估器将预测答案与参考标签进行比较，并确定其是否符合标准。LangChain中使用的评估LLM默认为GPT-4。但是，您可以通过指定其他聊天模型（例如ChatAnthropic或ChatOpenAI）以及所需的设置（例如温度）来配置评估LLM。通过将LLM对象作为参数传递给`load_evaluator()`函数，可以加载自定义LLM的评估器。LangChain支持自定义标准和预定义评估原则。可以使用`criterion_name: criterion_description`对的字典定义自定义标准。这些标准可以用于根据特定要求或规则评估输出。这里是一个简单的例子：

```
custom_criteria = {
    "simplicity": "Is the language straightforward and unpretentious?",
    "clarity": "Are the sentences clear and easy to understand?",
    "precision": "Is the writing precise, with no unnecessary words or details?",
    "truthfulness": "Does the writing feel honest and sincere?",
    "subtext": "Does the writing suggest deeper meanings or themes?",
}
evaluator = load_evaluator("pairwise_string", criteria=custom_criteria)
evaluator.evaluate_string_pairs(
    prediction="Every cheerful household shares a similar rhythm of joy; but sorrow, in each household, plays a unique, haunting melody.",
    prediction_b="Where one finds a symphony of joy, every domicile of happiness resounds in harmonious,"
    " identical notes; yet, every abode of despair conducts a dissonant orchestra, each"
    " playing an elegy of grief that is peculiar and profound to its own existence.",
    input="Write some prose about families.",
)
```

我们可以通过这个结果得到两个输出的非常微妙的比较：

```
{'reasoning': 'Response A is simple, clear, and precise. It uses straightforward language to convey a deep and sincere message about families. The metaphor of music is used effectively to suggest deeper meanings about the shared joys and unique sorrows of families.\n\nResponse B, on the other hand, is less simple and clear. The language is more complex and pretentious, with phrases like "domicile of happiness" and "abode of despair" instead of the simpler "household" used in Response A. The message is similar to that of Response A, but it is less effectively conveyed due to the unnecessary complexity of the language.\n\nTherefore, based on the criteria of simplicity, clarity, precision, truthfulness, and subtext, Response A is the better response.\n\n[[A]]', 'value': 'A', 'score': 1}
```

或者，您可以使用LangChain中提供的预定义原则，例如来自Constitutional AI的原则。这些原则旨在评估输出的道德、有害和敏感方面。在评估中使用原则可以更加专注地评估生成的文本。

### 字符串和语义比较

LangChain支持字符串比较和距离度量，用于评估LLM输出。像Levenshtein和Jaro这样的字符串距离度量提供了预测和参考字符串之间相似性的定量度量。使用类似SentenceTransformers这样的模型的嵌入距离计算生成和预期文本之间的语义相似性。嵌入距离评估器可以使用嵌入模型，例如基于GPT-4或Hugging Face嵌入的模型，计算预测和参考字符串之间的向量距离。这测量了两个字符串之间的语义相似性，并可以提供有关生成文本质量的见解。以下是文档中的一个快速示例：

```
from langchain.evaluation import load_evaluator
evaluator = load_evaluator("embedding_distance")
evaluator.evaluate_strings(prediction="I shall go", reference="I shan't go")
```

评估器返回得分0.0966466944859925。您可以在`load_evaluator()`调用中使用`embeddings`参数更改所使用的嵌入。这通常比旧的字符串距离度量方法效果更好，但这些方法也可用，并且允许进行简单的单元测试和准确性评估。字符串比较评估器将预测字符串与参考字符串或输入进行比较。字符串距离评估器使用距离度量，例如Levenshtein或Jaro距离，来衡量预测字符串与参考字符串之间的相似性或不相似性。这提供了一个量化的度量，用于衡量预测字符串与参考字符串之间的相似程度。最后，还有一个代理轨迹评估器，其中使用`evaluate_agent_trajectory()`方法来评估输入、预测和代理轨迹。我们还可以使用LangSmith来将我们的性能与数据集进行比较。我们将在关于可观察性部分更详细地讨论这个LangChain的伴随项目LangSmith。

### 基准数据集

使用LangSmith，我们可以评估模型在数据集上的性能。让我们通过一个示例来了解。首先，请确保您在LangSmith上创建一个帐户：[https://smith.langchain.com/](https://smith.langchain.com/) 您可以获取一个API密钥，并将其设置为环境中的`LANGCHAIN_API_KEY`。我们还可以为项目id和跟踪设置环境变量：

```
import os
os.environ["LANGCHAIN_TRACING_V2"] = "true"
os.environ["LANGCHAIN_PROJECT"] = "My Project"
```

这将配置LangChain记录跟踪。如果我们不告诉LangChain项目id，它将记录到`default`项目。设置完成后，当我们运行LangChain代理或链时，我们将能够在LangSmith上看到跟踪。让我们记录一个运行！

```
from langchain.chat_models import ChatOpenAI
llm = ChatOpenAI()
llm.predict("Hello, world!")
```

我们将在LangSmith上看到这样：LangSmith允许我们在LangSmith项目页面上列出到目前为止的所有运行：[https://smith.langchain.com/projects](https://smith.langchain.com/projects)

```
from langsmith import Client
client = Client()
runs = client.list_runs()
print(runs)
```

我们可以按照特定项目或`run_type`列出运行，例如“chain”。每次运行都有输入和输出，就像我们在这里看到的一样：

```
print(f"inputs: {runs[0].inputs}")
print(f"outputs: {runs[0]. outputs}")
```

我们可以使用`create_example_from_run()`函数从现有代理运行创建数据集，或者从其他任何地方创建数据集。以下是如何使用一组问题创建数据集：

```
questions = [
    "A ship's parts are replaced over time until no original parts remain. Is it still the same ship? Why or why not?",  # The Ship of Theseus Paradox
    "If someone lived their whole life chained in a cave seeing only shadows, how would they react if freed and shown the real world?",  # Plato's Allegory of the Cave
    "Is something good because it is natural, or bad because it is unnatural? Why can this be a faulty argument?",  # Appeal to Nature Fallacy
    "If a coin is flipped 8 times and lands on heads each time, what are the odds it will be tails next flip? Explain your reasoning.",  # Gambler's Fallacy
    "Present two choices as the only options when others exist. Is the statement \"You're either with us or against us\" an example of false dilemma? Why?",  # False Dilemma
    "Do people tend to develop a preference for things simply because they are familiar with them? Does this impact reasoning?",  # Mere Exposure Effect
    "Is it surprising that the universe is suitable for intelligent life since if it weren't, no one would be around to observe it?",  # Anthropic Principle
    "If Theseus' ship is restored by replacing each plank, is it still the same ship? What is identity based on?",  # Theseus' Paradox
    "Does doing one thing really mean that a chain of increasingly negative events will follow? Why is this a problematic argument?",  # Slippery Slope Fallacy
    "Is a claim true because it hasn't been proven false? Why could this impede reasoning?",  # Appeal to Ignorance
]
shared_dataset_name = "Reasoning and Bias"
ds = client.create_dataset(
    dataset_name=shared_dataset_name, description="A few reasoning and cognitive bias questions",
)
for q in questions:
    client.create_example(inputs={"input": q}, dataset_id=ds.id)
```

然后我们可以像这样在数据集上运行LLM代理或链：

```
from langchain.chat_models import ChatOpenAI
from langchain.chains import LLMChain
llm = ChatOpenAI(model="gpt-4", temperature=0.0)
def construct_chain():
    return LLMChain.from_string(
        llm,
        template="Help out as best you can.\nQuestion: {input}\nResponse: ",
    )
```

我们使用构造函数为每个输入初始化。为了评估模型在这个数据集上的性能，我们需要像在前一节中看到的那样定义一个评估器。

```
from langchain.evaluation import EvaluatorType
from langchain.smith import RunEvalConfig
evaluation_config = RunEvalConfig(
    evaluators=[
        # Arbitrary criterion as a key: value pair in the criteria dict:
        RunEvalConfig.Criteria({"helpfulness": "Is the response helpful?"}),
        RunEvalConfig.Criteria({"insightful": "Is the response carefully thought out?"})
    ]
)
```

我们将传递数据集和评估器给`run_on_dataset()`以生成指标和反馈：

```
from langchain.smith import run_on_dataset
results = run_on_dataset(
  client=client,
  dataset=dataset,
  llm_factory=lambda: my_agent, 
  evaluation=evaluation_config
)
```

同样，我们可以将数据集和评估器传递给`arun_on_dataset()`以异步生成指标和反馈。我们可以在LangSmith UI中查看评估器反馈，以确定改进的方向：

![图9.1：LangSmith中的评估器。](../media/file59.png)

图9.1：LangSmith中的评估器。

点击任何一个评估项，我们可以查看一些详细信息，例如，对于仔细思考评估器，我们得到了这个提示，其中包括LLM的原始答案：

```
You are assessing a submitted answer on a given task or input based on a set of criteria. Here is the data:
[BEGIN DATA]
***
[Input]: Is something good because it is natural, or bad because it is unnatural? Why can this be a faulty argument?
***
[Submission]: The argument that something is good because it is natural, or bad because it is unnatural, is often referred to as the "appeal to nature" fallacy. This argument is faulty because it assumes that what is natural is automatically good or beneficial, and what is unnatural is automatically bad or harmful. However, this is not always the case. For example, many natural substances can be harmful or deadly, such as certain plants or animals. Conversely, many unnatural things, such as modern medicine or technology, can greatly benefit our lives. Therefore, whether something is natural or unnatural is not a reliable indicator of its value or harm.
***
[Criteria]: insightful: Is the response carefully thought out?
***
[END DATA]
Does the submission meet the Criteria? First, write out in a step by step manner your reasoning about each criterion to be sure that your conclusion is correct. Avoid simply stating the correct answers at the outset. Then print only the single character "Y" or "N" (without quotes or punctuation) on its own line corresponding to the correct answer of whether the submission meets all criteria. At the end, repeat just the letter again by itself on a new line.
```

我们得到了这个评估：

```
The criterion is whether the response is insightful and carefully thought out. 
The submission provides a clear and concise explanation of the "appeal to nature" fallacy, demonstrating an understanding of the concept. It also provides examples to illustrate why this argument can be faulty, showing that the respondent has thought about the question in depth. The response is not just a simple yes or no, but a detailed explanation that shows careful consideration of the question. 
Therefore, the submission does meet the criterion of being insightful and carefully thought out.
Y
Y
```

提高少数问题类型性能的一种方法是进行少量提示。LangSmith也可以帮助我们。您可以在LangSmith文档中找到更多关于此的示例。这结束了评估。现在我们已经评估了我们的代理，假设我们对性能感到满意并部署它！

## 如何部署您的LLM应用程序？

鉴于LLMs在各个领域的不断增加使用，了解如何有效地将模型和应用程序部署到生产中至关重要。部署服务和框架可以帮助克服技术障碍。有许多不同的方法可以将LLM应用程序或具有生成式AI的应用程序投入生产。生产部署需要对生成式AI生态系统进行研究和了解，其中包括不同方面，包括：

+   模型和LLM作为服务：LLMs和其他模型可以直接运行或作为API提供在供应商提供的基础设施上。

+   推理启发式：检索增强生成（RAG），思维树等。

+   向量数据库：帮助检索与提示相关的上下文信息。

+   提示工程工具：这些工具有助于在上下文中学习，而无需昂贵的微调或敏感数据。

+   预训练和微调：针对特定任务或领域专门化的模型。

+   提示记录、测试和分析：受到了对了解和改进大型语言模型性能的愿望的启发而出现的新兴领域。

+   自定义LLM堆栈：一组工具，用于塑造和部署基于开源模型构建的解决方案。

我们在 *第1章* 和 *第3章* 中讨论了模型，在第4-7章中讨论了推理启发式，在第5章中讨论了向量数据库，在 *第8章* 中讨论了提示和微调。在本章中，我们将专注于部署的日志记录、监控和自定义工具。通常使用外部 LLM 提供商或自托管模型来利用 LLM。通过外部提供商，计算负担由公司如 OpenAI 或 Anthropic 承担，而 LangChain 促进了业务逻辑的实现。然而，自托管开源 LLM 可以显著降低成本、延迟和隐私问题。一些基础设施工具提供完整的解决方案。例如，您可以使用 Chainlit 部署 LangChain 代理，创建类似 ChatGPT 的 UI。一些关键功能包括中间步骤可视化、元素管理和显示（图像、文本、轮播图等）以及云部署。BentoML 是一个框架，可以将机器学习应用程序容器化，以便将它们用作独立运行和扩展的微服务，并自动生成 OpenAPI 和 gRPC 端点。您还可以将 LangChain 部署到不同的云服务端点，例如 Azure 机器学习在线端点。使用 Steamship，LangChain 开发人员可以快速部署他们的应用程序，其中包括：生产就绪的端点、跨依赖项的水平扩展、应用程序状态的持久存储、多租户支持等。以下是总结部署大型语言模型应用的服务和框架的表格：

| **名称** | **描述** | **类型** |
| --- | --- | --- |
| Streamlit | 用于构建和部署 Web 应用的开源 Python 框架 | 框架 |
| Gradio | 让您将模型包装在界面中，并托管在 Hugging Face 上 | 框架 |
| Chainlit | 构建和部署类似 ChatGPT 的对话应用 | 框架 |
| Apache Beam | 用于定义和编排数据处理工作流的工具 | 框架 |
| Vercel | 用于部署和扩展 Web 应用的平台 | 云服务 |
| FastAPI | 用于构建 API 的 Python Web 框架 | 框架 |
| Fly.io | 具有自动缩放和全球 CDN 的应用托管平台 | 云服务 |
| DigitalOcean App Platform | 用于构建、部署和扩展应用的平台 | 云服务 |
| Google Cloud | 提供像 Cloud Run 这样的服务来托管和扩展容器化应用 | 云服务 |
| Steamship | 用于部署和扩展模型的 ML 基础设施平台 | 云服务 |
| Langchain-serve | 用于将 LangChain 代理作为 Web API 提供的工具 | 框架 |
| BentoML | 用于模型服务、打包和部署的框架 | 框架 |
| OpenLLM | 提供商业 LLM 的开放 API | 云服务 |
| Databutton | 无代码平台，用于构建和部署模型工作流 | 框架 |
| Azure ML | Azure 上用于模型的托管 ML 运维服务 | 云服务 |

图 9.2：部署大型语言模型应用的服务和框架。

所有这些都有不同用例的详细文档，通常直接引用LLMs。我们已经展示了使用Streamlit和Gradio的示例，并讨论了如何将它们部署到HuggingFace Hub作为示例。运行LLM应用程序有几个主要要求：

+   可扩展的基础设施，用于处理计算密集型模型和潜在的流量峰值

+   低延迟用于实时提供模型输出

+   持久存储用于管理长对话和应用程序状态

+   用于集成到最终用户应用程序的API

+   监控和记录以跟踪指标和模型行为

在大量用户交互和与LLM服务相关的高成本下，保持成本效率可能具有挑战性。管理效率的策略包括自托管模型、根据流量自动调整资源分配、使用抢占式实例、独立扩展和批量请求以更好地利用GPU资源。工具和基础设施的选择决定了这些要求之间的权衡。灵活性和易用性非常重要，因为我们希望能够快速迭代，这对于ML和LLM领域的动态性至关重要。避免被绑定到一个解决方案是至关重要的。一个灵活、可扩展的服务层，能够容纳各种模型是关键。模型组合和云提供商的选择构成了这种灵活性方程的一部分。对于最大的灵活性，基础设施即代码（IaC）工具如Terraform、CloudFormation或Kubernetes YAML文件可以可靠快速地重新创建您的基础设施。此外，持续集成和持续交付（CI/CD）流水线可以自动化测试和部署过程，以减少错误并促进更快的反馈和迭代。设计一个强大的LLM应用服务可能是一个复杂的任务，需要在评估服务框架时理解权衡和关键考虑因素。利用这些解决方案之一进行部署，使开发人员能够专注于开发有影响力的AI应用程序，而不是基础设施。如前所述，LangChain与几个开源项目和框架如Ray Serve、BentoML、OpenLLM、Modal和Jina很好地配合。在下一节中，我们将基于FastAPI部署一个基于聊天服务的Web服务器。

### 快速API网络服务器

FastAPI是部署网络服务器的非常受欢迎的选择。设计快速、易于使用和高效，它是一个现代化、高性能的用Python构建API的Web框架。Lanarky是一个小型的开源库，用于部署LLM应用程序，提供了方便的Flask API和Gradio的包装器，用于部署LLM应用程序。这意味着您可以同时获得REST API端点和浏览器内可视化，而且只需要几行代码。

> 一个**REST API**（表述性状态转移应用程序编程接口）是一组规则和协议，允许不同的软件应用程序在互联网上进行通信。它遵循REST的原则，这是一种用于设计网络应用程序的架构风格。REST API使用HTTP方法（如GET、POST、PUT、DELETE）对资源执行操作，并通常以标准化格式（如JSON或XML）发送和接收数据。

在库文档中，有几个示例，包括一个带有源链的检索QA、一个对话检索应用程序和一个零射击代理。在另一个示例中，我们将使用Lanarky实现一个聊天机器人Web服务器。我们将使用Lanarky设置一个与Gradio集成的Web服务器，创建一个带有LLM模型和设置的`ConversationChain`实例，并定义用于处理HTTP请求的路由。首先，我们将导入必要的依赖项，包括用于创建Web服务器的FastAPI，用于与Gradio集成的`mount_gradio_app`，用于处理LLM对话的`ConversationChain`和`ChatOpenAI`来自Langchain的模块，以及其他所需的模块：

```
from fastapi import FastAPI
from lanarky.testing import mount_gradio_app
from langchain import ConversationChain
from langchain.chat_models import ChatOpenAI
from lanarky import LangchainRouter
from starlette.requests import Request
from starlette.templating import Jinja2Templates
```

请注意，您需要按照第3章中的说明设置您的环境变量。定义了一个`create_chain()`函数来创建`ConversationChain`的实例，指定LLM模型及其设置：

```
def create_chain():
    return ConversationChain(
        llm=ChatOpenAI(
            temperature=0,
            streaming=True,
        ),
        verbose=True,
    )
```

我们将链设置为`ConversationChain`。

```
chain = create_chain()
```

将app变量分配给`mount_gradio_app`，它创建了一个名为*ConversationChainDemo*的`FastAPI`实例，并将其与Gradio集成：

```
app = mount_gradio_app(FastAPI(title="ConversationChainDemo"))
```

模板变量设置为`Jinja2Templates`类，指定了用于呈现模板的目录。这指定了网页将如何显示，允许各种自定义：

```
templates = Jinja2Templates(directory="webserver/templates")
```

使用FastAPI装饰器`@app.get`定义了处理根路径（`/`）上的HTTP GET请求的端点。与此端点相关联的函数返回一个模板响应，用于呈现index.xhtml模板：

```
@app.get("/")
async def get(request: Request):
    return templates.TemplateResponse("index.xhtml", {"request": request})
```

创建了一个`LangchainRouter`类作为路由器对象。该对象负责定义和管理与`ConversationChain`实例相关的路由。我们可以为路由器添加额外的路由，用于处理基于JSON的聊天，甚至可以处理WebSocket请求：

```
langchain_router = LangchainRouter(
    langchain_url="/chat", langchain_object=chain, streaming_mode=1
)
langchain_router.add_langchain_api_route(
    "/chat_json", langchain_object=chain, streaming_mode=2
)
langchain_router.add_langchain_api_websocket_route("/ws", langchain_object=chain)
app.include_router(langchain_router)
```

现在我们的应用程序知道如何处理发送到路由中指定的路由的请求，将它们指向适当的函数或处理程序进行处理。我们将使用Uvicorn来运行我们的应用程序。Uvicorn擅长支持高性能、异步框架，如FastAPI和Starlette。由于其异步特性，它能够处理大量并发连接，并在重负载下表现良好。我们可以像这样从终端运行Web服务器：

```
uvicorn webserver.chat:app –reload
```

这个命令启动了一个 Web 服务器，你可以在浏览器中查看，地址是：[http://127.0.0.1:8000](http://127.0.0.1:8000)。`--reload` 开关特别方便，因为它意味着一旦你做出任何更改，服务器将自动重新启动。这是我们刚刚部署的聊天机器人应用程序的快照：

![图 9.3：Flask/Lanarky 中的聊天机器人](../media/file60.png)

图 9.3：Flask/Lanarky 中的聊天机器人

我认为我们所做的工作很少，看起来相当不错。它还带有一些不错的功能，如 REST API、Web UI 和 Websocket 接口。虽然 Uvicorn 本身不提供内置的负载均衡功能，但它可以与其他工具或技术（如 Nginx 或 HAProxy）一起工作，在部署设置中实现负载均衡，将传入的客户端请求分发到多个工作进程或实例中。使用 Uvicorn 与负载均衡器可以实现水平扩展，处理大量流量，提高客户端的响应时间，增强容错性。在下一节中，我们将看到如何使用 Ray 构建稳健且具有成本效益的生成式 AI 应用程序。我们将使用 LangChain 进行文本处理，使用 Ray 进行扩展索引和服务，构建一个简单的搜索引擎。

### Ray

Ray 提供了一个灵活的框架，通过在集群中扩展生成式 AI 工作负载，以满足生产中复杂神经网络的基础设施挑战。Ray 可以帮助解决常见的部署需求，如低延迟服务、分布式训练和大规模批量推理。Ray 还可以轻松地启动按需微调或将现有工作负载从一台机器扩展到多台机器。一些功能包括：

+   使用 Ray Train 在 GPU 集群上安排分布式训练作业

+   使用 Ray Serve 部署预训练模型以实现低延迟服务的大规模部署

+   使用 Ray Data 在 CPU 和 GPU 上并行运行大规模批量推理

+   编排端到端生成式 AI 工作流，结合训练、部署���批处理

我们将使用 LangChain 和 Ray 来构建一个简单的搜索引擎，用于 Ray 文档，这是根据 Waleed Kadous 在 anyscale 博客上实现的示例和在 Github 上的 langchain-ray 仓库中实现的。你可以将其视为 *Channel 5* 中示例的延伸。你可以在这里看到此示例的完整代码：[https://github.com/benman1/generative_ai_with_langchain](https://github.com/benman1/generative_ai_with_langchain)。你还将看到如何将其作为 FastAPI 服务器运行。首先，我们将摄取和索引 Ray 文档，以便快速找到相关段落以供搜索查询：

```
# Load the Ray docs using the LangChain loader
loader = RecursiveUrlLoader("docs.ray.io/en/master/") 
docs = loader.load()
# Split docs into sentences using LangChain splitter
chunks = text_splitter.create_documents(
    [doc.page_content for doc in docs],
    metadatas=[doc.metadata for doc in docs])
# Embed sentences into vectors using transformers
embeddings = LocalHuggingFaceEmbeddings('multi-qa-mpnet-base-dot-v1')  
# Index vectors using FAISS via LangChain
db = FAISS.from_documents(chunks, embeddings) 
```

这将通过摄取文档、将其拆分为句子、嵌入句子并索引向量来构建我们的搜索索引。或者，我们可以通过并行化嵌入步骤来加速索引：

```
# Define shard processing task
@ray.remote(num_gpus=1)  
def process_shard(shard):
  embeddings = LocalHuggingFaceEmbeddings('multi-qa-mpnet-base-dot-v1')
  return FAISS.from_documents(shard, embeddings)
# Split chunks into 8 shards
shards = np.array_split(chunks, 8)  
# Process shards in parallel
futures = [process_shard.remote(shard) for shard in shards]
results = ray.get(futures)
# Merge index shards
db = results[0]
for result in results[1:]:
  db.merge_from(result)
```

通过在每个分片上并行运行嵌入，我们可以显著减少索引时间。我们将数据库索引保存到磁盘：

```
db.save_local(FAISS_INDEX_PATH)
```

`FAISS_INDEX_PATH`是一个任意的文件名。我将其设置为`faiss_index.db`。接下来，我们将看到如何使用Ray Serve提供搜索查询。

```
# Load index and embedding
db = FAISS.load_local(FAISS_INDEX_PATH)
embedding = LocalHuggingFaceEmbeddings('multi-qa-mpnet-base-dot-v1')
@serve.deployment
class SearchDeployment:
  def __init__(self):
    self.db = db
    self.embedding = embedding

  def __call__(self, request):   
    query_embed = self.embedding(request.query_params["query"])
    results = self.db.max_marginal_relevance_search(query_embed) 
    return format_results(results) 
deployment = SearchDeployment.bind()
# Start service
serve.run(deployment)
```

这让我们可以将搜索查询作为Web端点提供！运行这个给我这个输出：

```
Started a local Ray instance. 
View the dashboard at 127.0.0.1:8265
```

现在我们可以从Python中查询它：

```
import requests
query = "What are the different components of Ray"
         " and how can they help with large language models (LLMs)?”
response = requests.post("http://localhost:8000/", params={"query": query})
print(response.text)
```

对我来说，服务器在Ray用例页面上获取了：[http://https://docs.ray.io/en/latest/ray-overview/use-cases.xhtml](http://https://docs.ray.io/en/latest/ray-overview/use-cases.xhtml)我真的很喜欢Ray仪表板的监控，看起来像这样：

![图9.4：Ray 仪表板。](../media/file61.png)

图9.4：Ray 仪表板。

这个仪表板非常强大，因为它可以为您提供大量的指标和其他信息。收集指标非常容易，因为您只需设置和更新部署对象或者actor中的`Counter`、`Gauge`、`Histogram`或其他类型的变量。对于时间序列图表，您应该安装Prometheus或Grafana服务器。正如您在Github上看到的完整实现，我们也可以将其作为FastAPI服务器启动。这结束了我们使用LangChain和Ray构建的简单语义搜索引擎。随着模型和LLM应用程序变得越来越复杂，并且高度交织到业务应用程序的结构中，生产中的可观察性和监控变得必不可少，以确保它们的准确性、效率和可靠性。下一节将重点介绍监控LLMs的重要性，并强调要跟踪的关键指标，以制定全面的监控策略。

## 如何观察LLM应用程序？

现实世界运营的动态性意味着离线评估中评估的条件几乎不可能涵盖LLMs在生产系统中可能遇到的所有潜在场景。因此，生产中需要可观察性 - 更持续、实时的观察，以捕捉离线测试无法预料到的异常情况。可观察性允许在模型与实际输入数据和用户在生产中交互时监控行为和结果。它包括日志记录、跟踪、追踪和警报机制，以确保系统正常运行、性能优化和及早捕捉模型漂移等问题。正如讨论的那样，LLMs已经成为健康、电子商务和教育等领域许多应用程序中越来越重要的组成部分。

> 跟踪、追踪和监控是软件运营和管理领域中的三个重要概念。虽然都与理解和改进系统性能有关，但它们各自扮演着不同的角色。跟踪和追踪是为了保留详细的历史记录以供分析和调试，而监控旨在实时观察和立即意识到问题，以确保系统在任何时候功能最佳。这三个概念都属于可观察性范畴。
> 
> > **监控**是持续监视系统或应用程序性能的过程。这可能涉及持续收集和分析与系统健康相关的指标，如内存使用情况、CPU利用率、网络延迟以及整体应用程序/服务性能（如响应时间）。有效的监控包括为异常或意外行为设置警报系统 - 当超过某些阈值时发送通知。而跟踪和追踪是关于保留详细的历史记录以进行分析和调试，监控旨在实时观察和立即意识到问题，以确保系统功能始终处于最佳状态。

监控和可观察性的主要目标是通过实时数据提供对模型性能和行为的洞察。这有助于：

+   **防止模型漂移**：模型随时间可能因输入数据或用户行为特征的变化而退化。定期监控可以及早识别这种情况并采取纠正措施。

+   **性能优化**：通过跟踪推理时间、资源使用情况和吞吐量等指标，您可以进行调整以提高LLM在生产中的效率和效果。

+   **A/B测试**：它有助于比较模型中轻微差异可能导致不同结果的方式，从而有助于决策改进模型。

+   **调试问题**：监控有助于识别运行时可能发生的未预料问题，从而实现快速解决。

重要的是考虑由几个方面组成的监控策略：

+   **监控的指标**：根据所需的模型性能定义关键的感兴趣指标，如预测准确性、延迟、吞吐量等。

+   **监控频率**：监控频率应根据模型对运营的关键程度来确定 - 高度关键的模型可能需要接近实时的监控。

+   **日志记录**：日志应提供有关LLM执行的每个相关操作的详细信息，以便分析人员可以追溯任何异常情况。

+   **警报机制**：系统应在检测到异常行为或性能急剧下降时发出警报。

监控LLM具有多种目的，包括评估模型性能、检测异常或问题、优化资源利用率以及确保一致和高质量的输出。通过通过验证、影子发布和解释以及可靠的离线评估持续评估LLM的行为和性能，组织可以识别和减轻潜在风险，保持用户信任，并提供最佳体验。以下是相关指标的列表：

+   **推理延迟**：衡量LLM处理请求并生成响应所需的时间。较低的延迟确保更快速和更具响应性的用户体验。

+   **每秒查询数（QPS）**：计算LLM在给定时间范围内可以处理的查询或请求数量。监控QPS有助于评估可伸缩性和容量规划。

+   **每秒令牌数（TPS）**：跟踪LLM生成令牌的速率。TPS指标有助于估计计算资源需求并了解模型效率。

+   **令牌使用量**：令牌数量与资源使用相关，如硬件利用率、延迟和成本。

+   **错误率**：监控LLM响应中错误或失败的发生，确保错误率保持在可接受范围内，以维持输出质量。

+   **资源利用率**：衡量计算资源的消耗，如CPU、内存和GPU，以优化资源分配并避免瓶颈。

+   **模型漂移**：通过将LLM的输出与基准或基本事实进行比较，检测LLM行为随时间的变化，确保模型保持准确性并与预期结果保持一致。

+   **超出分布输入**：识别落在LLM训练数据预期分布之外的输入或查询，这可能导致意外或不可靠的响应。

+   **用户反馈指标**：监控用户反馈渠道，收集关于用户满意度的见解，识别改进领域，并验证LLM的有效性。

数据科学家和机器学习工程师应使用模型解释工具如LIME和SHAP检查过时性、不正确的学习和偏见。最具预测性的特征突然变化可能表明数据泄漏。离线指标如AUC并不总是与在线转化率的影响相关，因此重要的是找到可靠的离线指标，这些指标转化为对业务相关的在线收益，理想情况下是系统直接影响的点击和购买等直接指标。有效的监控能够实现LLM的成功部署和利用，增强对其能力的信心并培养用户信任。然而，应当注意，依赖云服务平台时应研究隐私和数据保护政策。在下一节中，我们将看一下监控代理的轨迹。

### 跟踪和追踪

> **跟踪**通常指记录和管理有关应用程序或系统中特定操作或一系列操作的信息的过程。例如，在机器学习应用程序或项目中，跟踪可能涉及记录不同实验或运行中的参数、超参数、指标、结果等。它提供了一种记录进展和随时间变化的方式。
> 
> > **跟踪**是一种更专业的追踪形式。它涉及记录软件/系统中的执行流程。特别是在单个交易可能涵盖多个服务的分布式系统中，跟踪有助于维护审计或面包屑路径，详细信息关于该请求路径通过系统。这种细粒度视图使开发人员能够理解各种微服务之间的交互，并通过确定事务路径中发生问题的确切位置来解决延迟或故障等问题。

跟踪代理的轨迹可能具有挑战性，因为它们具有广泛的行动范围和生成能力。LangChain具有轨迹跟踪和评估功能。实际上，查看代理的痕迹非常容易！您只需在初始化代理或LLM时将return_`intermediate_steps`参数设置为`True`。让我们快速看一下这个。我会跳过导入和设置环境。您可以在此地址的github上找到完整的清单：[https://github.com/benman1/generative_ai_with_langchain/](https://github.com/benman1/generative_ai_with_langchain/)我们将定义一个工具。使用`@tool`装饰器非常方便，它将使用函数文档字符串作为工具的描述。第一个工具向网站地址发送一个ping，并返回有关传输包和延迟或（在错误情况下）错误消息的信息：

```
@tool
def ping(url: HttpUrl, return_error: bool) -> str:
    """Ping the fully specified url. Must include https:// in the url."""
    hostname = urlparse(str(url)).netloc
    completed_process = subprocess.run(
        ["ping", "-c", "1", hostname], capture_output=True, text=True
    )
    output = completed_process.stdout
    if return_error and completed_process.returncode != 0:
        return completed_process.stderr
    return output]
```

现在我们设置一个使用此工具与LLM的代理，以根据提示进行调用：

```
llm = ChatOpenAI(model="gpt-3.5-turbo-0613", temperature=0)
agent = initialize_agent(
    llm=llm,
    tools=[ping],
    agent=AgentType.OPENAI_MULTI_FUNCTIONS,
    return_intermediate_steps=True,  # IMPORTANT!
)
result = agent("What's the latency like for https://langchain.com?")
```

代理报告如下：

```
The latency for https://langchain.com is 13.773 ms
```

在`results[`"`intermediate_steps`"`]`中，我们可以看到有关代理操作的大量信息：

```
[(_FunctionsAgentAction(tool='ping', tool_input={'url': 'https://langchain.com', 'return_error': False}, log="\nInvoking: `ping` with `{'url': 'https://langchain.com', 'return_error': False}`\n\n\n", message_log=[AIMessage(content='', additional_kwargs={'function_call': {'name': 'tool_selection', 'arguments': '{\n  "actions": [\n    {\n      "action_name": "ping",\n      "action": {\n        "url": "https://langchain.com",\n        "return_error": false\n      }\n    }\n  ]\n}'}}, example=False)]), 'PING langchain.com (35.71.142.77): 56 data bytes\n64 bytes from 35.71.142.77: icmp_seq=0 ttl=249 time=13.773 ms\n\n--- langchain.com ping statistics ---\n1 packets transmitted, 1 packets received, 0.0% packet loss\nround-trip min/avg/max/stddev = 13.773/13.773/13.773/0.000 ms\n')]
```

通过提供对系统的可见性，并帮助识别问题和优化工作，这种跟踪和评估可以非常有帮助。LangChain文档演示了如何使用轨迹评估器来检查它们生成的完整动作和响应序列，并对OpenAI函数代理进行评分。让我们超越LangChain，看看可观察性领域有什么！

### 可观察性工具

在LangChain中或通过回调，有许多工具可用作集成：

+   **Argilla**：Argilla是一个开源数据整理平台，可以将用户反馈（人在循环工作流程）与提示和响应集成，以整理数据集进行微调。

+   **Portkey**：Portkey为LangChain添加了重要的MLOps功能，如监视详细指标、跟踪链、缓存和可靠性通过自动重试。

+   **Comet.ml**：Comet提供强大的MLOps功能，用于跟踪实验、比较模型和优化AI项目。

+   **LLMonitor**：跟踪许多指标，包括成本和使用分析（用户跟踪）、跟踪和评估工具（开源）。

+   **DeepEval**：记录默认指标，如相关性、偏见和毒性。还可以帮助测试和监视模型漂移或退化。

+   **Aim**：用于 ML 模型的开源可视化和调试平台。它记录输入、输出以及组件的序列化状态，使得可以对单个 LangChain 执行进行视觉检查，并将多个执行进行比较。

+   **Argilla**：用于跟踪训练数据、验证准确性、参数等的开源平台，适用于机器学习实验。

+   **Splunk**：Splunk 的机器学习工具包可以提供对生产中机器学习模型的可观察性。

+   **ClearML**：用于自动化训练管道的开源工具，无缝地从研究过渡到生产。

+   **IBM Watson OpenScale**：提供对 AI 健康状况的洞察，快速识别和解决问题，帮助减轻风险。

+   **DataRobot MLOps**：监视和管理模型，以在影响性能之前检测问题。

+   **Datadog APM 集成**：此集成允许您捕获 LangChain 请求、参数、提示完成，并可视化 LangChain 操作。您还可以捕获请求延迟、错误以及令牌/成本使用等指标。

+   **Weights and Biases (W&B) 跟踪**：我们已经展示了使用 (W&B) 监控微调收敛的示例，但它还可以跟踪其他指标，记录和比较提示。

+   **Langfuse**：使用这个开源工具，我们可以方便地监视有关我们的 LangChain 代理和工具的跟踪的详细信息，如延迟、成本、分数等。

大多数这些集成非常容易集成到 LLM 管道中。例如，对于 W&B，您可以通过将`LANGCHAIN_WANDB_TRACING`环境变量设置为`True`来启用跟踪。或者，您可以使用`wandb_tracing_enabled()`上下文管理器来跟踪特定的代码块。使用 Langfuse，我们可以将`langfuse.callback.CallbackHandler()`作为参数传递给`chain.run()`调用。其中一些工具是开源的，这些平台的优点在于允许完全定制和本地部署，适用于隐私重要的用例。例如，Langfuse 是开源的，并提供自托管选项。选择最适合您需求的选项，并按照 LangChain 文档中提供的说明启用代理的跟踪。虽然该平台最近才发布，但我相信还有更多功能将会推出，但已经很棒能看到代理执行的痕迹，检测循环和延迟问题。它可以与合作者共享跟踪和统计数据，讨论改进。

### LangSmith

LangSmith是由LangChain AI开发和维护的用于调试、测试、评估和监控LLM应用的框架，LangChain是LangChain背后的组织。LangSmith作为MLOps的有效工具，特别是针对LLMs，提供覆盖MLOps流程多个方面的功能。它可以帮助开发人员通过提供调试、监控和优化功能，将他们的LLM应用从原型推进到生产阶段。LangSmith旨在通过提供简单直观的用户界面，降低对没有软件背景的人的准入门槛。LangSmith是用LangChain构建的用于调试、测试和监控大型语言模型（LLMs）的平台。它允许您：

+   记录来自您的LangChain代理、链和其他组件的运行跟踪

+   创建数据集以评估模型性能

+   配置AI辅助评估器来评分您的模型

+   查看指标、可视化和反馈，以迭代和改进您的LLMs

LangSmith通过提供功能和能力来满足代理的MLOps要求，使开发人员能够调试、测试、评估、监控和优化语言模型应用。其在LangChain框架中的集成增强了整体开发体验，并促进了语言模型应用的充分潜力。通过同时使用这两个平台，开发人员可以将他们的LLM应用从原型阶段优化到生产阶段，并优化延迟、硬件效率和成本。我们可以获得一组大量的图表，展示了许多重要统计数据，就像我们在这里看到的：

![图9.5：LangSmith中的评估器指标。](../media/file62.png)

图9.5：LangSmith中的评估器指标。

监控仪表板包括以下图表，可以按不同的时间间隔进行分解：

| 统计数据 | 类别 |
| --- | --- |
| 跟踪计数，LLM调用计数，跟踪成功率，LLM调用成功率 | 量级 |
| 跟踪延迟（秒），LLM延迟（秒），每个跟踪的LLM调用，标记/秒 | 延迟 |
| 总标记数，每个跟踪的标记数，每个LLM调用的标记数 | 标记数 |
| % 带有流式处理的跟踪，% 带有流式处理的LLM调用，跟踪时间到第一个标记（毫秒），LLM时间到第一个标记（毫秒） | 流式处理 |

图9.6：LangSmith中的统计数据。

这是LangSmith中用于我们在评估部分中看到的基准数据集运行的跟踪示例：

![图9.7：LangSmith中的跟踪。](../media/file63.png)

图9.7：LangSmith中的跟踪。

该平台本身不是开源的，但是LangSmith和LangChain背后的公司LangChain AI为有隐私问题的组织提供了一些自托管的支持。然而，LangSmith有一些替代品，如Langfuse、Weights and Biases、Datadog APM、Portkey和PromptWatch，功能有一些重叠。我们将重点关注LangSmith，因为它具有用于评估和监控的大量功能，并且因为它与LangChain集成。在下一节中，我们将演示如何利用PromptWatch.io来跟踪LLM在生产环境中的提示。

### PromptWatch

PromptWatch记录了此交互期间有关提示和生成输出的信息。让我们先处理输入。

```
from langchain import LLMChain, OpenAI, PromptTemplate
from promptwatch import PromptWatch
from config import set_environment
set_environment()
```

如第3章所述，我已经在set_environment()函数中将所有API密钥设置在环境中。

```
prompt_template = PromptTemplate.from_template("Finish this sentence {input}")
my_chain = LLMChain(llm=OpenAI(), prompt=prompt_template)
```

使用`PromptTemplate`类，将提示模板设置为一个变量`input`，指示用户输入应放置在提示中的位置。在`PromptWatch`块内，通过以输入提示作为示例调用`LLMChain`，演示了模型根据提供的提示生成响应的过程。

```
with PromptWatch() as pw:
    my_chain("The quick brown fox jumped over")
```

![图9.8：PromptWatch.io上的提示跟踪。](../media/file64.png)

图9.8：PromptWatch.io上的提示跟踪。

这看起来非常有用。通过利用PromptWatch.io，开发人员和数据科学家可以有效地监视和分析LLM的提示、输出和成本在实际场景中的情况。PromptWatch.io为LLM提供了全面的链执行跟踪和监控功能。使用PromptWatch.io，您可以跟踪LLM链的所有方面，包括操作、检索文档、输入、输出、执行时间、工具详细信息等，以完全了解您的系统。该平台通过提供用户友好的可视界面，使用户能够识别问题的根本原因并优化提示模板，从而进行深入分析和故障排除。PromptWatch.io还可以帮助进行单元测试和版本化提示模板。让我们总结本章！

## 摘要

成功部署LLMs和其他生成式AI模型在生产环境中是一个复杂但可管理的任务，需要仔细考虑许多因素。这需要解决与数据质量、偏见、伦理、监管合规性、可解释性、资源需求以及持续监控和维护等挑战相关的问题。LLMs的评估是评估其性能和质量的重要步骤。LangChain支持模型之间的比较评估，检查输出是否符合标准，简单的字符串匹配以及语义相似性度量。这些提供了对模型质量、准确性和适当生成的不同见解。系统化评估是确保大型语言模型产生有用、相关和明智输出的关键。监控LLMs是部署和维护这些复杂系统的重要方面。随着LLMs在各种应用中的日益普及，确保它们的性能、有效性和可靠性至关重要。我们已经讨论了监控LLMs的重要性，强调了跟踪全面监控策略的关键指标，并举例说明了如何在实践中跟踪指标。LangSmith提供了强大的功能，用于跟踪、基准测试和优化使用LangChain构建的大型语言模型。其自动评估器、指标和可视化帮助加速LLM的开发和验证。让我们看看你是否记得本章的要点！

## 问题

请看看你是否能回答这些问题。如果你对任何问题不确定，你可能需要参考本章的相应部分：

1.  在你看来，什么是描述语言模型的操作化、LLM应用程序或依赖生成模型的应用程序的最佳术语？

1.  我们如何评估LLM应用程序？

1.  哪些工具可以帮助评估LLM应用程序？

1.  生产部署代理的考虑因素是什么？

1.  列举一些部署工具的名称？

1.  在生产环境中监控LLMs的重要指标是什么？

1.  我们如何监控这些模型？

1.  什么是LangSmith？
