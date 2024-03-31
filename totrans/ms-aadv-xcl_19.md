# [第18章VBA中的变量和数据类型](contents.xhtml#ch18a)

[介绍](contents.xhtml#sc2_256a)

在本章中，我们将探讨VBA（Visual Basic for Applications）中变量和数据类型的基础知识。变量是编程中的基本元素，它们在程序执行过程中存储和操作数据，而数据类型定义了变量中存储的数据的性质。理解变量和数据类型对于编写高效和有效的VBA代码至关重要。我们将涵盖声明变量和常量、指定数据类型、使用消息框和输入框、选择单元格、行和列以及与工作表、工作簿和应用程序对象一起工作等主题。

[结构](contents.xhtml#sc2_257a)

在本章中，我们将涵盖以下主题：

+   变量和常量

+   声明变量和常量

+   变量和常量的数据类型

+   消息框和输入框

+   选择和激活单元格

+   选择和激活行和列

+   与工作表一起工作

+   与工作簿一起工作

+   与应用程序对象一起工作

[目标](contents.xhtml#sc2_258a)

通过本章结束时，读者将能够理解VBA中变量和常量的概念，并学会如何声明它们，熟悉VBA中可用的不同数据类型及其各自的范围，并探索消息框和输入框用于用户交互的用法。此外，读者还将学习在Excel中选择和激活单元格、行和列的技巧，并了解在VBA中使用工作表、工作簿和应用程序对象的知识。

[变量和常量](contents.xhtml#sc2_259a)

现在让我们学习关于变量和常量。

[变量](contents.xhtml#sc3_260a)

变量的特点如下：

+   变量是一个命名的存储位置，其中包含在程序执行过程中可以修改的数据。

+   每个变量都有一个名称，用于在其范围内唯一标识它。

+   可以指定或不指定数据类型。

+   变量名称：

    +   必须以字母字符开头，

    +   在相同范围内必须是唯一的，

    +   不能超过255个字符，并且

    +   包含嵌入的句点或类型声明字符。

[常量](contents.xhtml#sc3_261a)

在程序执行过程中保持恒定值的命名项目。常量可以是字符串或数字文字。

[声明变量和常量](contents.xhtml#sc2_262a)

声明变量的语法是：

DIM name_of_variable AS type_of_variable

例如

Dim strName As String

Dim intX As Integer

Dim intX，intYAs Integer

声明常量的语法是：

Const name_of_variable AS type_of_variable = constant value

例如

Const conAge As Integer = 34

在声明变量时，使用Dim语句，而对于常量使用Const语句。

声明语句可以放置在过程中以创建过程级变量。或者它可以放置在模块的顶部，在声明部分中，以创建模块级变量。

[变量和常量的数据类型](contents.xhtml#sc2_263a)

[表 18.1](#tab18-1) 显示了数据类型的各种范围：

| 数据类型 | 范围 |
| --- | --- |
| 字节 | 0 到 255。 |
| 整型 | -32,768 到 32,767。 |
| 长整型 | -2,147,483,648 到 2,147,483,647。 |
| 单精度 | -3.402823E38 到 -1.401298E-45（负值）。 |
| -1.401298E-45 到 3.402823E38（正值）。 |
| 双精度 | -1.7200369313486231E308 到-4.94065645841247E-324（负值）。4.94065645841247E-324 到 1.7200369313486231E308（正值）。 |
| 货币 | -922,337,203,685,477.5808 到 922,337,203,685,477.5807。 |
| 字符串 | 零到大约两十亿个字符。 |
| 变体 | 日期值：公元 100 年 1 月 1 日到公元 9999 年 12 月 31 日。 |
| 数值：与双精度浮点数相同的范围。 |
| 字符串值：与字符串相同的范围。 |
| 也可以包含错误或空值。 |
| 布尔 | 真或假。 |
| 日期 | 公元 100 年 1 月 1 日到公元 9999 年 12 月 31 日。 |
| 对象 | 任何对象引用。 |

表 18.1：数据类型

[使用 Option Explicit 语句](contents.xhtml#sc3_264a)

使用 Option Explicit 强制声明变量。它必须出现在任何过程之前的模块中。如果不使用，未声明的变量将是 Variant 类型。

[消息框和输入框](contents.xhtml#sc2_265a)

Msgbox 函数在对话框中显示消息，等待用户点击按钮，然后返回一个整数，指示用户点击了哪个按钮。

InputBox 函数在对话框中显示提示，等待用户输入文本或点击按钮，然后返回一个包含文本框内容的字符串。

例如：

| 子过程问候()消息框 "你好 " & InputBOx("你叫什么名字？")结束子过程 |
| --- |

[选择和激活单元格](contents.xhtml#sc2_266a)

当你使用 Microsoft Excel 时，通常会选择一个单元格或多个单元格，然后执行操作，比如格式化单元格或在其中输入值。

参考[表 18.2](#tab18-2)，编写各种操作的代码：

| 要做这个 | 写下这段代码 |
| --- | --- |
| 选择单元格 A1 | Range("A1").select 或 Cells(1,1).select |
| 选择范围 A1:B5 | Range("A1:b5").select |
| 选择范围 A1:A5 和 C2:C10 | Range("A1:A5 , C2:C10").select |
| 选择当前单元格 | Activecell.select |
| 从当前单元格到 b6 选择范围 | Range(Activecell , "b6").select |
| 选择活动单元格的当前区域 | Activecell.currentregion.select |
| 从活动单元格按 Ctrl + Shift+ 下箭头 | Range(ActivecellActivecell.End(X lDown)).select |
| 从单元格 A2 按 Ctrl + Shift + 下箭头 | Range("A2" , Activecell.End(XlDown)).select |

表 18.2：各种操作的代码

[选择和激活行和列](contents.xhtml#sc2_267a)

有时您需要选择特定的行和列，然后执行操作。

要做这个，请写下面[表18.3](#tab18-3)中显示的代码：

| 要做这个 | 写这个代码 |
| --- | --- |
| 选择一行 | Rows("2:2").select |
| 选择从第2行到第5行 | Rows("2:5").select |
| 从活动单元格选择3行 | Activecell.entirerow.Range("1:3"). select |
| 选择一列 | Columns("A:A").select |
| 选择从B到E的列 | Columns("B:E").select |
| 从活动单元格选择3列 | Activecell.entirecolumn.Range("A:C").select |
| 选择当前行 | Activecell.entirerow.select |
| 选择当前列 | Activecell.entirecolumn.select |

表18.3：各种操作的代码

[与工作表一起工作](contents.xhtml#sc2_268a)

许多时候，您需要选择特定的工作表，或插入新工作表，重命名工作表等。请参考[表18.4](#tab18-4)：

| 要做这个 | 写这个代码 |
| --- | --- |
| 通过索引号选择任何工作表 | Sheets(2).selectWorksheets(2).select |
| 通过名称选择任何工作表 | Sheets("Sheet1").selectWorksheets("Sheet1").select |
| 重命名工作表 | Sheets("Sheet1").name="新名称" |
| 新名称 | Worksheets("Sheet1").name=Activesheet.name |
| 删除工作表 | Sheets("Sheet1").deleteWorksheets("Sheet1").deleteActivesheet.delete |
| 插入工作表 | Sheets.add before:= sheets("Sheet1")Worksheets.add before:=sheets("Sheet1") |

表18.4：各种操作的代码

[与工作簿一起工作](contents.xhtml#sc2_269a)

有时您需要处理不同的工作簿。请参考[表18.5](#tab18-5)：

| 要做这个 | 写这个代码 |
| --- | --- |
| 打开一个工作簿 | Workbooks.open filename:="带路径的文件名" |
| 打开包含自动宏的工作簿 | Workbooks.openfilename:="Activeworkbook.runautomacros" |
| 关闭工作簿 | Workbooks(2).close |
| 添加新工作簿 | Workbooks.add |

表18.5：各种操作的代码

[与应用程序对象一起工作](contents.xhtml#sc2_270a)

有时为了忽略不同的 Excel 消息，您需要使用应用程序对象，如下所示的[表18.6](#tab18-6)：

| 要做这个 | 写这个代码 |
| --- | --- |
| 关闭消息显示 | Application.DisplayAlert = False |
| 停止屏幕闪烁 | Application.ScreenUpdating = False |
| 停止复制/剪切模式 | Application.CutCopyMode = False |
| 计算 | Application.Calculate |

表18.6：各种操作的代码

[场景15](contents.xhtml#sc3_271a)

创建一个宏，应接受人员的姓名和城市，并将其存储在 Excel 工作表的单元格 A1 和 B1 中。如果用户输入 Mumbai 作为城市，则字体颜色必须为红色。使用 InputBox 函数从用户那里获取输入。使用 MsgBox 函数显示结果。

| Sub Accept_Details()Dim e_Name , e_City As StringName = InputBox("输入您的姓名")City = InputBox("输入您的城市")MsgBox "您的姓名是 " & Name & "，城市是 " & CityCells(1, 1).Value = e_Name Cells(1, 2).Value = e_CityIf Cells(1, 2).Value = "mumbai" ThenCells(1, 2).Font.ColorIndex = 3ElseCells(1, 2).Font.ColorIndex = 0EndIfEnd Sub |
| --- |

[场景16](contents.xhtml#sc3_272a)

创建一个名为 Data_Entry 的宏。接受一个人的员工编号、姓名、入职日期和工资。将这些值插入“数据库”工作表中。每条新记录必须存储在最后一条记录之后。

| Sub Data_Entry()Dim EmpCode As integer, Next_Row as integerDim EmpName As StringDim doj As DateDim Salary As CurrencyEmpCode = InputBox("Enter Employee Code")EmpName = InputBox("Enter Employee Name")doj = InputBox("enter Date of Joining mm/dd/yy")Salary = InputBox("Enter Salary of Employee")Range("a65536").selectSelection.end(xlup).select Next_Row= activecell.row+1Cells(Next_Row, 1).Value = EmpCode Cells(Next_Row, 2).Value = EmpNameCells(Next_Row, 3).Value = Format(doj, "MMM DD YYYY")Cells(Next_Row, 4).Value = SalaryEnd Sub |
| --- |

[结论](contents.xhtml#sc2_273a)

总之，本章全面介绍了 VBA 中的变量和数据类型。它涵盖了变量和常量的声明，解释了不同数据类型及其范围，演示了消息框和输入框的使用，并探讨了在 Excel 中选择和操作单元格、行和列的技巧。本章还涉及与工作表、工作簿和应用程序对象的工作。通过理解这些基础知识，读者可以编写高效且有效的 VBA 代码。

[练习](contents.xhtml#sc2_274a)

1.  编写一个 VBA 宏，提示用户使用输入框输入他们的姓名、年龄和喜欢的颜色。该宏应将这些值分别存储在活动工作表的单元格 A1、B1 和 C1 中。此外，如果用户的年龄大于或等于 18 岁，则相应单元格的字体颜色应设置为他们喜欢的颜色。通过运行宏并输入不同的值来测试宏。

加入我们书籍的 Discord 空间

加入本书的 Discord 工作区，获取最新更新、优惠、全球科技动态、新发布和与作者的交流：

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)
