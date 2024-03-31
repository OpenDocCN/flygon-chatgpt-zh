# 7种用于数据科学的LLMs

## 加入我们在Discord上的书籍社区

[https://packt.link/EarlyAccessCommunity](https://packt.link/EarlyAccessCommunity)

![自动生成的二维码描述](../media/file49.png)

本章讨论了生成式人工智能如何自动化数据科学。生成式人工智能，特别是大型语言模型（LLMs），有潜力加速各个领域的科学进展，尤其是通过提供对研究数据的高效分析和协助文献回顾过程。许多当前属于AutoML领域的方法可以帮助数据科学家提高生产力，并帮助使数据科学更具可重复性。我将首先概述数据科学中的自动化，然后我们将讨论生成式人工智能对数据科学的影响。接下来，我们将讨论如何以不同方式使用代码生成和工具来回答与数据科学相关的问题。这可以以模拟的形式进行，或者通过为数据集添加额外信息来丰富数据集。最后，我们将重点放在对结构化数据集的探索性分析上。我们可以设置代理来运行SQL或Pandas中的表格数据。我们将看到如何提出关于数据集的问题、关于数据的统计问题，或者要求可视化。在整个章节中，我们将使用LLMs进行数据科学的不同方法，您可以在书籍的Github存储库中的`data_science`目录中找到。主要章节包括：

+   自动化数据科学

+   代理可以回答数据科学问题

+   使用LLMs进行数据探索

让我们从讨论数据科学如何自动化以及其中的哪些部分开始，以及生成式人工智能将如何影响数据科学。

## 自动化数据科学

数据科学是一个结合了计算机科学、统计学和商业分析的领域，从数据中提取知识和见解。数据科学家使用各种工具和技术来收集、清洗、分析和可视化数据。然后他们利用这些信息帮助企业做出更好的决策。数据科学家的工作可能因具体角色和行业而异。然而，数据科学家可能执行的一些常见任务包括：

+   收集数据：数据科学家需要从各种来源收集数据，如数据库、社交媒体和传感器。

+   清洗数据：数据科学家需要清洗数据以消除错误和不一致性。

+   分析数据：数据科学家使用各种统计和机器学习技术来分析数据。

+   数据可视化：数据科学家使用数据可视化向利益相关者传达见解。

+   构建模型：数据科学家构建模型以预测未来结果或提出建议。

数据分析是数据科学的一个子集，专注于从数据中提取见解。数据分析师使用各种工具和技术来分析数据，但他们通常不构建模型。数据科学和数据分析之间的重叠之处在于两个领域都涉及与数据一起工作以提取见解。然而，数据科学家通常具有比数据分析师更丰富的技术技能。数据科学家也更有可能构建模型，并有时将模型部署到生产环境中。数据科学家有时将模型部署到生产环境中，以便实时做出决策，但在本讨论中，我们将避免自动部署模型。以下是总结数据科学和数据分析之间关键差异的表格：

| **特点** | **数据科学** | **数据分析** |
| --- | --- | --- |
| 技术技能 | 更丰富 | 较少 |
| 机器学习 | 是 | 否 |
| 模型部署 | 有时 | 否 |
| 焦点 | 提取见解和构建模型 | 提取见解 |

图 7.1：数据科学和数据分析的比较。

两者之间的共同点是收集数据、清洗数据、分析数据、可视化数据，所有这些都属于提取见解的范畴。数据科学另外还涉及训练机器学习模型，通常更加注重统计学。在某些情况下，根据公司的设置和行业惯例，部署模型和编写软件可能会被添加到数据科学的任务列表中。自动数据分析和数据科学旨在自动化许多与处理数据相关的繁琐、重复的任务。这包括数据清洗、特征工程、模型训练、调优和部署。目标是通过实现更快的迭代和减少常见工作流程的手动编码，使数据科学家和分析师更加高效。许多这些任务可以在一定程度上自动化。数据科学的一些任务与我们在第6章“开发软件”中讨论的软件开发人员的任务相似，即编写和部署软件，尽管焦点更窄，主要集中在模型上。数据科学平台如Weka、H2O、KNIME、RapidMiner和Alteryx是统一的机器学习和分析引擎，可用于各种任务，包括预处理大量数据和特征提取。所有这些都配备了图形用户界面（GUI），具有集成第三方数据源和编写自定义插件的能力。KNIME主要是开源的，但也提供了一个名为KNIME Server的商业产品。Apache Spark是一种多功能工具，可用于数据科学中涉及的各种任务。它可用于清洁、转换、提取特征和准备大容量数据进行分析，还可用于训练和部署机器学习模型，无论是在流式场景中，当涉及实时决策或监控事件时。此外，在其最基本的层面上，用于科学计算的库，如NumPy，可以用于自动化数据科学中涉及的所有任务。深度学习和机器学习库，如TensorFlow、Pytorch和Scikit-Learn，可用于各种任务，包括创建复杂的机器学习模型以外的数据预处理和特征提取。编排工具，如Airflow、Kedro或其他工具，可以帮助完成所有这些任务，并包含许多与数据科学各个步骤相关的特定工具的集成。几个数据科学工具支持生成式人工智能。在第6章“开发软件”中，我们已经提到了GitHub Copilot，但还有其他工具，如PyCharm AI助手，甚至更为重要的Jupyter AI，它是Project Jupyter的一个子项目，为Jupyter笔记本带来了生成式人工智能。Jupyter AI允许用户生成代码、修复错误、总结内容，甚至使用自然语言提示创建整个笔记本。该工具将Jupyter与各种提供商的LLM连接起来，使用户可以选择其首选模型和嵌入。Jupyter AI优先考虑负责任的人工智能和数据隐私。底层提示、链和组件是开源的，确保透明度。它保存有关模型生成内容的元数据，使跟踪工作流中的AI生成代码变得容易。Jupyter AI尊重用户数据隐私，仅在明确请求时才与LLMs联系，这是通过LangChain集成完成的。要使用Jupyter AI，用户可以安装适用于JupyterLab的适当版本，并通过聊天界面或魔术命令界面访问它。聊天界面具有Jupyternaut，一个可以回答问题、解释代码、修改代码和识别错误的AI助手。用户还可以从文本提示中生成整个笔记本。该软件允许用户教导Jupyternaut有关本地文件，并在笔记本环境中使用魔术命令与LLMs进行交互。它支持多个提供商，并为输出格式提供定制选项。文档中的此截图显示了聊天功能，Jupyternaut聊天：

![图 7.2：Jupyter AI – Jupyternaut 聊天。](../media/file50.png)

图 7.2：Jupyter AI – Jupyternaut 聊天。

很明显，像这样随时可以提问、创建简单函数或更改现有函数的聊天工具对数据科学家来说是一个福音。使用这些工具的好处包括提高效率，在模型构建或特征选择等任务中减少手动工作量，增强模型的可解释性，识别和解决数据质量问题，与其他 scikit-learn 管道（pandas_dq）集成，以及结果可靠性的整体改善。总的来说，自动化数据科学可以极大加速分析和机器学习应用程序的开发。它使数据科学家能够专注于过程的更高价值和创造性方面。为业务分析师民主化数据科学也是自动化这些工作流程的一个关键动机。在接下来的章节中，我们将依次研究这些步骤，并讨论如何自动化它们，以及我们将强调生成式人工智能如何为改善工作流程和创造效率带来贡献。

### 数据收集

自动化数据收集是在没有人为干预的情况下收集数据的过程。自动数据收集可以成为企业的有价值工具。它可以帮助企业更快速、更高效地收集数据，并可以释放人力资源专注于其他任务。通常，在数据科学或分析的背景下，我们将 ETL（提取、转换和加载）称为不仅从一个或多个来源获取数据（数据收集），还为特定用例准备数据的过程。ETL 过程通常遵循以下步骤：

1.  Extract：数据从源系统中提取出来。可以使用各种方法进行提取，例如网页抓取，API 集成或数据库查询。

1.  Transform：数据被转换为数据仓库或数据湖可以使用的格式。这可能涉及清洗数据，去重和标准化数据格式。

1.  Load：数据被加载到数据仓库或数据湖中。可以使用各种方法进行加载，例如批量加载或增量加载。

ETL 和数据收集可以使用各种工具和技术完成，例如：

+   网页抓取：网页抓取是从网站提取数据的过程。可以使用各种工具进行此操作，例如 Beautiful Soup、Scrapy、Octoparse 等。

+   API（应用程序编程接口）：这是软件应用程序相互通信的一种方式。企业可以使用 API 从其他公司收集数据，而无需构建自己的系统。

+   查询语言：任何数据库都可以作为数据源，包括 SQL（结构化查询语言）或无 SQL 类型。

+   机器学习：机器学习可以用于自动化数据收集过程。例如，企业可以使用机器学习识别数据中的模式，然后根据这些模式收集数据。

一旦数据被收集，就可以对其进行处理，以准备在数据仓库或数据湖中使用。ETL过程通常会清理数据，删除重复项，并标准化数据格式。然后数据将被加载到数据仓库或数据湖中，数据分析师或数据科学家可以利用这些数据来获取对业务的洞察。有许多ETL工具，包括商业工具如AWS Glue、Google Dataflow、Amazon Simple Workflow Service（SWF）、dbt、Fivetran、Microsoft SSIS、IBM InfoSphere DataStage、Talend Open Studio或开源工具如Airflow、Kafka和Spark。在Python中还有许多其他工具，太多了无法列出所有，例如用于数据提取和处理的Pandas，甚至celery和joblib，可以作为ETL编排工具。在LangChain中，与Zapier集成，这是一种可以用于连接不同应用程序和服务的自动化工具。这可以用于自动化从各种来源收集数据的过程。使用自动化ETL工具的一些好处包括：

+   提高准确性：自动化的ETL工具可以帮助提高数据提取、转换和加载过程的准确性。这是因为工具可以编程遵循一套规则和程序，可以帮助减少人为错误。

+   缩短上市时间：自动化的ETL工具可以帮助缩短将数据导入数据仓库或数据湖所需的时间。这是因为工具可以自动化ETL过程中涉及的重复任务，如数据提取和加载。

+   提高可扩展性：自动化的ETL工具可以帮助提高ETL过程的可扩展性。这是因为工具可以用于处理大量数据，并且可以轻松地按需扩展或缩减以满足业务需求。

+   提高合规性：自动化的ETL工具可以帮助提高符合GDPR和CCPA等法规的合规性。这是因为工具可以编程遵循一套规则和程序，可以帮助确保数据以符合法规的方式处理。

自动数据收集的最佳工具将取决于企业的具体需求。企业应考虑他们需要收集的数据类型、需要收集的数据量以及他们可用的预算。

### 可视化和探索性数据分析

自动化探索性数据分析（EDA）和可视化是指使用软件工具和算法自动分析和可视化数据，无需重大手动干预的过程。传统的EDA涉及手动探索和总结数据，以了解其各个方面，然后再执行机器学习或深度学习任务。它有助于识别模式、检测不一致性、测试假设并获得洞察。然而，随着大型数据集的出现和对高效分析的需求，自动化EDA变得重要。自动化EDA和可视化工具提供了几个好处。它们可以加快数据分析过程，减少在数据清洗、处理缺失值、异常值检测和特征工程等任务上花费的时间。这些工具还通过生成交互式可视化，提供对数据的全面概述，实现对复杂数据集的更有效探索。有许多用于自动化EDA和可视化的工具，包括：

+   D-Tale：一个库，方便地可视化pandas数据框。它支持交互式图表、3D图表、热图、相关性分析、自定义列创建。

+   ydata-profiling（之前称为pandas profiling）：这是一个开源库，生成交互式HTML报告（`ProfileReport`），总结数据集的不同方面，如缺失值统计、变量类型分布概况、变量之间的相关性。它适用于Pandas和Spark DataFrames。

+   Sweetviz：一个Python库，提供探索性数据分析的可视化功能，只需很少的代码。它允许在变量或数据集之间进行比较。

+   Autoviz：这个库可以自动生成数据集的可视化，无论其大小，只需几行代码。

+   DataPrep：只需几行代码，您就可以从常见数据源中收集数据，进行探索性数据分析和数据清洗，比如标准化列名或条目。

+   Lux：通过交互式小部件显示数据集中有趣的趋势和模式的一组可视化结果，用户可以快速浏览以获取洞察。

在数据可视化中使用生成式人工智能为自动探索性数据分析增加了另一个维度，使算法能够基于现有的可视化或特定用户提示生成新的可视化。生成式人工智能有潜力通过自动化设计过程的一部分来增强创造力，同时保持人类对最终输出的控制。总的来说，自动化的探索性数据分析和可视化工具在时间效率、全面分析以及生成有意义的数据可视化方面提供了显著优势。生成式人工智能有潜力以多种方式革新数据可视化。例如，它可以用于创建更真实和引人入胜的可视化，有助于商业沟通并更有效地向利益相关者传达数据，以为每个用户提供他们需要获取洞察并做出明智决策所需的信息。生成式人工智能可以通过制作针对每个用户个性化需求的可视化来增强和扩展传统工具的创作能力。此外，生成式人工智能可以用于创建交互式可视化，让用户以新颖创新的方式探索数据。

### 预处理和特征提取

自动化数据预处理是自动化数据预处理中涉及的任务的过程。这可能包括数据清洗、数据集成、数据转换和特征提取等任务。它与ETL中的转换步骤相关，因此在工具和技术上存在很多重叠。数据预处理很重要，因为它确保数据以数据分析师和机器学习模型可以使用的格式存在。这包括从数据中删除错误和不一致性，以及将其转换为与将要使用的分析工具兼容的格式。手动工程特征可能会很繁琐和耗时，因此自动化这个过程是有价值的。最近，出现了几个开源的Python库，可以帮助从原始数据中自动生成有用的特征，正如我们将看到的那样。Featuretools提供了一个通用框架，可以从事务性和关系数据中合成许多新特征。它集成了多个ML框架，使其灵活。Feature Engine提供了一组更简单的转换器，专注于处理缺失数据等常见数据转换。为了专门为基于树的模型优化特征工程，来自Microsoft的ta通过自动交叉等技术展现出强大的性能。AutoGluon Features应用神经网络风格的自动特征生成和选择来提高模型准确性。它与AutoGluon自动ML功能紧密集成。最后，TensorFlow Transform直接在Tensorflow管道上运行，为模型在训练期间准备数据。随着现在有多种开源选项，它已经迅速发展。Featuretools提供了最多的自动化和灵活性，同时集成了多个ML框架。对于表格数据，ta和Feature Engine提供了易于使用的转换器，针对不同的模型进行了优化。Tf.transform非常适合TensorFlow用户，而AutoGluon专门针对Apache MXNet深度学习软件框架。至于时间序列数据，Tsfel是一个从时间序列数据中提取特征的库。它允许用户指定特征提取的窗口大小，并可以分析特征的时间复杂性。它计算统计、频谱和时间特征。另一方面，tsflex是一个灵活高效的时间序列特征提取工具包，适用于序列数据。它对数据结构做出了很少的假设，可以处理缺失数据和不等长度。它还计算滚动特征。与tsfresh相比，这两个库提供了更现代的自动化时间序列特征工程选项。Tsfel功能更全面，而tsflex强调对复杂序列数据的灵活性。一些工具专注于机器学习和数据科学的数据质量，具有数据概要和自动数据转换。例如，pandas-dq库可以与scikit-learn管道集成，为数据概要、训练-测试比较、数据清理、数据填充（填补缺失值）和数据转换（例如，偏度校正）提供一系列有用的功能。它通过在建模之前解决潜在��题来改善数据分析的质量。更专注于通过早期识别潜在问题或错误来提高可靠性的工具包括Great Expectations和Deequ。Great Expectations是一个用于验证、记录和概要数据以保持质量并改善团队间沟通的工具。它允许用户对数据提出期望，通过数据的单元测试快速捕捉问题，基于期望创建文档和报告。Deequ建立在Apache Spark之上，用于在大型数据集中定义数据质量的单元测试。它允许用户明确陈述关于数据集的假设，并通过对属性进行检查或约束来验证这些假设。通过确保遵守这些假设，它可以防止下游应用程序中的崩溃或错误输出。所有这些库都允许数据科学家缩短特征准备时间，并扩展特征空间以提高模型质量。自动特征工程正变得越来越重要，以充分利用ML算法在复杂现实世界数据上的全部潜力。

### AutoML

自动化机器学习（AutoML）框架是一种自动化机器学习模型开发过程的工具。它们可以用于自动化任务，如数据清洗、特征选择、模型训练和超参数调整。这可以节省数据科学家大量的时间和精力，也有助于提高机器学习模型的质量。AutoML 的基本思想在 mljar autoML 库的 Github 仓库中有所体现（来源：https://github.com/mljar/mljar-supervised）：

![图 7.3：AutoML 的工作原理。](../media/file51.png)

图 7.3：AutoML 的工作原理。

加载一些数据，尝试不同的预处理方法、机器学习算法、训练和模型参数的组合，创建解释，将结果与可视化一起在排行榜上进行比较。AutoML 框架的主要价值主张在于易用性和提高开发者在找到机器学习模型、理解它并将其投入生产中的生产力。AutoML 工具已经存在很长时间了。其中一个最早的广泛框架是 AutoWeka，用 Java 编写，旨在自动化 Weka（Waikato 知识分析环境）机器学习套件中表格数据的机器学习模型开发过程，该套件是在 Waikato 大学开发的。自 AutoWeka 发布以来，已经开发了许多其他 AutoML 框架。如今一些最受欢迎的 AutoML 框架包括 auto-sklearn、autokeras、NASLib、Auto-Pytorch、tpot、optuna、autogluon 和 ray（tune）。这些框架用各种编程语言编写，支持各种机器学习任务。最近在 autoML 和神经架构搜索方面取得的进展使工具能够自动化机器学习流程的大部分。像 Google AutoML、Azure AutoML 和 H2O AutoML/Driverless AI 这样的领先解决方案可以根据数据集和问题类型自动处理数据准备、特征工程、模型选择、超参数调整和部署。这使得机器学习对非专家更加易于接触。当前的 autoML 解决方案可以非常有效地处理结构化数据，如表格和时间序列数据。它们可以自动生成相关特征，选择算法如树集成、神经网络或 SVM，并调整超参数。由于大规模超参数搜索，性能通常与手动流程相当甚至更好。对于像图像、视频和音频这样的非结构化数据，autoML 也在快速发展，采用神经架构搜索技术。像 AutoKeras、AutoGluon 和 AutoSklearn 这样的开源库也提供了易于访问的 autoML 能力。然而，大多数 autoML 工具仍需要一些编码和数据科学专业知识。完全自动化数据科学仍然具有挑战性，autoML 在灵活性和可控性方面存在局限性。但随着更加用户友好和高性能的解决方案进入市场，进展迅速。以下是框架的表格总结：

| **框架** | **语言** | **机器学习框架** | **首次发布** | **关键特点** | **数据类型** | **维护者** | **Github 星数** |
| --- | --- | --- | --- | --- | --- | --- | --- |
| Auto-Keras | Python | Keras | 2017 | 神经架构搜索，易于使用 | 图像、文本、表格 | Keras 团队（DATA 实验室，德克萨斯 A&M 大学） | 8896 |
| Auto-PyTorch | Python | PyTorch | 2019 | 神经架构搜索，超参数调整 | 表格、文本、图像、时间序列 | AutoML Group, 弗莱堡大学 | 2105 |
| Auto-Sklearn | Python | Scikit-learn | 2015 | 自动化scikit-learn工作流程 | 表格 | AutoML Group，弗莱堡大学 | 7077 |
| Auto-WEKA | Java* | WEKA | 2012 | 贝叶斯优化 | 表格 | 不列颠哥伦比亚大学 | 315 |
| AutoGluon | Python | MXNet, PyTorch | 2019 | 优化用于深度学习 | 文本，图像，表格 | 亚马逊 | 6032 |
| AWS SageMaker Autopilot | Python | XGBoost, sklearn | 2020 | 云端，简单 | 表格 | 亚马逊 | - |
| Azure AutoML | Python | Scikit-learn, PyTorch | 2018 | 可解释模型 | 表格 | 微软 | - |
| DataRobot | Python, R | 多种 | 2012 | 监控，可解释性 | 文本，图像，表格 | DataRobot | - |
| Google AutoML | Python | TensorFlow | 2018 | 易于使用，云端 | 文本，图像，视频，表格 | 谷歌 | - |
| H2O AutoML | Python, R | XGBoost, GBMs | 2017 | 自动化工作流程，集成 | 表格，时间序列，图像 | h2o.ai | 6430 |
| hyperopt-sklearn | Python | Scikit-learn | 2014 | 超参数调整 | 表格 | Hyperopt团队 | 1451 |
| Ludwig | Python | Transformers/Pytorch | 2019 | 用于构建和调整自定义LLMs和深度神经网络的低代码框架 | 多种 | Linux基金会 | 9083 |
| MLJar | Python | 多种 | 2019 | 可解释，可定制 | 表格 | MLJar | 2714 |
| NASLib | Python | PyTorch, TensorFlow/Keras | 2020 | 神经架构搜索 | 图像，文本 | AutoML Group，弗莱堡大学 | 421 |
| Optuna | Python | 通用 | 2019 | 超参数调整 | 通用 | Preferred Networks Inc | 8456 |
| Ray (Tune) | Python | 通用 | 2018 | 分布式超参数调整；加速ML工作负载 | 通用 | 加州大学伯克利分校 | 26906 |
| TPOT | Python | Scikit-learn, XGBoost | 2016 | 遗传编程，管道 | 表格 | Epistasis Lab, 宾夕法尼亚州立大学 | 9180 |
| TransmogrifAI | Scala | Spark ML | 2018 | Spark上的AutoML | 文本，表格 | Salesforce | 2203 |

图7.4：开源AutoML框架的比较。Weka可以通过pyautoweka从Python访问。Ray Tune和H2O的星号涉及整个项目而不仅仅是自动化部分。与AutoML相关的H2O商业产品是Driverless AI。大多数项目由一群与任何公司无关的贡献者维护

我只包括了最大的框架、库或产品 - 省略了一些。虽然重点是在Python中的开源框架上，我也包括了一些大型商业产品。Github 星标旨在展示框架的流行程度 - 它们与专有产品无关。Pycaret 是另一个大型项目（7562星），它提供了同时训练多个模型并用相对较少的代码进行比较的选项。像Nixtla的Statsforecast和MLForecast，或者Darts这样的项目具有针对时间序列数据的类似功能。像Auto-ViML和deep-autoviml这样的库处理各种类型的变量，并分别构建在scikit-learn和keras之上。它们旨在使新手和专家都能轻松尝试不同类型的模型和深度学习。然而，建议用户行使自己的判断以获得准确和可解释的结果。AutoML框架的重要特性包括以下内容：

+   部署：一些解决方案，特别是云中的解决方案，可以直接部署到生产环境。其他则导出到tensorflow或其他格式。

+   数据类型：大多数解决方案侧重于表格数据集；深度学习自动化框架通常处理不同类型的数据。例如，autogluon促进了图像、文本、时间序列以及表格数据的快速比较和原型设计。一些专注于超参数优化的解决方案，如optuna和ray tune，对格式完全不可知。

+   可解释性：这在某些行业中可能非常重要，与监管（例如，医疗保健或保险）或可靠性（金融）相关。对于一些解决方案，这是一个独特的卖点。

+   监控：部署后，模型性能可能会下降（漂移）。一些提供商提供性能监控。

+   可访问性：一些提供商需要编码或至少基本的数据科学理解，而其他人则是即插即用的解决方案，几乎不需要编码。通常，低代码和无代码解决方案的可定制性较低。

+   开源：开源平台的优势在于完全透明地展示实现和方法及其参数的可用性，并且它们是完全可扩展的。

+   迁移学习：这种能力意味着能够扩展或定制现有的基础模型。

这里还有很多内容需要涵盖，超出了本章的范围，比如可用方法的数量。支持较少的功能包括自监督学习、强化学习，或生成图像和音频模型。对于深度学习，一些库专注于后端，专门针对Tensorflow、Pytorch或MXNet。Auto-Keras、NASLib和Ludwig具有更广泛的支持，特别是因为它们与Keras一起工作。从计划于2023年秋季发布的版本3.0开始，Keras将支持三个主要后端TensorFlow、JAX和PyTorch。Sklearn拥有自己的超参数优化工具，如网格搜索、随机搜索、逐步减半。更专业的库，如auto-sklearn和hyperopt-sklearn，通过提供贝叶斯优化方法，超越了这一点。Optuna可以与各种ML框架集成，如AllenNLP、Catalyst、Catboost、Chainer、FastAI、Keras、LightGBM、MXNet、PyTorch、PyTorch Ignite、PyTorch Lightning、TensorFlow和XGBoost。Ray Tune具有自己的集成，其中包括optuna。它们都具有最先进的参数优化算法和用于扩展（分布式训练）的机制。除了上述列出的功能外，其中一些框架可以自动执行特征工程任务，例如数据清洗和特征选择，例如删除高度相关的特征，并以图形方式生成性能结果。列出的每个工具都有各自的实现，例如特征选择和特征转换 - 不同之处在于这种自动化程度。更具体地说，使用AutoML框架的优势包括：

+   节省时间：AutoML框架可以通过自动化机器学习模型开发过程来节省数据科学家大量时间。

+   提高准确性：AutoML框架可以通过自动化超参数调整过程来帮助提高机器学习模型的准确性。

+   提高可访问性：AutoML框架使得那些没有太多机器学习经验的人更容易接触机器学习。

然而，使用AutoML框架也存在一些缺点：

+   黑盒子：AutoML框架可能是“黑盒子”，意味着很难理解它们的工作原理。这可能会导致难以调试AutoML模型的问题。

+   灵活性有限：AutoML框架在可以自动化的机器学习任务类型方面可能受到限制。

上述工具中很多都至少具有某种自动特征工程或预处理功能，然而，也有一些更专业的工具。

### 生成模型的影响

生成式人工智能和像GPT-3这样的LLM已经给数据科学和分析领域带来了重大变革。这些模型，特别是LLMs，有潜力以多种方式彻底改变数据科学中涉及的所有步骤，为研究人员和分析师提供令人兴奋的机会。生成式人工智能模型，如ChatGPT，能够理解和生成类似人类的回应，使它们成为增强研究生产力的有价值工具。生成式人工智能可以在分析和解释研究数据方面发挥关键作用。这些模型可以协助进行数据探索，发现隐藏的模式或相关性，并提供通过传统方法可能不明显的见解。通过自动化数据分析的某些方面，生成式人工智能节省时间和资源，使研究人员能够专注于更高级别的任务。生成式人工智能可以在帮助研究人员进行文献综述和识别研究空白方面发挥作用。ChatGPT和类似模型可以总结大量来自学术论文或文章的信息，提供现有知识的简明概述。这有助于研究人员更有效地识别文献中的空白，并指导他们自己的调查。我们已经在*第4章*，*问答*中探讨了使用生成式人工智能模型的这一方面。生成式人工智能的其他用例可能包括：

+   自动生成合成数据：生成式人工智能可以用于自动生成合成数据，用于训练机器学习模型。对于没有大量真实世界数据的企业来说，这可能会有所帮助。

+   识别数据中的模式：生成式人工智能可以用于识别数据中人类分析师无法看到的模式。这对于希望从数据中获得新见解的企业可能有所帮助。

+   从现有数据中创建新特征：生成式人工智能可以用于从现有数据中创建新特征。这对于希望提高其机器学习模型准确性的企业可能有所帮助。

根据麦肯锡和毕马威等机构最近的报告，AI的后果涉及数据科学家将从事的工作、他们将如何工作以及谁可以从事数据科学任务。主要影响领域包括：

+   人工智能的民主化：生成模型使更多人能够利用人工智能，通过简单提示生成文本、代码和数据。这将AI的使用扩展到数据科学家以外的领域。

+   提高生产力：通过自动生成代码、数据和文本，生成式人工智能可以加速开发和分析工作流程。这使数据科学家和分析师能够专注于更高价值的任务。

+   数据科学的创新：生成式人工智能正在带来的是以新的更有创意的方式探索数据，并生成新的假设和见解，这是传统方法所无法实现的。

+   行业的颠覆：生成式人工智能的新应用可能通过自动化任务或增强产品和服务来颠覆行业。数据团队需要确定高影响的使用案例。

+   仍存在限制：当前模型仍存在准确性限制、偏见问题和缺乏可控性。需要数据专家监督负责任的开发。

+   治理的重要性：对生成式人工智能模型的开发和道德使用进行严格的治理将对维护利益相关者的信任至关重要。

+   合作伙伴关系的必要性 - 公司将需要与合作伙伴、社区和平台提供商建立生态系统，以有效利用生成式人工智能的能力。

+   数据科学技能的变化 - 需求可能从编码专业知识转向数据治理、道德、翻译业务问题和监督AI系统的能力。

关于数据科学的民主化和创新，更具体地说，生成式人工智能也对数据可视化方式产生影响。过去，数据可视化通常是静态的和二维的。然而，生成式人工智能可以用于创建交互式和三维的可视化，有助于使数据更易访问和理解。这使得人们更容易理解和解释数据，从而促进更好的决策。再次强调，生成式人工智能带来的最大变革之一是数据科学的民主化。过去，数据科学是一个需要深入了解统计学和机器学习的非常专业领域。然而，生成式人工智能使得技术专业知识较少的人能够创建和使用数据模型。这将数据科学领域开放给更广泛的人群。LLMs和生成式人工智能可以在自动化数据科学中发挥关键作用，提供多种好处：

+   自然语言交互：LLMs允许进行自然语言交互，使用户能够使用普通英语或其他语言与模型进行交流。这使得非技术用户能够使用日常语言与数据进行交互和探索，而无需专业的编码或数据分析技能。

+   代码生成：生成式人工智能可以自动生成代码片段，执行EDA期间的特定分析任务。例如，它可以生成检索数据的代码（例如SQL）、清理数据、处理缺失值或创建可视化（例如Python）的代码。这一功能节省时间，减少了手动编码的需求。

+   自动报告生成：LLMs可以生成自动报告，总结EDA的关键发现。这些报告提供了关于数据集各个方面的见解，如统计摘要、相关性分析、特征重要性等，使用户更容易理解和展示他们的发现。

+   数据探索和可视化：生成式人工智能算法可以全面探索大型数据集，并自动生成可视化图表，自动揭示数据中的潜在模式、变量之间的关系、异常值或异常情况。这有助于用户在不需要手动创建每个可视化图表的情况下全面了解数据集。

此外，我们可以认为生成式人工智能算法应该能够从用户互动中学习，并根据个人偏好或过去行为调整推荐。它们通过持续的自适应学习和用户反馈不断改进，提供更个性化和有用的见解，在自动化的探索性数据分析过程中提供更多个性化和有用的见解。最后，生成式人工智能模型可以通过从现有数据集中学习模式（智能错误识别）在探索性数据分析过程中识别数据中的错误或异常。它们可以快速准确地检测不一致之处并快速准确地突出潜在问题。总的来说，大型和复杂数据集的更有效分析。然而，尽管这些模型具有增强研究和辅助文献审阅过程的巨大潜力，但它们不应被视为不可靠的信息源。正如我们之前所看到的，LLMs是通过类比工作的，而且在推理和数学方面有困难。它们的优势在于创造力，而不是准确性，因此，研究人员必须运用批判性思维，并确保这些模型生成的输出准确、无偏见，并符合严格的科学标准。一个显著的例子是微软的Fabric，它集成了由生成式人工智能驱动的聊天界面。这使用户可以使用自然语言提出与数据相关的问题，并在不必等待数据请求队列的情况下立即获得答案。通过利用像OpenAI模型这样的LLMs，Fabric实现了对有价值见解的实时访问。Fabric在其他分析产品中脱颖而出，因为它采用了全面的方法。它解决了组织分析需求的各个方面，并为参与分析过程的不同团队提供了特定角色的体验，如数据工程师、仓储专业人员、科学家、分析师和业务用户。通过在每一层集成Azure OpenAI服务，Fabric利用生成式人工智能的力量来释放数据的全部潜力。像Microsoft Fabric中的Copilot这样的功能提供了对话式语言体验，允许用户创建数据流、生成代码或整个函数、构建机器学习模型、可视化结果，甚至开发定制的对话式语言体验。据传闻，ChatGPT（以及Fabric扩展）经常生成不正确的SQL查询。当分析人员可以检查输出的有效性时，这对于使用者来说是可以接受的，但对于非技术业务用户来说，作为自助式分析工具则是一场灾难。因此，组织在使用Fabric进行分析时必须确保他们有可靠的数据管道，并采用数据质量管理实践。虽然生成式人工智能在数据分析中的可能性令人兴奋，但必须谨慎行事。LLMs的可靠性和准确性应通过首创性推理和严格分析进行验证。虽然这些模型在临时分析、研究过程中的创意生成和总结复杂分析方面显示出潜力，但由于需要领域专家验证，它们并不总是适���非技术用户的自助式分析工具。让我们开始使用代理来运行代码或调用其他工具来回答问题！

## 代理可以回答数据科学问题

正如我们在Jupyter AI（Jupyternaut chat）中看到的 - 以及在第6章*开发软件*中看到的 - 利用生成式AI（代码LLMs）提高创建和编写软件的效率的潜力很大。这是本章实践部分的一个很好的起点，因为我们将探讨在数据科学中使用生成式AI的用途。我们之前已经看到了不同的带有工具的代理。例如，LLMMathChain可以执行Python来回答数学问题，如下所示：

```
from langchain import OpenAI, LLMMathChain
llm = OpenAI(temperature=0)
llm_math = LLMMathChain.from_llm(llm, verbose=True)
llm_math.run("What is 2 raised to the 10th power?")
```

虽然这对提取信息并反馈信息很有用，但如何将其插入传统的EDA过程并不那么明显。同样，CPAL（`CPALChain`）和PAL（`PALChain`）链可以回答更复杂的推理问题，同时保持幻觉受控，但很难想出它们的真实用例。通过`PythonREPLTool`，我们可以创建玩具数据的简单可视化或使用合成数据进行训练，这对于项目的说明或引导可能很好。这是LangChain文档中的一个示例：

```
from langchain.agents.agent_toolkits import create_python_agent
from langchain.tools.python.tool import PythonREPLTool
from langchain.llms.openai import OpenAI
from langchain.agents.agent_types import AgentType
agent_executor = create_python_agent(
    llm=OpenAI(temperature=0, max_tokens=1000),
    tool=PythonREPLTool(),
    verbose=True,
    agent_type=AgentType.ZERO_SHOT_REACT_DESCRIPTION,
)
agent_executor.run(
    """Understand, write a single neuron neural network in PyTorch.
Take synthetic data for y=2x. Train for 1000 epochs and print every 100 epochs.
Return prediction for x = 5"""
)
```

请注意，这应该谨慎执行，因为Python代码直接在机器上执行而没有任何保障。这实际上是有效的，可以创建数据集，训练模型，然后我们得到一个预测：

```
Entering new AgentExecutor chain...
I need to write a neural network in PyTorch and train it on the given data
Action: Python_REPL
Action Input: 
import torch
model = torch.nn.Sequential(
    torch.nn.Linear(1, 1)
)
loss_fn = torch.nn.MSELoss()
optimizer = torch.optim.SGD(model.parameters(), lr=0.01)
# Define the data
x_data = torch.tensor([[1.0], [2.0], [3.0], [4.0]])
y_data = torch.tensor([[2.0], [4.0], [6.0], [8.0]])
for epoch in range(1000):  # Train the model
    y_pred = model(x_data)
    loss = loss_fn(y_pred, y_data)
    if (epoch+1) % 100 == 0:
        print(f'Epoch {epoch+1}: {loss.item():.4f}')
    optimizer.zero_grad()
    loss.backward()
    optimizer.step()
# Make a prediction
x_pred = torch.tensor([[5.0]])
y_pred = model(x_pred)
Observation: Epoch 100: 0.0043
Epoch 200: 0.0023
Epoch 300: 0.0013
Epoch 400: 0.0007
Epoch 500: 0.0004
Epoch 600: 0.0002
Epoch 700: 0.0001
Epoch 800: 0.0001
Epoch 900: 0.0000
Epoch 1000: 0.0000
Thought: I now know the final answer
Final Answer: The prediction for x = 5 is y = 10.00.
```

再次强调，这非常酷，但很难看到如何在没有更严格的工程支持的情况下扩展，类似于我们在第6章*开发软件*中所做的。如果我们想要用类别或地理信息丰富我们的数据，LLMs和工具可能会很有用。例如，如果我们的公司从东京提供航班，并且我们想知道客户距离东京的距离，我们可以使用Wolfram Alpha作为工具。这是一个简单的例子：

```
from langchain.agents import load_tools, initialize_agent
from langchain.llms import OpenAI
from langchain.chains.conversation.memory import ConversationBufferMemory
llm = OpenAI(temperature=0)
tools = load_tools(['wolfram-alpha'])
memory = ConversationBufferMemory(memory_key="chat_history")
agent = initialize_agent(tools, llm, agent="conversational-react-description", memory=memory, verbose=True)
agent.run(
    """How far are these cities to Tokyo?
* New York City
* Madrid, Spain
* Berlin
""")
```

请确保您已经设置了OPENAI_API_KEY和WOLFRAM_ALPHA_APPID环境变量，如第3章*开始使用LangChain*中所讨论的。这是输出：

```
> Entering new AgentExecutor chain...
AI: The distance from New York City to Tokyo is 6760 miles. The distance from Madrid, Spain to Tokyo is 8,845 miles. The distance from Berlin, Germany to Tokyo is 6,845 miles.
> Finished chain.
'
The distance from New York City to Tokyo is 6760 miles. The distance from Madrid, Spain to Tokyo is 8,845 miles. The distance from Berlin, Germany to Tokyo is 6,845 miles.
```

现在，很多这些问题都非常简单。然而，我们可以给代理提供数据集来处理，这就是当我们连接更多工具时可以变得非常强大的地方。让我们开始问答关于结构化数据集的问题！

## 使用LLMs进行数据探索

数据探索是数据分析中至关重要且基础的一步，使研究人员能够全面了解其数据集并发现重要见解。随着像ChatGPT这样的LLM的出现，研究人员可以利用自然语言处理的力量促进数据探索。正如我们之前提到的生成式AI模型，如ChatGPT，具有理解和生成类似人类响应的能力，使它们成为增强研究生产力的宝贵工具。用自然语言提出问题并获得易消化的回答可以极大地促进分析。LLM不仅可以帮助探索文本数据，还可以帮助探索其他形式的数据，如数值数据集或多媒体内容。研究人员可以利用ChatGPT的能力提出关于数值数据集中统计趋势的问题，甚至查询图像分类任务的可视化。让我们加载一个数据集并开始处理。我们可以从scikit-learn快速获取一个数据集：

```
from sklearn.datasets import load_iris
df = load_iris(as_frame=True)["data"]
```

鸢尾花数据集是众所周知的 - 它是一个玩具数据集，但它将帮助我们展示使用生成式人工智能进行数据探索的能力。我们将在接下来使用DataFrame。我们现在可以创建一个Pandas dataframe代理，看看完成简单任务有多容易！

```
from langchain.agents import create_pandas_dataframe_agent
from langchain import PromptTemplate
from langchain.llms.openai import OpenAI
PROMPT = (
    "If you do not know the answer, say you don't know.\n"
    "Think step by step.\n"
    "\n"
    "Below is the query.\n"
    "Query: {query}\n"
)
prompt = PromptTemplate(template=PROMPT, input_variables=["query"])
llm = OpenAI()
agent = create_pandas_dataframe_agent(llm, df, verbose=True)
```

我已经告诉模型在怀疑和逐步思考时说它不知道的指令，这样可以减少幻觉。现在我们可以针对DataFrame查询我们的代理：

```
agent.run(prompt.format(query="What's this dataset about?"))
```

我们得到了答案“'这个数据集是关于某种花的测量。”'这是正确的。让我们展示如何获得一个可视化：

```
agent.run(prompt.format(query="Plot each column as a barplot!"))
```

它并不完美，但我们得到了一个看起来不错的图表：

![图7.5：鸢尾花数据集条形图。](../media/file52.png)

图7.5：鸢尾花数据集条形图。

我们还可以要求以可视化方式查看列的分布，这将给我们这个整洁的图表：

![图7.6：鸢尾花数据集箱线图。](../media/file53.png)

图7.6：鸢尾花数据集箱线图。

我们可以要求图使用其他绘图后端，如seaborn，但请注意这些必须已安装。我们还可以询问有关数据集的更多问题，比如哪一行的花瓣长度和花瓣宽度之间的差异最大。我们得到了带有中间步骤的答案如下（缩短）：

```
df['difference'] = df['petal length (cm)'] - df['petal width (cm)']
df.loc[df['difference'].idxmax()]
Observation: sepal length (cm)    7.7
sepal width (cm)     2.8
petal length (cm)    6.7
petal width (cm)     2.0
difference           4.7
Name: 122, dtype: float64
Thought: I now know the final answer
Final Answer: Row 122 has the biggest difference between petal length and petal width.
```

我认为这值得表扬，LLM！下一步可能是在提示中添加更多关于绘图的指令，比如关于绘图大小的指令。在streamlit应用程序中实现相同的绘图逻辑有点困难，因为我们需要在相应的streamlit函数中使用绘图功能，例如，`st.bar_chart()`，但是这也是可以做到的。您可以在Streamlit博客中找到关于此的解释（“使用ChatGPT构建Streamlit和scikit-learn应用程序”）。统计测试呢？

```
agent.run(prompt.format(query="Validate the following hypothesis statistically: petal width and petal length come from the same distribution."))
```

我们得到了这个回应：

```
Thought: I should use a statistical test to answer this question.
Action: python_repl_ast 
Action Input: from scipy.stats import ks_2samp
Observation: 
Thought: I now have the necessary tools to answer this question.
Action: python_repl_ast
Action Input: ks_2samp(df['petal width (cm)'], df['petal length (cm)'])
Observation: KstestResult(statistic=0.6666666666666666, pvalue=6.639808432803654e-32, statistic_location=2.5, statistic_sign=1)
Thought: I now know the final answer
Final Answer: The p-value of 6.639808432803654e-32 indicates that the two variables come from different distributions.
```

'6.639808432803654e-32的p值表明这两个变量来自不同的分布。'这是统计检验！这很酷。我们可以用简单的提示用普通英语提出相当复杂的关于数据集的问题。还有pandas-ai库，它在内部使用LangChain并提供类似的功能。以下是文档中的一个示例数据集：

```
import pandas as pd
from pandasai import PandasAI
df = pd.DataFrame({
    "country": ["United States", "United Kingdom", "France", "Germany", "Italy", "Spain", "Canada", "Australia", "Japan", "China"],
    "gdp": [19294482071552, 2891615567872, 2411255037952, 3435817336832, 1745433788416, 1181205135360, 1607402389504, 1490967855104, 4380756541440, 14631844184064],
    "happiness_index": [6.94, 7.16, 6.66, 7.07, 6.38, 6.4, 7.23, 7.22, 5.87, 5.12]
})
from pandasai.llm.openai import OpenAI
llm = OpenAI(api_token="YOUR_API_TOKEN")
pandas_ai = PandasAI(llm)
pandas_ai(df, prompt='Which are the 5 happiest countries?') 
```

这将给我们提供类似于直接使用LangChain时的请求结果。请注意，pandas-ai不是本书的设置的一部分，所以如果你想使用它，你需要单独安装它。对于SQL数据库中的数据，我们可以连接一个`SQLDatabaseChain`。LangChain文档展示了这个例子：

```
from langchain.llms import OpenAI
from langchain.utilities import SQLDatabase
from langchain_experimental.sql import SQLDatabaseChain
db = SQLDatabase.from_uri("sqlite:///../../../../notebooks/Chinook.db")
llm = OpenAI(temperature=0, verbose=True)
db_chain = SQLDatabaseChain.from_llm(llm, db, verbose=True)
db_chain.run("How many employees are there?")
```

我们首先连接到数据库。然后我们可以用自然语言提问关于数据的问题。这也是非常强大的。一个LLM会为我们创建查询。我期望这在我们不了解数据库架构时特别有用。如果设置了`use_query_checker`选项，`SQLDatabaseChain`还可以检查查询并自动更正它们。让我们总结一下！

## 总结

在本章中，我们探讨了自动化数据分析和数据科学的最新技术。有很多领域可以从LLMs中受益，主要是作为编码助手或数据探索。我们从涵盖数据科学过程中每个步骤的框架概述开始，比如AutoML方法，讨论了LLMs如何帮助我们进一步提高生产力，使数据科学和数据分析更容易访问，无论是对利益相关者还是开发人员或用户。然后，我们研究了代码生成和工具，类似于代码LLMs *第6章*，*开发软件*，可以通过创建我们可以查询的函数或模型来帮助数据科学任务，或者我们如何使用LLMs或第三方工具（如Wolfram Alpha）来丰富数据。然后，我们看了一下在数据探索中使用LLMs。在*第4章*，*问答*中，我们研究了摄入大量文本数据进行分析。在本章中，我们专注于SQL或表格形式的结构化数据集的探索性分析。总之，人工智能技术有潜力彻底改变我们分析数据的方式，ChatGPT插件或Microsoft Fabric就是这方面的例子。然而，在当前的情况下，人工智能不能取代数据科学家，只能帮助他们。让我们看看你是否记得本章的一些关键要点！

## 问题

请看看你是否能够从记忆中回答这些问题。如果你对任何问题不确定，我建议你回到本章的相应部分：

1.  数据科学和数据分析有什么区别？

1.  数据科学涉及哪些步骤？

1.  为什么我们想要自动化数据科学/分析？

1.  有哪些用于自动化数据科学任务的框架，它们能做什么？

1.  生成式人工智能如何帮助数据科学家？

1.  我们可以使用什么样的代理和工具来回答简单问题？

1.  我们如何让LLM与数据一起工作？
