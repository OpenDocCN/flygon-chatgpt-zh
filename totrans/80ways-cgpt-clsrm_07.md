第八章

## 使用 chatGPT 进行计算机编程

本章将教你如何利用 chatGPT 来简化编码过程。通过 chatGPT，你可以快速使用各种语言编写代码。提供具体的输入，让 chatGPT 发挥其魔力。ChatGPT 不仅可以编写代码和解释其作用，还可以解决任何问题、编写 SQL 代码、清理 HTML 代码、编写应用程序脚本，甚至为你的代码添加注释。通过本章的学习，你将更好地了解如何利用 chatGPT 提高编码效率。

## 54\. 写代码

需要帮助写代码吗？解释你想要实现什么以及要使用哪种语言。ChatGPT 将尽力提供可用的代码。有些人已经与 chatGPT 协作编写了整个应用程序。

这是一个简单脚本的示例：

**编写 PHP 中的数据库连接代码，以显示数据为 HTML 表，包括以下信息：姓名、地址、城市、州和邮政编码。**

ChatGPT:

*以下是如何使用 PHP 将 MySQL 数据库中名为“address_list”的表中的数据显示为 HTML 表的示例：*

*<?php*

*$servername = “localhost”;*

*$username = “your_username”;*

*$password = “your_password”;*

*$dbname = “your_database”;*

*// 创建连接*

*$conn = new mysqli($servername, $username, $password, $dbname);*

*// 检查连接*

*if ($conn->connect_error) {*

*die(“连接失败：” . $conn->connect_error);*

*}*

*// 从表中选择数据*

*$sql = “SELECT name, address, city, state, zipcode FROM address_list”;*

*$result = $conn->query($sql);*

*echo “<table>*

*<tr>*

*<th>Name</th>*

*<th>Address</th>*

*<th>City</th>*

*<th>State</th>*

*<th>Zip Code</th>*

*</tr>”;*

*// 输出每行的数据*

*while($row = $result->fetch_assoc()) {*

*echo “<tr>*

*<td>“.$row[”name”].”</td>*

*<td>“.$row[”address”].”</td>*

*<td>“.$row[”city”].”</td>*

*<td>“.$row[”state”].”</td>*

*<td>“.$row[”zipcode”].”</td>*

*</tr>”;*

*}*

*echo “</table>”;*

*$conn->close();*

*?>*

*这段代码使用 MySQLi 扩展从“address_list”表中选择数据，然后遍历结果行并将它们添加到 HTML 表中。表头使用 <th> 标签创建，数据行使用 <td> 标签创建。重要的是要注意，你应该将 $username、$password、$dbname 和 $servername 变量更改为你的实际凭据。另外，请确保表“address_list”已经存在，否则你将收到错误消息。*

## 55\. 解释代码的作用

你有一段计算机代码，不确定是什么语言或它的作用吗？ChatGPT 很乐意告诉你。粘贴一段代码块，询问 chatGPT 解释代码的作用。

**<%**

**Set fs=Server.CreateObject(“Scripting.FileSystemObject”)**

**Set f=fs.OpenTextFile(Server.MapPath(“testread.txt”), 1)**

**do while f.AtEndOfStream = false**

**Response.Write(f.ReadLine)**

**Response.Write(“<br>”)**

**loop**

**f.Close**

**Set f=Nothing**

**Set fs=Nothing**

**%>**

**代码的解释**

ChatGPT：

*这是一个使用 VBScript 编写的服务器端脚本，通常嵌入在 ASP（Active Server Pages）文件中。*

*脚本使用***Server.CreateObject***方法创建一个“Scripting.FileSystemObject”对象的实例，用于与文件系统交互。这个对象保存在变量***fs***中。*

*然后，脚本使用***fs***对象的***OpenTextFile***方法打开一个名为“testread.txt”的文本文件，该文件位于与 ASP 文件相同的目录中。变量***f***保存文件对象。*

*然后，脚本进入一个循环，使用***do while***语句检查文件是否到达流的末尾，这意味着文件是否到达文件的末尾。如果没有到达，它使用***ReadLine***方法读取文件的下一行，并使用***Response.Write***将其写入响应。它还使用***Response.Write(“<br>”)***写入一个换行符，以分隔文件的行。*

*当文件末尾被达到时，脚本使用***f.Close***关闭文件，并将***f***和***fs***变量设置为***Nothing***，释放文件对象和文件系统对象使用的内存。*

*简而言之，这个脚本读取了一个名为“testread.txt”的文本文件的内容，该文件位于与 ASP 文件相同的目录中，并将文件的每一行写入响应，用换行符分隔。*

## 56\. 排查脚本

ChatGPT 可以帮助您排查代码问题。请 ChatGPT 检查您的代码是否有错误。以下是一个快速示例，我引入了两个典型错误：

**这段代码有什么问题**

**<?php function familyName($fname, $year) {**

**echo “$fname Refsnes. Born in $year <br>”;**

**}**

**familyName(“Hege”,”1975″);**

**familyName(“Stale”,”1978″)**

**familyname(“Kai Jim”,”1983″);**

**?>**

ChatGPT：*这段代码有两个问题。*

1.  *最后一个函数调用使用了“familyname”而不是“familyName”（注意正确版本中大写的“N”）。这意味着该函数不会被调用，会出现错误。*

1.  *对函数的第二次调用在行末���少一个分号。这将导致解析错误，代码将无法正确执行。应该是：familyName(“Stale”,”1978″);*

## 57\. 写 SQL 代码

使用数据库查询语言可能会很棘手和耗时，但如果使用 MySQL、Oracle SQL 甚至 Microsoft Access，这是必不可少的。ChatGPT 将通过将您的意图转换为 SQL 代码来帮助您快速编写查询。以下是一个使用 Postgres SQL 的示例：

**Postgres SQL 表，及其属性：**

**Employee(id, name, department_id)**

**Department(id, name, address)**

**Salary_Payments(id, employee_id, amount, date)**

**查询列出过去 3 个月雇佣了超过 10 名员工的部门的名称**

ChatGPT：

*SELECT Department.name FROM Employee*

*INNER JOIN Department ON Employee.department_id = Department.id*

*WHERE Employee.id IN ( SELECT Salary_Payments.employee_id FROM Salary_Payments*

*WHERE date >= NOW() - INTERVAL ‘3 months’ )*

*GROUP BY Department.id*

*HAVING COUNT(Employee.id) > 10;*

*上述查询将在 department_id 列上连接 Employee 和 Department 表，然后将结果筛选为仅包括最近 3 个月有薪水记录的员工。之后，查询将按部门对结果进行分组，并计算每个部门的员工人数。最后，HAVING 子句将筛选出仅包括员工人数超过 10 人的部门的结果。*

## 58\. 清理 HTML 代码

从文字处理器或网站复制内容到学习管理系统（LMS）或网页通常会引入非必要的 HTML 代码。这些额外的代码会增加编辑的难度。我喜欢剔除不必要的代码。ChatGPT 会为您完成这项工作。以下是一个示例：

**清理这段 HTML 代码“<h2 style=”;”><strong>犯罪学：犯罪理论</strong></h2> <p style=”;”><img src=”https://mysite.com/myimage.jpg” width=”640″ height=”354″ data-api-endpoint=”https://mysite.com/myimage.jpg” data-api-returntype=”File” />  </p> <h2 style=”;”><strong>欢迎！ </strong></h2> <p style=”;”><strong><i>我很高兴在 2023 年春季学期教授这门课程，并期待我们在一起的时间。</i></strong></p> <p>课程编号/班级：  <strong><span lang=”FR”>CRM 205 犯罪学：犯罪理论</span></strong><br />上课时间：    <strong><span>周二和周四，下午 3:30 – 4:45  </span></strong><br />上课地点：  <strong>主楼，201 教室（注意：如果因任何原因我们必须远程上课，将是同步的，您应该使用我们的班级微软团队。请通过以下链接加入团队：<a href=”https://teams.microsoft.com/courselink”>https://teams.microsoft.com/courselink</a>)</strong></p> <p><br />期末考试日期/时间：  <strong>202x 年 5 月 2 日，周二 @ 下午 2:00</strong></p> <p>教师：       <strong><span>Stan Skrabut         </span></strong><br />办公时间地点：    <strong>虚拟</strong><br />办公时间： <strong><span>周三下午 4 点-5 点 </span></strong><i><span>或通过预约</span></i><br />电子邮件地址：  <strong>myemail@gmail.com</strong><br />电话：    <strong>通过微软团队群组联系</strong></p> <p>教材和材料： </p> <p>必需教材： <strong>Siegel, L.J. (2019). 犯罪学：核心（第 7 版）Cengage Learning, Inc.</strong></p> <p>必需材料： <strong>可能由教师提供补充材料</strong></p> <p>教学大纲</p>”**

ChatGPT:

*<h2>犯罪学：犯罪理论</h2>*

*<p><img src=“https://mysite.com/myimage.jpg” width=”640″ height=”354″ ></p>*

*<h2>欢迎！</h2>*

*<p><i>我很高兴在 2023 年春季学期教授这门课程，并期待我们在一起的时间。</i></p>*

*<p>课程编号/部分：CRM 205 犯罪学：犯罪理论<br>*

*上课日期/时间：周二和周四，下午 3:30 至 4:45<br>*

*课程地点：主楼，201 室<br>*

*最后一周日期/时间：202x 年 5 月 2 日星期二 @ 下午 2:00</p>*

*<p>讲师：Stan Skrabut<br>*

*办公时间地点：虚拟<br>*

*办公时间：周三下午 4 点至 5 点，或通过预约<br>*

*电子邮件地址：myemail@gmail.com<br>*

*电话：通过 Microsoft Teams 群组联系</p>*

*<p>教科书和材料：</p>*

*<p>必需教科书：Siegel, L.J. (2019). 犯罪学：核心（第 7 版）Cengage Learning, Inc.</p>*

*<p>必需材料：辅助材料可能由讲师提供</p>*

*<p>教学大纲</p>*

## 59\. 编写应用程序脚本

ChatGPT 可以将您的意图转化为行动。例如，您可以通过脚本编写来改进软件应用程序的功能。您可以使用 chatGPT 创建解决方案来解决问题。ChatGPT 可以为 Microsoft、Google、Apple 和 Linux 产品编写脚本。您还可以增强特定产品，如电子表格或文字处理程序。例如，我有兴趣在目录中的所有文件名前缀为“stan_”。这是我写的提示：

**编写一个 PowerShell 脚本，将目录中所有文件名的开头添加“stan_”。**

ChatGPT:

*# 获取当前目录*

*$dir = Get-Location*

*# 获取目录中的所有文件*

*$files = Get-ChildItem -Path $dir*

*# 循环遍历每个文��*

*foreach ($file in $files) {*

*# 检查文件是否不是目录*

*if (-not $file.PSIsContainer) {*

*# 通过在当前文件名前添加“stan_”来创建新文件名*

*$newFileName = “stan_” + $file.Name*

*# 重命名文件*

*Rename-Item $file.FullName $newFileName*

*}*

*}*

*此脚本将获取当前目录，检索该目录中的所有文件，并循环遍历每个文件。对于找到的每个文件，它将检查是否不是目录，然后通过在当前文件名的开头添加“stan_”来创建新文件名。最后，它将使用新文件名重命名文件。*

您试图解决什么问题？

## 60\. 为您的代码添加注释

在上面的示例中，您可以看到 chatGPT 可以成为编写代码和解释代码功能的绝佳助手。您还可以要求 chatGPT 记录您的脚本。

**重写下面的代码并添加注释：**

**<?php**

**require_once ‘_db.php’;**

**$stmt = $db->prepare(‘SELECT * FROM events WHERE NOT ((end <= :start) OR (start >= :end))’);**

**$stmt->bindParam(‘:start’, $_GET[’start’]);**

**$stmt->bindParam(‘:end’, $_GET[’end’]);**

**$stmt->execute();**

**$result = $stmt->fetchAll();**

**class Event {}**

**$events = array();**

**foreach($result as $row) {**

**$e = new Event();**

**$e->id = $row[‘id’];**

**$e->text = $row[‘name’];**

**$e->start = $row[‘start’];**

**$e->end = $row[‘end’];**

**$events[] = $e;**

**}**

**echo json_encode($events);**

**?>**

chatGPT:

*<?php*

*// 需要 _db.php 文件*

*require_once ‘_db.php’;*

*// 准备一个 SELECT 语句，从‘events’表中检索事件，其中结束日期在传入的$_GET 变量中的开始日期之后。*

*$stmt = $db->prepare(‘SELECT * FROM events WHERE NOT ((end <= :start) OR (start >= :end))’);*

*// 将$_GET 变量中的开始和结束参数绑定到语句*

*$stmt->bindParam(‘:start’, $_GET[’start’]);*

*$stmt->bindParam(‘:end’, $_GET[’end’]);*

*// 执行语句*

*$stmt->execute();*

*// 从查询中获取所有数据行并存储在$result 变量中*

*$result = $stmt->fetchAll();*

*// 创建一个空的 Event 类*

*class Event {}*

*// 创建一个空数组来存储事件对象*

*$events = array();*

*// 遍历从查询返回的每一行数据*

*foreach($result as $row) {*

*// 创建一个新的 Event 对象*

*$e = new Event();*

*// 将行中的值分配给 Event 对象的属性*

*$e->id = $row[‘id’];*

*$e->text = $row[‘name’];*

*$e->start = $row[‘start’];*

*$e->end = $row[‘end’];*

*// 将 Event 对象添加到事件数组中*

*$events[] = $e;*

*}*

*// 将事件数组编码为 JSON 并输出*

*echo json_encode($events);*

*?>*
