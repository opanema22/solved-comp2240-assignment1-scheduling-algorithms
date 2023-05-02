Download Link: https://assignmentchef.com/product/solved-comp2240-assignment1-scheduling-algorithms
<br>
Write a program that simulates <strong>First Come First Serve</strong> <strong>(FCFS)</strong>, <strong>Shortest Process Next</strong> <strong>(SPN)</strong>, <strong>Preemptive Priority</strong> <strong>(PP)</strong> and <strong>Priority Round Robin</strong> <strong>(PRR)</strong> scheduling algorithms. For each algorithm, the program should <strong>list the order and time</strong> of the jobs being loaded in the CPU and <strong>compute waiting time</strong> and <strong>turnaround time</strong> for every job as well as the <strong>average waiting time</strong> and <strong>average turnaround time</strong>.

The average values should be consolidated in a table for easy comparison (<em>check the sample outputs</em>).

Two sample input data sets and the corresponding outputs have been supplied. Additional datasets will be used to test your program. The format of the input data will be the same as in the supplied sample files.

Each input data set contains the following information (<em>check the sample input files for exact format</em>):

<ol>

 <li>Time for running the dispatcher (DISP) which can be zero or more</li>

 <li>For each process: process id (ID) , arrival time (Arrive), service time (ExecSize) and process priority</li>

</ol>

(Priority)

<ol>

 <li>Each process will have a priority from {0, 1, 2, 3, 4, 5} where 0 is the highest priority and 5 is the lowest priority.</li>

 <li>It can be assumed that process P_i will always arrive before or at the same time of process</li>

</ol>

P_(i+1)

<strong>Dispatcher:</strong> It is assumed that the dispatcher runs to select the next process to run. The dispatcher should behave as follows:

<ul>

 <li>The time to run the dispatcher (context switching time) is fixed and taken as input (DISP) from the input file. No other time is wasted in switching between processes other than this.</li>

 <li>If there is only one process running in the processor and no other process is waiting in the ready queue then there is no need to switch the process and the dispatcher will NOT run. For example, in PRR scheduling if process P1 is running in the CPU and no other process is waiting in the ready queue then P1 will continue after its time quantum expires – no need to interrupt P1 to send it to ready queue after its time quantum expires then run the dispatcher to reload P1 from the ready queue.</li>

 <li>If the dispatcher starts at <strong><em>t<sub>1</sub></em></strong> and finishes at <strong><em>t<sub>2</sub></em></strong> (<em>e. time to run the dispatcher is</em> <strong><em>t<sub>2</sub>-t<sub>1</sub></em></strong>) then in that run it will choose from the processes that have arrived at or before <strong><em>t<sub>1</sub></em></strong>. It will not consider any process that arrives after <strong><em>t<sub>1</sub></em></strong> for dispatching in that run.</li>

 <li>If a process P1 is interrupted at <strong><em>t<sub>1</sub></em></strong> and another process P2 arrives at the same time <strong><em>t<sub>1</sub></em></strong> then the newly arrived process P2 is added in the ready queue first and the interrupted process P1 is added after that.</li>

 <li>If two processes Px and Py have all other properties same (<em>g. arrival time, priority etc.</em>) then the tie between them is broken using their ID i.e. Px will be chosen before Py if x&lt;y.</li>

</ul>

Some details about the scheduling algorithms are as follows:

<strong>FCFS:</strong> Standard FCFS scheduling algorithm. Process priority is ignored in scheduling.

<strong>SPN:</strong> Standard SPN scheduling algorithm. Process priority is ignored in scheduling.

<strong>PP:</strong> Standard preemptive priority scheduling algorithm.

<strong>PRR:</strong> This is a variant of the standard Round Robin (RR) algorithm. Processes are divided into two priority classes <em>Higher Priority Class (HPC)</em>: processes with priority 0, 1 or 2 and <em>Lower Priority Class (LPC)</em>: processes with priority 3, 4 or 5. PRR algorithm is exactly same as the standard RR algorithm except each HPC process receives a <em>time quantum of 4 units</em> and each LPC process receives a <em>time quantum of 2 units</em>.

<strong>COMP6240 Students:</strong>

In addition to the above simulations, you are to implement a RR scheduling simulation for a <strong>dual processor system</strong>. Assume that two processors share the same ready queue and the <strong>time quantum</strong> for processor 1 is <strong>2 milliseconds</strong> and for processor 2 is <strong>3 milliseconds</strong>, and that the system starts loading processes from processor 1. For dispatching a

process, the dispatcher will run on the processor that is idle. If both processors are idle at the same time and there are jobs in the ready queue then at first the dispatcher will run on processor 1 and then it will run on processor 2 to dispatch processes for them respectively. Output the same data as required for the other simulations. Additionally you will need to specify in which processor a job is assigned at a specific time [i.e. instead of  T1: p1(0) use            P1-T1: p1(0) to clarify that the <em>process 1</em> (p1) is running in <em>processor 1</em> (P1) starting at <em>time 1</em> (T1)].

<strong>Programming Language: </strong>

The programming language is Java, versioned as per the University Lab Environment (<strong>currently a subversion of Java 1.8</strong>). You may only use standard Java libraries as part of your submission.

<strong>User Interface: </strong>

The output should be printed to the console, and strictly following the output samples given in the assignment package. While there are no marks allocated specifically for the Output Format, there will be a deduction when the result format varies from those provided.

<strong>Input and Output: </strong>

Your program will accept data from an input file of name specified as a command line argument. The sample files datafile1.txt and datafile2.txt (containing the set1 and set2 data) are provided to demonstrate the required input file format.

Your submission will be tested with the above data and will also be tested with other input files.

Your program should output to standard output (<em>this means output to the Console</em>). Output should be strictly in the order FCFS, SPN, PP, PRR, Summary.

The sample files datafile1_output.txt and datafile2_output.txt (containing output for datafile1.txt and datafile2.txt respectively) are provided to demonstrate the required output (and input) format which <strong><u>must be strictly maintained</u></strong><u>.<strong> If output is not generated in the required format then your program</strong></u><strong> <u>will be considered incorrect.</u></strong>




Two Gantt’s charts are provided to explain the corresponding behaviour of different algorithms and the dispatcher for the two sample data files.

<strong>Deliverable: </strong>

<ol>

 <li>Your submission will contain your program source code, documentation (below) and a txt (containing any special instructions required to compile and run the source code) in the root of the submission. These files will be zipped and submitted in an archive named <strong>c9876543.zip</strong> (where <strong>c9876543</strong> is your student number) – do not submit a .rar, or a .7z, or etc.</li>

 <li>Your main class should be <strong>java</strong> you program will compile with the command line <strong>javac A1.java</strong></li>

</ol>

and your program will be executed by running <strong>java A1 input.txt</strong>.

<ol start="3">

 <li>Brief <strong>1 page</strong> (<em>A4</em>) report, reviewing the results from your program and any interesting observations. Specifically, write a note about the relative performance of the algorithms based on your implemented versions of the algorithms.</li>

 <li>Completed Assignment Coversheet.</li>

</ol>

<strong>Mark Distribution: </strong>

Mark distribution can be found in the assignment feedback document (Assign1Feedback2240.pdf and Assign1Feedback6240.pdf).