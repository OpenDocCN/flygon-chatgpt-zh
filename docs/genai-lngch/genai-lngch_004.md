# 3 使用 LangChain 入门

## 在 Discord 上加入我们的书籍社区

[`packt.link/EarlyAccessCommunity`](https://packt.link/EarlyAccessCommunity)

![自动生成的二维码描述](img/file19.png)

在本章中，我们将首先设置**LangChain**和本书所需的库，提供了关于常见依赖管理工具如**Docker**、**Conda**、**Pip**和**Poetry**的说明。然后我们将介绍可以使用的模型集成，如**OpenAI**的**Chatgpt**，Huggingface 和 Jina AI 上的模型等。我们将依次介绍、设置和使用几个提供商。我们将获取 API 密钥令牌，然后进行一个简短的实际示例。这将为我们提供更多关于如何有效使用**LangChain**的上下文，并介绍使用它的技巧和窍门。作为最后一部分，我们将开发一个**LangChain**应用程序，这是一个实际示例，说明了在客户服务的实际业务用例中如何应用**LangChain**。主要部分包括：

+   如何设置**LangChain**？

+   模型集成

+   客户服务助手

我们将从在您的计算机上设置**LangChain**开始本章。

## 如何设置 LangChain？

在本书中，我们谈论的是 LangChain。我们可以通过在终端中简单地输入`pip install langchain`来安装 LangChain，然而，在本书中，我们还将在几种不同的用例中使用各种其他工具和集成。为了确保所有示例和代码片段按预期工作，并且不仅仅在我的机器上工作，而是对于任何安装此软件的人都能工作，我提供了设置环境的不同方法。设置 Python 环境有各种方法。在这里，我们描述了四种安装相关依赖项的流行方法：Docker、Conda、Pip 和 Poetry。如果在安装过程中遇到问题，请参考各自的文档或在本书的 Github 存储库上提出问题。这些不同的安装在发布本书时已经经过测试，但是事情可能会发生变化，我们将在线更新 Github 自述文件，包括可能出现问题的解决方法。请在本书的存储库中找到一个用于 docker 的`Dockerfile`，一个用于 pip 的`requirements.txt`，一个用于 poetry 的`pyproject.toml`和一个用于**Conda**的`langchain_ai.yml`文件：[`github.com/benman1/generative_ai_with_langchain`](https://github.com/benman1/generative_ai_with_langchain)让我们从 Python 开始设置我们的环境。

### Python 安装

在设置 Python 环境并安装相关依赖项之前，通常应该安装 Python 本身。我假设，大多数购买本书的人都已经安装了 Python，但是，为了确保，让我们来看看。您可以从 python.org 下载最新版本适用于您操作系统的版本，或者使用您平台的软件包管理器。让我们看看在 MacOS 使用 Homebrew 和在 Ubuntu 使用 apt-get。在 MacOS 上，使用 Homebrew，我们可以：

```
brew install python
```

对于 Ubuntu，我们可以使用 apt-get：

```
sudo apt-get updatesudo apt-get install python3.10
```

> **提示**：如果您是编程或 Python 的新手，建议在继续 LangChain 和本书中的应用之前先参考一些初学者级别的教程。

一个重要的工具，用于交互式地尝试数据处理和模型的是 Jupyter 笔记本和 lab。让我们现在来看看这个。

### Jupyter Notebook 和 JupyterLab

Jupyter Notebook 和 JupyterLab 是用于创建、共享和协作计算文档的开源基于 Web 的交互式环境。它们使用户能够在单个称为笔记本的文档中编写代码、显示可视化效果并包含解释性文本。两者之间的主要区别在于它们的界面和功能。

> **Jupyter Notebook** 的目标是支持像 Julia、Python 和 R 这样的各种编程语言 - 实际上，项目名称是对这三种语言的引用。Jupyter Notebook 提供了一个简单的用户界面，允许用户使用线性布局创建、编辑和运行笔记本。它还支持用于额外功能和自定义的扩展。
> 
> > 另一方面，**JupyterLab** 是 Jupyter Notebook 的增强版本。JupyterLab 于 2018 年推出，提供了一个更强大和灵活的环境，用于处理笔记本和其他文件类型。它提供了一个模块化、可扩展和可定制的界面，用户可以在其中并排排列多个窗口（例如笔记本、文本编辑器、终端），从而促进更高效的工作流程。

您可以像这样从终端在计算机上启动笔记本服务器：

```
jupyter notebook
```

您应该看到您的浏览器打开一个新标签页，显示类似这样的 Jupyter 笔记本：

![图 3.1：带有 LangChain 代理的 Jupyter Notebook。](img/file20.png)

图 3.1：带有 LangChain 代理的 Jupyter Notebook。

或者，我们也可以使用 JupyterLab，这是下一代带来显著改进的笔记本服务器。您可以像这样从终端启动 JupyterLab 笔记本服务器：

```
jupyter lab
```

我们应该看到类似这样的东西：

![图 3.2：带有 LangChain 代理的 Jupyter Lab。](img/file21.png)

图 3.2：带有 LangChain 代理的 Jupyter Lab。

`Jupyter notebook`或`JupyterLab`中的任何一个都将为您提供一个**集成开发环境**（**IDE**），用于处理本书中将介绍的一些代码。安装 Python 和笔记本或实验室后，让我们快速探讨依赖管理工具（**Docker**、**Conda**、**Pip**和**Poetry**）之间的区别，并使用它们完全设置我们的环境，以便在 LangChain 项目中进行工作！

### 环境管理

在我们探索为在**LangChain**中使用生成模型设置 Python 环境的各种方法之前，了解主要依赖管理工具之间的区别是至关重要的：**Docker**、**Conda**、**Pip**和**Poetry**。这四个工具在软件开发和部署领域被广泛使用。

> **Docker** 是一个提供操作系统级虚拟化的开源平台，通过容器化自动化应用程序的部署。它在安装了 Docker 的任何系统上都可以一致地运行轻量级、可移植的容器内的应用程序。
> 
> > **Conda** 是一个跨平台的包管理器，擅长安装和管理来自多个渠道的软件包，不仅限于 Python。主要面向数据科学和机器学习项目，它可以强大地处理复杂的依赖关系树，满足具有大量依赖关系的复杂项目的需求。
> > 
> > **Pip** 是 Python 最常用的包管理器，允许用户轻松安装和管理第三方库。然而，Pip 在处理复杂依赖关系时存在局限性，增加了在安装包时出现依赖冲突的风险。
> > 
> > **Poetry** 是一个较新的包管理器，结合了 Pip 和 Conda 的最佳特性。拥有现代直观的界面、强大的依赖解析系统以及支持创建虚拟环境，Poetry 提供了额外的功能，如依赖隔离、锁定文件和版本控制。

诗歌和 Conda 都简化了虚拟环境管理，而使用 Pip 通常涉及使用类似 virtualenv 的单独工具。这里推荐使用 Conda 进行安装。我们也会为 Pip 提供一个 requirements 文件以及 Poetry 的说明，但在某些情况下可能需要进行一些调整。我们将依次使用这些不同的工具进行安装。对于所有的说明，请确保您已经下载了本书的存储库（使用 Github 用户界面）或在您的计算机上克隆，并且已经切换到项目的根目录。以下是您在 Github 上找到下载选项的方法：

![图 3.3：Github 用户界面（UI）中的下载选项。](img/file22.png)

图 3.3：Github 用户界面（UI）中的下载选项。

如果您是 git 的新手，您可以按下 **Download ZIP**，然后使用您喜欢的工具解压缩存档。或者，使用 git 克隆存储库并切换到项目目录，您可以输入以下命令：

```
git clone https://github.com/benman1/generative_ai_with_langchain.git
cd generative_ai_with_langchain
```

现在我们在计算机上有了存储库，让我们从 Docker 开始吧！

#### Docker

Docker 是一个平台，使开发人员能够自动化部署、打包和管理应用程序。Docker 使用容器化技术，有助于标准化和隔离环境。使用容器的优势在于它保护您的本地环境免受您在容器内运行的任何 - 可能不安全的 - 代码的影响。缺点是镜像可能需要一些时间来构建，并且可能需要大约 10 千兆字节的存储容量。与其他环境管理工具类似，Docker 很有用，因为您可以为项目创建一个可重现的环境。您可以使用 Docker 创建一个包含您项目所需的所有库和工具的环境，并与他人共享该环境。要开始使用 Docker，请按照以下步骤进行：

1.  在您的计算机上安装 Docker。您可以在您的网络浏览器中转到 Docker 网站，并按照此处的安装说明进行操作：[`docs.docker.com/get-docker/`](https://docs.docker.com/get-docker/)

1.  在终端中运行以下命令构建 Docker 镜像（请注意：您需要在项目根目录中才能正常工作）。

```
docker build -t langchain_ai
```

这将从 Docker Hub 拉取 continuumio/miniconda3 镜像，并构建镜像。

1.  使用创建的镜像交互式地启动 Docker 容器：

```
docker run -it langchain_ai
```

这将在容器内启动我们的笔记本。我们应该能够从浏览器中导航到`Jupyter Notebook`。我们可以在此地址找到它：`http://localhost:8080/`接下来让我们看看 conda。

#### Conda

`Conda` 允许用户为不同项目管理多个环境。它适用于 Python、R 和其他语言，并通过维护与 Python 库相关的库列表来帮助安装系统库。开始使用 conda 的最佳方法是按照此链接中的说明安装 anaconda 或 miniconda：[`docs.continuum.io/anaconda/install/`](https://docs.continuum.io/anaconda/install/)虽然 conda 环境占用的磁盘空间比 Docker 少，但从 anaconda 开始，完整环境仍然需要大约 2.5 千兆字节。miniconda 设置可能会节省一些磁盘空间。还有一个图形界面可以使用 `conda`，Anaconda Navigator，可以安装在 macOS 和 Windows 上，并且可以从终端安装任何依赖项以及 `conda` 工具。让我们继续使用 `conda` 工具并安装本书的依赖项。要创建一个新环境，请执行以下命令：

```
conda env create --file langchain_ai.yml
```

`Conda`允许我们创建具有许多不同库的环境，还可以使用不同版本的 Python。我们在本书中一直使用 Python 3.10。通过运行以下命令激活环境：

```
conda activate langchain_ai
```

这就是全部，我们完成了。我们可以看到这应该是轻松和直接的。您现在可以在环境中启动`jupyter notebook`或`jupyter lab`，例如：

```
jupyter notebook
```

让我们来看一下 pip，这是`conda`的一个替代方案。

#### Pip

`Pip`是 Python 的默认软件包管理器。它允许您轻松安装和管理第三方库。我们可以安装单个库，还可以维护完整的 Python 库列表。如果它尚未包含在您的 Python 发行版中，请按照[`pip.pypa.io/`](https://pip.pypa.io/)上的说明安装 pip。要使用 pip 安装库，请使用以下命令。例如，要安装 NumPy 库，您将使用以下命令：

```
pip install numpy
```

您也可以使用`pip`来安装库的特定版本。例如，要安装 NumPy 库的 1.0 版本，您将使用以下命令：

```
pip install numpy==1.0
```

为了设置一个完整的环境，我们可以从一个要求列表开始 - 按照惯例，这个列表在一个名为`requirements.txt`的文件中。我已经将这个文件包含在项目的根目录中，列出了所有必要的库。您可以使用以下命令安装所有库：

```
pip install -r requirements.txt
```

请注意，正如前面提到的，Pip 不负责环境。Virtualenv 是一个可以帮助维护环境的工具，例如不同版本的库。让我们快速看一下这个：

```
# create a new environment myenv:
virtualenv myenv
# activate the myenv environment:
source myenv/bin/activate
# install dependencies or run python, for example:
python
# leave the environment again:
deactivate
Please note that in Windows, the activation command is slightly different – you'd run a shell script:
# activate the myenv environment:
myenv\Scripts\activate.bat
```

接下来让我们来看一下 Poetry。

#### Poetry

Poetry 是 Python 的依赖管理工具，简化了库的安装和版本控制。安装和使用都很简单，我们将看到。以下是 poetry 的快速概述：

1.  按照[`python-poetry.org/`](https://python-poetry.org/)上的说明安装 poetry

1.  在终端中运行`poetry install`（从之前提到的项目根目录）

该命令将自动创建一个新环境（如果您尚未创建），并安装所有依赖项。这就完成了 Poetry 的设置。现在我们将开始使用模型提供程序。

## 模型集成

在正式开始生成式人工智能之前，我们需要设置访问**大型语言模型**（**LLMs**）或文本到图像模型等模型的访问权限，以便将它们集成到我们的应用程序中。正如在*第一章*中讨论的*生成模型是什么*中所述，各大科技巨头都有各种**LLMs**，如**OpenAI**的**GPT-4**，**Google**的**BERT**和**PaLM-2**，**Meta AI**的**LLaMA**等等。借助**LangChain**的帮助，我们可以与所有这些模型进行交互，例如通过**应用程序编程接口**（**APIs**），或者我们可以调用我们在计算机上下载的开源模型。其中一些集成支持文本生成和嵌入。在本章中，我们将重点讨论文本生成，并在*第五章*中讨论嵌入、向量数据库和神经搜索，构建类似 ChatGPT 的聊天机器人。有许多模型托管提供商。目前，**OpenAI**、**Hugging Face**、**Cohere**、**Anthropic**、**Azure**、**Google Cloud Platform Vertex AI**（**PaLM-2**）和**Jina AI**是**LangChain**支持的众多提供商之一，但这个列表一直在不断增长。您可以在[`integrations.langchain.com/llms`](https://integrations.langchain.com/llms)查看所有支持的**LLMs**的集成。至于图像模型，主要开发者包括**OpenAI**（**DALL-E**）、Midjourney 公司（Midjourney）和 Stability AI（**Stable Diffusion**）。**LangChain**目前没有直接处理非文本模型的功能，但其文档描述了如何与 Replicate 合作，后者也提供了与 Stable Diffusion 模型交互的接口。对于这些提供商中的每一个，要调用他们的应用程序编程接口（API），您首先需要创建一个帐户并获取一个 API 密钥。这对所有人都是免费的。有些提供商甚至不需要您提供信用卡信息。为了在环境中设置 API 密钥，在 Python 中我们可以这样做：

```
import os
os.environ["OPENAI_API_KEY"] = "<your token>"
```

这里`OPENAI_API_KEY`是适用于 OpenAI 的环境密钥。将密钥设置在您的环境中的好处是我们不需要将它们包含在我们的代码中。您也可以像这样从终端暴露这些变量：

```
export OPENAI_API_KEY=<your token>
```

让我们依次介绍一些知名的模型提供商。我们将为每个模型提供一个示例用法。让我们从一个用于测试的 Fake LLM 开始，以便展示基本思想！

### Fake LLM

Fake LM 是用于测试的。LangChain 文档中有一个关于该工具与 LLMs 一起使用的示例。您可以直接在 Python 中执行此示例，也可以在笔记本中执行。

```
from langchain.llms.fake import FakeListLLM
from langchain.agents import load_tools
from langchain.agents import initialize_agent
from langchain.agents import AgentType
tools = load_tools(["python_repl"])
responses = ["Action: Python_REPL\nAction Input: print(2 + 2)", "Final Answer: 4"]
llm = FakeListLLM(responses=responses)
agent = initialize_agent(
    tools, llm, agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION, verbose=True
)
agent.run("whats 2 + 2")
```

我们连接了一个工具，一个名为 Python **Read-Eval-Print Loop**（**REPL**）的工具，根据**LLM**的输出来调用。虚拟列表**LLM**将给出两个响应，`responses`，这些响应不会根据输入而改变。我们设置了一个代理，根据我们在第二章中解释的 ReAct 策略做出决策，这个策略是基于 LangChain 的介绍（`ZERO_SHOT_REACT_DESCRIPTION`）。我们用一个文本运行代理，问题是“2 + 2 等于多少”。我们可以观察到虚拟 LLM 的输出如何导致调用 Python 解释器，后者返回 4。请注意，操作必须与工具的`name`属性匹配，即`PythonREPLTool`，它的启动方式如下：

```
class PythonREPLTool(BaseTool):
    """A tool for running python code in a REPL."""
    name = "Python_REPL"
    description = (
        "A Python shell. Use this to execute python commands. "
        "Input should be a valid python command. "
        "If you want to see the output of a value, you should print it out "
        "with `print(...)`."
    )
```

工具的名称和描述被传递给**LLM**，然后根据提供的信息做出决定。Python 解释器的输出被传递给虚拟**LLM**，后者忽略观察结果并返回 4。显然，如果我们将第二个响应更改为“`最终答案：5`”，代理的输出将不对应问题。在接下来的章节中，我们将通过使用一个真实的**LLM**而不是一个虚假的**LLM**来使这更有意义。目前，任何人首先会想到的提供者之一是 OpenAI。

### OpenAI

如*第一章*中所解释的，*生成模型是什么？*，OpenAI 是一家美国人工智能研究实验室，目前是生成式人工智能模型的市场领导者，尤其是 LLM。他们提供一系列不同功率级别的模型，适用于不同的任务。在本章中，我们将看到如何使用**LangChain**和 OpenAI Python 客户端库与 OpenAI 模型进行交互。OpenAI 还为文本嵌入模型提供了一个 Embedding 类。我们将主要用 OpenAI 进行我们的应用。有几种模型可供选择 - 每个模型都有自己的优点、令牌使用计数和用例。主要的 LLM 模型是 GPT-3.5 和 GPT-4，具有不同的令牌长度。你可以在[`openai.com/pricing`](https://openai.com/pricing)看到不同模型的定价。我们首先需要获取一个 OpenAI API 密钥。要创建 API 密钥，请按照以下步骤操作：

1.  你需要在[`platform.openai.com/`](https://platform.openai.com/)创建一个登录账号。

1.  设置你的账单信息。

1.  你可以在*个人 -> 查看 API 密钥*下看到**API 密钥**。

1.  点击**创建新的秘密密钥**并给它一个**名称**。

这是在 OpenAI 平台上的样子：

![图 3.4：OpenAI API 平台 - 创建新的秘密密钥。](img/file23.png)

图 3.4：OpenAI API 平台 - 创建新的秘密密钥。

点击“**创建秘钥**”后，您应该会看到消息“API 秘钥已生成”。您需要将该秘钥复制到剪贴板并保存。我们可以将该秘钥设置为环境变量（`OPENAI_API_KEY`），或者在每次构建 OpenAI 调用类时作为参数传递。我们可以使用`OpenAI`语言模型类来建立一个**LLM**以进行交互。让我们创建一个使用这个模型进行计算的代理 - 我省略了前一个示例中的导入部分：

```
from langchain.llms import OpenAI
llm = OpenAI(temperature=0., model="text-davinci-003")
agent = initialize_agent(
    tools, llm, agent=AgentType.ZERO_SHOT_REACT_DESCRIPTION, verbose=True
)
agent.run("whats 4 + 4")
```

我们应该看到以下输出：

```
> Entering new  chain...
 I need to add two numbers
Action: Python_REPL
Action Input: print(4 + 4)
Observation: 8
Thought: I now know the final answer
Final Answer: 4 + 4 = 8
> Finished chain.
'4 + 4 = 8'
```

这看起来相当有前途，我认为。让我们继续前往下一个提供商和更多示例！

### Hugging Face

Hugging Face 是自然语言处理领域中非常重要的参与者，在开源和托管解决方案方面具有相当大的影响力。该公司是一家美国公司，开发用于构建机器学习应用程序的工具。其员工开发和维护 Transformers Python 库，用于自然语言处理任务，包括 BERT 和 GPT-2 等最先进和流行的模型的实现，并兼容**PyTorch**、**TensorFlow**和**JAX**。Hugging Face 还提供 Hugging Face Hub，这是一个托管基于 Git 的代码存储库、机器学习模型、数据集和 Web 应用程序的平台，提供超过 12 万个模型、2 万个数据集和 5 万个演示应用程序（Spaces）供机器学习使用。这是一个在线平台，人们可以在此协作并共同构建机器学习。这些工具允许用户加载和使用来自 Hugging Face 的模型、嵌入和数据集。例如，`HuggingFaceHub`集成提供了访问不同模型的功能，如文本生成和文本分类。`HuggingFaceEmbeddings`集成允许用户使用句子转换模型。他们在其生态系统中还提供了其他各种库，包括用于数据集处理的 Datasets，用于模型评估的*Evaluate*，用于模拟的*Simulate*，以及用于机器学习演示的*Gradio*。除了他们的产品，Hugging Face 还参与了一些倡议，如 BigScience 研究研讨会，他们发布了一个名为 BLOOM 的开放大型语言模型，拥有 1760 亿个参数。他们获得了大量资金，包括 4 亿美元的 B 轮融资和最近由 Coatue 和 Sequoia 领投的 C 轮融资，估值 20 亿美元。Hugging Face 还与 Graphcore 和亚马逊网络服务等公司合作，优化其产品并使其面向更广泛的客户群体。要将 Hugging Face 用作您模型的提供商，您可以在[`huggingface.co/settings/profile`](https://huggingface.co/settings/profile)上创建帐户和 API 秘钥。您可以将令牌作为`HUGGINGFACEHUB_API_TOKEN`在您的环境中使用。让我们看一个示例，我们使用了由 Google 开发的开源模型 Flan-T5-XXL：

```
from langchain.llms import HuggingFaceHub
llm = HuggingFaceHub(
    model_kwargs={"temperature": 0.5, "max_length": 64},
    repo_id="google/flan-t5-xxl"
)
prompt = "In which country is Tokyo?"
completion = llm(prompt)
print(completion)
```

我们得到了回应"`japan`"。**LLM**接受文本输入，本例中是一个问题，并返回一个完成。该模型具有大量知识，可以回答知识性问题。我们还可以得到简单的建议：

### Azure

由微软运行的云计算平台 Azure 与 OpenAI 集成，提供强大的语言模型，如 GPT-3、Codex 和 Embeddings。它通过全球数据中心提供访问、管理和开发应用程序和服务，用例包括写作辅助、摘要、代码生成和语义搜索。它提供**软件即服务**（**SaaS**）、**平台即服务**（**PaaS**）和**基础设施即服务**（**IaaS**）等功能。通过 Github 或微软凭据进行身份验证，我们可以在[`azure.microsoft.com/`](https://azure.microsoft.com/)上创建 Azure 账户。然后可以在*Cognitive Services -> Azure OpenAI*下创建新的 API 密钥。这涉及到一些步骤，个人而言，我觉得这个过程很烦人和令人沮丧，所以我放弃了。设置完成后，模型应该可以通过**LangChain**中的`AzureOpenAI()` llm 类访问。

### Google Cloud

通过**Google Cloud Platform**（**GCP**）和其机器学习平台 Vertex 提供许多模型和功能。Google Cloud 提供访问**LLM**，如**LaMDA**、**T5**和**PaLM**。Google 还更新了 Google Cloud **自然语言**（**NL**）API，使用基于 LLM 的新模型进行内容分类。这个更新版本提供了一个广泛的预训练分类分类法，以帮助广告定位和基于内容的过滤。**NL** API 的改进 v2 分类模型增加了超过 1,000 个标签，并支持 11 种语言，具有更高的准确性。对于 GCP 中的模型，您需要安装 gcloud **命令行界面**（**CLI**）。您可以在这里找到说明：[`cloud.google.com/sdk/docs/install`](https://cloud.google.com/sdk/docs/install)然后可以通过终端使用以下命令进行身份验证并打印一个密钥令牌：

```
gcloud auth application-default login
```

您还需要为您的项目启用 Vertex。如果您还没有启用它，您应该会收到一个有用的错误消息，指向正确的网站，在那里您必须点击"启用"。让我们运行一个模型！

```
from langchain.llms import VertexAI
from langchain import PromptTemplate, LLMChain
template = """Question: {question}
Answer: Let's think step by step."""
prompt = PromptTemplate(template=template, input_variables=["question"])
llm = VertexAI()
llm_chain = LLMChain(prompt=prompt, llm=llm, verbose=True)
question = "What NFL team won the Super Bowl in the year Justin Beiber was born?"
llm_chain.run(question)
```

我们应该看到这个回应：

```
[1m> Entering new chain...[0m
Prompt after formatting:
[[Question: What NFL team won the Super Bowl in the year Justin Beiber was born?
Answer: Let's think step by step.[0m
[1m> Finished chain.[0m
Justin Beiber was born on March 1, 1994\. The Super Bowl in 1994 was won by the San Francisco 49ers.
```

我已将 verbose 设置为 True，以便查看模型的推理过程。令人印象深刻的是，即使给出了名字的拼写错误，它也能给出正确的回应。逐步提示指导是得出正确答案的关键。在 Vertex 中有各种模型可用，例如：

| **模型** | **描述** | **属性** |
| --- | --- | --- |
| text-bison | 经过微调以遵循自然语言指令 | 最大输入标记数：8,192 最大输出标记数：1,024 训练数据：截至 2023 年 2 月 |
| chat-bison | 专为多轮对话而调整 | 最大输入标记：4,096 最大输出标记：1,024 训练数据：截至 2023 年 2 月 最大轮数：2,500 |
| code-bison | 专为根据自然语言描述生成代码而调整 | 最大输入标记：4,096 最大输出标记：2,048 |
| codechat-bison | 专为帮助解决与代码相关问题的聊天机器人对话而调整 | 最大输入标记：4,096 最大输出标记：2,048 |
| code-gecko | 专为建议代码完成而调整 | 最大输入标记：2,048 最大输出标记：64 |

表 3.1：Vertex Generative AI 中可用的模型。您可以查看文档[`cloud.google.com/vertex-ai/docs/generative-ai`](https://cloud.google.com/vertex-ai/docs/generative-ai)。我们还可以生成代码。让我们看看**Code-Bison**模型是否能解决 FizzBuzz，这是入门和中级软件开发人员职位常见的面试问题：

```
question = """
Given an integer n, return a string array answer (1-indexed) where:
answer[i] == "FizzBuzz" if i is divisible by 3 and 5.
answer[i] == "Fizz" if i is divisible by 3.
answer[i] == "Buzz" if i is divisible by 5.
answer[i] == i (as a string) if none of the above conditions are true.
"""
llm = VertexAI(model_name="code-bison")
llm_chain = LLMChain(prompt=prompt, llm=llm)
print(llm_chain.run(question))
```

我们得到这个响应：

```
```python

答案 = []

for i in range(1, n + 1)：

    如果 i % 3 == 0 并且 i % 5 == 0：

        答案.append("FizzBuzz")

    否则如果 i % 3 == 0：

        答案.append("Fizz")

    否则如果 i % 5 == 0：

        答案.append("Buzz")

    否则：

        答案.append(str(i))

返回答案

```
```

你会雇用代码-野牛加入你的团队吗？

### Anthropic

Anthropic 是一家总部位于美国的人工智能初创公司和公益公司。它由 OpenAI 的前成员，包括兄弟达尼埃拉·阿莫代和达里奥·阿莫代于 2021 年创立。该公司专注于开发通用人工智能系统和语言模型，重点关注负责任的人工智能使用。截至 2023 年 7 月，Anthropic 已筹集了 15 亿美元的资金。他们还致力于项目，如 Claude，一个类似于 OpenAI 的 ChatGPT 的 AI 聊天机器人，并对机器学习系统的可解释性进行研究，特别是变压器架构。不幸的是，Claude 目前尚不向普通公众开放。您需要申请访问权限以使用 Claude 并设置`ANTHROPIC_API_KEY`环境变量。

### Jina AI

Jina AI 成立于 2020 年 2 月，由韩潇和何选斌创立，是一家总部位于柏林的德国人工智能公司，专注于提供基于云原生的神经搜索解决方案，涵盖文本、图像、音频和视频模型。他们的开源神经搜索生态系统使企业和开发人员能够轻松构建可扩展且高可用的神经搜索解决方案，实现高效的信息检索。最近，**Jina AI**推出了*Finetuner*，这是一款工具，可以对任何深度神经网络进行特定用例和需求的微调。该公司通过三轮融资共筹集了 3750 万美元，最近一轮融资是在 2021 年 11 月的 A 轮融资中获得的。**Jina AI**的知名投资者包括**GGV Capital**和**Canaan Partners**。您可以在[`cloud.jina.ai/`](https://cloud.jina.ai/)上设置登录。在该平台上，我们可以为不同用例设置 API，如图像描述、文本嵌入、图像嵌入、视觉问答、视觉推理、图像放大或中文文本嵌入。在这里，我们正在设置一个视觉问答 API，并使用推荐的模型：

![图 3.5：Jina AI 中的视觉问答 API。](img/file24.png)

图 3.5：Jina AI 中的视觉问答 API。

我们可以在 Python 和 cURL 中获取客户端调用的示例，以及一个演示，我们可以提出问题。这很酷，不幸的是，这些 API 目前还不能通过**LangChain**使用。我们可以通过在**LangChain**中将`LLM`类子类化为自定义**LLM**接口来实现这些调用。让我们再设置一个聊天机器人，这次由 Jina AI 提供支持。我们可以生成 API 令牌，并将其设置为`JINA_AUTH_TOKEN`，在[`chat.jina.ai/api`](https://chat.jina.ai/api)上设置。让我们在这里将英语翻译成法语：

```
from langchain.chat_models import JinaChat
from langchain.schema import HumanMessage
chat = JinaChat(temperature=0.)
messages = [
    HumanMessage(
        content="Translate this sentence from English to French: I love generative AI!"
    )
]
chat(messages)
```

```
We should be seeing 
```

```
AIMessage(content="J'adore l'IA générative !", additional_kwargs={}, example=False).
```

我们可以设置不同的温度，低温会使响应更可预测。在这种情况下，几乎没有什么区别。我们将以系统消息开始对话，澄清聊天机器人的目的。让我们询问一些食物推荐：

```
chat = JinaChat(temperature=0.)
chat(
    [
        SystemMessage(
            content="You help a user find a nutritious and tasty food to eat in one word."
        ),
        HumanMessage(
            content="I like pasta with cheese, but I need to eat more vegetables, what should I eat?"
        )
    ]
)
```

我在 Jupyter 中看到了这个响应：

```
AIMessage(content='A tasty and nutritious option could be a vegetable pasta dish. Depending on your taste, you can choose a sauce that complements the vegetables. Try adding broccoli, spinach, bell peppers, and zucchini to your pasta with some grated parmesan cheese on top. This way, you get to enjoy your pasta with cheese while incorporating some veggies into your meal.', additional_kwargs={}, example=False)
```

它忽略了单词指令，但我实际上很喜欢阅读这些想法。我想我可以尝试这个给我儿子。在其他聊天机器人中，我得到了 Ratatouille 的建议。了解 LangChain 中 LLMs 和 Chat Models 之间的区别很重要。LLMs 是文本完成模型，接受字符串提示作为输入，并输出字符串完成。Chat Models 类似于 LLMs，但专门设计用于对话。它们接受带有讲话者标签的聊天消息列表作为输入，并返回聊天消息作为输出。LLMs 和 Chat Models 都实现了 Base Language Model 接口，其中包括`predict()`和`predict_messages()`等方法。这种共享接口允许在应用程序中以及 Chat 和 LLM 模型之间实现不同类型模型的互换。

### 复制

成立于 2019 年的 Replicate Inc.是一家总部位于旧金山的初创公司，为人工智能开发者提供了一个简化的流程，他们可以通过利用云技术以最少的代码输入实现和发布人工智能模型。该平台可以与私有模型和公共模型一起工作，并实现模型推理和微调。该公司最近一轮融资来自一笔总额为 1250 万美元的 A 轮融资，由 Andreessen Horowitz 领投，Y Combinator、Sequoia 以及各种独立投资者参与其中。Ben Firshman 曾在 Docker 负责开源产品工作，Andreas Jansson 曾是 Spotify 的前机器学习工程师，他们共同创立了 Replicate Inc.，共同的愿景是消除阻碍人工智能大规模接受的技术障碍。因此，他们创建了 Cog，这是一个开源工具，可以将机器学习模型打包成标准的生产就绪容器，可以在任何当前操作系统上运行，并自动生成 API。这些容器也可以通过 Replicate 平台部署在 GPU 集群上。因此，开发者可以集中精力进行其他重要任务，从而提高他们的生产力。您可以在[`replicate.com/`](https://replicate.com/)上使用您的 Github 凭据进行身份验证。然后，如果您点击左上角的用户图标，您会找到 API 令牌 - 只需复制 API 密钥并在您的环境中提供`REPLICATE_API_TOKEN`。为了运行更大的作业，您需要设置您的信用卡（在账单下）。您可以在[`replicate.com/explore`](https://replicate.com/explore)找到许多可用的模型。这里有一个创建图像的简单示例：

```
from langchain.llms import Replicate
text2image = Replicate(
    model="stability-ai/stable-diffusion:db21e45d3f7023abc2a46ee38a23973f6dce16bb082a930b0c49861f96d1e5bf",
    input={"image_dimensions": "512x512"},
)
image_url = text2image("a book cover for a book about creating generative ai applications in Python")
```

我得到了这张图片：

![图 3.7：一本关于使用 Python 进行生成式人工智能的书籍封面 - Stable Diffusion。](img/file25.png)

图 3.7：一本关于使用 Python 进行生成式人工智能的书籍封面 - Stable Diffusion。

我认为这是一幅不错的图像 - 那是一个创作艺术的 AI 芯片吗？让我们快速看看如何在 Huggingface transformers 或 Llama.cpp 中本地运行模型！

### 本地模型

我们也可以从 LangChain 运行本地模型。在此之前，我想先提醒一下：LLM 很大，这意味着它会占用很多空间。如果您有一台旧电脑，您可以尝试托管服务，如 google colabs。这些服务可以让您在具有大量内存和不同硬件（包括 Tensor 处理单元（TPUs）或 GPU）的机器上运行。由于这两种用例可能需要很长时间才能运行或导致 Jupyter 笔记本崩溃，我没有在笔记本中包含此代码或在设置说明中包含依赖项。但我认为在这里讨论它仍然是值得的。本地运行模型的优势是完全控制模型，不会在互联网上传输任何数据。让我们首先看看 Hugging Face 的 transformers 库。

#### Hugging Face transformers

我将快速展示设置和运行流水线的一般步骤：

```
from transformers import pipeline
import torch
generate_text = pipeline(
    model="aisquared/dlite-v1-355m",
    torch_dtype=torch.bfloat16,
    trust_remote_code=True,
    device_map="auto",
    framework="pt"
)
generate_text("In this chapter, we'll discuss first steps with generative AI in Python.")
```

这个模型非常小（3.55 亿个参数），但相对性能良好，并且针对对话进行了调整。请注意，对于本地模型，我们不需要 API 令牌！这将下载模型所需的一切，如分词器和模型权重。然后我们可以运行文本完成以为本章提供一些内容。为了将此流水线插入 LangChain 代理或链中，我们可以像之前看到的那样使用它：

```
from langchain import PromptTemplate, LLMChain
template = """Question: {question}
Answer: Let's think step by step."""
prompt = PromptTemplate(template=template, input_variables=["question"])
llm_chain = LLMChain(prompt=prompt, llm=generate_text)
question = "What is electroencephalography?"
print(llm_chain.run(question))
```

在这个示例中，我们还看到了使用`PromptTemplate`的示例，为任务提供具体的指令。接下来让我们来看看 Llama.cpp。

#### Llama.cpp

Llama.cpp 是一个 C++程序，执行基于 Llama 架构的模型，Llama 是 Meta AI 发布的第一个大型开源模型之一，随后衍生出许多其他模型的开发。请注意，您需要安装 md5 校验工具。这在几个 Linux 发行版中默认包含，如 Ubuntu。在 MacOs 上，您可以像这样使用 brew 安装：

```
brew install md5sha1sum
```

我们需要从 Github 下载 llama.cpp 存储库。您可以在线选择 Github 上的下载选项之一进行此操作，或者您可以从终端使用 git 命令，如下所示：

```
git clone https://github.com/ggerganov/llama.cpp.git
```

然后我们需要安装 python 要求，可以使用 pip 软件包安装程序来完成 - 为了方便起见，让我们也切换到 llama.cpp 项目根目录：

```
cd llama.cpp
pip install -r requirements.txt
```

您可能希望在安装要求之前创建一个 Python 环境 - 但这取决于您。现在我们需要编译 llama.cpp：

```
make -C . -j4 # runs make in subdir with 4 processes
```

我们可以使用 4 个进程并行构建。为了获得 Llama 模型权重，您需要注册并等待来自 Meta 的注册电子邮件。有一些工具，比如 pyllama 项目中的 llama 模型下载器，但请注意它们可能不符合 Meta 的许可规定。您可以从 Hugging Face 下载模型 - 这些模型应与 llama.cpp 兼容，比如 Vicuna 或 Alpaca。假设您已将 7B Llama 模型的模型权重下载到 models/7B 目录中。您可以下载更大尺寸的模型，如 13B、30B、65B，但是这里需要注意一点：这些模型在内存和磁盘空间方面都相当大。我们需要将模型转换为 llama.cpp 格式，称为**ggml**，使用转换脚本。然后我们可以选择对模型进行量化，以节省推理时的内存。量化是指减少用于存储权重的位数。

```
python3 convert.py models/7B/
./quantize ./models/ggml-model-f16.bin ./models/7B/ggml-model-q4_0.bin q4_0
```

这个最后的文件比之前的文件要小得多，在内存中占用的空间也要少得多，这意味着您可以在较小的机器上运行它。一旦我们选择了要运行的模型，我们可以将其集成到代理或链中，例如：

```
llm = LlamaCpp(
    model_path="./ggml-model-q4_0.bin",
    verbose=True
```

)

这结束了模型提供者的介绍。让我们构建一个应用程序！

## 客户服务助手

在本节中，我们将在 LangChain 中为客服代理构建一个文本分类应用程序。给定一个文档，比如一封电子邮件，我们希望将其分类为与意图相关的不同类别，提取情感，并提供摘要。客服代理负责回答客户查询，解决问题和处理投诉。他们的工作对于维护客户满意度和忠诚度至关重要，这直接影响公司的声誉和财务成功。生成式人工智能可以在几个方面帮助客服代理：

+   情感分类：这有助于识别客户情绪，并允许代理个性化回应。

+   摘要：这使代理能够理解冗长客户消息的要点并节省时间。

+   意图分类：类似于摘要，这有助于预测客户的目的，并允许更快地解决问题。

+   答案建议：这为代理提供了对常见查询的建议响应，确保提供准确和一致的消息。

这些方法的结合可以帮助客服代理更准确地并及时地回应，最终提高客户满意度。在这里，我们将集中讨论前三点。我们将记录查找，这可以用于答案建议在*第五章*，*构建类似 ChatGPT 的聊天机器人*。**LangChain**是一个非常灵活的库，具有许多集成，可以使我们解决各种文本问题。我们可以在执行这些任务时选择许多不同的集成。我们可以要求任何 LLM 为我们提供一个开放域（任何类别）分类或在多个类别之间进行选择。特别是由于它们的大训练规模，LLMs 是非常强大的模型，特别是在给定少量提示的情况下，用于情感分析，不需要任何额外的训练。这是由 Zengzhi Wang 等人在他们 2023 年 4 月的研究“ChatGPT 是一个好的情感分析器吗？初步研究”中分析的。对于情感分析的 LLM 的提示可能是这样的：

```
Given this text, what is the sentiment conveyed? Is it positive, neutral, or negative?
Text: {sentence}
Sentiment:
```

LLMs 在摘要方面也非常有效，比以往任何模型都要好。缺点可能是这些模型调用比传统的 ML 模型慢，成本更高。如果我们想尝试更传统或更小的模型。Cohere 和其他提供商将文本分类和情感分析作为其功能的一部分。例如，NLP Cloud 的模型列表包括 spacy 和许多其他模型：[`docs.nlpcloud.com/#models-list`](https://docs.nlpcloud.com/#models-list)许多 Hugging Face 模型支持这些任务，包括：

+   文档问答

+   摘要

+   文本分类

+   文本问答

+   翻译

我们可以在本地执行这些模型，通过在 transformer 中运行`pipeline`，在 Hugging Face Hub 服务器上远程执行（`HuggingFaceHub`），或者作为`load_huggingface_tool()`加载器的工具。Hugging Face 包含了成千上万的模型，许多经过特定领域微调。例如，`ProsusAI/finbert`是一个在 Financial PhraseBank 数据集上训练的 BERT 模型，可以分析金融文本的情感。我们也可以使用任何本地模型。对于文本分类，模型往往要小得多，因此这对资源的消耗会较小。最后，文本分类也可能是嵌入的一个案例，我们将在*第五章*，*构建类似 ChatGPT 的聊天机器人*中讨论。我决定尽可能多地使用我在 Hugging Face 上找到的较小模型来进行这个练习。我们可以通过 huggingface API 列出 Hugging Face Hub 上用于文本分类的下载量最高的 5 个模型：

```
def list_most_popular(task: str):
    for rank, model in enumerate(
        list_models(filter=task, sort="downloads", direction=-1)
):
        if rank == 5:
            break
        print(f"{model.id}, {model.downloads}\n")
list_most_popular("text-classification")
```

让我们看看列表：

| **模型** | **下载量** |
| --- | --- |
| nlptown/bert-base-multilingual-uncased-sentiment | 5805259 |
| SamLowe/roberta-base-go_emotions | 5292490 |
| cardiffnlp/twitter-roberta-base-irony | 4427067 |
| salesken/query_wellformedness_score | 4380505 |
| marieke93/MiniLM-evidence-types | 4370524 |

表 3.2：Hugging Face Hub 上最受欢迎的文本分类模型。我们可以看到这些模型涉及到情感、情绪、讽刺或格式良好等小范围的类别。让我们使用情感模型。

```
I've asked GPT-3.5 to put together a long rambling customer email complaining about a coffee machine. You can find the email on GitHub. Let's see what our sentiment model has to say:
from transformers import pipeline
sentiment_model = pipeline(
    task="sentiment-analysis",
    model="nlptown/bert-base-multilingual-uncased-sentiment"
)
print(sentiment_model(customer_email))
```

我得到了这个结果：

```
[{'label': '2 stars', 'score': 0.28999224305152893}]
```

不是一个开心的露营者。让我们继续！让我们也看看最受欢迎的 5 个摘要模型：

| **模型** | **下载量** |
| --- | --- |
| t5-base | 2710309 |
| t5-small | 1566141 |
| facebook/bart-large-cnn | 1150085 |
| sshleifer/distilbart-cnn-12-6 | 709344 |
| philschmid/bart-large-cnn-samsum | 477902 |

表 3.3：Hugging Face Hub 上最受欢迎的摘要模型。

所有这些模型与大型模型相比具有相对较小的占用空间。让我们在服务器上远程执行摘要模型：

```
from langchain import HuggingFaceHub
summarizer = HuggingFaceHub(
    repo_id="facebook/bart-large-cnn",
    model_kwargs={"temperature":0, "max_length":180}
)
def summarize(llm, text) -> str:
    return llm(f"Summarize this: {text}!")
summarize(summarizer, customer_email)
```

请注意，您需要设置您的`HUGGINGFACEHUB_API_TOKEN`才能使其工作。我看到了这个摘要：一个顾客的咖啡机到达时已经破损，引发了一种深深的不信和绝望感。顾客写道：“这种令人心碎的疏忽行为粉碎了我对每天享受完美咖啡的梦想，让我情感上感到痛苦和无法安慰。”他补充道：“我希望这封邮件能在我写信时内心充满理解的氛围中找到你。”这个摘要还算过得去，但不是很令人信服。摘要中仍然有很多啰嗦的内容。我们可以尝试其他模型，或者直接使用一个带有摘要提示的 LLM。让我们继续。了解客户写的是什么问题可能会很有用。让我们问问**VertexAI**：

```
from langchain.llms import VertexAI
from langchain import PromptTemplate, LLMChain
template = """Given this text, decide what is the issue the customer is concerned about. Valid categories are these:
* product issues
* delivery problems
* missing or late orders
* wrong product
* cancellation request
* refund or exchange
* bad support experience
* no clear reason to be upset
Text: {email}
Category:
"""
prompt = PromptTemplate(template=template, input_variables=["email"])
llm = VertexAI()
llm_chain = LLMChain(prompt=prompt, llm=llm, verbose=True)
print(llm_chain.run(customer_email))
```

我们得到了“产品问题”的反馈，这在我这里使用的长电子邮件示例中是正确的。希望看到我们可以多快地将几个模型和工具组合在一起在 LangChain 中得到实际有用的东西是令人兴奋的。我们可以很容易地将其展示在一个界面中，供客服代理查看。让我们总结一下。

## 总结

在本章中，我们已经介绍了四种不同的安装 LangChain 和本书所需的其他库的方法作为一个环境。然后，我们介绍了几个文本和图像模型的提供者。对于每一个模型，我们解释了如何获取 API 令牌，并演示了如何调用模型。最后，我们为客服的文本分类开发了一个 LLM 应用程序。通过在 LangChain 中链接各种功能，我们可以帮助减少客服的响应时间，并确保答案准确且切题。在第三章和第四章中，我们将更深入地探讨诸如通过增强检索进行问答等用例，使用工具如网络搜索和依赖文档搜索通过索引的聊天机器人。让我们看看您是否记得本章的一些关键要点！

## 问题

请看看是否能够回答这些问题。如果您对其中任何问题不确定，我建议您回到本章的相应部分查看：

1.  如何安装 LangChain？

1.  除了 OpenAI，至少列出 4 家 LLM 的云服务提供商！

1.  什么是 Jina AI 和 Hugging Face？

1.  如何使用 LangChain 生成图像？

1.  如何在本地机器上运行模型，而不是通过服务运行？

1.  如何在 LangChain 中执行文本分类？

1.  如何通过生成式人工智能帮助客服代理工作？
