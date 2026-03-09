# Problem 1
## Step-1

**Manually Operated System**

In manually operated systems the sequence of operation of programs was decided according to the need of resources for the program. Manually operated system was in which every application was run by user itself. The sequence of operations in this system was decided by the programmer and this sequence is categorized as follows:

• To reduce the set up time programs with similar needs were grouped together and run together.

• Jobs that require same compiler and that are written in same language are run at the same time so that the compiler is loaded only once and can be used for both of the programs.

• The program was loaded in machine and was forced to run until it completed it or crashed it.

• Compilers and assemblers were programmed to translate program into machine code.


---

# Problem 2
## Step-1

300-23-2E

Each new I/O device had its own characteristics, requiring careful programming. A special subroutine called a device driver was written for each I/O device, CPU can often be idle. The problem is the speed of the mechanical I/O devices, which are slower than electronic device. Even a slow CPU works in the micro second, with thousands of instruction executed per second. The difference in speed between CPU and its I/O device may be three orders of magnitude or more.

Earlier one solution for this problem was to replace slow card readers and line printers (I/O devices mostly used then) with magnetic-tape units. Rather than have CPU read directly from cards, however the cards were first copied onto a magnetic tape via a separate device. When the tape was successfully full, it was taken down and carried over to the computer. When a card was needed for input to a program, the equivalent record was read from the tape. Similarly, output was written to the tape, and the contents of the tape were printed later. The card readers and the line printers were operated off-line, rather than by the main computer.


---

# Problem 3
## Step-1

300-23-3E

If page fault occurs, a page – replacement algorithm was invoked. Page – replacement algorithm attempts to predict future memory-according behavior based on past behavior.

• Any page with![](https://media.cheggcdn.com/study/bfd/bfdb5555-52d7-41f4-8267-1e2a38906067/300-23-3e-i1.png). Such a page is considered to be no longer 

in use

• If ![](https://media.cheggcdn.com/study/e3b/e3bfc3e3-18dd-42b2-8741-91ce178ff953/300-23-3e-i2.png) pages, then replace the page with the largest![](https://media.cheggcdn.com/study/9f7/9f74d2ea-af16-4e20-a73b-54c9f5002ca0/300-23-3e-i3.png).

If![](https://media.cheggcdn.com/study/15e/15ede4e7-e08a-4968-8272-9bbf504217bb/300-23-3e-i4.png), it is assumed no page is being used, and the page is replace.

_Clock algorithm_

Implementation can be done through a circular queue. A pointer indicates which page to be replaced next. Once a victim page is found, the page is replaced and new page is inserted in circular queue in that position. 

Clock algorithm degenerates to FIFO replacement if all bits are set.


---

# Problem 4
## Step-1

• CTSS is The Compatible Time-Sharing Operating System designed at MIT. This OS was implemented on the processor of IBM 7090. It was designed to support 32 interactive users. Set of Interactive commands are given to users which can be used to modify files and also for compiling and running programs.

• The CPU Scheduling is implemented using multilevel feedback queue algorithm. According to this algorithm ![](https://media.cheggcdn.com/study/702/7027be6a-6dce-4c85-8278-032927957243/13258-20-4E-i1.png)amount of time units are allocated as the time quantum for level _i_. 

• If a given program does not finish its CPU burst in one quantum time, then it is moved down one level of the queue and hence giving it ![](https://media.cheggcdn.com/study/151/15154669-0ebb-400b-ac0f-0ccaa7fbe998/13258-20-4E-i2.png)quantum of time. The program at the topmost level is the one with least quantum and hence runs first. 

• The level of the program is determined by the size initially, so that the time quantum should be at least as long as the swap time. 

## Step-2

Thus, if a multilevel feedback queue as used in CTSS and MULTICS is considered then assuming that a program takes 7 time units each time it executes an I/O Operation and blocks and it is at level _i_ , then time allocation will be as follows, according to the algorithm above:

For level 2, Time quantum is ![](https://media.cheggcdn.com/study/fd0/fd00f55b-d189-4620-86ad-5d97e9f6da9a/13258-20-4E-i3.png)Time Units.

For level 3, Time quantum is ![](https://media.cheggcdn.com/study/8cf/8cfe16fa-b343-4b5a-bc5d-d87c5b53b123/13258-20-4E-i4.png)Time Units.

For level 4, Time quantum is ![](https://media.cheggcdn.com/study/5b9/5b9c2f6d-ac96-4ce7-9d0d-2dc77cd0b415/13258-20-4E-i5.png)Time Units.


---

# Problem 5
## Step-1

**Mach Operating System**

Mach operating system was designed to fulfill the following conditions:

1) To make the files of UNIX system executable under Mach operating system.

2) It was establish as modern operating system that supports many memory models for parallel and distributed computing.

3) It used a kernel that was simpler and easier to do modifications than 4.3 **BSD (Berkley Software Design).**

In the second release of Mach it included much of the **BSD’** s code inside the kernel. This new release of Mach made kernels larger than the kernels of BSD. Mach 3 removed the BSD code outside of the kernel and thus giving a very small microkernel. This new Mach 3 evicted all **UNIX** specific code so that is can run in user mode servers. After the eviction of the UNIX specific code from the kernel it allowed the replacement of BSD with any other operating system.

User mode implementation in BSD has been developed for DOS which is **Machintosh** operating system. This concept is similar to the virtual machine concept. But this virtual machine is defined by software here rather than hardware which ensure the efficient handling of messages. Mach provides great flexibility in the design and in managing the memory object tasks.


---

# Problem 6
## Step-1

**Evolution of Operating System**

A various types of operating systems have evolved by the time and according to the changing requirement of the user. The evolution of the operating system is discussed below:

• The early computers were made to use **batch** **operating** **system** , in which the system used to run many jobs without any halt. Programs were punched to cards which were copied to **tape** for other processing. Whenever the one job was finished, other was started on the tape.

• **Time** **shared** operating system replaced batch operating system. Now the users could interact with the system with the help of a printing terminal.

• The **Atlair** **8800** was the first personal computer given to individuals. It was sold in kit form to users and it did not have an operating system as it contained only switches and light emitting diodes to give the input and to receive the output.

• The **graphical** **user** **interface** (GUI) computers were the systems having displays with bit mapped pixels. The first success of such kind of computer was **Apple** **Macintosh** introduced in 1984.

The conclusion about the evolution of operating system is that systems evolved as according to the need of user and provided them more secure, scalable and systems with good user interface.

## Step-2

Some operating system became popular as they were suitable for various types of requirements and they were compatible with **mini** **computers** , **microcomputers** , and **mainframe** **computers**. Other operating system failed because they were not able to run thousands of applications simultaneously and were not easy to use, also they dint provide security to users and good graphical user interface.


---

