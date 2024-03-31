# [第19章VBA中的循环结构](contents.xhtml#ch19a)

[介绍](contents.xhtml#sc2_275a)

在本章中，我们将深入探讨Visual Basic for Applications（VBA）中的循环结构主题。循环是强大的工具，可以使代码重复执行，提高效率并自动化任务。本章探讨了不同类型的循环，如Do...Loop、For...Next和For Each...Next循环，以及基于特定事件运行的自动执行的宏。

[结构](contents.xhtml#sc2_276a)

在本章中，我们将讨论以下主题：

+   使用循环（重复动作）

+   使用Do…Loop语句

+   使用For…Next语句

+   使用For Each…Next语句

+   自动执行的宏

[目标](contents.xhtml#sc2_277a)

通过本章结束时，读者将学习VBA中的循环结构，如Do...Loop、For...Next和For Each...Next，以及实际示例的实现。

[使用循环（重复动作）](contents.xhtml#sc2_278a)

循环允许您重复运行一组语句。一些循环重复语句直到条件为False；其他循环重复语句直到条件为True。还有一些循环重复语句特定次数或对集合中的每个对象重复。

[选择要使用的循环](contents.xhtml#sc3_279a)

有各种循环可以使用，例如：

+   Do…Loop：在条件为True时循环。

+   For…Next：使用计数器运行指定次数的语句。

+   For Each…Next：为集合中的每个对象重复一组语句。

[使用Do…Loop语句](contents.xhtml#sc2_280a)

您可以使用Do...Loop语句无限次运行一组语句。这些语句在条件为True时重复，或者直到条件变为True。

语法：

Do [{While | Until} 条件]

[语句]

[退出 Do]

[语句]

循环

[在条件为真时重复语句](contents.xhtml#sc3_281a)

在Do...Loop语句中，有两种使用While关键字检查条件的方式¾您可以在进入循环之前检查条件，或者¾您可以在循环至少运行一次后检查条件。

[在进入循环之前检查条件](contents.xhtml#sc3_282a)

在进入循环之前检查条件的语法是：

DO WHILE (条件)

要重复的代码

循环

[在循环至少运行一次后检查条件](contents.xhtml#sc3_283a)

在循环至少运行一次后检查条件的语法是：

DO

要重复的代码

LOOP WHILE (条件)

[场景17](contents.xhtml#sc3_284a)

编写一个接受和验证用户名的代码。不应允许空名称。参考培训文件5.xls：

参考[图19.1](#fig19-1)：

![](images/Figure_19.1.png)

图19.1：场景17

| Sub validate_name()Dim name As Stringname = InputBox("输入您的姓名")Do While Trim(name) = ""MsgBox "姓名不能为空"name = InputBox("输入您的姓名")LoopEnd Sub |
| --- |

注意：Trim函数会删除单词开头和结尾的空格。

[使用For…Next语句](contents.xhtml#sc2_285a)

+   您可以使用For...Next语句重复执行一组语句特定次数。

+   For循环使用一个计数器变量，其值在每次循环内部重复时增加或减少。

语法：

对于计数变量=初始值到最终值STEP步长值

要重复的代码

下一个

注意：数据类型越小，更新所需的时间越短。

[场景18](contents.xhtml#sc3_286a)

创建一个名为fill_series的宏，以显示从1到10的数字（从单元格A1开始）。

Sub fill_series()

声明fill_val为整数

Range("A1").Select

对于fill_val = 1到10

ActiveCell.Value = fill_val

ActiveCell.Offset(1, 0).Select Next

End Sub

Offset函数()用于指向或引用对象的上、下、左或右。

语法：

OFFSET(行，列)

示例

1.  Activecell.Offset(1,0).select：这将选择Activecell下面1行，右边0列的单元格，

1.  Activecell.Offset(0,1).select：这将选择Activecell右边0行，1列的单元格，

1.  Activecell.Offset(-1,0).select：这将选择Activecell上面1行，右边0列的单元格，

1.  Activecell.Offset(0,-1).select：这将选择Activecell下面0行，左边1列的单元格。

[使用ForEach…Next语句](contents.xhtml#sc2_287a)

For Each...Next语句为集合中的每个对象或数组中的元素重复执行一组语句。

Visual Basic每次循环运行时都会自动设置一个变量。

可以在循环中的任何位置放置任意数量的Exit For语句作为退出的替代方式。

语法：

对于每个元素在组中

[语句]

[退出For]

[语句]

下一个[element]

必需：用于迭代集合或数组元素的变量。对于集合，元素只能是Variant变量、通用对象变量或任何特定对象变量。对于数组，元素只能是Variant变量。

组：必需。对象集合或数组的名称

语句

可选。在组中的每个项目上执行的一个或多个语句。

[场景19](contents.xhtml#sc3_288a)

创建一个名为UPPER_CASE的宏，将数据转换为大写字母。使用Ucase()函数将大小写转换为大写字母

参考以下[图19.2](#fig19-2)：

![](images/Figure_19.2.png)

图19.2：场景19

| Sub UPPER_CASE()Dim wscell As RangeFor Each wscell In Selectionwscell.Value = UCase(wscell.Value)NextEnd Sub |
| --- |

[场景20](contents.xhtml#sc3_289a)

创建一个名为lower_case的宏，将数据转换为小写字母。使用lcase()函数将大小写转换为小写字母

参考[图19.3](#fig19-3)：

![](images/Figure_19.3.png)

图19.3：场景20

| Sub lower_case()Dim wscell As RangeFor Each wscell In Selectionwscell.Value = LCase(wscell.Value)NextEnd Sub |
| --- |

[场景21](contents.xhtml#sc3_290a)

创建一个名为Proper_case的宏，将数据转换为标题大小写字母。使用WorksheetFunction对象在VBA中使用Excel中的任何函数。

参考[图19.4](#fig19-4)：

![](images/Figure_19.4.png)

图19.4：场景21

| Sub Proper_Case()Dim wscell As RangeFor Each wscell In Selectionwscell.Value = Application.WorksheetFunction.Proper(wscell.Value) NextEnd Sub |
| --- |

[场景22](contents.xhtml#sc3_291a)

打开场景22并进行修改。在记录宏后，您应该询问用户是否继续，并根据用户的响应运行。如果用户点击确定，则应继续数据输入。如果用户点击取消，则显示“谢谢”并结束宏。参考[图19.5](#fig19-5)：

![](images/Figure_19.5.png)

图19.5：场景22

| Sub Data_Entry1()Dim EmpCode As Integer, next_row As IntegerDim EmpName As StringDim doj As DateDim Salary As CurrencyWorksheets("database").SelectRange("a65536").SelectSelection.End(xlUp).Selectnext_row = ActiveCell.Row + 1DoEmpCode = InputBox("输入员工编号")EmpName = InputBox("输入员工姓名")doj = InputBox("输入入职日期 mm/dd/yy")Salary = InputBox("输入员工工资")Cells(next_row , 1).Value = EmpCodeCells(next_row , 2).Value = EmpNameCells(next_row , 3).Value = Format(doj, "MMM DD YYYY")Cells(next_row , 4).Value = Salarynext_row =next_row + 1Loop While (MsgBox("是否继续？", vbOKCancel) = vbOK)MsgBox "谢谢"End Sub |
| --- |

[场景23](contents.xhtml#sc3_292a)

创建一个宏，将为每个员工计算以下内容

+   住房津贴（工资的75%）

+   DA（工资的60%）

+   总计（工资+住房津贴+DA）

参考[图19.6](#fig19-6)：

![](images/Figure_19.6.png)

图19.6：场景23

解决这个问题可能有两种方法

参考培训文件6.xls

1.  通过宏，您可以将公式放入单元格中：

    | Sub Gross_Salary()‘用户将选择范围H2:H101单元格作为范围。对于选择中的每个wscellwscell.Offset(0, 1).Value = "=rc[-1]*75%"wscell.Offset(0, 2).Value = "=rc[-2]*60%"wscell.Offset(0, 3).Value = "=sum(rc[-1]:rc[-3])"NextEnd Sub |
    | --- |

1.  在您的宏中计算并仅将结果放入单元格中：

    | Sub Gross_Salary()用户将选择范围H2:H101 Dim wscell As RangeFor Each wscell In Selectionwscell.Offset(0, 1).Value= wscell.Value * .75wscell.Offset(0, 2).Value = wscell.Value * 60%wscell.Offset(0, 3).Value = wscell.value + wscell.Offset(0, 1).Value + wscell.Offset(0, 2).ValueNextEnd Sub |
    | --- |

[场景24](contents.xhtml#sc3_293a)

创建一个宏来显示当前工作簿中工作表名称的列表。参考[图19.7](#fig19-7)：

![](images/Figure_19.7.png)

图19.7：场景24

| Sub list_sheets()„ 声明一个工作表对象变量Dim sht As WorksheetFor Each sht In WorksheetsActiveCell.Value = sht.nameActiveCell.Offset(1, 0).SelectNextEnd Sub |
| --- |

[自动执行的宏](contents.xhtml#sc2_294a)

语法是：

| fydyr |
| --- |

参考以下[表19.1](#tab19-1)：

| 到 | 使用 |
| --- | --- |
| 在工作簿打开时运行宏 | Sub auto_open()End Sub |
| 在工作簿关闭时运行宏 | Sub auto_close()End Sub |

表19.1：自动执行的宏

[练习 3](contents.xhtml#sc3_295a)

编写一个名为“Search_sheet”的函数来检查任何工作表是否存在。

| Function Search_sheet(newSht)Dim sht As WorksheetFor Each sht In WorksheetsIf UCase(sht.name) = UCase(newSht) ThenSearch_sheet = "工作表(" & newSht & ") 存在"Exit FunctionEnd IfNextSearch_sheet = "工作表(" & newSht & ") 不存在"End Function |
| --- |

[练习 4](contents.xhtml#sc3_296a)

编写一个宏，为每位员工增加2000的工资。

[场景 25](contents.xhtml#sc3_297a)

创建一个宏，使用数据透视表生成按区域和部门工资总和以及员工数量的总计。修改代码，使每次都在当前数据上生成数据透视表。

参考培训文件6.xls

| Sub Pivot_Summary()Range("A2").SelectActiveWorkbook.PivotCaches.Add(SourceType:=xlDatabase, SourceData:= _ Range("a2").CurrentRegion).CreatePivotTable TableDestination:="", TableName:= _ "PivotTable2", DefaultVersion:=xlPivotTableVersion10ActiveSheet.PivotTableWizard TableDestination:=ActiveSheet.Cells(3, 1)ActiveSheet.Cells(3, 1).SelectActiveSheet.PivotTables("PivotTable2").AddFields RowFields:=Array("Region", _ "Dept", "Data")With ActiveSheet.PivotTables("PivotTable2").PivotFields("salary").Orientation = xlDataField.Position = 1End WithWith ActiveSheet.PivotTables("PivotTable2").PivotFields("Empcode").Orientation = xlDataField.Caption = "Count of Empcode".Function = xlCountEnd WithRange("C3").SelectWith ActiveSheet.PivotTables("PivotTable2").DataPivotField.Orientation = xlColumnField.Position = 1End WithEnd Sub |
| --- |

[场景 26](contents.xhtml#sc3_298a)

编写一段代码，如果“master”工作表中存在，则从“daily”工作表中删除重复记录。

（使用嵌套循环）

[解决方案 26](contents.xhtml#sc4_299a)

参考培训文件7.xls

| Sub duplicates()Dim wscell As Range, tcell As RangeWorksheets("master").SelectRange("a2").SelectRange(ActiveCell, ActiveCell.End(xlDown)).SelectFor Each wscell In SelectionWorksheets("daily").SelectRange("a2").SelectRange(ActiveCell, ActiveCell.End(xlDown)).SelectFor Each tcell In SelectionIf tcell.Value = wscell.Value Thentcell.EntireRow.Delete End IfNextNextActiveCell.SelectEnd Sub |
| --- |

可以使用查找命令编写相同的代码如下

| Sub duplicates_With_find()Worksheets("master").SelectRangec("a2").SelectRange(ActiveCell, ActiveCell.End(xlDown)).SelectFor Each tcell In SelectionWorksheets("daily").SelectSet c = Cells.Find(What:=tcell.Value)If Not c Is Nothing Then Rows(c.Row).DeleteEnd IfNextEnd Sub |
| --- |

[场景 27](contents.xhtml#sc3_300a)

创建一个名为Merging_Sheets的宏，将所有工作表的数据复制到一个工作表中

你的宏应该生成一个按区域销售数量总计和员工代码总计的数据透视表。

[解决方案](contents.xhtml#sc4_301a)

| Sub Merging_Sheets()'Scenario27'在末尾添加一个工作表，并将其命名为consolidate并创建标题Worksheets.Add After:=Worksheets(Worksheets.Count)ActiveSheet.Name = "consolidate"ActiveSheet.Range("a1").SelectRange("a1").Value = "Product"Range("b1").Value = "Sales"将每个工作表的数据复制到consolidate工作表For Index = 1 To Worksheets.Count - 1Worksheets(Index).SelectRange("a2").SelectRange(Selection, Selection.End(xlDown)).SelectRange(Selection, Selection.End(xlToRight)).SelectSelection.CopyWorksheets("consolidate").SelectCells(Range("a65536").End(xlUp).Row + 1, 1).SelectActiveSheet.PasteNext,生成一个关于合并数据的数据透视表Sheets("consolidate").SelectRange("A1").SelectApplication.CutCopyMode = FalseActiveWorkbook.PivotCaches.Add(SourceType:=xlDatabase, SourceData:= _Range("a1").CurrentRegion).CreatePivotTable TableDestination:="", TableName _:="PivotTable1", DefaultVersion:=xlPivotTableVersion10ActiveSheet.PivotTableWizard TableDestination:=ActiveSheet.Cells(3, 1) ActiveSheet.Cells(3, 1).SelectActiveSheet.PivotTables("PivotTable1").AddFields RowFields:="Product"ActiveSheet.PivotTables("PivotTable1").PivotFields("Sales").Orientation = _ xlDataFieldEnd Sub |
| --- |

[结论](contents.xhtml#sc2_302a)

精通循环结构对于有效的VBA编程至关重要。通过利用循环，您可以自动化重复任务，处理大量数据，并提高VBA程序的整体效率。本章全面介绍了循环及其在VBA中的应用，为您提供了编写简洁而强大的代码的技能，节省时间和精力。

[练习](contents.xhtml#sc2_303a)

1.  编写一个名为“PrintNumbers”的VBA宏，将数字从1打印到100在即时窗口中。

1.  创建一个名为“CalculateSum”的VBA宏，用于计算从1到10的数字的总和，并在消息框中显示结果。

1.  编写一个名为“EvenNumbers”的VBA宏，在即时窗口中打印从1到20的所有偶数。

1.  创建一个名为“Factorial”的VBA宏，用于计算给定数字的阶乘。该宏应提示用户输入一个数字，然后在消息框中显示阶乘结果。

1.  编写一个名为“ReverseString”的VBA宏，提示用户输入一个字符串，然后在即时窗口中打印字符串的反转。

1.  创建一个名为“TableOfSquares”的VBA宏，生成从1到10的平方表。该宏应在新工作表中的不同列中显示数字及其平方。

1.  编写一个���为“CountCharacters”的VBA宏，计算给定字符串中的字符数。该宏应提示用户输入一个字符串，然后在消息框中显示计数。

加入我们书籍的Discord空间

加入书籍的Discord Workspace，获取最新更新、优惠、全球科技动态、新发布和与作者的交流：

**[https://discord.bpbonline.com](https://discord.bpbonline.com)**

![](images/fm1.png)
