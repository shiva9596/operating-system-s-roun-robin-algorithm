QUESTION : 
Design a scheduler that can schedule the processes arriving system at periodical intervals. Every process is assigned with a fixed time slice t milliseconds. If it is not able to complete its execution within the assigned time quantum, then automated timer generates an interrupt. The scheduler will select the next process in the queue and dispatcher dispatches the process to processor for execution. Compute the total time for which processes were in the queue waiting for the processor. Take the input for CPU burst, arrival time and time quantum from the user.

DESCRIPTION :

The above statement defines that this is the ROUND ROBIN preemptive method.
The Algorithm focuses on Time Sharing. In this algorithm, every process gets executed in a cyclic way. A certain time slice is defined in the system which is called time quantum. Each process present in the ready queue is assigned the CPU for that time quantum, if the execution of the process is completed during that time then the process will terminate else the process will go back to the ready queue and waits for the next turn to complete the execution.


EXPLANATION :
1.	Round Robin is the preemptive process scheduling algorithm.
2.	Each process is provided a fix time to execute, it is called a quantum.
3.	Once a process is executed for a given time period, it is preempted and other process executes for a given time period.
4.	Context switching is used to save states of preempted processes.

REVISION 1: 
Assume there are 5 processes with process ID and burst time.
Process id     arrival time      burst time       
P1                   0                       6
P2                   0                       5
P3                   0                       2
P4                   0                       3
P5                   0                       7
Time quantum : 2 units.
Calculate average waiting time for processes to complete.

EXPLANATION :
First p1 process is picked from the ready queue and executes for 2 per unit time (time slice = 2). If arrival time is not available, it behaves like FCFS with time slice. – After P2 is executed for 2 per unit time, P3 is picked up from the ready queue. Since P3 burst time is 2 so it will finish the process execution at once. – Like P1 & P2 process execution, P4 and p5 will execute 2 time slices and then again it will start from P1 same in cyclic manner till the execution is complete.
Ready queue
    P1                              P1 is executed for time slice of 2 units. As P1 has not completed
                                                     It added to ready queue.
   P1    
0   	2

Ready queue
P2 p3 p4 p5 p1           p2,p3,p4,p5 arrives to ready queue and p2 gona executed like FCFS
  P1	   P2
0    2        4

Ready queue
P3 p4 p5 p1 p2           As p2 is not completed its added to ready queue and then p3 is                                  
                                       Executed.                             
   P1	     P2	    P3
0       2      4     6

Ready queue
P4 p5 p1 p2               p3 is completed so it doesn’t added in ready queue. Then p4 is 
                                       executed .
   P1	     P2	     P3	   P4
0      2       4      6      8

Ready queue
P5 p1 p2 p4           p4 is not completed it will be added to ready queue,p5 executes

  P1	  P2	 P3	   p4   	P5
0     2    4    6     8      10

Ready queue
P1 p2 p4 p5      p5 is not completed its added to ready queue then p1 executes

P1	           P2         	P3	        P4	         P5	        P1
0        2            4           6            8           10           12
Ready queue
P2 p4 p5 p1     p1 is not completed its added to ready queue then p2 executes

    P1	       P2	        P3	          P4	        P5	         P1       	P2
0        2           4            6            8           10          12          14


Ready queue
P4 p5 p1 p2        p2 is not completed its added to ready queue then p4 executes

    P1	      P2	         P3         	P4	       P5         	P1        	P2        	P4
0        2           4            6            8          10           12          14          15

Ready queue
P5 p1 p2          p4 is completed it doesn’t added to ready queue then p5 executes

    P1     	P2    	P3  	P4	    P5      	P1        	P2      	P4	         P5
0      2         4      6      8       10         12        14            15          17

Ready queue
P1 p2 p5                           p5 is not completed it added to ready queue then p1 executes

  P1	    P2     	P3      	P4     	P5       	P1    	P2    	P4     	P5    	P1
0     2        4        6        8        10      12      14     15       17      19

Ready queue
P2 p5                              p1 is completed it doesn’t added to ready queue then p1 executes

   P1	   P2 	P3	 P4 	P5	     P1	     P2      	P4    	P5	  P1  p2
0      2    4    6    8      10       12      14      15    17    19   20

Ready queue
P5             p2 is completed it not added to ready queue then p5 executes
  P1	       P2          	P3	       P4	        P5        	P1      	P2      	P4        P5        	P1      	P2     	P5
0        2          4           6          8           10        12        14         15        17         19        20       22

Ready queue
P5     p5 is not completed its gona added to ready queue then p5 executes

  P1	    P2	       P3	      P4       	P5       	P1      	P2	    P4      	P5	    P1	     P2     	P5	     P5
0     2         4         6         8         10       12       14       15       17       19       20       22       23

Process id     arrival time      burst time                      completion time               T.A.T           W.T  
P1                   0                       6                      19                         19              13
P2                   0                       5                      20                         20              15
P3                   0                       2                       6                          6                4
P4                   0                       3                      15                         15              12
P5                   0                       7                      23                          23              16
                                                                    T.A.T=turn around time
                                                                            = Completion time –arrival time
                                                                     W.T= waiting time
                                                                           =turn around time –burst time.

Average waiting time=13+15+4+12+16/5 =12 units.
Average turn around time =19+20+6+15+23/5 =16.6 units.

REVISION 2 :
Assume there are 5 processes with process ID , arrival time and burst time.
Process id     arrival time      burst time       
P1                   0                       5
P2                   1                      3
P3                   2                       1
P4                   3                       2
P5                   4                       3
Time quantum = 2 units.
Calculate Average waiting time for the given processes.


EXPLANATION :
First p1 process is picked from the ready queue and executes for 2 per unit time (time slice = 2).The  arrival time is given, it behaves like FCFS with time slice. – After P2 is executed for 2 per unit time, P3 is picked up from the ready queue. Since P3 burst time is 2 so it will finish the process execution at once. – Like P1 & P2 process execution, P4 and p5 will execute 2 time slices and then again it will start from P1 same in cyclic manner till the execution is complete.
Ready queue
P1       p1 is executed for a time slice of 2 units.

        P1
0                 2

Ready queue
P2 p3 p5 p4 p1        p2 p3 p4 p5 come to ready queue to executed then p2 is executes.

   P1 	P2
0     2    4

Ready queue
P3 p5 p4 p1 p2          p2 is not completed its added to ready queue then p3 executes

  P1	P2	P3
0   2   4     5

Ready queue
P5 p4 p1 p2        p3 is completed its not added to ready queue then p5 executes.

  P1	 P2  	 P3     	P5
0    2     4       5       7

Ready queue
P4 p1 p2 p5    p5 is not completed its added to ready queue then p4 executes.

      P1          	P2             	P3               	P5	            P4
0            2                4                5                7                 9
Ready queue
P1 p2 p5     p4 is completed its not added to ready queue then p1 executes.

      P1            	P2            	P3               	P5              	P4            	P1
0             2                4                5                7                 9               11

Ready queue
P2 p5 p1   p1 is not completed its added to ready queue then p2 executes.

   P1       	P2        	P3        	P5         	P4         	P1        	P2
0      2            4           5            7           9           11         12

Ready queue
P1 p5  p2 is completed its not added to ready queue then p1 executes.

    P1	       P2	           P3	        P5        	P4          	P1        	P2      	P1
0         2          4             5           7           9             11         12        13

Ready queue 
P5           p1 is completed its not added to ready queue then p5 executes.

    P1	      P2	         P3         	P5        	P4	       P1	         P2         	P1      	P5
 0      2           4             5           7           9           11          12          13         14

READY QUEUE:
                            P5, P1, P2, P5, P4, P1, P3, P2, P1

Process id     arrival time      burst time                   completion time                  T.A.T           W.T  
P1                   0                       5                      13                         13               8 
P2                   1                       3                      12                         11               8
P3                   2                       1                       5                          3               2
P4                   3                       2                       9                          6               4
P5                   4                       3                      14                         10               7
                                                                    T.A.T=turn around time
                                                                            = Completion time –arrival time
                                                                     W.T= waiting time
                                                                           =turn around time –burst time.

Average waiting time =8+8+2+4+7/5 = 29/5 =5.8 units
Average turn around time =13+11+3+6+10/5 = 43/5 = 8.6 units






REVISION : 3
 Assume there are 3 processes with process ID , arrival time and burst time.
Process id     arrival time      burst time       
P1                   0                      4
P2                   0                      3
P3                   0                      5
Time quantum = 2 units.
Calculate Average waiting time for the given processes.

Ghantt chart:
    P1	           P2             	P3        	P1            	P2	               P3              	P3
0            2                 4         6               8                  9                11              12

Average waiting time:
P1 =0+4 =4
P2 =2+4= 6
P3 =4+3 =7
Average waiting time =4+6+7/3 =17/3 =5.6 units

REVISION : 4
Assume there are 5 processes with process ID , arrival time and burst time.
Process id     arrival time      burst time       
P1                   0                      8
P2                   0                      2
P3                   0                      7
P4                   0                      3
P5                   0                      5
Time quantum = 3 units.
Calculate Average waiting time for the given processes.

Ghantt chart:
   P1	         P2	         P3         	P4	       P5	        P1	      P3          P5          P1	       P3
0     3    4         6   7      10  11      14  15     18  19    22 23       26  27     29 30      32  33       34
Waiting queue:
P1 p2 p3 p4 p5 p1 p3 p5 p1 p3

Completion time                   turn around time                                waiting time
 32                                              32                                      24
6                                                6                                        4
34                                              34                                       27
14                                              14                                       11
29                                              29                                       24

Average waiting time =24+4+27+11+24/5 = 18 units.

REVISION :5
Assume there are 6 processes with process ID , arrival time and burst time.
Process id     arrival time      burst time       
P1                   0                       5
P2                   1                       6
P3                   2                       3
P4                   3                       1
P5                   4                       5
P6                   6                       4
Time quantum = 4 units.
Calculate Average waiting time for the given processes.

GHANTT CHART:

    P1         	P2           	P3        	P4         	P5          	P1        	P6          	P2         	P5
0          4             8           11          12            16          17           21           23           24

Waiting queue:
P1 p2 p3 p4 p5 p1 p6 p2 p5

Completion time                         turn around time                         waiting time
17                                                     17                               12
23                                                     22                               16
11                                                      9                                6
12                                                      9                                8 
24                                                     20                               15
21                                                     15                               11

Average waiting time =12+16+6+8+15+11/6 =76/6 =12.6 units


ALGORITHM :
1.	Create an array arrival_time[], burst_time[] to keep track of arrival and bust time of processes.
2.	Create another array temp[] to store waiting times of processes temporarily in between execution.
3.	Initialize time: total = 0, counter = 0, wait time = 0, turnaround time = 0.
4.	Ask user for no of process and store it in limit.
5.	Repetitively ask user to give input for - arrival time, bust time up to limit.
6.	Ask user to enter time quantum and store it into time_quantum.
7.	Keep traversing the all processes while all processes are not done. Do following for i'th process if it is not done yet. a. If temp[i] <= time_quantum && temp[i] > 0 (i) total = total + temp[i]; (ii) temp[i] = 0; (iii) counter = 1; b. Else if temp[i] > 0 (i) temp[i] = temp[i] - time_quantum; (ii) total = total + time_quantum; c. If temp[i] == 0 && counter == 1 (i) x--; (ii) print burst_time[i], total, arrival_time[i], total - arrival_time[i] - burst_time[i]); (iii) wait_time = wait_time + total - arrival_time[i] - burst_time[i]; (iv) turnaround_time = turnaround_time + total - arrival_time[i]; (v) counter = 0; d. If i == limit – 1 (i) i = 0; e. Else if arrival_time[i + 1] <= total (i) i++; c. Else (i) i = 0;
8.	Print total waiting time - wait_time, average waiting time - wait_time/limit, average turnaround time - average_turnaround_time/limit.
Complexity :
• Complexity of initialization of variables is O(1). total = 0 counter = 0 wait_time = 0 turnaround_time = 0 • Complexity for initializing arrays with for loop is O(limit). for(i = 0; i < limit; i++) { … } • Complexity of calculating waiting and turnaround time is O(limit). for(total = 0, i = 0; x != 0;) { …. } • Complexity of implemented algorithm is O(limit).
Constraints :
1.	If we have large number of processes and a process with very less burst time. According to round robin it will have to wait for very long time if burst time of other processes is large and its turn comes late.
2.	If we have some processes running according to round robin and we have a process whose arrival time is after the completion of those processes, then that process will not execute. If we want that all the processes should execute successfully then the arrival time of other process must be less than or equal to the completion time of the running processes.
Round robin in c :
    
	#include<stdio.h>
	int main() 
	{ 
	      int i, limit, total = 0, x, counter = 0, time_quantum;
	      int wait_time = 0, turnaround_time = 0, arrival_time[10], burst_time[10], temp[10]; 
	      float average_wait_time, average_turnaround_time;
	      printf("\nEnter Total Number of Processes:\t"); 
	      scanf("%d", &limit); 
	      x = limit; 
	      for(i = 0; i < limit; i++) 
	      {
	            printf("\nEnter Details of Process[%d]\n", i + 1);
	            printf("Arrival Time:\t");
	            scanf("%d", &arrival_time[i]);
	            printf("Burst Time:\t");
	            scanf("%d", &burst_time[i]); 
	            temp[i] = burst_time[i];
	      } 
	      printf("\nEnter Time Quantum:\t"); 
	      scanf("%d", &time_quantum); 
	      printf("\nProcess ID\t\tBurst Time\t Turnaround Time\t Waiting Time\n");
	      for(total = 0, i = 0; x != 0;) 
	      { 
	            if(temp[i] <= time_quantum && temp[i] > 0) 
	            { 
	                  total = total + temp[i]; 
	                  temp[i] = 0; 
	                  counter = 1; 
	            } 
	            else if(temp[i] > 0) 
	            { 
	                  temp[i] = temp[i] - time_quantum; 
	                  total = total + time_quantum; 
	            } 
	            if(temp[i] == 0 && counter == 1) 
	            { 
	                  x--; 
	                  printf("\nProcess[%d]\t\t%d\t\t %d\t\t\t %d", i + 1, burst_time[i], total - arrival_time[i], total - arrival_time[i] - burst_time[i]);
	                  wait_time = wait_time + total - arrival_time[i] - burst_time[i]; 
	                  turnaround_time = turnaround_time + total - arrival_time[i]; 
	                  counter = 0; 
	            } 
	       
	      } 
	      average_wait_time = wait_time * 1.0 / limit;
	      average_turnaround_time = turnaround_time * 1.0 / limit;
	      printf("\n\nTotal Waiting Time:\t%d", wait_time); 
	      printf("\n\nAverage Waiting Time:\t%f", average_wait_time); 
	      printf("\nAvg Turnaround Time:\t%f\n", average_turnaround_time); 
	      return 0; 
	}
EXPLANATION OF CODE :
At first used the header name stdio.h and then initialised the variables like int , float , character. And then asking the user that how many processes and printing the values
And therafter by using loop condition that number of process that can taken is as user given , Asking the user to give Arrival time , burst time until the limit of number of processes. And also asking time quantum printing the values in the form of tabular form using counter =1 start from static node and appling the formula logic of turn around time and waiting time and printing the total values that obtained by given values , printing values in tabular form . 
TEST CASES  :
1.	 If we select same arrival time for 2 processes. Expected Result: The process having less burst time should have less turnaround time. Actual Result:
Test case passed successfully.
2.	If p1 process arrives at 2 and burst time=4 but p2 and p3 process arrives at 6. Expected Result: Here only process p1 will execute because p2 and p3 are unable to arrive within the completion of process p1. Actual Result:
Test case passed successfully.
3.	Now if process p1 arrives at 0 and two other processes p2 and p3 arrives within the completion of process p1. Expected Result: All 3 process will execute.



TEST CASES  :
1.	 If we select same arrival time for 2 processes. Expected Result: The process having less burst time should have less turnaround time. Actual Result:
Test case passed successfully.
2.	If p1 process arrives at 2 and burst time=4 but p2 and p3 process arrives at 6. Expected Result: Here only process p1 will execute because p2 and p3 are unable to arrive within the completion of process p1. Actual Result:
Test case passed successfully.
3.	Now if process p1 arrives at 0 and two other processes p2 and p3 arrives within the completion of process p1. Expected Result: All 3 process will execute.



Conclusion :      
We have  shown  that the  round-robin tournament scheduling  can  be used  to generate  the 
test suite for software testing. The proposed method based on  the  strategy  that  a  value  must be 
contained in two or more test cases, produce the 1-wise coverage test suite with the less number 
of test cases than that of the base-choice combination method. In practice, if we know in advance 
that  there is  no  relation  between  parameters  so that  the pair-wise  testing  is  unnecessary,  then 
using the proposed test suite will save time and energy greatly
We have  shown  that the  round-robin tournament scheduling  can  be used  to generate  the 
test suite for software testing. The proposed method based on  the  strategy  that  a  value  must be 
contained in two or more test cases, produce the 1-wise coverage test suite with the less number 
of test cases than that of the base-choice combination method. In practice, if we know in advance 
that  there is  no  relation  between  parameters  so that  the pair-wise  testing  is  unnecessary,  then 
using the proposed test suite will save time and energy greatly
We have  shown  that the  round-robin tournament scheduling  can  be used  to generate  the 
test suite for software testing. The proposed method based on  the  strategy  that  a  value  must be 
contained in two or more test cases, produce the 1-wise coverage test suite with the less number 
of test cases than that of the base-choice combination method. In practice, if we know in advance 
that  there is  no  relation  between  parameters  so that  the pair-wise  testing  is  unnecessary,  then 
using the proposed test suite will save time and energy greatly
 The  round-robin scheduling  can  be used  to generate  the test suite for software testing.Hence from the test cases we conclude that if we want that all the processes should execute successfully then the arrival time of other process must be less than or equal to the completion time of the running processes.






                                                                                                                      Done by rakshith kumar
                                                                                                                                   Id:11808453
