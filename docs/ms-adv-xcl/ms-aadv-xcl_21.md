# 第二十章 VBA 中的数组和集合

介绍

数组和集合是 VBA 编程中的基本组件，可以有效地存储和操作多个值。在本章中，我们将探讨它们的概念，学习如何声明和使用它们，了解数组索引和动态数组，并研究它们在 VBA 中应用的实际示例。

结构

在本章中，我们将讨论以下主题：

+   数组

+   声明数组

+   使用数组

+   数组索引

+   声明动态数组

+   调整动态数组的大小

目标

在本章结束时，读者将学习在 VBA 编程中使用数组和集合，学习如何声明、调整大小和高效使用数组，并探讨集合相对于数组在高级数据操作任务中的优势。

数组

数组是具有相同内在数据类型的一组按顺序索引的元素。数组的每个元素都有一个唯一的标识索引号。

对数组的一个元素进行更改不会影响其他元素。

不同类型的数组如下：

+   指定大小的数组是固定大小的数组。

+   在程序运行时可以更改大小的数组是动态数组。

+   单维数组：只有行

+   多维数组：带有行和列

声明数组

数组的声明方式与其他变量相同。

语法：

Dim name_Of_array(Size) As Data_Type

示例

单维数组：声明一个可以存储整数项目的大小为 10 行的单维数组变量。

Dim Myarray(10) As Integer

多维数组（最多 60 维）：声明一个可以存储 15 个整数项目的 3 行 5 列的多维数组变量。

Dim Myarray(3 , 5) As Integer

使用数组

使用数组可以通过以下示例解释：为了存储每个月每天的日常开支，您可以声明一个具有 31 个元素的数组变量，而不是声明 31 个变量。

数组中的每个元素包含一个值。

| Sub Single_array()Dim curExpense(31) As CurrencyDim intI As IntegerFor intI = 0 to 31curExpense(intI) = 20NextEnd Sub |
| --- |

注意：在上面的示例中，数组索引将从 0 开始

数组索引

所有数组索引都从零开始。数组是从 0 还是 1 开始索引取决于 Option Base 语句的设置。

如果未指定 Option Base 1，则所有数组索引都从零开始。

示例

| 选项基础 1Sub Single_array()Dim curExpense(31) As CurrencyDim intI As IntegerFor intI = 1 to 31curExpense(intI) = 20NextEnd Sub |
| --- |

注意：在上面的示例中，数组索引将从 1 开始。

声明动态数组

通过声明动态数组，您可以在代码运行时调整数组的大小。

使用 Dim 语句声明一个数组，括号留空。

语法：

Dim Name_Of_Array() As Data_Type

调整动态数组大小

使用 ReDim 语句在过程内隐式声明一个数组。

在使用 ReDim 语句时，小心不要拼错数组的名称。

数组示例

| Option Base 1 ' 初始化数组索引 1Sub Searchdata()Dim mycell_array() As String ' 声明动态数组 Dim a, i As Longi = 1Sheets(1).Selecta = Range("a65536").End(xlUp).Row - 1ReDim mycell_array(a) ' 重新声明数组大小 Range("a2", Range("a2").End(xlDown)).SelectFor Each mycell In Selection mycell_array(i) = mycelli = i + 1NextSheets("database").SelectRange("a2", Range("a2").End(xlDown)).Selecti = 1For i = 1 To aFor Each mycell In SelectionIf mycell_array(i) = mycell Thenmycell.EntireRow.Delete 'mycell.Offset(0, 1).Value = "found"End IfNextEnd Sub |
| --- |

结论

数组和集合是 VBA 编程中强大的工具，有助于管理数据集并增强代码效率。掌握这些概念，可以优化 VBA 代码，提高可读性，并有效处理复杂的数据结构。将数组和集合纳入编程技能范围，将扩展您的能力，使您能够处理更广泛的 VBA 项目。

练习

1.  声明一个动态数组，用于存储 5 名员工的日常开支。

1.  使用循环输入每位员工在指定天数内的开支。

1.  计算每位员工的总开支并显示结果。

1.  确定总开支最高的员工，并打印其姓名和相应金额。

1.  计算整个团队每天的平均开支并显示结果。

加入我们书籍的 Discord 空间

加入书籍的 Discord Workspace，获取最新更新、优惠、全球科技动态、新发布和与作者的交流：

**[`discord.bpbonline.com`](https://discord.bpbonline.com)**

![](img/fm1.png)
