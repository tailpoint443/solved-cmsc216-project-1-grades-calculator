Download Link: https://assignmentchef.com/product/solved-cmsc216-project-1-grades-calculator
<br>
5/5 - (1 vote)

For this project you will write a C program that reads assignment scores and computes numeric grades and statistical information. 2 Objectives

<ul>

 <li>To practice functions and arrays.3 WarningDo not leave your computers unattended. If you don’t lock your computer, someone can execute submit on your project folder and steal all your code.</li>

</ul>

3.1 Good Faith Attempt

Remember that you need to satisfy the good faith attempt for every project in order to pass the class (see syllabus). The deadlines for good faith attempts is not the end of the semester. Make sure you check the course web page for deadline information.

3.2 Debugging Guidelines

Make sure you are familiar with the information provided at

<pre>http://www.cs.umd.edu/~nelson/classes/resources/cdebugging/</pre>

3.3 Obtaining project files

To obtain the project files, copy the folder project1 available in the 216 public directory to your 216 directory.

You need to copy the project1 folder we have provided as it has a file (.submit) that will allow you to submit your project. Notice that the project description can be found in the project descriptions directory.

4 Specifications 4.1 Input Data

Your project will read information about class assignments and compute a numeric score. The data provided consists of:

• Number of assignments• Points penalty per day late• Number of assignments to drop• Whether statistical information will be generated• Assignments information (assignment number, score, weight, days late).

The data format is:

1

<pre>   Points_Penalty_Per_Day_Late Drop_N_Lower_Value_Assignments Stats_Y/N   Number_of_Assignments(n)   Assignment Info #1   Assignment Info #2</pre>

<pre>   ...   Assignment Info #n</pre>

Each assignment info entry has the following information: assignment’s number, assignment’s score, assign- ment’s weight (percentage), days late (integer). The following is an example of the data your program will process:

<pre> 10 2 Y 4 2, 82, 40, 1 1, 91, 40, 0 4, 84, 10, 3 3, 73, 10, 3</pre>

For the above data, there is a 10 points penalty per day late, the 2 lower scores need to be dropped, statistical information will be generated (Y), and a total of four assignments are provided. For assignment number 2 the student’s score is 82, the assignment represents 40% of the student’s grade and it was submitted 1 day late.

4.2 Processing

Your program will compute the numeric score after dropping the n lowest scoring assignments and taking into account days late, penalty per day late, and the weight associated with the assignments. If statistical information is requested, the mean and standard deviation will be computed. For example, for the above data, your program is expected to generate the following output:

<pre>     Numeric Score: 81.5000     Points Penalty Per Day Late: 10     Number of Assignments Dropped: 2     Values Provided:     Assignment, Score, Weight, Days Late     1, 91, 40, 0     2, 82, 40, 1     3, 73, 10, 3     4, 84, 10, 3     Mean: 65.0000, Standard Deviation: 18.2346</pre>

Regarding the data and processing:

<ol>

 <li>Use double as your floating-type (e.g., double tmp, double numeric score).</li>

 <li>The assignment number will be a value between 1 and the maximum number of assignments. You can assume valid assignment numbers are provided.</li>

 <li>Assignments can be provided in any order; however they must be printed in order (by assignment number).</li>

 <li>An assignment score will be an integer value between 0 (inclusive) and 100 (inclusive). You can assume we will provide valid scores.</li>

</ol>

2

<ol start="5">

 <li>The weight will be an integer value between 0 (inclusive) and 100 (inclusive). You need to check the that sum of weights for all assignments add to a 100. If after reading the data the total weights do not add to a 100, your program will generate the error message ERROR: Invalid values provided and the program will terminate. The message should be printed on a line by itself.</li>

 <li>Your program should remove the n lowest valued assignments before performing any numeric score computation. We define value as an assignment’s score × the assignment’s weight. For a total of x assignments, we will provide a value of assignments to drop that is in the inclusive range (0 .. x – 1). Notice that number of days late and the penalty per day WILL NOT be used in order to decide what assignment to drop. If two assignments have the same value (score × weight) the one with the lowest assignment number will be dropped.</li>

 <li>The numeric score will be a value between 0 (inclusive) and a 100 (inclusive). For the numeric grade computation, adjust the score for an assignment based on the number of days late and the points penalty per day late. An assignment score will be set to 0 if the assignment’s score becomes less than 0 after the late penalty is applied. This adjusted score along with the assignment’s weight will allow you to compute the numeric score.</li>

 <li>If any assignment is dropped, the sum of assignment weights will, nearly always, not correspond to a 100.</li>

 <li>Either ’Y’ or ’y’ will request statistical information. Any other character will indicate that no statistical information will be generated.</li>

 <li>For the computation of the mean and standard deviation you need to apply the late penalty, but do not drop any assignments (even if there was a assignment drop request). In addition, do not use weights for the computation of mean and standard deviation.</li>

 <li>Points penalty per day late will be an integer value.</li>

</ol>

4.3 Functions Requirements

<ol>

 <li>You must have at least two other functions in addition to main.</li>

 <li>One of your functions must take at least one array as a parameter.</li>

</ol>

4.4 Other

<ol>

 <li>Use %5.4f as the format for a float.</li>

 <li>The maximum number of assignments in the input is 50.</li>

 <li>IMPORTANT: You may not use the following C constructs. If you do you will lose significant credit.

  <ol>

   <li>C structures.</li>

   <li>Global variables.</li>

   <li>Two-dimensional (2D) arrays.</li>

   <li>An array of pointers to arrays. We consider them 2D arrays.</li>

   <li>Dynamic memory allocation (e.g., malloc, calloc).</li>

  </ol></li>

 <li>To use the sqrt function or any function from the math library you need to include the file &lt;math.h&gt; and compile with the -lm option (e.g., gcc grades.c -lm). You can find additional information about the math library by using the linux man pages (“man sqrt” on grace).</li>

 <li>You must name your C file grades.c otherwise it will not compile on the submit server.</li>

 <li>You may not use the qsort function.</li>

 <li>If you decide to use the indent tool make sure you define the appropriate alias as specified in the in- dent utility info.txt file that can be found in the grace info folder.</li>

 <li>You need to use #define (e.g., instead of 50 use #define to define a symbolic constant). 3</li>

</ol>

9. A standard deviation calculator can be found at:

http://www.mathsisfun.com/data/standard-deviation-calculator.html

4.5 Compilation

Make sure your gcc alias has been set as defined in the file gcc aliases info.txt available in the info folder of the grace public account.

4.6 Execution