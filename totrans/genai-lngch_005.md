# 使用工具进行查询

## 在Discord上加入我们的书籍社区

[https://packt.link/EarlyAccessCommunity](https://packt.link/EarlyAccessCommunity)

![自动生成的二维码描述](../media/file26.png)

在当今快节奏的商业和研究环境中，跟上不断增长的信息量可能是一项艰巨的任务。对于计算机科学和人工智能等领域的工程师和研究人员来说，保持对最新发展的了解至关重要。然而，阅读和理解大量论文可能是耗时且劳动密集的。这就是自动化发挥作用的地方。在本章中，我们将描述一种自动化研究论文摘要和回答问题的方法，使研究人员更容易消化和保持信息。通过利用语言模型和一系列问题，我们将开发的摘要可以以简洁和简化的格式总结论文的核心论点、含义和机制。这不仅可以节省研究主题时的时间和精力，还可以确保我们能有效地应对科学进步的加速步伐。我们还将尝试使用OpenAI模型的功能，并将其应用于信息提取。我们将看到它们如何（或尚未）用于解析简历（CVs）的应用。这个函数语法是特定于OpenAI的API，并且有许多应用，然而，LangChain提供了一个平台，允许创建用于任何大型语言模型（LLMs）的工具，增强它们的功能。这些工具使LLMs能够与API交互，访问实时信息，并执行各种任务，如检索搜索、数据库查询、撰写电子邮件，甚至打电话。我们将使用检索增强生成（RAG）实现一个问答应用程序。这是一种通过将相关数据注入上下文来更新大型语言模型（LLMs）如GPT的技术。最后，我们将讨论代理的不同决策策略。我们将实现两种策略，即计划和执行（或计划和解决）和一次性代理，并将它们集成到一个可视化界面中，作为浏览器中的可视化应用程序（使用Streamlit）用于问答。主要部分包括：

+   什么是幻觉？

+   如何总结长篇文档？

+   从文档中提取信息

+   使用工具回答问题

+   推理策略

我们将从讨论LLMs的可靠性问题开始。

## 什么是幻觉？

生成式语言模型（如GPT-3、Llama和Claude 2）的快速发展引起了人们对其局限性和潜在风险的关注。一个主要关注点是幻觉，即模型生成的输出是荒谬的、不连贯的或与提供的输入不符。幻觉在现实世界的应用中，如医学或机器翻译中，会带来性能和安全风险。幻觉的另一个方面是，LLM生成包含敏感个人信息的文本，如电子邮件地址、电话号码和物理地址。这引发了重大的隐私问题，因为它表明语言模型可以从其训练语料库中记忆和恢复这些私人数据，尽管这些数据不在源输入中。

> 在LLM的背景下，**幻觉**指的是生成的文本与预期内容不忠实或荒谬的现象。这个术语与心理幻觉类似，涉及感知不存在的事物。在自然语言生成中，幻觉文本可能在提供的上下文中看起来流畅自然，但缺乏特定性或可验证性。**忠实性**，即生成的内容保持与源内容一致和真实，被认为是幻觉的反义词。
> 
> > **内在幻觉**发生在生成的输出与源内容相矛盾时，而**外在幻觉**涉及生成无法验证或支持的信息。外在幻觉有时可能包含事实正确的外部信息，但其不可验证性引发了从事实安全角度的担忧。

解决幻觉的努力正在进行中，但需要在不同任务之间全面了解，以开发有效的缓解方法。LLM中的幻觉可能由各种因素引起：

1.  编码器的不完美表示学习。

1.  错误解码，包括关注源输入的错误部分和解码策略的选择。

1.  曝光偏差，即训练和推理时间之间的差异。

1.  参数化知识偏见，即预训练模型优先考虑自己的知识而不是输入，导致生成过多的信息。

> **幻觉缓解方法**可以分为两组：数据相关方法和建模与推理方法（根据“自然语言生成中的幻觉调查”，季子伟等人，2022年）：
> 
> > **数据相关方法：**
> > 
> > 构建忠实数据集：从头开始构建具有干净和忠实目标的数据集，或者在确保语义一致性的同时重写真实句子。
> > 
> > 自动清理数据：识别和过滤现有语料库中的不相关或矛盾信息，以减少语义噪音。
> > 
> > 信息增强：通过外部信息（如检索的知识或合成数据）增强输入，以改善语义理解并解决源目标分歧。
> > 
> > **建模和推理方法：**
> > 
> > 架构：修改编码器架构以增强语义解释，注意机制以优先处理源信息，解码器结构以减少虚构并强制隐式或显式约束。
> > 
> > 训练：结合规划、强化学习（RL）、多任务学习和可控生成技术，通过改善对齐、优化奖励函数和平衡忠实度和多样性来减轻虚构。
> > 
> > 后处理：通过生成然后精炼策略或专门用于忠实度的后处理校正方法，纠正输出中的虚构。

虚构的结果是，自动事实核查可以应用，存在传播不正确信息或滥用政治目的的危险。**错误信息**，包括**虚假信息**、欺骗性新闻和谣言，对社会构成重大威胁，尤其是通过社交媒体轻松创作和传播内容。社会面临的威胁包括对科学、公共卫生叙事、社会极化和民主进程的不信任。新闻学和档案学已广泛研究了这个问题，事实核查倡议也在应对中不断增长。致力于事实核查的组织为独立事实核查员和记者提供培训和资源，从而扩大专家事实核查工作的规模。解决错误信息对保持信息的完整性和对抗其对社会的有害影响至关重要。在文献中，这种问题被称为文本蕴涵，其中模型预测文本对之间的方向性真实关系（即“句子t蕴含h”如果，通常，阅读t的人会推断h最有可能是真实的）。在本章中，我们将重点关注通过信息增强和后处理进行**自动事实核查**。事实可以从LLMs或使用外部工具检索。在前一种情况下，预训练语言模型可以取代知识库和检索模块，利用其广泛的知识回答开放域问题，并使用提示检索特定事实。我们可以在这个图表中看到这个一般想法（来源：https://github.com/Cartus/Automated-Fact-Checking-Resources by Zhijiang Guo）：

![图4.1：三个阶段的自动事实核查流程。](../media/file27.png)

图4.1：三个阶段的自动事实核查流程。

我们可以区分三个阶段：

1.  主张检测 - 识别需要验证的主张

1.  检索 - 检索证据���找到支持或反驳主张的来源

1.  主张验证 - 根据证据评估主张的真实性

从2018年开始使用24层BERT-Large，语言模型已经在大型知识库（如维基百科）上进行了预训练，因此能够从维基百科或其他来源（因为它们的训练集越来越多地包括其他来源）- 互联网、教科书、arxiv和Github回答知识问题。查询事实的工作与简单提示（如掩码提示）一起进行。例如，为了回答问题“微软的总部在哪里？”，问题将被重写为“微软的总部在[MASK]”，然后输入到语言模型中以获取答案。在这种方法中，最终的激活在条件LLM接收到源文本（有条件LLM）产生目标时的损失比未接收源文本的LLM（无条件LLM）产生目标时的损失更小，这表明生成的标记是幻觉的（Fillippova, 2020）。幻觉标记与目标标记总数的比率可以作为生成输出中幻觉程度的度量。在LangChain中，我们有一个可用于事实核查的链，其中模型通过提示链式提问对陈述中的假设进行主动质疑。在这个自检链中，`LLMCheckerChain`，模型被依次提示多次，首先明确做出假设 - 看起来像这样：

```
Here’s a statement: {statement}\nMake a bullet point list of the assumptions you made when producing the above statement.\n
```

请注意，这是一个字符串模板，其中花括号中的元素将被变量替换。接下来，这些假设将被反馈给模型，以便逐个用类似这样的提示检查它们：

```
Here is a bullet point list of assertions:
    {assertions}
    For each assertion, determine whether it is true or false. If it is false, explain why.\n\n
```

最后，模型被要求做出最终判断：

```
In light of the above facts, how would you answer the question '{question}'
```

`LLMCheckerChain`就像这个例子展示的那样自动完成所有这些。

```
from langchain.chains import LLMCheckerChain
from langchain.llms import OpenAI
llm = OpenAI(temperature=0.7)
text = "What type of mammal lays the biggest eggs?"
checker_chain = LLMCheckerChain.from_llm(llm, verbose=True)
checker_chain.run(text)
```

这个模型对这个问题可能会返回不同的结果，其中一些是错误的，而一些则会被正确识别为错误。当我尝试时，我得到了蓝鲸、北美海狸或已灭绝的巨型恐鸟等结果。我认为这是正确答案：

```
Monotremes, a type of mammal found in Australia and parts of New Guinea, lay the largest eggs in the mammalian world. The eggs of the American echidna (spiny anteater) can grow as large as 10 cm in length, and dunnarts (mouse-sized marsupials found in Australia) can have eggs that exceed 5 cm in length.
• Monotremes can be found in Australia and New Guinea
• The largest eggs in the mammalian world are laid by monotremes
• The American echidna lays eggs that can grow to 10 cm in length
• Dunnarts lay eggs that can exceed 5 cm in length
• Monotremes can be found in Australia and New Guinea – True
• The largest eggs in the mammalian world are laid by monotremes – True
• The American echidna lays eggs that can grow to 10 cm in length – False, the American echidna lays eggs that are usually between 1 to 4 cm in length. 
• Dunnarts lay eggs that can exceed 5 cm in length – False, dunnarts lay eggs that are typically between 2 to 3 cm in length.
The largest eggs in the mammalian world are laid by monotremes, which can be found in Australia and New Guinea. Monotreme eggs can grow to 10 cm in length.
> Finished chain.
```

因此，虽然这并不能保证正确答案，但它可以阻止一些错误结果。至于增强检索（或RAG），我们在本章中看到了这种方法，在关于问答的部分。事实核查方法涉及将声明分解为更小的可检查查询，这些查询可以被制定为问答任务。专为搜索领域数据集设计的工具可以帮助事实核查人员有效地找到证据。像谷歌和必应这样的现成搜索引擎也可以检索与主题和证据相关的内容，准确捕捉陈述的真实性。在下一节中，我们将应用这种方法基于网络搜索和其他工具返回结果。在下一节中，我们将实现一个链来总结文档。我们可以从这些文档中提出任何问题。

## 如何总结长篇文档？

在这一部分，我们将讨论自动化长文本和研究论文摘要的过程。在当今快节奏的商业和研究环境中，跟上不断增长的信息量可能是一项艰巨的任务。对于计算机科学和人工智能等领域的工程师和研究人员来说，了解最新发展至关重要。然而，阅读和理解大量论文可能是耗时且劳动密集的。这就是自动化发挥作用的地方。作为工程师，我们受到建设和创新的愿望驱使，通过创建管道和流程来自动化避免重复性任务。这种常被误解为懒惰的方法使工程师能够专注于更复杂的挑战，并更有效地利用他们的技能。在这里，我们将构建一个自动化工具，可以快速以更易消化的格式总结长文本的内容。该工具旨在帮助研究人员跟上每天发表的论文数量，特别是在人工智能等快速发展领域。通过自动化摘要过程，研究人员可以节省时间和精力，同时确保他们了解其领域的最新发展。该工具将基于LangChain，并利用大型语言模型（LLMs）以更简洁和简化的方式总结论文的核心论点、含义和机制。它还可以回答关于论文的具体问题，使其成为文献综述和加速科学研究的宝贵资源。作者计划进一步开发该工具，以允许自动处理多个文档并针对特定研究领域进行定制。总体而言，该方法旨在通过提供更高效和更易访问的方式帮助研究人员跟上最新研究。LangChain支持使用LLMs处理文档的映射减少方法，这允许对文档进行高效处理和分析。在阅读大文本并将其分割为适合LLM令牌上下文长度的文档（块）时，可以将链应用于每个文档，并将输出组合成单个文档。核心论点是映射减少过程涉及两个步骤：

+   映射步骤 - 将LLM链应用于每个文档，将输出视为新文档，并

+   减少步骤 - 所有新文档都传递到单独的组合文档链以获得单个输出。

这在这里的图中有所说明：

![图4.2：LangChain中的映射减少链（来源：LangChain文档）。](../media/file28.jpg)

图4.2：LangChain中的映射减少链（来源：LangChain文档）。

这种方法的影响是它允许对文档进行并行处理，并且使LLMs能够用于推理、生成或分析单个文档以及组合它们的输出。该过程的机制涉及压缩或折叠映射文档，以确保它们适合于组合文档链，这可能还涉及利用LLMs。如果需要，压缩步骤可以递归执行。这里是加载PDF文档并对其进行摘要的简单示例：

```
from langchain.chains.summarize import load_summarize_chain
from langchain import OpenAI
from langchain.document_loaders import PyPDFLoader
pdf_loader = PyPDFLoader(pdf_file_path)
docs = pdf_loader.load_and_split()
llm = OpenAI()
chain = load_summarize_chain(llm, chain_type="map_reduce")
chain.run(docs)
```

变量`pdf_file_path`是一个包含PDF文件路径的字符串。地图和减少步骤的默认提示是这样的：

```
Write a concise summary of the following:
{text}
CONCISE SUMMARY:
```

我们可以为每个步骤指定任何提示。在为本章开发的文本摘要应用程序中，我们可以看到如何传递其他提示。在LangChainHub上，我们可以看到qa-with sources提示，它采用了一个类似于这样的减少/组合提示：

```
Given the following extracted parts of a long document and a question, create a final answer with references (\"SOURCES\"). \nIf you don't know the answer, just say that you don't know. Don't try to make up an answer.\nALWAYS return a \"SOURCES\" part in your answer.\n\nQUESTION: {question}\n=========\nContent: {text}
```

在这个提示中，我们会制定一个具体的问题，但同样我们也可以给LLM一个更抽象的指令，以提取假设和推论。文本将是地图步骤的摘要。这样的指令可以帮助防止幻觉。其他指令的例子可能是将文档翻译成另一种语言或以某种风格重新表述。一旦我们开始做很多调用，特别是在地图步骤中，我们会看到成本增加。我们正在做很多调用，并总共使用了很多令牌。是时候让这些变得更加可见了！

### 令牌使用

在使用模型时，特别是在长循环中，比如在地图操作中，跟踪令牌使用量并了解你花费了多少钱是很重要的。对于任何严肃的生成式人工智能使用，我们需要了解不同语言模型的能力、定价选项和用例。OpenAI提供不同的模型，包括GPT-4、ChatGPT和InstructGPT，以满足各种自然语言处理需求。GPT-4是一个强大的语言模型，适用于解决自然语言处理中的复杂问题。它提供基于使用的令牌大小和数量的灵活定价选项。ChatGPT模型，如GPT-3.5-Turbo，专门用于对话应用，如聊天机器人和虚拟助手。它们擅长生成准确流畅的回应。ChatGPT模型的定价基于使用的令牌数量。InstructGPT模型专为单轮指令跟随而设计，并针对快速准确的响应生成进行了优化。InstructGPT系列中的不同模型，如Ada和Davinci，提供不同级别的速度和功率。Ada是最快的模型，适用于速度至关重要的应用，而Davinci是最强大的模型，能够处理复杂的指令。InstructGPT模型的定价取决于模型的能力，从像Ada这样的低成本选项到像Davinci这样的更昂贵选项。OpenAI的DALL·E、Whisper和API服务用于图像生成、语音转录、翻译和访问语言模型。DALL·E是一种AI驱动的图像生成模型，可以无缝集成到应用程序中，用于生成和编辑新颖的图像和艺术品。OpenAI提供三个分辨率层次，允许用户选择他们需要的细节级别。更高的分辨率提供更复杂和详细的内容，而较低的分辨率提供更抽象的表示。每张图像的价格根据分辨率而变化。Whisper是一种可以将语音转录为文本并将多种语言翻译成英语的AI工具。它有助于捕捉对话，促进交流，并提高跨语言理解。使用Whisper的成本基于每分钟的费率。OpenAI的API提供对强大语言模型如GPT-3的访问，使开发人员能够创建高级应用程序。在注册API时，用户会获得一个初始令牌使用限制，代表在特定时间范围内与语言模型交互的令牌数量。随着用户的记录和使用增加，OpenAI可能会增加令牌使用限制，为模型提供更多访问权限。用户还可以请求增加配额，如果他们的应用程序需要更多令牌。我们可以通过连接到OpenAI回调来跟踪OpenAI模型中的令牌使用：

```
with get_openai_callback() as cb:
    response = llm_chain.predict(text=”Complete this text!”)
    print(f"Total Tokens: {cb.total_tokens}")
    print(f"Prompt Tokens: {cb.prompt_tokens}")
    print(f"Completion Tokens: {cb.completion_tokens}")
    print(f"Total Cost (USD): ${cb.total_cost}")
```

在这个例子中，带有`llm_chain`的行可以是对OpenAI模型的任何使用。我们应该看到一个包含成本和令牌的输出。还有另外两种获取令牌使用情况的方法。作为OpenAI回调的替代方案，`llm`类的`generate()`方法返回一个`LLMResult`类型的响应，而不是字符串。这包括令牌使用情况和完成原因，例如（来自LangChain文档）：

```
input_list = [
    {"product": "socks"},
    {"product": "computer"},
    {"product": "shoes"}
]
llm_chain.generate(input_list)
```

结果看起来像这样：

```
 LLMResult(generations=[[Generation(text='\n\nSocktastic!', generation_info={'finish_reason': 'stop', 'logprobs': None})], [Generation(text='\n\nTechCore Solutions.', generation_info={'finish_reason': 'stop', 'logprobs': None})], [Generation(text='\n\nFootwear Factory.', generation_info={'finish_reason': 'stop', 'logprobs': None})]], llm_output={'token_usage': {'prompt_tokens': 36, 'total_tokens': 55, 'completion_tokens': 19}, 'model_name': 'text-davinci-003'})
```

最后，OpenAI API中的聊天完成响应格式包括一个带有令牌信息的使用对象，例如它可能看起来像这样（摘录）：

```
 {
  "model": "gpt-3.5-turbo-0613",
  "object": "chat.completion",
  "usage": {
    "completion_tokens": 17,
    "prompt_tokens": 57,
    "total_tokens": 74
  }
}
```

接下来，我们将看看如何使用LangChain中的OpenAI函数从文档中提取特定信息。

## 从文档中提取信息

2023年6月，OpenAI宣布了OpenAI API的更新，包括对函数调用的新功能，这将开启增强功能。开发人员现在可以描述函数给gpt-4-0613和gpt-3.5-turbo-0613模型，并让模型智能地生成一个包含调用这些函数参数的JSON对象。此功能旨在增强GPT模型与外部工具和API之间的连接，提供一种可靠的方式从模型中检索结构化数据。函数调用使开发人员能够创建能够使用外部工具或OpenAI插件回答问题的聊天机器人。它还允许将自然语言查询转换为API调用或数据库查询，并从文本中提取结构化数据。更新的机制涉及使用新的API参数，即`functions`，在`/v1/chat/completions`端点中。函数参数通过名称、描述、参数和要调用的函数本身进行定义。开发人员可以使用JSON Schema描述模型的函数，并指定要调用的所需函数。在LangChain中，我们可以使用这些函数调用在OpenAI中进行信息提取或调用插件。对于信息提取，我们可以从文本和文档中的提取链中使用OpenAI聊天模型来指定实体及其属性。例如，这可以帮助识别文本中提到的人物。通过使用OpenAI函数参数并指定模式，可以确保模型输出所需的实体和属性及其适当的类型。这种方法的影响是它允许通过定义具有所需属性和类型的模式来精确提取实体。它还可以指定哪些属性是必需的，哪些是可选的。模式的默认格式是字典，但我们也可以在Pydantic中定义属性及其类型，提供对提取过程的控制和灵活性。这里是一个关于Curricum Vitae（简历）中信息的所需模式的示例：

```
from typing import Optional
from pydantic import BaseModel
class Experience(BaseModel):
    start_date: Optional[str]
    end_date: Optional[str]
    description: Optional[str]
class Study(Experience):
    degree: Optional[str]
    university: Optional[str]
    country: Optional[str]
    grade: Optional[str]
class WorkExperience(Experience):
    company: str
    job_title: str
class Resume(BaseModel):
    first_name: str
    last_name: str
    linkedin_url: Optional[str]
    email_address: Optional[str]
    nationality: Optional[str]
    skill: Optional[str]
    study: Optional[Study]
    work_experience: Optional[WorkExperience]
    hobby: Optional[str]
```

我们可以利用这个来从简历中提取信息。这里有一个来自[https://github.com/xitanggg/open-resume](https://github.com/xitanggg/open-resume)的示例简历。

![图4.3：示例简历摘录。](../media/file29.png)

图4.3：示例简历摘录。

我们将尝试从这份简历中解析信息。利用LangChain中的`create_extraction_chain_pydantic()`函数，我们可以将我们的模式作为输入提供，输出将是一个符合它的实例化对象。简单来说，我们可以尝试这段代码片段：

```
from langchain.chains import create_extraction_chain_pydantic
from langchain.chat_models import ChatOpenAI
from langchain.document_loaders import PyPDFLoader
pdf_loader = PyPDFLoader(pdf_file_path)
docs = pdf_loader.load_and_split()
# please note that function calling is not enabled for all models!
llm = ChatOpenAI(model_name="gpt-3.5-turbo-0613")
chain = create_extraction_chain_pydantic(pydantic_schema=Resume, llm=llm)
return chain.run(docs)
```

我们应该得到这样的输出：

```
[Resume(first_name='John', last_name='Doe', linkedin_url='linkedin.com/in/john-doe', email_address='hello@openresume.com', nationality=None, skill='React', study=None, work_experience=WorkExperience(start_date='May 2023', end_date='Present', description='Lead a cross-functional team of 5 engineers in developing a search bar, which enables thousands of daily active users to search content across the entire platform. Create stunning home page product demo animations that drives up sign up rate by 20%. Write clean code that is modular and easy to maintain while ensuring 100% test coverage.', company='ABC Company', job_title='Software Engineer'), hobby=None)]
```

这还远非完美 - 只有一个工作经验被解析出来。但考虑到我们迄今为止所付出的少量努力，这是一个很好的开始。请查看Github上的示例以获取完整示例。我们可以添加更多功能，例如猜测个性或领导能力。OpenAI将这些函数调用注入到系统消息中，采用一定的语法，这是他们的模型经过优化的。这意味着函数会计入上下文限制，并相应地计入输入令牌。LangChain本身具有将函数调用注入为提示的功能。这意味着我们可以在LLM应用程序中使用除OpenAI之外的模型提供者进行函数调用。我们现在将看看这一点，并将其构建为一个带有Streamlit的交互式Web应用程序。

## 用工具回答问题

LLMs是在一般语料库数据上训练的，可能对需要领域特定知识的任务不够有效。单独使用LLMs无法与环境互动和访问外部数据源，然而，LangChain提供了一个平台，用于创建访问实时信息并执行任务的工具，如天气预报、预订、建议食谱和管理任务。代理和链框架内的工具允许开发由LLMs驱动的应用程序，这些应用程序具有数据感知和代理性，并且开辟了解决LLMs问题的广泛方法，扩展了它们的用例并使其更加多功能和强大。工具的一个重要方面是它们能够在特定领域内工作或处理特定输入。例如，LLM缺乏固有的数学能力。然而，像计算器这样的数学工具可以接受数学表达式或方程式作为输入并计算结果。LLM与这样的数学工具结合进行计算并提供准确答案。通常，这种检索方法和LLMs的组合被称为**检索增强生成**（**RAG**），通过从外部源中检索相关数据并将其注入上下文来解决LLMs的限制。这些检索到的数据作为附加信息用于增强提供给LLMs的提示。通过通过RAG将LLMs与用例特定信息联系起来，可以提高响应的质量和准确性。通过检索相关数据，RAG有助于减少LLMs的幻觉响应。例如，在医疗应用中使用的LLM可以在推断过程中从外部源（如医学文献或数据库）检索相关医疗信息。然后，这些检索到的数据可以被整合到上下文中，以增强生成的响应并确保它们准确且与领域特定知识一致。在这种情况下实施RAG的好处是双重的。首先，尽管模型的训练数据截止日期，它允许将最新信息纳入响应中。这确保用户即使对于最新事件或不断发展的主题也能收到准确和相关的信息。其次，RAG通过利用外部信息源检索特定上下文，增强了ChatGPT提供更详细和上下文答案的能力。通过从新闻文章或与特定主题相关的网站等来源检索特定上下文，响应将更加准确。

> RAG（检索增强生成）通过从数据源中检索信息来补充提供给语言模型的提示，为模型提供生成准确响应所需的上下文。RAG包括几个步骤：

+   **提示**：用户向聊天机器人提供提示，描述他们对输出的期望。

+   **研究**：执行上下文搜索并从各种数据源中检索相关信息。这可能涉及查询数据库，根据关键词搜索索引文档，或调用API从外部源检索数据。

+   **更新资源**：检索到的上下文被注入到原始提示中，用额外的事实信息增强它，与用户的查询相关。这种增强的提示提高了准确性，因为它提供了对事实数据的访问。

+   **叙述**：基于这个增强的输入，LLM生成包含事实正确信息的响应，并将其发送回聊天机器人以传递给用户。

因此，通过结合外部数据源并将相关上下文注入提示中，RAG增强了LLMs生成准确、最新且与特定领域或感兴趣主题相关的响应能力。通过工具和推理增强LLMs的示例如下（来源：https://github.com/billxbf/ReWOO，由Binfeng Xu等人于2023年5月撰写的论文“Decoupling Reasoning from Observations for Efficient Augmented Language Models Resources”实施）：

![图4.4：工具增强的LM范式，利用语言模型的可预见推理能力来提高系统参数和提示效率](../media/file30.jpg)

图4.4：工具增强的LM范式，利用语言模型的可预见推理能力来提高系统参数和提示效率

让我们看看这个过程！在LangChain中有很多可用的工具，如果这还不够的话，自己开发工具也不难。让我们设置一个带有几个工具的代理：

```
from langchain.agents import (
    AgentExecutor, AgentType, initialize_agent, load_tools
)
from langchain.chat_models import ChatOpenAI
def load_agent() -> AgentExecutor:
    llm = ChatOpenAI(temperature=0, streaming=True)
    # DuckDuckGoSearchRun, wolfram alpha, arxiv search, wikipedia
    # TODO: try wolfram-alpha!
    tools = load_tools(
        tool_names=["ddg-search", "wolfram-alpha", "arxiv", "wikipedia"],
        llm=llm
    )
    return initialize_agent(
        tools=tools, llm=llm, agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION, verbose=True
    )
```

要知道`AgentExecutor`是一个链的重要细节，因此 - 如果我们愿意的话，我们可以将其集成到更大的链中。我们可以使用不同的语法初始化这个链，就像这样：

```
return MRKLChain.from_chains(llm, chains, verbose=True)
```

在这种语法中，我们将工具作为链配置传递。MRKL代表Modular Reasoning, Knowledge and Language。Zero-Shot Agent是MRKL框架中最通用的操作代理。请注意`ChatOpenAI`构造函数中的`streaming`参数，设置为`True`。这样可以提供更好的使用体验，因为这意味着文本响应将在接收到时更新，而不是等到所有文本完成后再更新。目前只有OpenAI、ChatOpenAI和ChatAnthropic实现支持流式传输。所有提到的工具都有其特定的目的，这是描述的一部分，传递给语言模型。这些工具被插入到代理中：

+   DuckDuckGo - 一个专注于隐私的搜索引擎；一个额外的优势是它不需要开发者注册

+   Wolfram Alpha - 一种将自然语言理解与数学能力结合的集成，用于问题如“2x+5 = -3x + 7是什么？”

+   Arxiv - 在学术预印本出版物中搜索；这对于研究导向的问题很有用

+   Wikipedia - 用于任何关于显著知名实体的问题

请注意，为了使用 Wolfram Alpha，您必须设置一个账户，并设置`WOLFRAM_ALPHA_APPID`环境变量，其中包含您在[https://developer.wolframalpha.com/](https://developer.wolframalpha.com/)创建的开发者令牌。除了 DuckDuckGo 外，LangChain 集成了许多其他搜索工具，让您可以利用 Google 或 Bing 搜索引擎或使用元搜索引擎。还有一个用于天气信息的 Open-Meteo - 集成，不过，这些信息也可以通过搜索获得。让我们将我们的代理作为一个 streamlit 应用程序提供。

> **Streamlit** 是一个面向机器学习和数据科学团队的开源应用程序框架。它允许用户使用 Python 在几分钟内创建漂亮的 Web 应用程序。

让我们使用我们刚刚定义的`load_agent()`函数编写代码：

```
import streamlit as st
from langchain.callbacks import StreamlitCallbackHandler
chain = load_agent()
st_callback = StreamlitCallbackHandler(st.container())
if prompt := st.chat_input():
    st.chat_message("user").write(prompt)
    with st.chat_message("assistant"):
        st_callback = StreamlitCallbackHandler(st.container())
        response = chain.run(prompt, callbacks=[st_callback])
        st.write(response)
```

请注意，我们在调用链时使用了回调处理程序，这意味着我们将看到从模型返回的响应。我们可以像这样从终端本地启动应用程序：

```
PYTHONPATH=. streamlit run question_answering/app.py
```

> Streamlit 应用程序的部署可以是本地的或在服务器上。或者，您可以将其部署在 Streamlit Community Cloud 或 Hugging Face Spaces 上。

+   对于**Streamlit Community Cloud**，请执行以下操作：

+   1\. 创建一个 Github 存储库

+   2\. 转到 Streamlit Community Cloud，点击“新应用程序”并选择新的存储库

+   3\. 点击“部署！”

+   至于**Hugging Face Spaces**的工作原理如下：

+   1\. 创建一个 Github 存储库

+   2\. 在 https://huggingface.co/ 创建一个 Hugging Face 账户

+   3\. 转到“Spaces”并点击“创建新空间”。在表单中，填写名称，空间类型为“Streamlit”，并选择新的存储库。

这是应用程序的屏幕截图：

![图 4.5：Streamlit 中的问答应用程序。](../media/file31.png)

图 4.5：Streamlit 中的问答应用程序。

搜索效果相当不错，尽管根据使用的工具不同，可能仍会出现错误结果。对于关于哺乳动物中哪种动物有最大蛋的问题，使用DuckDuckGo会返回一个讨论鸟类和哺乳动物蛋的结果，并有时得出鸵鸟是哺乳动物中有最大蛋的结论，尽管鸭嘴兽有时也会出现。以下是正确推理的日志输出（缩短版）：

```
> Entering new AgentExecutor chain...
I'm not sure, but I think I can find the answer by searching online.
Action: duckduckgo_search
Action Input: "mammal that lays the biggest eggs"
Observation: Posnov / Getty Images. The western long-beaked echidna ...
Final Answer: The platypus is the mammal that lays the biggest eggs.
> Finished chain.
```

您可以看到，有一个强大的自动化和问题解决框架在您手边，您可以将需要数百小时的工作压缩到几分钟内。您可以尝试不同的研究问题，看看工具是如何使用的。书籍存储库中的实际实现允许您尝试不同的工具，并提供自我验证选项。通过LLMs的检索增强生成（RAG），可以通过将外部来源的相关数据注入上下文中显着提高响应的准确性和质量。通过用特定用例的知识来基础LLMs，我们可以减少幻觉，并使它们在现实场景中更有用。RAG比重新训练模型更具成本效益和效率。您可以在BlockAGI项目中看到LangChain的增强信息检索的一个非常先进的示例，该项目受到BabyAGI和AutoGPT的启发，网址为[https://github.com/blockpipe/BlockAGI](https://github.com/blockpipe/BlockAGI)在接下来的章节中，我们将通过它们的决策策略比较主要类型的代理。

## 推理策略

当前一代生成模型（如LLMs）擅长发现现实世界数据中的模式，如视觉和音频信息，以及非结构化文本，然而，它们在涉及结构化知识表示和推理的任务中所需的符号操作方面存在困难。推理问题对LLMs构成挑战，有不同的推理策略可以补充神经网络生成模型固有的模式补全能力。通过专注于在提取信息上进行符号操作，这些混合系统可以增强语言模型的能力。**模块化推理、知识和语言**（**MRKL**）是一个结合语言模型和工具执行推理任务的框架。在LangChain中，这包括三个部分：

1.  工具，

1.  一个`LLMChain`，以及

1.  代理本身。

工具是代理可以使用的可用资源，如搜索引擎或数据库。LLMChain负责生成文本提示并解析输出以确定下一步操作。代理类使用LLMChain的输出来决定采取哪种行动。我们在*第2章*，*LangChain简介*中讨论了工具使用策略。您可以在这个图表中看到观察推理模式：

![图 4.6：观察推理（来源：https://arxiv.org/abs/2305.18323；徐斌峰等，2023年5月）。](../media/file32.png)

图 4.6：观察推理（来源：https://arxiv.org/abs/2305.18323；徐斌峰等，2023年5月）。

**依赖观察的推理**涉及根据当前知识状态或通过观察获取的证据做出判断、预测或选择。在每次迭代中，代理向语言模型（LLM）提供上下文和示例。用户的任务首先与上下文和示例结合，然后交给LLM启动推理。LLM生成一个思考和一个动作，然后等待来自工具的观察。观察被添加到提示中以启动对LLM的下一次调用。在LangChain中，这是一个**行动代理**（也称为**零射击代理**，`ZERO_SHOT_REACT_DESCRIPTION`），这是创建代理时的默认设置。如前所述，计划也可以在任何行动之前制定。在LangChain中称为**计划和执行代理**的策略在这里示例化：

![图4.7：将推理与观察分离（来源：https://arxiv.org/abs/2305.18323；徐斌峰等人，2023年5月）。](../media/file33.png)

图4.7：将推理与观察分离（来源：https://arxiv.org/abs/2305.18323；徐斌峰等人，2023年5月）。

规划者（一个LLM），可以进行规划和工具使用的微调，生成计划列表（P）并调用一个工作者（在LangChain中：代理）通过使用工具收集证据（E）。P和E与任务结合，然后馈送给求解器（一个LLM）得到最终答案。我们可以编写一个伪算法如下：

+   规划所有步骤（规划者）

+   对于步骤中��每一步：

    +   确定完成步骤所需的适当工具

规划者和求解器可以是不同的语言模型。这打开了使用更小、专门的模型进行规划者和求解器，并为每个调用使用更少标记的可能性。我们可以在我们的研究应用程序中实现计划和解决方案，让我们开始吧！首先，让我们向`load_agent()`函数添加一个`strategy`变量。它可以取两个值，要么是“计划和解决”，要么是“一次性反应”。对于“一次性反应”，逻辑保持不变。对于“计划和解决”，我们将定义一个规划者和一个执行者，我们将用它们创建一个`PlanAndExecute`代理执行者：

```
from typing import Literal
from langchain.experimental import load_chat_planner, load_agent_executor, PlanAndExecute
ReasoningStrategies = Literal["one-shot-react", "plan-and-solve"]
def load_agent(
        tool_names: list[str],
        strategy: ReasoningStrategies = "one-shot-react"
) -> Chain:
    llm = ChatOpenAI(temperature=0, streaming=True)
    tools = load_tools(
        tool_names=tool_names,
        llm=llm
    )
    if strategy == "plan-and-solve":
        planner = load_chat_planner(llm)
        executor = load_agent_executor(llm, tools, verbose=True)
        return PlanAndExecute(planner=planner, executor=executor, verbose=True)
    return initialize_agent(
        tools=tools, llm=llm, agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION, verbose=True
    )
```

为简洁起见，我省略了我们之前已经导入的内容。让我们定义一个通过Streamlit中的单选按钮设置的新变量。我们将这个变量传递给`load_agent()`函数：

```
strategy = st.radio(
    "Reasoning strategy",
    ("plan-and-solve", "one-shot-react", ))
```

你可能已经注意到`load_agent()`接受一个字符串列表`tool_names`。这也可以在用户界面（UI）中选择：

```
tool_names = st.multiselect(
    'Which tools do you want to use?',
    [
        "google-search", "ddg-search", "wolfram-alpha", "arxiv",
        "wikipedia", "python_repl", "pal-math", "llm-math"
    ],
    ["ddg-search", "wolfram-alpha", "wikipedia"])
```

最后，在应用程序中，代理是这样加载的：

```
agent_chain = load_agent(tool_names=tool_names, strategy=strategy)
```

我们可以在这里看到UI：

![图4.8：在我们的研究应用程序中实现计划和执行。](../media/file34.png)

图4.8：在我们的研究应用程序中实现计划和执行。

请查看应用程序，并查看关于“在大型语言模型的背景下，什么是计划和解决代理”的不同步骤。简单来说，第一步，计划如下：

1.  定义大型语言模型：大型语言模型是在大量文本数据上训练的AI模型，可以根据其接收到的输入生成类似人类的文本。

1.  在大型语言模型的背景下理解计划的概念：在大型语言模型的背景下，计划指的是模型为解决问题或回答问题而生成的结构化大纲或一系列步骤。

1.  在大型语言模型的背景下理解解决代理的概念：解决代理是大型语言模型的一个组成部分，负责生成计划以解决问题或回答问题。

1.  认识到在大型语言模型中计划和解决代理的重要性：计划和解决代理有助于组织模型的思维过程，并为解决问题或回答问题的任务提供了结构化方法。

1.  给出上述步骤后，请回答用户的原始问题：在大型语言模型的背景下，计划是由解决代理生成的用于解决问题或回答问题的结构化大纲或一系列步骤。解决代理是大型语言模型的一个组成部分，负责生成这些计划。

因此，第一步是执行LLMs的查找：

```
Action:
{
"action": "Wikipedia",
"action_input": "large language models"
}
```

我们没有讨论这个问题的另一个方面，即在这些步骤中使用的提示策略。例如，不同的提示策略为LLMs在复杂推理问题中提供了解决挑战的方法。一种方法是**few-shot chain-of-thought**（**CoT**）提示，其中LLMs通过逐步推理演示进行引导。例如，在算术推理中，可以向LLM展示解方程的演示示例，以帮助其理解过程。另一种策略是**zero-shot-CoT**提示，它消除了手动演示的需要。相反，会向提供给LLM的问题陈述附加一个通用提示，如“让我们逐步思考”。这使得模型能够在没有先前明确示例的情况下生成推理步骤。在算术推理中，问题陈述可以用这个提示进行增强，并输入LLM。**Plan-and-Solve (PS)提示**，涉及将复杂任务分解为较小的子任务，并根据计划逐步执行它们。例如，在解方程或涉及多个步骤的文字问题的数学推理问题中，PS提示使LLM能够为处理每个子步骤制定计划，如提取相关变量和计算中间结果。为了进一步提高推理步骤和指导的质量，引入了**PS+**提示。它包括更详细的说明，如强调提取相关变量和考虑计算和常识。PS+提示确保LLMs更好地理解问题，并能够生成准确的推理步骤。例如，在算术推理中，PS+提示可以引导LLM识别关键变量，正确执行计算，并在推理过程中应用常识知识。这结束了我们对推理策略的讨论。所有策略都存在问题，可能表现为计算错误、遗漏步骤错误和语义误解。然而，它们有助于提高生成的推理步骤的质量，提高解决问题任务的准确性，并增强LLMs处理各种类型推理问题的能力。

## 总结

在本章中，我们讨论了幻觉问题、自动事实核查以及如何使 LLMs 更可靠。特别强调了工具和提示策略。我们首先研究并实施提示策略，以分解和总结文档。这对消化大型研究文章或分析非常有帮助。一旦我们开始频繁调用 LLMs，这可能意味着我们会产生很多成本。因此，我专门为令牌使用开辟了一个章节。工具为 LLMs 在各个领域提供了创造性解决方案，并开辟了新的可能性。例如，可以开发一个工具来使 LLM 能够执行高级检索搜索、查询数据库以获取特定信息、自动撰写电子邮件，甚至处理电话。OpenAI API 实现了我们可以使用的功能，其中包括在文档中进行信息提取。我们实现了一个非常简单的简历解析器的示例功能。然而，工具和函数调用并不是 OpenAI 所独有的。通过 Streamlit，我们可以实现调用工具的不同代理。我们实现了一个应用程序，可以通过依赖外部工具如搜索引擎或维基百科来帮助回答研究问题。然后，我们研究了代理使用的不同决策策略。主要区别在于决策点。我们将计划和解决以及一次性代理实现到了一个 Streamlit 应用程序中。希望这能展示出在几行代码中我们可以实现在某些情况下非常令人印象深刻的应用程序。然而，重要的是要清楚，本章开发的应用程序有局限性。它们可以帮助您显著提高效率，但是您作为人类必须运用判断力并改进写作，以确保其连贯并有意义。让我们看看您是否记得本章的一些关键要点！

## 问题

请看看您是否能够从记忆中找到这些问题的答案。如果您对任何问题不确定，我建议您回到本章的相应部分：

1.  什么是幻觉？

1.  自动事实核查是如何工作的？

1.  在 LangChain 中，我们可以做些什么来确保输出是有效的？

1.  什么是 LangChain 中的 map-reduce？

1.  我们如何计算我们使用的令牌（以及为什么应该这样做）？

1.  RAG 代表什么，使用它有什么优势？

1.  LangChain 中有哪些可用工具？

1.  请定义计划和解决代理

1.  请定义一次性代理

1.  我们如何在 Streamlit 中实现文本输入字段和单选按钮？
