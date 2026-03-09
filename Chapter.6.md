# Problem 1
## Step-1

2481-5-2E SA: 8683

SR: 4578

________________________________________________________________________

Given that there are _n_ processes to be scheduled on one processor, and the first schedule can be done for any of the _n_ processes, the total numbers of possible schedules in terms of ‘n’ are **factorial of n** => **n! (** n! = n×n –1×n–2×...×2×1).

For example, for 1 process, there is only one possible ordering: (1), for 2 processes, there are 2 possible orderings: (1, 2), (2, 1). For 3 processes, there are 6 possible orderings: (1, 2, 3), (1, 3, 2), (2, 1, 3), (2, 3, 1), (3, 1, 2), (3, 2, 1). For 4 processes, there are 24 possible orderings. So, for _n_ processes, there are _n_! possible orderings.


---

# Problem 2
## Step-1

**Scheduling**

The difference between preemptive and non-preemptive scheduling is explained in the table below:

**S. No** |  **Preemptive Scheduling** |  **Non-Preemptive Scheduling**  
---|---|---  
1. |  It interrupts a process in the middle of its execution. |  Once a process enters the running state, it is **not** allowed to be **interrupted** till it has completed its service time.  
2. |  It **takes the CPU away** from the process being executed and allocates it to another process with a higher priority. |  It makes sure that the process **keeps hold of the CPU** until it has completed its current CPU burst, thus completing its execution.  
3. |  It is **complex** to implement. |  It is **easier** to implement.  
4. |  **High overhead** it produced due to constant switching. |  **Lower overhead** due to simple implementation.  
5. |  The process switches from **running state** to **ready state** and then **waiting state** to **ready** **state**. |  The process switches from **running state** to **waiting state** and then the process terminates.  
6. |  It is **costlier** to implement due to being complex. |  It is **cheaper** to implement due to being simple.


---

# Problem 3
## Step-1

2481-5-17E SA: 8683

SR: 4578

________________________________________________________________________

a) 

Given data:

_Process_ _Arrival Time_ _Burst Time_

P1 0.0 8

P2 0.4 4

P3 1.0 1

## Step-2

If the processes arrive in the order p1, p2, p3, and are served in FCFS order, the result shown in Gantt chart, which is a bar chart that including start and finish times of each of the participating processes:

P1 |  P2 |  P3  
---|---|---  
  
0 8 12 13

**The Formula’s are:**

Turnaround time(Pi) = Completion Time(Pi) – Arrival Time(Pi) n Average Turnaround time = 1/n ∑ (Ci – Ai) i=1 where Ci is Completion Time(Pi) and Ai is Arrival Time (Pi)  
---  
  
Average Turnaround time = 1/3[(8-0) + (12-0.4) + (13-1) ]

= 1/3[8 + 11.6 + 12]

= 1/3[31.6]

= 31.6/3

= 10.53

Therefore, the Average Turnaround time with FCFS algorithm =10.53

## Step-3

b)

**** Using SJF scheduling, we would schedule the processes according to the following Gantt chart:

P1 |  P3 |  P2  
---|---|---  
  
0 8 9 13

Average Turnaround time = 1/3[(8-0) + (13-0.4) + (9-1)]

= 1/3[8 + 12.6 + 8]

= 1/3[28.6]

= 28.6/3

= 9.53

Therefore, the Average Turnaround time with SJF algorithm=9.53

## Step-4

c)

Using future –knowledge scheduling algorithm, we would schedule the processes according to the following Gantt chart:

|  P3 |  P2 |  P1  
---|---|---|---  
  
0 1 2 6 14

Average Turnaround time = 1/3[(14-0) + (6-0.4) + (2-1) ]

= 1/3[14 + 5.6 + 1]

= 1/3[20.6]

= 20.6/3

= 6.87

Therefore, the Average Turnaround time with future-knowledge algorithm = 6.87


---

# Problem 4
## Step-1

2481-5-4E SA: 8683

SR: 4578

________________________________________________________________________

The advantage of having different time-quantum sizes at different levels of a multilevel queuing system is processes that need more frequent servicing for instance, interactive processes such as editors, can be in a queue with a small time quantum. Processes with no need for frequent servicing can be in a queue with a larger time quantum, requiring fewer context switches to complete the processing, making more efficient use of the computer.


---

# Problem 5
## Step-1

**CPU Scheduling Algorithms**

a. The relationship between priority and SJF or Shortest Job First is that the shortest job has the highest priority and is served first.

## Step-2

b. The relationship shared between Multilevel Feedback Queues and FCFS or First Come First Serve is that the lowest level of Multilevel Feedback Queues is First Come First Serve.

## Step-3

c. The relationship between priority and FCFS or First Come First Serve is that First Come First Serve assigns the highest priority to the job that has been in existence the longest time, thus serving the job that came first before the others.

## Step-4

d. There is no relationship between the two scheduling algorithms RR or Round Robin and SJF or Shortest Job First. RR is a preemptive scheduling algorithm whereas SJF is a non-preemptive scheduling algorithm.


---

# Problem 6
## Step-1

2481-5-10E SA: 8683

SR: 4578

________________________________________________________________________

The I/O-bound processes would spend more time waiting for I/O than using the processor. So, they usually have used less CPU time in the recent past than other process. As soon as they are done with an I/O burst, they will get to execute on the processor. So this algorithm will favor I/O bound programs.

CPU-bound programs would spend more time on executing programs than I/O. However, since the algorithm takes into account only recent history, the CPU bound processes will not starve permanently. If a process has been prevented from using the processor for some time, it becomes one of the processes that have the least CPU time(=0) in the recent past and eventually it will get a chance to use CPU.


---

# Problem 7
## Step-1

**Scheduling**

The difference between **Process Contention Scope** or **PCS** scheduling and **System Contention Scope** or **SCS** scheduling is explained in the table given below:

**S. No** |  **PCS Scheduling** |  **SCS Scheduling**  
---|---|---  
1. |  PCS scheduling is performed**within the process**. That is local to the process. |  SCS scheduling is carried out**on the operating system** with kernel threads.  
2. |  PCS involves the thread library scheduling threads onto available Light Weight Processes. |  In SCS scheduling, the system scheduler scheduling kernel threads to operate on single or multiple CPUs.  
3. |  On systems implementing **many-to-one** and **many-to-many** threads, PCS occurs, as competition occurs between threads that are part of the same process. |  Systems employing **one-to-one** threads use only SCS.  
4. |  In Pthread scheduling, PTHREAD_SCOPE_PROCESS schedules threads by using PCS Scheduling, by scheduling the user threads onto attainable LWPs, using the many-to-many model. |  In Pthread scheduling, PTHREAD_SCOPE_SYSTEM schedules threads by using SCS Scheduling, by connecting user threads to specific LWPs, effectively employing a one-to-one model.


---

# Problem 8
## Step-1

**Threads**

**Y** **es** it is**important** to **bind** a **real-time** **thread** to a light weight process **(LWP)**. By doing so, there will not be any latency while waiting for an accessible light weight process and the real-time user thread can be scheduled rapidly. If a real-time thread is not bound to an LWP, then the user thread may have to fight for an available LWP before being scheduled.


---

# Problem 9
## Step-1

Consider the data for the three processes and the recent CPU usage are as follows: 

**S. No** |  **process** |  **Recent CPU usage**  
---|---|---  
1 |  P1 |  40  
2 |  P2 |  18  
3 |  P3 |  10  
  
Formulae to compute priority is as follows: 

![](https://media.cheggcdn.com/study/bf1/bf1f4265-6946-4b17-b7eb-87be38d0074d/13258-6-9PE-i1.png)

## Step-2

Compute the priorities for each process as follows:

• For process P1, substitute the recent CPU usage as 40 and base is 60:

![](https://media.cheggcdn.com/study/900/90021d92-1b05-40ee-8288-f8c34a6e4f72/13258-6-9PE-i2.png)

• For process P2, substitute the recent CPU usage as 18 and base is 60:

![](https://media.cheggcdn.com/study/6b4/6b4270a5-3efc-406d-a9ff-8db194045383/13258-6-9PE-i3.png)

• For process P3, substitute the recent CPU usage as 10 and base is 60:

![](https://media.cheggcdn.com/study/a2c/a2c6476e-9405-4680-941b-c593caad49bd/13258-6-9PE-i4.png)

## Step-3

From the above data the priorities for the three processes P1, P2, and P3 are 80, 69 and 65 respectively.

Here process P1 has the highest priority, P2 is the next priority and P3 has the lowest priority.

In traditional Unix scheduler the process priority is dynamic. The priorities are raised or lowered depends on the CPU interval time to execute a process by adjusting the priorities dynamically. 

Hence, from the above information the first process is ready for execution which has highest priority, but the CPU time is 40(higher compared to other process). So, scheduler cannot wait longer time to wait for the first process execution, So, the priorities are lowered.


---

# Problem 10
## Step-1

**Importance of distinguish I/O-bound and CPU-bound programs**

The scheduler need to distinguish I/O (Input/Output) – bound programs from CPU (Central Processing Unit) – bound programs for efficient use of computer resources. The scheduler efficiency depends on the optimum utilization of CPU. This can be achieved by observing the properties and distinguishing the programs.

I/O-bound programs utilize small amount of CPU resources. They have the property of performing small amount of computations before performing IO. This property makes I/O-bound programs not to use their entire CPU quantum.

CPU-bound programs utilize large amount of CPU resources. They have the property of performing computations without performing any blocking IO operations. This property makes CPU-bound programs to utilize their entire CPU quantum.

Based on these properties of I/O-bound and CPU-bound programs, scheduler should distinguish and give priorities. **Scheduler should give high priority to I/O-bound programs.** It should allow I/O-bound programs to execute before the CPU-bound programs. This scheduling will help in better utilization of computer resources. 


---

# Problem 11
## Step-1

**CPU utilization and response time:**

• Generally, CPU utilization should be maximized and response time should be minimized.

• CPU utilization can be maximized by minimizing the time spent in context switching, as the CPU is idle during context switching. 

• The time taken from the submission of request to time the first response is produced is called the response time. 

• When context switching is done rarely, then it would indeed result in decrease in the response time.

## Step-2

**b.**

**Average turnaround time and maximum waiting time:**

• Generally, average turnaround time and average waiting time should be minimized.

• The interval from the time of submission of a process to the time of completion of a process is the turnaround time. 

• Turnaround time is the time spent by a process waiting to get into memory, waiting in the ready queue, executing on CPU, and doing I/O. 

• Waiting time is the time spent by a process waiting in the ready queue.

• The average turnaround time can be minimized by executing the jobs with shortest CPU bursts. 

• If the jobs with shortest CPU bursts are executed first, then it will indeed increase the waiting time of the jobs with large CPU bursts and thus it will maximize the waiting time.

## Step-3

**c.**

**I/O device utilization and CPU utilization:**

• Jobs can be categorized into CPU bound jobs and I/O bound jobs.

• I/O bound jobs spend most of the time using I/O devices and spend less time doing computation using CPU.

• CPU bound jobs spend most of the time doing computation using CPU and spend less time using I/O devices.

• CPU utilization can be maximized by executing CPU bound jobs that have large CPU bursts.

• I/O device utilization can be maximized by executing I/O bound jobs. As soon as the I/O device is free, it can be allocated to an I/O bound job.


---

# Problem 12
## Step-1

Lottery ticket are based on the probabilistic scheduling algorithm in which each processor are provided with some number of lottery tickets and scheduler make decision of picking next process by drawing random ticket.

## Step-2

Since every process are assigned a lottery ticket so if higher-priority processes are assigned more tickets, than the BTV scheduler can assure that threads which are higher priority gain more consideration from the CPU than threads that have lower priority. The reason behind is that the process which have more tickets has higher probability of getting the CPU.


---

# Problem 13
## Step-1

There are two ways for maintaining a queue of processes for a processor:

• Processing core having its own run queue

• All processing core sharing single run queue

## Step-2

**Processing core having its own run queue:** In this method each CPU works on its own local run queue. A processor can takes the process directly from queue.

**Advantages:**

• The processes present on the run queue are evenly distributed across the processor maintaining that run queue. This is known as load balancing.

• There is no interference or conflict even if two or more processors are making use of a scheduler simultaneously. 

• At the time of making decision for a processing core, scheduler only requires to look at its local run queue.

**Disadvantages:**

• Extra required for maintaining different queue for different processor.

• Each processor has its own queue so when some processor’s queue get completely empty then that processor get idle where as it might be possible that other processors are busy.

## Step-3

**All processing core sharing single run queue:** In this method there is only one run queue which is shared by all CPU. Whenever any process assign a processor then process is taken from shared queue.

**Advantages** **:**

• This method leads to better utilization of processor.

• Any CPU that is idle can extract a runnable process from the common run queue and executes it.

• No extra work is required for maintaining different queue for different processor.

**Disadvantages:**

• There is load balancing problem in shared queue method.

• When there are different run queues, this can even lead to deadlock state if not protected with any locking scheme.


---

# Problem 14
## Step-1

The formula to predict the length of the next CPU burst is as follows: 

![](https://media.cheggcdn.com/study/0e3/0e38a6d1-911d-4201-8edb-6cf14cb06b0a/13258-6-14E-i1.png)

a.

Given ![](https://media.cheggcdn.com/study/7cd/7cd3050d-22b2-44d1-b4c8-794e1a015f53/13258-6-14E-i2.png)and ![](https://media.cheggcdn.com/study/28f/28f6fb2b-0219-40e3-b9a0-825d7277246e/13258-6-14E-i3.png).

Substitute ![](https://media.cheggcdn.com/study/d5e/d5e53d77-7691-48da-9a2b-9b96a6a63198/13258-6-14E-i4.png) in equation (1).

![](https://media.cheggcdn.com/study/a6d/a6d0a742-3a00-4349-9045-19cc85567762/13258-6-14E-i5.png)

So, when ![](https://media.cheggcdn.com/study/6cd/6cd5ed4c-7cd6-4224-8083-5bedb45b008b/13258-6-14E-i6.png)and ![](https://media.cheggcdn.com/study/96b/96b869c1-02f9-4152-85e6-c9fff053f844/13258-6-14E-i7.png), the prediction for the next CPU burst will be 100 ms.

The recent history has no effect (current conditions are assumed to be transient).

## Step-2

b.

Given ![](https://media.cheggcdn.com/study/d99/d9955e21-3a4d-444d-b990-556a66804284/13258-6-14E-i8.png) and ![](https://media.cheggcdn.com/study/b92/b9275e78-d583-4301-b70e-61362842eeb9/13258-6-14E-i9.png).

Substitute ![](https://media.cheggcdn.com/study/28e/28ed569d-065b-4bde-b666-f7cb1b01f83d/13258-6-14E-i10.png) in equation (1).

![](https://media.cheggcdn.com/study/66c/66c9ceba-77cc-497d-aeae-29a3babdac5f/13258-6-14E-i11.png)

So, when ![](https://media.cheggcdn.com/study/d76/d76bca55-99ad-4c54-aebf-12786959196c/13258-6-14E-i12.png) and ![](https://media.cheggcdn.com/study/eb5/eb5fa228-b1ea-4812-8d2f-9c0a58c0072b/13258-6-14E-i13.png), the prediction for the next CPU burst depends more on the most recent behavior of the process and less on the past history of the process.


---

# Problem 15
## Step-1

A **CPU bound** process is one which has more CPU bound operations and an **I/O bound** process is one which has more of I/O bound operations. 

• In the given scheduling algorithm, each process has initial 50 milliseconds of time quantum and a priority.

• So, if a process utilizes all of its time quantum, then 10 milliseconds more are assigned to it and its priority is also increased. This type of process is CPU bound process.

• On the other hand, when a process blocks for I/O before utilizing its full-time quantum, then its time quantum is reduced by 5 milliseconds but the priority remains same. This type of process is I/O bound process.

• It can be induced that after completion of each round, a CPU bound process gets more time quantum for execution and its priority is also increased.

## Step-2

**Hence, a regressive round-robin scheduler favors CPU-bound processes.**


---

# Problem 16
## Step-1

**Turnaround time** is the total time taken by process from submission to its completion.

**Waiting time** is the time spent by process in ready queue for getting the processor.

The burst time and priority of each processor is given below as:

process |  burst time |  Priority  
---|---|---  
P1 |  2 |  2  
P2 |  1 |  1  
P3 |  8 |  4  
P4 |  4 |  2  
P5 |  5 |  3  
  
## Step-2

**FCFS algorithm** : It Stand for First Come First Serve. In this, the process which comes first execute first, come second execute next.

Gantt chart for FCFS algorithm:

![C:\\Users\\kaifi\\Desktop\\CDR Tif\\5.png](https://media.cheggcdn.com/media/122/122ce139-b50e-4818-ab75-56b4037631cd/13258-6-16E-i1.png)

In the above Gantt chart processes arrive in the order P1, P2, P3, P4 and P5. 

**SJF algorithm** : It stands for Shortest Job First. The process which has least burst time execute first the second least execute second and so on.

Gantt chart for SJF algorithm:

![C:\\Users\\kaifi\\Desktop\\CDR Tif\\2.png](https://media.cheggcdn.com/media/ad8/ad8b1592-85dd-4758-8830-8a6cfe9e13c1/13258-6-16E-i2.png)

In the above Gantt chart processes when there is availability of CPU it is assigned to the processes. 

**Non- preemptive priority algorithm** : The process having highest priority showing with largest number execute first and showing second largest number execute second and so on.

Gantt chart for Non- preemptive priority algorithm:

![A close up of a clock Description automatically generated](https://media.cheggcdn.com/media/e03/e0337beb-0669-45a4-a175-de7c6cd5f9e1/13258-6-16E-i3.png)

**Round robin algorithm:** It works on time quantum.

Gantt chart for round robin algorithm with quantum=2

![C:\\Users\\kaifi\\Desktop\\CDR Tif\\4.png](https://media.cheggcdn.com/media/56f/56f59770-2d9f-4761-9c22-7573e6bd0bf6/13258-6-16E-i4.png)

In the above Gantt chart each processes is interrupted after time slice of 2 quanta. 

## Step-3

![](https://media.cheggcdn.com/media/b96/b966115b-3a9d-4773-b2ac-72e92ac96b1c/13258-6-16E-i5.png)

Turnaround time of each processor in FCFS:

process |  Turnaround time  
---|---  
P1 |  2  
P2 |  3  
P3 |  11  
P4 |  15  
P5 |  20  
  
Turnaround time of each processor in SJF:

process |  Turnaround time  
---|---  
P1 |  3  
P2 |  1  
P3 |  20  
P4 |  7  
P5 |  12  
  
Turnaround time of each processor in Non-preemptive priority:

process |  Turnaround time  
---|---  
P1 |  15  
P2 |  20  
P3 |  8  
P4 |  19  
P5 |  13  
  
Turnaround time of each processor in Round Robin:

process |  Turnaround time  
---|---  
P1 |  2  
P2 |  3  
P3 |  20  
P4 |  13  
P5 |  18  
  
## Step-4

![](https://media.cheggcdn.com/media/647/6474d3e2-383f-4dd0-a94f-912b875b81cb/13258-6-16E-i6.png).

Waiting time of each process in FCFS:

process |  Waiting time  
---|---  
P1 |  0  
P2 |  2  
P3 |  3  
P4 |  11  
P5 |  15  
  
Waiting time of each process in SJF:

process |  Waiting time  
---|---  
P1 |  1  
P2 |  0  
P3 |  12  
P4 |  3  
P5 |  7  
  
Waiting time of each process in Non-preemptive priority:

process |  Waiting time  
---|---  
P1 |  13  
P2 |  19  
P3 |  0  
P4 |  15  
P5 |  8  
  
Waiting time of each process in Round Robin:

process |  Waiting time  
---|---  
P1 |  0  
P2 |  2  
P3 |  12  
P4 |  9  
P5 |  13  
  
## Step-5

![](https://media.cheggcdn.com/media/b3b/b3b73a01-1519-4c63-a7b4-aaf40d0691b7/13258-6-16E-i7.png)

![](https://media.cheggcdn.com/media/6b8/6b827055-3fc6-47a8-bae0-2a1ba77bce9f/13258-6-16E-i8.png)

![](https://media.cheggcdn.com/media/c98/c98ec611-764c-42f3-8116-320d5a0adae5/13258-6-16E-i9.png)

![](https://media.cheggcdn.com/media/502/50298e02-59b9-46f4-b604-3ff84094bf5d/13258-6-16E-i10.png)

![](https://media.cheggcdn.com/media/b19/b19834bc-ed5f-444e-a18e-c7e636cf52f9/13258-6-16E-i11.png)

SJF algorithm has the minimum average waiting time of 4.6.


---

# Problem 17
## Step-1

• It is given that Preemptive and round robin algorithm is used to schedule the process and each process has given a priority value. If there is no process to run then the task is taken as _P_ idle.

• According to **Preemptive algorithm** , if any process is running and any other higher priority comes into existence then the running process is preempted by higher priority process.

• **Round Robin scheduling algorithm** is based on the time quantum. The process will be provided to CPU by mechanism first come first serve. After processing each process at once with time quantum, the sequence will be repeated.

## Step-2

Scheduling order of the process using Gantt chart is given below:

![C:\\Users\\susan\\Desktop\\100.png](https://media.cheggcdn.com/study/cc2/cc20a82c-66e6-46c7-a602-50c217e3d00c/13258-6-17e-i1.png)

**Explanation of above Gantt chart:**

• **In time interval 0 to 20:**![](https://media.cheggcdn.com/study/b9f/b9f9b470-ddb9-41e9-8880-9962a10b772c/13258-6-17e-i2.png) will execute in this slot as arrival time of ![](https://media.cheggcdn.com/study/9b4/9b42d410-251f-49a8-8440-273b23d1dfc5/13258-6-17e-i3.png) is 0 and no other process has arrived during the time slot.

• **In time interval 20 to 25:** No process will execute as ![](https://media.cheggcdn.com/study/92e/92e51139-2363-4096-b231-dd4a9a0b7f4d/13258-6-17e-i4.png) already completed and no other process is available in ready queue. 

• **In time interval 25 to 35:**![](https://media.cheggcdn.com/study/bf6/bf61a990-96f0-4ceb-b0ac-1957b8d10092/13258-6-17e-i5.png) will execute.

• **In time interval 35 to 45:**![](https://media.cheggcdn.com/study/636/636bdc73-389b-42fc-8692-16e813e5bfec/13258-6-17e-i6.png) will execute.

• **In time interval 45 to 55:**![](https://media.cheggcdn.com/study/8d9/8d96bdaa-aa5c-4617-a131-7abf49d009e0/13258-6-17e-i7.png) will execute.

• **In time interval 55 to 60:**![](https://media.cheggcdn.com/study/708/70849185-22c5-4a6c-bd67-06c44e4c4612/13258-6-17e-i8.png) will execute. ![](https://media.cheggcdn.com/study/bde/bdeab79a-ae4a-4b76-8e33-0e3c3a2f2b69/13258-6-17e-i9.png) will be preempted as process ![](https://media.cheggcdn.com/study/10b/10b2d1db-c07a-46ee-8173-2db4cd19ea4b/13258-6-17e-i10.png) with priority higher than ![](https://media.cheggcdn.com/study/95e/95e6813f-ffd1-4446-8b0e-2b7805689672/13258-6-17e-i11.png) has arrived.

• **In time interval 60 to 75:**![](https://media.cheggcdn.com/study/a96/a962ef1a-56f5-4965-acf4-a44b1d0453cf/13258-6-17e-i12.png) will execute.

• **In time interval 75 to 80:**![](https://media.cheggcdn.com/study/003/003098b3-76d1-4216-a236-8dd30422727f/13258-6-17e-i13.png) will execute.

• **In time interval 80 to 90:**![](https://media.cheggcdn.com/study/37f/37f1f18b-c8ba-4171-a9ff-42393bc1b7c5/13258-6-17e-i14.png) will execute.

• **In time interval 90 to 100:** No process will execute as![](https://media.cheggcdn.com/study/800/800cfc48-91ec-4618-894b-b30ec5dad336/13258-6-17e-i15.png),![](https://media.cheggcdn.com/study/dee/deefe347-4561-4738-bbe3-2d1ef241e8a8/13258-6-17e-i16.png), ![](https://media.cheggcdn.com/study/cab/cab53915-c76a-4826-bd5f-542abc5008a6/13258-6-17e-i17.png) ![](https://media.cheggcdn.com/study/a03/a030ff8e-e5db-4d99-920e-b0afdc6dbceb/13258-6-17e-i18.png) already completed and no other processes are available in ready queue. 

• **In time interval 100 to 105:**![](https://media.cheggcdn.com/study/527/5277758b-8ace-4f20-9e6e-fcccc312cb18/13258-6-17e-i19.png) will execute as no other process available at this moment. 

• **In time interval 105 to 115:** ![](https://media.cheggcdn.com/study/b09/b09cc91b-b43d-4e17-9595-9028bd96f7c7/13258-6-17e-i20.png) will execute because it has more priority then![](https://media.cheggcdn.com/study/96b/96ba5c40-6074-4cab-8fdc-2bf7d05d5789/13258-6-17e-i21.png).

• **In time interval 115 to 120:**![](https://media.cheggcdn.com/study/2a0/2a0e2ae4-b259-4ef6-b59e-5b3da5b4c1f4/13258-6-17e-i22.png) will execute as****![](https://media.cheggcdn.com/study/900/900fd290-be78-41b2-b748-b3da3c3f8a7f/13258-6-17e-i23.png) has completed its burst time.

## Step-3

**Turnaround time** is the total time taken by process from submission to its completion. 

![](https://media.cheggcdn.com/study/7dc/7dc5c8ed-c151-4d68-9d3f-8ab363089d74/13258-6-17e-i24.png).

![](https://media.cheggcdn.com/study/e91/e913480d-9e1c-454c-9029-3c9ea7e5d054/13258-6-17e-i25.png)

![](https://media.cheggcdn.com/study/bed/bed29fa2-f3bf-42e9-856f-fede52ce69c3/13258-6-17e-i26.png)

![](https://media.cheggcdn.com/study/d81/d8145c3c-d077-42fd-aa15-d1b7b635a8cd/13258-6-17e-i27.png)

![](https://media.cheggcdn.com/study/fef/feffd744-0c64-4b5e-a08b-4ac6c3db6eb3/13258-6-17e-i28.png)

![](https://media.cheggcdn.com/study/f52/f52fabcd-451c-4513-b32a-2b1cc72abba8/13258-6-17e-i29.png)

![](https://media.cheggcdn.com/study/5de/5de03e22-c0af-4b83-83c6-db7673b1c92a/13258-6-17e-i30.png)

## Step-4

c.

**Waiting time** is the time spent by a process waiting in the ready queue.

Waiting time for ![](https://media.cheggcdn.com/study/219/219a8ed0-bc2c-4260-974b-3f45a5975294/13258-6-17e-i31.png)

![](https://media.cheggcdn.com/study/fd5/fd52d342-aa87-4015-aa78-30cb720f6fb9/13258-6-17e-i32.png)

![](https://media.cheggcdn.com/study/0f2/0f2b8320-116c-438f-8feb-8c0ba61b7854/13258-6-17e-i33.png)

![](https://media.cheggcdn.com/study/c23/c2313d6f-9751-4694-ba38-db93641b2388/13258-6-17e-i34.png)

![](https://media.cheggcdn.com/study/f5d/f5d26a81-206c-45b8-abf2-8347ba9b279c/13258-6-17e-i35.png)

![](https://media.cheggcdn.com/study/36b/36b11a67-d3e2-4fff-86a4-ddd4ef272785/13258-6-17e-i36.png)

## Step-5

d.

CPU utilization can be calculated as given below:

![](https://media.cheggcdn.com/study/b96/b9617e0a-2cb1-4703-a382-19ae2acd402c/13258-6-17e-i37.png)


---

# Problem 18
## Step-1

**Nice value** is used to provide a specific priority to the process at the time of invoking or calling. 

• The default nice value is 0.

• The limits of nice value are -20 to +19.

• A lower nice value indicates a higher priority. It means -20 indicates a highest priority. 

• A higher value indicates a lower priority. It means 20 or 19 shows the lower priority.

• A higher priority process is always assigned more CPU time than a low priority process. 

## Step-2

The non- root processes are allowed to assign nice values greater than or equal to zero. 

• If the non- root processes are allowed to assign nice values less than zero, then all the non- root processes will provide themselves a higher priority. 

• Then there will be an issue to which non-root processes the CPU is to allocated as they are all of high priority.

Hence, the root user can only be allowed to assign nice values less than zero.


---

# Problem 19
## Step-1

**Starvation due to scheduling algorithms**

**First – come, first – served (FCFS) algorithm** : This scheduling algorithm allocates the CPU (Central Processing Unit) resources to the process that requests the resources first. 

**Shortest – Job – First (SJF):** This scheduling algorithm allocates the CPU (Central Processing Unit) resources to the process that has the smallest CPU burst.

**Round – robin** : This scheduling algorithm allocates the CPU (Central Processing Unit) resources to each of the process in the circular queue for a time interval of up to 1 quantum (Time quantum is a small amount of generally from 10 to 100 milliseconds). 

**Priority Scheduling** : This scheduling algorithm allocates the CPU (Central Processing Unit) resources to the process that has the highest priority (a priority is associated with each process).

**Among all the four scheduling algorithms Shortest – Job – First and Priority scheduling could result in starvation.**

## Step-2

In the Shortest – Job – First scheduling algorithm, the longest job will be in the indefinite blocking or starvation. Starvation arises when shortest jobs keep on arriving before the current shortest job completes its execution. In this case, the shortest job is always available to execute and longest job will starve. 

In the Priority scheduling algorithm, the lowest priority job will be in the indefinite blocking or starvation. Starvation arises when highest priority job keeps on arriving before the current highest priority job completes its execution. In this case, the highest priority job is always available to execute and low priority job will starve. 

**Therefore, Shortest – Job – First and Priority scheduling could result in starvation.**


---

# Problem 20
## Step-1

**a)**

• ****If the two pointers referred to the same process in the ready queue using Round Robin scheduling Algorithm, the process priority get increased every time.

• This phenomenon also called receiving preferential treatment. 

• Preferential treatment means take the advantage over the other process in the ready queue which are having more priority.

Consider the two pointer **p** 1 and **p** 2 have the same references to the Process **P** 1 and these two pointers are put in the ready queue at time quantum **t.**

Then each process gets ½ = 50% of CPU time with at most ‘t’ time units.

Each process waits for maximum time i.e (2-1)xt time unit until its next time quantum.

## Step-2

**b)**

The two-major advantage of this preferential treatment scheme is as follows:

• In the Process control block, the CPU can give high priority to the Important processes. Hence, the important process will complete the job first.

• Higher Priority in the received treatment.

The Disadvantages**** preferential treatment are as follows:

• Shorter jobs will suffer to wait in the ready queue for its execution.

• Less Priority.

## Step-3

**c)**

The best advice to modify the RR algorithm to avoid this issue without the duplicate pointers is allot a longer amount of time to processes deserving higher priority. 

It means provide various time quantum to complete the jobs one after the other in the RR scheduling algorithm.


---

# Problem 21
## Step-1

Given data:

• Number of I/O bound tasks=10

• Number of CPU bound tasks=1

• Time taken for context-switching=0.1 millisecond

**Time quantum is 1 millisecond:**

The CPU bound job will be preempted after the time quantum of 1 millisecond. 

The I/O bound job will execute for 1 millisecond and after that context switching takes place. 

When the time quantum is 1 millisecond, there will be 0.1 units of context switch for both CPU and I/O bound jobs. 

Hence, the CPU utilization ![](https://media.cheggcdn.com/study/e5d/e5de4e16-796c-4160-8872-cf628c4b6cec/13258-6-21e-i1.png)

![](https://media.cheggcdn.com/study/062/0625b3a5-2a45-49ec-bef1-2c5ca2221f6d/13258-6-21e-i2.png)

## Step-2

Hence, the CPU utilization when the time quantum is 1 millisecond is **91%****.**

## Step-3

**The time quantum is 10 milliseconds:**

The CPU bound job will be executed for 10 milliseconds and then context switch takes place. The CPU bound job will not be preempted for 10 milliseconds. 

Therefore, the time taken for a CPU bound job will be 10+0.1=10.1 ms.

The I/O bound job will take 10 milliseconds to complete. The I/O bound job will perform a context switch once for 1 millisecond. This is because it issues an I/O operation for every 1 millisecond of CPU utilization. 

Therefore, the time taken for an I/O bound job will be 1ms + 0.1ms =1.1 ms.

As there are 10 jobs, the time taken for ten I/O bound jobs will be ![](https://media.cheggcdn.com/study/4be/4beb0d46-c5a9-4bcf-a8f5-7778104d9806/13258-6-21e-i3.png).

Hence, the CPU utilization ![](https://media.cheggcdn.com/study/4c2/4c24c750-8018-448c-9dc2-2127432a4ae7/13258-6-21e-i4.png)

![](https://media.cheggcdn.com/study/169/169d5fa8-f6f0-45ca-aabe-34e2a0eac389/13258-6-21e-i5.png)

Hence, the CPU utilization when the time quantum is 10 millisecond is **95%****.**


---

# Problem 22
## Step-1

One possibility:

If the program uses only a large fraction of its time quantum and not the entire time quantum, thereby increase of priority associated with that process, The program could maximize the CPU time allocated to it by not fully utilizing its time quantums. 

Another Possibility: 

Round Robin Scheduling: A multilevel queue scheduling algorithm partitions the ready queue in several separate queues. The processes are permanently assigned to one queue, based on memory size, process priority, process type. 

Breaks a process up into many smaller processes and dispatch each to be started and scheduled by the operating system. Separate queue might be used for foreground and background processes. Foreground queue might be Round Robin where as background may be FCFS algorithm.


---

# Problem 23
## Step-1

**(a)**

![](https://media.cheggcdn.com/study/1a3/1a35531f-4f1c-43dd-852b-a87507e7b302/13258-6-23E-i1.png)

![](https://media.cheggcdn.com/study/d51/d516eeec-0d3b-444b-b374-7a5659153bd9/13258-6-23E-i2.png) is the rate of change of priority when the process is running

![](https://media.cheggcdn.com/study/232/232ee71c-7359-424d-b7fe-0d3550b3cc51/13258-6-23E-i3.png) is the rate of change of priority when the process is waiting

0 is the rate when the rate when the process entered in ready queue.

• From the above question, all the processes having initial priority of 0 when it is entered into the ready queue.

• The priority is increased when the process is running from the ready state at the rate ![](https://media.cheggcdn.com/study/215/215fabff-a636-4d9e-a098-ff448c71fa39/13258-6-23E-i4.png) which is greater than 0. Therefore, the highest priority of the process is ![](https://media.cheggcdn.com/study/a88/a88f7f35-e97c-4469-9c2b-5eaab9a2bf9b/13258-6-23E-i5.png).

• When the highest priority process is running (the first processes which entered into the ready queue), its priority is increasing at a rate (![](https://media.cheggcdn.com/study/b58/b5838edc-69bf-42cb-939f-eb0f4f906e54/13258-6-23E-i6.png)). Therefore, no other processes will preempt until its completion.

• As the highest priority processes running is higher than the processes which are waiting, it seems to be a **First-Come-First-Serve (FCFS)** algorithm. The processors which are waiting for a long time will be run and its priority is increasing. __

Hence, the algorithm results from the equation are **FCFS**. 

## Step-2

**(b)**

![](https://media.cheggcdn.com/study/8cf/8cf2eb90-d953-41cf-848d-c7b9247cafc6/13258-6-23E-i7.png)

• As the highest priority processes are running, no other processes which are in the ready queue will not preempt the running process. Therefore, its priority is decreasing at a rate ![](https://media.cheggcdn.com/study/167/167171d0-ffd8-416e-ab19-fda0e56f5d6b/13258-6-23E-i8.png).

• But, the process can be preempted by the new processes because when the new process enters into the ready queue, its initial priority is 0. The 0th priority is greater than the priority of the waiting process ![](https://media.cheggcdn.com/study/898/89877a91-7019-4db2-bc83-e8c12c087b00/13258-6-23E-i9.png) . 

Therefore, the last come process is served first. Therefore, the algorithm results from the explanation is **LIFO (Last In First Out).**


---

# Problem 24
## Step-1

**(a) FCFS** —discriminates against short jobs since any short jobs arriving after long jobs

will have a longer waiting time.

## Step-2

**(b) RR** —treats all jobs equally (giving them equal bursts of CPU time) so short jobs will

be able to leave the system faster since they will finish first.

## Step-3

**(c)Multilevel feedback queues** —work similar to the RR algorithm—they discriminate

favorably toward short jobs.


---

# Problem 25
## Step-1

Windows scheduling algorithm uses 2 type of scheduling algorithm, one is priority based scheduling and preemptive scheduling algorithm.

There are 6 priority classes given below as: 

• IDLE_PRIORITY_CLASS 

• BELOW_NORMAL_PRIORITY_CLASS 

• NORMAL_PRIORITY_CLASS

• ABOVE_NORMAL_PRIORITY_CLASS

• HIGH_PRIORITY_CLASS

• REALTIME_PRIORITY_CLASS 

The values can be: IDLE, LOWEST, BELOW_NORMAL, NORMAL, ABOVE_NORMAL, HIGHEST, TIME_CRITICAL.

## Step-2

A thread in the REALTIME_PRIORITY_CLASS with a relative priority of NORMAL is 24 (given from figure 6.22).

## Step-3

A thread in the ABOVE_NORMAL_PRIORITY_CLASS with a relative priority of HIGHEST is 12 (given from figure 6.22).

## Step-4

A thread in the BELOW_NORMAL_PRIORITY_CLASS with a relative priority of ABOVE_NORMAL is 7 (given from figure 6.22).


---

# Problem 26
## Step-1

• The combination of REALTIME_PRIORITY_CLASS and TIME_CRTICAL priority provides the highest possible relative priority that is 31. 

• Assume there is no threads belong to the REALTIME_PRIORITY_CLASS and that none may be assigned a TIME_CRTICAL priority.

• If above condition is true then a combination of HIGH_PRIORITY_CLASS and HIGHEST priority within that class with a numeric priority of 15 corresponds to the highest possible relative priority in Windows scheduling (According to figure 6.22).


---

# Problem 27
## Step-1

**Time quantum** is also known as time slice. It is small unit of time. Time quantum is used in time sharing system. 

Time quantum and priority are inversely proportion to each other. Higher priority refers lesser the time quantum and vice versa.

## Step-2

According to the Solaris operating system for time sharing needs the time quantum (in milliseconds) for a thread with priority 15 is 160 and for a thread with priority 40 is 40 (according to figure 6.23).

## Step-3

A thread with priority 50 has used its entire time quantum without blocking, so the scheduler will assign a new priority to this thread that is 40 (according to figure 6.23).

## Step-4

A thread with priority 20 blocks for I/O before its time quantum has expired, so the scheduler will assign a new priority to this thread of 52 (according to figure 6.22).


---

# Problem 28
## Step-1

**CFS** stands for Completely Fair Scheduler and it is default linux scheduling algorithm. Priority value is not provided directly by the CFS scheduler but it maintain the virtual run time of each task by pre-task variable vruntime which provide the runtime of each process. 

Lower nice value shows higher priority and higher nice value shows the lower priority. A higher priority process is always assigned more CPU time than a low priority process.

## Step-2

When both tasks A and B are CPU bound and nice value of A and B is given as -5 and +5 respectively then vruntime will be small for task A than task B as -5 for task A indicates a higher priority than task B.

## Step-3

When task A is I/O bound and B is CPU bound, the vruntime will be smaller for task A than task B because task A has high priority and I/O bound process will run shortly before blocking for another I/O. 

## Step-4

When task A is CPU bound and task B is I/O bound the vruntime of task A will be less than value of vruntime of task B as CPU bound process will consume its time period whenever it will run on processor and it can be preempted by I/O bound. 


---

# Problem 29
## Step-1

In**Proportional share scheduler,** some CPU time is previously allocated to each processor and every job contains certain weight. And on the proportion of the weight, each job gets the part of available resources.

## Step-2

A **priority inversion problem** is one in which a resource required by a high priority process is being acquired by a low priority process and that has preempted by medium priority process. 

Due to which the highest priority process cannot be implemented before the medium priority process and lower priority process.

**Example:** A and B are 2 processes A has higher priority than B and B acquire an exclusive shared resource that is required by the A. let C be a medium priority that comes into existence. If B is running, A and C is blocked. 

B can be preempted by C as it has higher priority. But A cannot run before B as A needs that resource which is acquired by B. So the priority of A and B is inverted.

## Step-3

The solution to this problem is that a high priority process and a low priority process should interchange their priorities only till the high priority process completes its work with the resource, after that priorities can be same as initial. 

This can be a solution which can be implemented within the context of a proportional share scheduler.


---

# Problem 30
## Step-1

Rate-monotonic scheduling is the scheduling algorithm which is used today in real-time operating system. In this static-priority scheduling class is being used. In case of static-priority scheduling class if the duration of the cycle is short then priority of the job will be higher. 

Earliest - deadline – first scheduling places a process in priority queue which is having a due deadline that means the process which is near its deadline given the highest priority, whereas **rate-monotonic scheduling** places a process in priority queue having shorter period which leads to higher priority. 

## Step-2

Circumstances where rate-monotonic scheduling algorithms are inferior in comparison to the earliest-deadline first scheduling algorithm in meeting the processes are as follows:

• In case of static priority assignment rate monotonic is preferred whereas in case of dynamic priority assignment earliest deadline first assignment is preferred. 

• When tasks-sets with the higher processor utilization is required then in that situation Rate-monotonic scheduling algorithm is not preferred. 


---

# Problem 31
## Step-1

Rate-monotonic scheduling places a process in priority queue having shorter period which leads to higher priority. It plays an important role in real time as it guarantee that the tasks are basically schedulable. The tasks which is meeting their deadline in a proper time is said to be schedulable. 

Consider the following Gantt chart:

![Description: C:\\Users\\kaifi\\Desktop\\CDR Tif\\10.png](https://media.cheggcdn.com/study/10e/10ee076e-aafe-468f-bac7-920100763c0e/13258-6-31E-i1.png)

Explanation of the Gantt chart:

• Process![](https://media.cheggcdn.com/study/d22/d227e8b1-a05a-41c8-9074-b2b6e361f1c3/13258-6-31E-i2.png)has the shorter period so it will be scheduled first at time![](https://media.cheggcdn.com/study/d26/d265677f-e888-4008-a712-ff6471dabaad/13258-6-31E-i3.png). Its burst will finish at![](https://media.cheggcdn.com/study/108/108ec0f5-ba44-40ba-8721-c1b06e262cce/13258-6-31E-i4.png), giving the CPU to process![](https://media.cheggcdn.com/study/ed0/ed05cc63-197f-48e1-ba25-00acdcebd3c7/13258-6-31E-i5.png). 

• This process will get to execute till the end of the deadline for process![](https://media.cheggcdn.com/study/b41/b418af5e-8edd-4c05-ba45-4cb670e115ec/13258-6-31E-i6.png)at![](https://media.cheggcdn.com/study/29a/29ac147f-5940-42dc-8814-9de1b608e157/13258-6-31E-i7.png), upon which it will get preempted.

• Thus process![](https://media.cheggcdn.com/study/953/95395b65-15c6-4f01-ae39-c75c0457248b/13258-6-31E-i8.png)got to execute for![](https://media.cheggcdn.com/study/507/5075ae34-a8f9-4cc3-861b-2b684537106f/13258-6-31E-i9.png). Process![](https://media.cheggcdn.com/study/433/433cd456-6c91-445f-b41a-4fc6213cadd5/13258-6-31E-i10.png)will execute till![](https://media.cheggcdn.com/study/d4b/d4b8b424-535b-41cf-b2cb-539122ee43dd/13258-6-31E-i11.png). 

• This is the deadline for process![](https://media.cheggcdn.com/study/323/32395e4b-77c4-4fd5-a969-35fa16b7547a/13258-6-31E-i12.png)but it still needs![](https://media.cheggcdn.com/study/839/839e7910-46b3-4383-9caa-83c936a072d3/13258-6-31E-i13.png)to complete its burst.

Hence, it can be said that the 2 processes cannot be scheduled by rate-monotonic scheduling.

## Step-2

Earliest-deadline-first scheduling places a process in priority queue which is having a due deadline that means the process which is near its deadline given the highest priority. 

Consider the following Gantt chart:

![Description: C:\\Users\\kaifi\\Desktop\\CDR Tif\\9.png](https://media.cheggcdn.com/study/46b/46b35ddf-ffa9-41de-bd00-4694f9bee2cf/13258-6-31E-i14.png)

Explanation of the Gantt chart:

• These two processes can be scheduled with earliest-deadline-first scheduling. Scheduling will start with process![](https://media.cheggcdn.com/study/ef3/ef34fbb9-ad6d-4df4-a443-105a10ae2630/13258-6-31E-i15.png)since it has the earliest deadline![](https://media.cheggcdn.com/study/561/561dcc70-795d-4fdf-adee-aa8e68200f1b/13258-6-31E-i16.png). 

• Process![](https://media.cheggcdn.com/study/354/354313cc-c89e-49d8-8863-59e3b7fc4dd4/13258-6-31E-i17.png)will be scheduled in at![](https://media.cheggcdn.com/study/941/941a48c2-e275-421a-bf38-eb497acfe9b8/13258-6-31E-i18.png). It will not get preempted by process![](https://media.cheggcdn.com/study/a94/a94662e8-64a7-4af5-8202-6c22f9308e88/13258-6-31E-i19.png)at![](https://media.cheggcdn.com/study/d1d/d1d76973-f97d-43e5-8418-3be1da20e25a/13258-6-31E-i20.png)as it has the earlier deadline, that is![](https://media.cheggcdn.com/study/851/85139212-4596-4947-a19e-fb947c697c50/13258-6-31E-i21.png). 

• It will relinquish control of the CPU at the end of its burst, at![](https://media.cheggcdn.com/study/036/0366d1f8-e17d-4f68-b4eb-0c2ec86a3cae/13258-6-31E-i22.png). 

• At this point, process![](https://media.cheggcdn.com/study/4ab/4ab776ad-b329-4af4-b57d-ed22525f6841/13258-6-31E-i23.png)will be scheduled in. It too will execute till its burst’s end, till![](https://media.cheggcdn.com/study/82f/82f22c9c-df35-4d73-b5bb-67703e22a57b/13258-6-31E-i24.png). 

• At this time, process![](https://media.cheggcdn.com/study/f7f/f7fbc619-65a1-486e-be27-a7a0886251c3/13258-6-31E-i25.png)will be scheduled in as process![](https://media.cheggcdn.com/study/dd6/dd6708f3-92bb-4a25-8062-77ffe2dc77bd/13258-6-31E-i26.png)’s deadline has been met. It will not be preempted by process![](https://media.cheggcdn.com/study/f49/f49d79e2-64de-43f3-8268-50230314ad4e/13258-6-31E-i27.png)at![](https://media.cheggcdn.com/study/33b/33b1a259-8d22-473a-b26f-c4b5c475ee11/13258-6-31E-i28.png)as both the processes’ deadlines are the same, that is![](https://media.cheggcdn.com/study/5ae/5aef8dc9-c871-402f-b881-20d381370723/13258-6-31E-i29.png). 

• Process![](https://media.cheggcdn.com/study/d12/d1280bcf-b712-4ac2-94fc-dc31c19944e8/13258-6-31E-i30.png)will get the CPU at![](https://media.cheggcdn.com/study/50f/50fa7450-41b1-46ff-a537-5ee72975ca0b/13258-6-31E-i31.png). Its burst will finish at![](https://media.cheggcdn.com/study/381/38165654-36c2-46f8-b955-16081bc4b87a/13258-6-31E-i32.png), where the CPU will remain idle till![](https://media.cheggcdn.com/study/028/028e8b6b-f245-4fbc-874c-a9524c6f290c/13258-6-31E-i33.png).

Hence, it can be said that the 2 processes can be scheduled by earliest-deadline first scheduling.


---

# Problem 32
## Step-1

A **hard real time** system is one in which a process is serviced within a given deadline or time. 

The performance of the hard real time systems is affected by the interrupt latency and dispatch latency.

## Step-2

**Interrupt latency** is the amount of time between the occurrence of the interrupt to the CPU and the first respond of the CPU to the interrupt.

For a hard real time system, Interrupt should be bounded as the CPU has to first complete the currently running instruction, save its state and then the interrupt will be serviced by ISR (Interrupt Service routine) which will check what type of interrupt has been occurred.

It is very important in real operating system to reduce the interrupt latency because if interrupt latency is reduced, it will be ensured that the real time system get immediate attention. 

## Step-3

**Dispatch latency** is the amount of time required for the scheduler to stop currently running process and start another.

It must be bounded with hard real time system because preemption is needed for a current process to be stopped, save its state and then the CPU will be assigned to a high priority process immediately. To service it within in a given deadline, immediate retrieval to the CPU is necessary for real time system to reduce dispatch latency. 

## Step-4

So, minimization of the interrupt and dispatch latency should be done for ensuring that all the tasks in the real time need proper attention. 

Therefore, both are necessary to be bounded in hard real time system.


---

