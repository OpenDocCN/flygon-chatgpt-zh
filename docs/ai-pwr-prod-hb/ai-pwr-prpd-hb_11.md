# 用于编码的人工智能

*"最好的错误消息是永远不会出现的。" - 托马斯·福克斯*

![](images/image-26.png)

编码 - 由 Midjourney AI 生成的图像

## 介绍

如果您是一名编码人员，您会知道在寻找编码问题答案时很容易迷失方向。有时您正在尝试解决特定问题，下一刻您已经深入了几个小时的新资源、技巧和巧妙的代码的兔子洞。虽然这些发现可能很有用，但它们也可能严重浪费时间和生产力。这就是 ChatGPT 的用武之地。通过其快速准确地回答编码问题的能力，ChatGPT 可以帮助您摆脱噪音，重新专注于您最初的任务。如果第一个解决方案不起作用，ChatGPT 可以提供解决方法和替代方案，帮助您重新回到正轨。无论您是经验丰富的编码人员还是刚刚开始，ChatGPT 都可以成为提高您生产力和效率的宝贵工具。

请记住，文档是完成代码的重要部分。即使您的代码是功能性的，直到文档完成为止，它才算真正完成。幸运的是，ChatGPT 也可以协助文档编写，提供最佳实践指导，并提供模板和工具，使流程更加顺畅和高效。借助 ChatGPT 的帮助，您可以确保您的代码完全文档化，并准备好供他人使用。

## 分析和审查代码，无论是什么

ChatGPT 可以分析代码并解释其功能。例如，如果您在浏览旧计算机上的旧媒体时遇到一些陌生的代码，您可以��助于 ChatGPT 来帮助解释其目的。这将简化理解代码的任务。

让我们分析下面的代码并理解它的作用。这种语言看起来很熟悉，但我们并不确定，我们可以做出聪明的猜测并尝试理解它的作用，或者只是拿出那段代码块让 ChatGPT 分析。

```
PROGRAM Sort(input, output); CONST
(* Max array size. *) MaxElts = 50; TYPE
(* Type of the element array. *) IntArrType = ARRAY [1..MaxElts] OF Integer; VAR
(* Indexes, exchange temp, array size. *) i, j, tmp, size: integer; (* Array of ints *) arr: IntArrType; (* Read in the integers. *)
PROCEDURE ReadArr(VAR size: Integer; VAR a: IntArrType); BEGIN size := 1; WHILE NOT eof DO BEGIN readln(a[size]); IF NOT eof THEN size := size + 1
END
END; BEGIN
(* Read *) ReadArr(size, arr); (* Sort using bubble sort. *)
FOR i := size - 1 DOWNTO 1 DO
FOR j := 1 TO i DO
IF arr[j] > arr[j + 1] THEN BEGIN tmp := arr[j];
                    arr[j] := arr[j + 1];
                    arr[j + 1] := tmp; END; (* Print. *)
FOR i := 1 TO size DO writeln(arr[i]) END.
```

拿着这段代码问 ChatGPT 在提示中。

#### 提示 - 它是做什么的：

```
What does this code do ? : PROGRAM Sort(input, output); CONST
(* Max array size. *) MaxElts = 50; TYPE
(* Type of the element array. *) IntArrType = ARRAY [1..MaxElts] OF Integer; VAR
(* Indexes, exchange temp, array size. *) i, j, tmp, size: integer; (* Array of ints *) arr: IntArrType; (* Read in the integers. *)
PROCEDURE ReadArr(VAR size: Integer; VAR a: IntArrType); BEGIN size := 1; WHILE NOT eof DO BEGIN readln(a[size]); IF NOT eof THEN size := size + 1
END
END; BEGIN
(* Read *) ReadArr(size, arr); (* Sort using bubble sort. *)
FOR i := size - 1 DOWNTO 1 DO
FOR j := 1 TO i DO
IF arr[j] > arr[j + 1] THEN BEGIN tmp := arr[j];
                    arr[j] := arr[j + 1];
                    arr[j + 1] := tmp; END; (* Print. *)
FOR i := 1 TO size DO writeln(arr[i]) END.
```

#### 输出 - - 它是做什么的

```
This is a Pascal program that reads in integers and sorts them in ascending order using the bubble sort algorithm. The program defines a constant MaxElts, which is the maximum size of the array of integers that the program can handle. The program declares a type called IntArrType, which is an array of integers with a size of MaxElts. The program then declares some variables: i, j, tmp, size, and arr. i and j are used as loop indices in the bubble sort algorithm, tmp is a temporary variable used to swap elements in the array during sorting, size is the number of integers to be read in and sorted, and arr is the array of integers. The program defines a procedure called ReadArr, which reads integers from input and stores them in the array a. The size of the array is stored in the variable size. The program calls the ReadArr procedure to read in the integers, and then sorts them using the bubble sort algorithm. Finally, the sorted integers are printed to the output. Note: Pascal is a programming language that was popular in the 1980s and 1990s, and this code may not be compatible with modern compilers.
```

好的，所以这段代码是用 Pascal 编写的，我们对其有一些了解，让我们请 ChatGPT 将代码翻译成 Python

#### 提示 - 到 python：

```
translate  the code to python
```

#### 输出 - 到 python

```
Here is the Python version of the provided code: def bubble_sort(arr):
    n = len(arr) # Traverse through all array elements  for i in range(n): # Last i elements are already sorted  for j in range(0, n-i-1): # Swap if the element found is greater than the next element  if arr[j] > arr[j+1]:
                arr[j], arr[j+1] = arr[j+1], arr[j] # Read in the integers arr = [] while True: try:
        arr.append(int(input())) except EOFError: break
# Sort using bubble sort bubble_sort(arr) # Print the sorted array for i in range(len(arr)): print(arr[i])

Note that in the original Pascal code, the eof function is used to check if the end of the input file has been reached. In the Python version, the try and except blocks are used to handle the end of the input stream.
```

让我们尝试将另一个翻译成 Perl

#### 提示 - perl：

```
translate the code to perl
```

#### 输出 - perl

```
Here is the code translated to Perl: use strict; use warnings; my $MaxElts = 50; my @arr = (); sub ReadArr { my $size = 0; while (my $line = <STDIN>) { chomp($line); last if ($line eq ""); $arr[$size++] = $line;
    } return $size;
} my $size = ReadArr(); for (my $i = $size - 1; $i >= 1; $i--) { for (my $j = 0; $j < $i; $j++) { if ($arr[$j] > $arr[$j+1]) { my $tmp = $arr[$j]; $arr[$j] = $arr[$j+1]; $arr[$j+1] = $tmp;
        }
    }
} for (my $i = 0; $i < $size; $i++) { print "$arr[$i]\n";
}

Note that in Perl, stdin is read from the default input filehandle, which is STDIN. Also, the chomp() function is used to remove the newline character from each input line.
```

## 记录您的代码

编码人员喜欢编码，但不太喜欢记录他们的代码。ChatGPT 可以轻松为您生成文档。让我们请 ChatGPT 为冒泡排序生成的 perl 代码生成一个手册页面。

#### 提示 - man 页面：

```
give me a man page for the below code: use strict; use warnings; my $MaxElts = 50; my @arr = (); sub ReadArr { my $size = 0; while (my $line = <STDIN>) { chomp($line); last if ($line eq ""); $arr[$size++] = $line;
    } return $size;
} my $size = ReadArr(); for (my $i = $size - 1; $i >= 1; $i--) { for (my $j = 0; $j < $i; $j++) { if ($arr[$j] > $arr[$j+1]) { my $tmp = $arr[$j]; $arr[$j] = $arr[$j+1]; $arr[$j+1] = $tmp;
        }
    }
} for (my $i = 0; $i < $size; $i++) { print "$arr[$i]\n";
}
```

#### 输出 - man 页面

```
.TH SORT 1 "2023-02-22" "1.0" "sort man page" .SH NAME sort - sort a list of integers

.SH SYNOPSIS sort .SH DESCRIPTION
The sort program reads integers from standard input and sorts them in ascending order using the bubble sort algorithm. The sorted integers are then printed to standard output, each on a separate line. .SH OPTIONS
None

.SH EXAMPLES
To sort a list of integers in a file called "input.txt", run the following command:

.B sort < input.txt

The integers in the file will be sorted in ascending order and printed to standard output. .SH AUTHOR
Written by [Your Name Here].
```

## 编码帮助

在编码过程中，您可能会有一些疑问，偶尔当您向某人寻求帮助时，他们可能会粗鲁地回答 RTFM（阅读该手册）。然而，通过 ChatGPT，您可以简单地提出问题并获得准确的回答。

例如：

#### 提示 - 连接：

```
How do I concatenate several strings in C ?
```

#### 输出 - 连接

```
In C, you can concatenate several strings using the strcat function from the string.h library. Here's an example:   #include <stdio.h> #include <string.h>   int main() {  char str1[20] = "Hello"; char str2[20] = " world"; char str3[20] = " and universe"; char finalStr[60];   strcpy(finalStr, str1); // copy first string strcat(finalStr, str2); // concatenate second string strcat(finalStr, str3); // concatenate third string   printf("%s", finalStr); // print concatenated string return 0; }   In this example, the strcat function is used to concatenate str2 and str3 onto str1 to create the final string finalStr. The strcpy function is used to copy the first string into finalStr before concatenation. Note that finalStr must be large enough to hold the concatenated result. 
```

## 学习新技能

你得到了一份新工作，你大学的大部分工作都是用Python完成的，新工作的地方主要使用Objective-C，你需要快速学习它。

#### 提示 - Obj C：

```
give me an objective C syntax cheat sheet that is useful for every day coding
```

#### 输出 - Obj C

```
Sure, here's an Objective-C syntax cheat sheet that may be useful for everyday coding:   Declaring and Initializing Variables:   // Declare a variable type variableName;   // Declare and initialize a variable type variableName = value;     Class and Object Syntax:   // Declaring a class @interface ClassName : Superclass {  // Instance variables type instanceVariableName; }   // Properties @property (nonatomic, strong) type propertyName;   // Methods - (void)methodName;   @end   // Creating an object ClassName *objectName = [[ClassName alloc] init];     Conditionals:   if (condition) {  // Code to execute when condition is true } else {  // Code to execute when condition is false }   switch (variable) {  case value1: // Code to execute when variable equals value1 break; case value2: // Code to execute when variable equals value2 break; default: // Code to execute when variable doesn't match any case
break;
}

Loops: // for loop for (int i = 0; i < count; i++) { // Code to execute on each iteration } // while loop while (condition) { // Code to execute while condition is true } // do-while loop do { // Code to execute at least once } while (condition);

Arrays: // Declare an array type arrayName[size]; // Initialize an array type arrayName[] = {value1, value2, value3}; // Accessing array elements arrayName[index]; // Iterating over an array for (int i = 0; i < sizeof(arrayName)/sizeof(type); i++) { // Code to execute on each element } NSString Formatting: // Creating an NSString with format NSString *string = [NSString stringWithFormat:@"The value is %d", value]; // Converting a string to a number NSNumberFormatter *formatter = [[NSNumberFormatter alloc] init]; NSNumber *number = [formatter numberFromString:string];

Memory Management: // Allocating and deallocating memory type *pointer = malloc(sizeof(type)); free(pointer); // Retaining and releasing objects [object retain];
[object release];

Blocks: // Defining a block ^returnType(parameters) { // Code to execute }; // Using a block [object methodWithCompletionHandler:^{ // Code to execute when the method is complete }];

I hope you find this Objective-C syntax cheat sheet useful for your everyday coding needs!
```

好的，这是一个很好的开始，但如果我们想学到更多，让我们获取一些书籍建议吧

#### 提示 - 书籍：

```
what are good books that will help me learn objective C fast
```

#### 输出 - 书籍

```
Here are some books that could help you learn Objective-C: "Programming in Objective-C" by Stephen G. Kochan - This is a popular book that covers the basics of the Objective-C programming language. "Objective-C Programming: The Big Nerd Ranch Guide" by Aaron Hillegass and Mikey Ward - This is a comprehensive guide to Objective-C programming, which covers topics such as memory management, design patterns, and debugging. "Objective-C for Absolute Beginners: iPhone, iPad, and Mac Programming Made Easy" by Gary Bennett, Brad Lees, and Mitchell Fisher - This book is designed for those who have no prior programming experience and teaches the basics of Objective-C programming with a focus on iOS and macOS development. "iOS Programming: The Big Nerd Ranch Guide" by Joe Conway and Aaron Hillegass - This book covers iOS programming with Objective-C, as well as Swift. It includes practical exercises and detailed explanations of iOS development. "Objective-C Fundamentals" by Matt Neuburg - This book provides a thorough introduction to Objective-C programming, with an emphasis on object-oriented programming concepts. "Effective Objective-C 2.0: 52 Specific Ways to Improve Your iOS and OS X Programs" by Matt Galloway - This book focuses on advanced topics in Objective-C programming, providing tips and best practices for writing efficient and effective code. These books can help you learn Objective-C programming at different levels of expertise, so you can choose the one that best suits your needs.
```

也许我们从视频中学习更好，让我们看看ChatGPT告诉我们什么：

#### 提示 - 视频：

```
can i get video suggestions with urls to learn objective C
```

#### 输出 - 视频

```
Sure, here are some video tutorials for learning Objective-C:

Objective-C Tutorial for Beginners by TheNewBoston: https://www.youtube.com/playlist?list=PLFE2CE09D83EE3E28
Objective-C Programming Course by Udemy: https://www.udemy.com/course/objective-c-programming-course/
iOS Development with Objective-C by Stanford University: https://www.youtube.com/watch?v=71pyOB4TPRE&list=PL9FA4C410EBA1384C
Objective-C Crash Course for Swift Developers by Devslopes: https://www.youtube.com/watch?v=eLTYvQCM_Z4
Objective-C Programming for iOS Development by Treehouse: https://www.youtube.com/watch?v=dFyT09BCzU0
I hope you find these resources helpful!
```

经过检查，所有链接似乎都无法使用，可能已过时。然而，这个问题可能会在未来得到解决。或者，我们可以再次询问ChatGPT以获取更新的资源。

#### 提示 - 损坏的链接：

```
none of the links work
```

#### 输出 - 损坏的链接

```
I apologize for the inconvenience. Here are some updated video suggestions for learning Objective-C, along with their corresponding URLs:

Objective-C Tutorial for Beginners by Derek Banas: https://www.youtube.com/watch?v=7wv1LHsMXzo
Objective-C Programming Tutorial by thenewboston: https://www.youtube.com/watch?v=8EYYw-nsSbE&list=PLFE2CE09D83EE3E28
Objective-C Tutorial - iOS Development Course by Udemy: https://www.udemy.com/course/objective-c-tutorial-for-absolute-beginners/
Objective-C Programming Course for Beginners by CodeWithChris: https://www.youtube.com/watch?v=3z6X1L6dL0M&list=PLMRqhzcHGw1ZrHbNvYWQ6K1noHDK1X6Gb
I hope this helps. Please let me know if you have any further questions or concerns.
```

提供的新链接似乎都无法使用，除了一个重定向到Java教程的链接。这突显了以谨慎验证ChatGPT提供的信息的重要性。虽然ChatGPT的回答大多是准确的，但仔细核实信息可以增强你对其准确性的信心。

## 模板和片段

ChatGPT非常适合代码模板，你可以专注于实际的代码。

#### 提示 - COBOL 模板：

```
i need a code template in Cobol that says "Hello World"
```

#### 输出 - COBOL 模板

```
Sure, here's a sample code template in COBOL that prints out "Hello World" to the console:

IDENTIFICATION DIVISION. PROGRAM-ID. HELLO-WORLD. PROCEDURE DIVISION. DISPLAY 'Hello World'. STOP RUN. The IDENTIFICATION DIVISION specifies the name of the program as HELLO-WORLD, while the PROCEDURE DIVISION contains the instructions to display the message and stop the program. When you run this program, it will simply display the message "Hello World" on the console.
```

这里有一个更加当前的例子，可能会有用，涉及HTML和Javascript

#### 提示 - html：

```
i need a code template for an html page with an embedded button that plays 3 beeps written in javascript 
```

#### 输出 - html

```
Certainly, here's an HTML code template with an embedded button that plays three beeps using JavaScript:

<!DOCTYPE html>
<html>
<head>
	<title>Play 3 Beeps</title>
</head>
<body>
	<button onclick="playBeeps()">Play 3 Beeps</button>

	<script> function playBeeps() { var beepSound = new Audio('beep.mp3'); beepSound.play(); setTimeout(function() { beepSound.play();
			}, 1000); setTimeout(function() { beepSound.play();
			}, 2000);
		}
	</script>
</body>
</html>

Here's what each part of the code does:

The button element creates a button that triggers the playBeeps() function when clicked. The script element contains the JavaScript code that defines the playBeeps() function. In the playBeeps() function, we first create a new Audio object that loads the beep.mp3 file. Then, we use the play() method to play the beep sound immediately, and use setTimeout to play the sound again after a delay of 1 second and 2 seconds respectively. Note that you will need to replace the beep.mp3 file with an actual audio file that contains the beep sound you want to play. Additionally, you may need to adjust the file path or change the file format depending on your requirements.
```

## 结论

虽然ChatGPT可能无法完全取代编码，但它可以通过帮助检测错误、调试、文档编写以及分析他人的代码来显著提高生产力。这些好处真的是无价的。

*"一个好的程序员是那种在穿过单行道之前总是看两边的人。" - 道格·林德*
