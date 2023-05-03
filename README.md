Download Link: https://assignmentchef.com/product/solved-cs3423-systems-programming-assignment-3
<br>
: awk




<h1>Part A</h1>

For this part of the assignment, you will create a <strong>single command </strong>which will take the contents of a passwd file (usually found in <strong><sub>/etc/passwd</sub></strong>) and print it in sorted order by the user’s last name (that is, their surname, not their username). Normally, you could solve this with the following options on <strong>sort</strong>: <strong>$ sort -t: -k6 /path/to/passwd</strong>

You, however, must solve this problem with the utilities covered in class so far. You may (and should) use <strong><sub>sort</sub></strong>, but you may not use any of its options (e.g., -k, -t, etc).

<h1>Example</h1>

<strong>Input:</strong>

<ul>

 <li>lkj293:x:1539:1543:Albert Einstein:/home/einstein:/bin/bash</li>

 <li>kkr590:x:1540:1544:Elvis Presley:/home/presley:/bin/bash</li>

 <li>nwk409:x:1541:1545:George Washington:/home/washington:/bin/bash</li>

 <li>yaa265:x:1542:1546:Bruce Banner:/home/banner:/bin/bash</li>

 <li>yhn211:x:1543:1547:George Harrison:/home/harrison:/bin/bash</li>

 <li>lfa806:x:1544:1548:Jane Austen:/home/austen:/bin/bash</li>

 <li>ilo709:x:1545:1549:Walt Disney:/home/disney:/bin/bash</li>

 <li>rfd576:x:1546:1550:Buzz Aldrin:/home/aldrin:/bin/bash</li>

 <li>lko889:x:1547:1551:Marie Curie:/home/curie:/bin/bash</li>

 <li>cfq219:x:1548:1552:J.R.R. Tolkien:/home/tolkien:/bin/bash</li>

 <li>ncz856:x:1549:1553:Christopher Columbus:/home/columbus:/bin/bash</li>

 <li>pql747:x:1550:1554:Julius Caesar:/home/caesar:/bin/bash</li>

</ul>

<strong>Output:</strong>

<ul>

 <li>rfd576:x:1546:1550:Buzz Aldrin:/home/aldrin:/bin/bash</li>

 <li>lfa806:x:1544:1548:Jane Austen:/home/austen:/bin/bash</li>

 <li>yaa265:x:1542:1546:Bruce Banner:/home/banner:/bin/bash</li>

 <li>pql747:x:1550:1554:Julius Caesar:/home/caesar:/bin/bash</li>

 <li>ncz856:x:1549:1553:Christopher Columbus:/home/columbus:/bin/bash</li>

 <li>lko889:x:1547:1551:Marie Curie:/home/curie:/bin/bash</li>

 <li>ilo709:x:1545:1549:Walt Disney:/home/disney:/bin/bash</li>

 <li>lkj293:x:1539:1543:Albert Einstein:/home/einstein:/bin/bash</li>

 <li>yhn211:x:1543:1547:George Harrison:/home/harrison:/bin/bash</li>

 <li>kkr590:x:1540:1544:Elvis Presley:/home/presley:/bin/bash</li>

 <li>cfq219:x:1548:1552:J.R.R. Tolkien:/home/tolkien:/bin/bash</li>

 <li>nwk409:x:1541:1545:George Washington:/home/washington:/bin/bash</li>

</ul>

<h1>Script Execution (Part A)</h1>

Since the fox machines do not have useful <strong><sub>/etc/passwd </sub></strong>files (no first and last names), you will use the one provided with this assignment. Your submission will include a bash file (<strong><sub>assign3A.sh</sub></strong>) with <em>exactly one line </em>in it (you do not need a shebang) and should take the path to the passwd file as the first argument. Do not include an awk file or any other files besides <strong><sub>assign3A.sh</sub></strong>.

<strong>$ assign3A.sh /path/to/passwd</strong>

<h1>Part B</h1>

For this part of the assignment, you will only use the utilities covered in class so far (primarily awk) to create a program for printing user process information. Do not use Python or any programs/utilities not covered in class.

Your program should take the output from <strong><sub>ps -ef </sub></strong>and print the following for each user <strong>having a username matching the abc123 format</strong>:

<ul>

 <li>Username</li>

 <li>List of commands</li>

</ul>

After listing statistics for each user, the program should print the following information for all users having a username matching the abc123 format:

<ul>

 <li>Line with earliest start time</li>

 <li>Line with latest start time</li>

</ul>

<strong>Do not </strong>use sed, Python, or any other languages/utilities not covered in class.

<h1>Example</h1>

The example below is an excerpt from the <strong><sub>ps -ef </sub></strong>command which your program should be able to take as input. Note that if a process began execution on a previous calendar day, its <sub>STIME </sub>value will not be in the usual “hours and minutes” format, but rather in “month and day” format. This should be accounted for properly, and thus a simple text/numerical comparison will not suffice.

<strong>Input:</strong>

<table width="605">

 <tbody>

  <tr>

   <td width="85">UID</td>

   <td width="243">PID PPID C STIME TTY</td>

   <td colspan="2" width="277">TIME CMD</td>

  </tr>

  <tr>

   <td width="85">adz110</td>

   <td width="243">5344 5334 0 08:47 pts/2</td>

   <td width="75">00:00:00</td>

   <td width="202">bash</td>

  </tr>

  <tr>

   <td width="85">dmq292</td>

   <td width="243">6908 6854 0 Jun04 pts/1</td>

   <td width="75">00:00:00</td>

   <td width="202">bash</td>

  </tr>

  <tr>

   <td width="85">adz110</td>

   <td width="243">7227 7150 0 Jul11 pts/9</td>

   <td width="75">00:00:00</td>

   <td width="202">who</td>

  </tr>

  <tr>

   <td width="85">erg474</td>

   <td width="243">7466 7461 0 08:54 pts/10</td>

   <td width="75">00:00:00</td>

   <td width="202">ls</td>

  </tr>

  <tr>

   <td width="85">dmq292</td>

   <td width="243">7966 7960 0 Jun04 pts/13</td>

   <td width="75">00:00:00</td>

   <td width="202">assign1.sh if of</td>

  </tr>

  <tr>

   <td width="85">xle135</td>

   <td width="243">8983 8636 0 08:59 pts/15</td>

   <td width="75">00:00:00</td>

   <td width="202">ssh ctf.cs.utsarr.net</td>

  </tr>

  <tr>

   <td width="85">zeh458</td>

   <td width="243">9057 1980 0 08:59 pts/7</td>

   <td width="75">00:00:00</td>

   <td width="202">vim prog.c</td>

  </tr>

  <tr>

   <td width="85">rslavin</td>

   <td width="243">9150 9139 0 08:59 pts/16</td>

   <td colspan="2" width="277">00:00:00 ps -af</td>

  </tr>

  <tr>

   <td width="85">xle135</td>

   <td width="243">8636 8628 0 08:58 pts/15</td>

   <td colspan="2" width="277">00:00:00 bash</td>

  </tr>

 </tbody>

</table>

1

2

3

4

5

6

7

8

9

10

<strong>Output:</strong>

<table width="605">

 <tbody>

  <tr>

   <td width="328">User: adz110bash whoUser: dmq292bash assign1.sh if ofUser: erg474lsUser: xle135bashssh ctf.cs.utsarr.netUser: zeh458vim prog.cEarliest Start Time :dmq292                             6908 6854 0 Jun04 pts/1</td>

   <td width="277">00:00:00 bash</td>

  </tr>

  <tr>

   <td width="328">Latest Start Time :xle135                                 8983 8636 0 08:59 pts/15</td>

   <td width="277">00:00:00 ssh ctf.cs.utsarr.net</td>

  </tr>

 </tbody>

</table>

1

2

3

4

5

6

7

8

9

10

11

12

13

14

15

16

17

18

19

Also, if there is a tie for earliest or latest start times, take the one with the UID that comes first alphabetically.

<strong>Hint: </strong>Consider using <strong><sub>sort </sub></strong>to help with grouping.

<h1>Script Execution (Part B)</h1>

Your program should each be invoked through a single bash file (see below) with input taken from stdin. The resulting output should be printed directly to stdout.

<strong>$ assign3B.sh &lt; ps.in</strong>

or

<strong>$ ps -ef | assign3B.sh</strong>

<h1>Assignment Data</h1>

Sample input files can be found in:

<strong>/usr/local/courses/ssilvestro/cs3423/Fall19/assign3</strong>.

<h1>Script Files</h1>

Your submission should consist of multiple files:

<ul>

 <li><strong><sub>sh </sub></strong>– a bash script with a single line of code (i.e., one command) for part A</li>

 <li><strong><sub>sh </sub></strong>– a bash script to invoke for part B.</li>

 <li><strong>awk </strong>– the awk program used in <strong>assign3B.awk</strong></li>

</ul>

<h1>Verifying Your Programs</h1>

<strong>Part A </strong>can be tested with the sample input provided with <strong><sub>passwd.in</sub></strong>.

<strong>Part B </strong>can be tested with the sample input provided with <strong><sub>ps.in</sub></strong>. Your program should also work with arbitrary input from the <strong><sub>ps -ef </sub></strong>command.


