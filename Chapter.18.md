# Problem 1
## Step-1

**Dynamically Loadable Kernel Modules**

Yes, these kernel modules have certain disadvantages as well. Two of these advantages are given below:

1\. **Memory Management:** Managing entire modules takes up a lot of memory owing to its **heavy size**. A kernel with multiple modules will take up much more memory space than a similar simple kernel in which the drivers are compiled within the image of the kernel.

2\. **Complexity:** These modules make the bootstrapping process of the kernel more complicated. If the driver that is required to access a disk is a module that itself takes some time to load; then, loading a set of modules from that disk is even more difficult. Due to this reason, extra efforts are required to manage the bootstrapping process of the kernel.

## Step-2

It is better to keep a kernel split into modules when certain drivers are not always required. The kernel modules let the drivers that aren’t required at present to be loaded and unloaded as per requests, which saves the physical memory because the drivers do not use the memory unnecessarily. For example, it is better to use modules when the kernel is to be used by multiple systems, like in case of distributed kernels, where the priority is to support a huge range of hardware in the easiest way possible.

Whereas, it is better to compile a kernel into a single binary file and keep its size as small as possible when the drivers are being used constantly; especially, when they are being used for the boot itself. The drivers keep running with the help of the physical memory. An example of where to use kernels in the form of single binary files is, if a kernel is made just for one machine with known configuration, using modules will just make the system complex.


---

# Problem 2
## Step-1

**The three different ways to implement threads are** :

1\. Kernel-based threads

2\. User-mode threads and

3\. Hybrid threads

## Step-2

1\. **Kernel-based threads** :

The operating system kernel may provide support for threads itself. So, the threads may be implemented as separate processes that happen to share a common address space, or they may be implemented as separate execution contexts within a single process. Whichever way the threads are organized, they appear as fully independent execution contexts to the application.

## Step-3

The advantages of implementing Kernel-threaded systems are:

1\. Kernel-threaded systems can take advantage of multiple processors if they are available and

2\. If one thread blocks in a kernel service routine, 

other threads are still able to run.

## Step-4

2\. **User-mode threads** :

User-mode thread packages rely on some kernel support—they may require timer interrupt facilities, for example—but the scheduling between threads is not performed by the kernel but by some library of user-mode code. Multiple threads in such an implementation appear to the operating system as a single execution context. When the multithreaded process is running, it decides for itself which of its threads to execute, using non-local jumps to switch between threads according to its own preemptive or non-preemptive scheduling rules.

## Step-5

However, user-mode implementations do have their own advantages. The most obvious is performance: invoking the kernel’s own scheduler to switch between threads involves entering a new protection domain as the CPU switches to kernel mode, whereas switching between threads in user mode can be achieved simply by saving and restoring the main CPU registers. User-mode threads may also consume less system memory: most UNIX systems will reserve at least a full page for a kernel stack for each kernel thread, and this stack may not be pageable.

## Step-6

3\. **Hybrid** :

Hybrid implementations are also possible, where a large number of threads are made available to the application using a smaller number of kernel threads. Runnable user threads are run by the first available kernel thread. In Linux, threads are implemented within the kernel by a clone mechanism that creates a new process within the same virtual address space as the parent process. Unlike some kernel-based thread packages,

The Linux kernel does not make any distinction between threads and processes: a thread is simply a process that did not create a new virtual address space when it was initialized.

## Step-7

The hybrid approach, implementing multiple user threads over a smaller number of kernel threads, allows a balance between these tradeoffs to be achieved. The kernel threads will allow multiple threads to be in blocking kernel calls at once and will permit running on multiple CPUs, and user-mode thread switching can occur within each kernel thread to perform lightweight threading without the overheads of having too many kernel threads. The downside of this approach is complexity: giving control over the tradeoff complicates the thread library’s user interface.


---

# Problem 3
## Step-1

2481-21-14E AID: 268

RID: 146

The effect does not allow paging out of kernel memory in Linux is that the non-preemptability of the kernel is preserved. Any process taking a page fault, whether in kernel or in user mode, risks being rescheduled while the required data is paged in from disk. Because the kernel can rely on not being rescheduled during access to its primary data structures, locking requirements to protect the integrity of those data structures are very greatly simplified. 

The advantages of this design is

Simplicity in itself, 

It also provides an important performance advantage on uniprocessor machines due to the fact that it is not necessary to do additional locking on most internal data structures.

There are a number of disadvantages to the lack of page able kernel memory, however. First of all, it imposes constraints on the amount of memory that the kernel can use. It is unreasonable to keep very large data structures in non-pageable memory, since that represents physical memory that absolutely cannot be used for anything else. This has two impacts: first of all, the kernel must prune back many of its internal data structures manually, instead of being able to rely on a single virtual memory mechanism to keep physical memory usage under control.

Second, it makes it infeasible to implement certain features that require large amounts of virtual memory in the kernel, such as the /tmp filesystem (a fast virtual-memory-based file system found on some UNIX systems).

Note that the complexity of managing page faults while running kernel code is not an issue here. The Linux kernel code is already able to deal with page faults: it needs to be able to deal with system calls whose arguments reference user memory that may be paged out to disk.


---

# Problem 4
## Step-1

**Dynamic and Static Linkage of Libraries**

A shared library is a file that is shared by many executable files. Dynamic linkage of library is also known as **DLL** and it provides a method to implement shared library concept. Shared libraries have file extension as **DLL** , **DRV** or **OCX**. A static library has functions, variables and routines which are copied to any application at compile time. 

The advantages of the static and dynamic libraries are given as follows:

**S. No.** |  **Dynamic Library** |  **Static Library**  
---|---|---  
1. |  The main advantage of **shared** or **dynamic** **library** is that is reduces the space in disk and memory used by the system to save the information. |  It requires linking of the files at compile time which decreases the startup time for program execution.  
2. |  When many running programs share the libraries, the starting time to run every new program is minimized because many functions required by the program are already present in the physical memory. |  In case if shared libraries get corrupted, some basic libraries are linked statically this gives the chance to correct the fault.  
3. |  The dynamic linkage of library also improves the **maintainability** compared to static linkage library. |  Static linkage provides **ease** **of** **distribution** if the provider is not assured that user will have the right files installed in advance.  
  
## Step-2

Cases where static linkage of library is preferred over dynamic one are given as follows:

• When a program is to be executed for the first time in the system it will link up the files at compile time rather than run time hence **reducing** the **time** to load the required data.

• If shared libraries get corrupted then it will affect every linked program; in these cases static linkage of library is preferred.

• Static linkage provides ease of distribution.


---

# Problem 5
## Step-1

**Communication between Processes on a Single Computer**

The comparison between the use of Networking Sockets as opposed to the use of Shared Memory as a mode of communicating data between processes on a computer is shown in the table below:

**S. No** |  **Networking Sockets** |  **Shared Memory**  
---|---|---  
1. |  Networking Socket programming interface **has** numerous **synchronization** properties. |  Shared memory interface **does** **not** **have** **synchronization** properties.  
2. |  Processes **can** **detect** whenever new data arrives on the network connection, how much data has arrived, and the sender’s information as well. |  Processes **cannot detect** if another process has sent data or made any changes to the data stored in the memory that is being shared.  
3. |  There is a provision for the **processes** to **block** themselves until new data has reached the networking socket. Processes can request for a signal to be sent when the data has been sent completely to unblock themselves. |  There is **no provision** for the processes to **block** themselves and request for a signal for when the data has been delivered.  
4. |  While communicating data in a networking socket, **data** is **copied** from one memory to another multiple times. |  Shared memory interface does not require copying of data multiple times. **Data** is just **updated** in the memory **once** , and is accessible by all processes.  
5. |  Requires a **service call** to be made by the kernel system to start the transfer of data. |  Data transfer can be done in user-mode **without** the kernel system making any **service call**.  
  
## Step-2

The advantages of Networking Sockets are listed below:

• **Data Delivery Detection** : This interface possesses the ability to detect whenever new data arrives, what is the size of the new data and who has sent that data.

• **Blocking of Processes** : Processes can block themselves whilst data is being delivered. They can request for a wake up signal to unblock themselves when data has been delivered completely.

• **Multiple connections** : Processes with a networking socket can approve more than one connection on that socket. Processes can determine when new processes are trying to make a connection as well as when the old processes terminate the connection.

## Step-3

The advantages of Shared Memory are listed below:

• **Fast** : It is a lot faster than networking socket interface.

• **No Data Copied:** Data is just updated once in the common memory. There is no requirement to copy data multiple times.

• **No System Service Calls required:** Unlike in the case of Networking Sockets, communication can be done in user-mode itself, without shifting control to the kernel system to begin the transferring of data.

## Step-4

Networking Sockets are preferred over Shared Memory in cases where it is important to **manage connections** or when **synchronization** of the **sender** as well as **receiver** of the data is mandatory. **Servers** mostly make use of networking sockets to communicate with their client. A socket is set up by the server to listen to client requests. The client builds connection to the same socket to send requests to the client. In this manner, the client can detect whenever a new request is received and by whom was it sent.

## Step-5

Shared Memory is preferred over Networking Sockets when multiple **processes** need **access** to a huge size of **data** , which is **common** to all processes or when a big amount of **data** is required to be **transferred** for certain purposes, but such a large amount of data is difficult to copy multiple times. An example of this is, in offices, all **workstations** connected by a Local Area Network are connected to a shared memory, so that data does not have to be updated multiple times. It is just updated once in the common shared memory an all systems have access to the updated data.


---

# Problem 6
## Step-1

Yes, once upon a time, UNIX systems used disk-layout optimizations based on the rotation position of disk data, but present implementations, including Linux, simply optimize for sequential data access because the performance characteristics of disk may changed substantially in latest years, many enhancements introduced to increase the maximum bandwidth that can be achieved on a disk.

## Step-2

The main **hardware characteristic** takes an advantage in sequential access:

In present systems have capable of high bandwidth and a long pipeline is there between the operating system and disk’s read-write head. Here one local control is there, through that I/O request passed over bus logic to disk drive and then internally to the disk, the controller can accesses cache data and optimize the order of I/O requests.

## Step-3

The rotational optimization is not useful for longer period because an operating system has burden to search the position of the data on such disks, capable of understand the complete geometry. To determine the optimal scheduling of I/O’s here only disk internal logic available.


---

# Problem 7
## Step-1

C makes UNIX highly portable as evidenced by many systems it runs on. It is also faster to write and debug code in a high-level language, allowing UNIX to be modified more quickly than assembly language based operating systems. Of course it runs less efficiently than if it had been written in assembly language, like most other operating systems. It is generally larger than assembly-language operating system too.

The Libraries may also provide more complex version of basic system calls. C language’s buffered file – handling functions are all implemented in the system libraries, providing more advanced control of file I/O than the basic Kernel system calls. The Libraries also provide routines that do not correspond to system calls at all, such as sorting algorithms, mathematical functions and string manipulation routines. Use of some sophisticated features like implementation operating system is quite easily done from the C language without writing any assembly language. The main disadvantage is it is procedural, not object-oriented.


---

# Problem 8
## Step-1

_**fork() exec() :** _

A new process is created by fork() system call; and a new program runs after a call to exec(). A new process may be created with fork() without a new program being run- the new sub process simply continues to execute exactly the same program that the first, parent process was running. Equally, running a new program does not require that a new process be created first. Any process may call exec() at any time. The currently running program is immediately terminated and new program starts executing in the context of the existing process.

_**vfork():** _

Some systems have a system call vfork(), which was originally designed as a lower-overhead version of fork(). Since fork() involved copying the entire address space of the process, and was therefore quite expensive, the vfork() function was introduced.

The basic difference between the two is that when a new process is created with vfork(), the parent process is temporarily suspended, and the child process might borrow the parent's address space. This strange state of affairs continues until the child process either exits, or calls execve(), at which point the parent process continues. 

This means that the child process of a vfork() must be careful to avoid unexpectedly modifying variables of the parent process. In particular, the child process must not return from the function containing the vfork() call, and it must not call exit() 


---

# Problem 9
## Step-1

Reliable delivered message would be best, because transfers are sure to occur but open connections are not needed between the systems. Datagrams are the next best, because they are unreliable. Perhaps streams are another choice if open connection is desired. Sun NFS uses datagrams because reliable delivered messages are not implemented. A datagram is about the only choice for testing the availability of other systems, since they may or may not be able to receive a packet (disallowing the reliable delivered messages).


---

# Problem 10
## Step-1

The organization of architecture-dependent and architecture-independent code in the Linux kernel is designed to satisfy two design goals: to as much code as possible common between architectures and to provide a clean way of defining architecture specific properties and code.

There are different levels of architecture dependence in the kernel, and different techniques are appropriate in each case to comply with the design requirements. These levels include:

**CPU word size and endianess** There are issues that affect the portability of all software written in C, but especially so for an operating system, where the size and alignment of data must be carefully arranged.

**CPU process architecture** Linux relies on many forms of hardware support for its process and memory management. Different processors have their own mechanisms for changing between protection domains, rescheduling processes, managing virtual memory, and handling incoming interrupts.

The Linux kernel source is organized so as to allow as much of the kernel as possible to be independent of the details of these-architecture specific features. To this end, the kernel keeps not one but two separate subdirectory hierarchies for each hardware architecture. One contains the code that is appropriate only for that architecture including such functionality as the system call interface and low-level interrupt management code.

The second architecture specific directory tree contains C header files that are descriptive of the architecture. These header files contain type definitions and macros designed to hide the differences between architectures. They provide standard types for obtaining words of a given length, macro constants defining such things as the architecture word size or page size, and function macros to perform common tasks such as converting word to a given byte-order or doing standard manipulations to a page table entry.

Given these two architecture specific subdirectory trees, a large portion of the Linux kernel can be made portable between architectures. When a 32-bit integer is required, the programmer must use the explicit _int32 type rather than assume than an int is a given size, for example. However, as long as the architecture specific header files are used, then most process and page-table manipulation can be performed using common code between the architectures. Code that definitely cannot be shared is kept safely detached from the main common kernel code.


---

# Problem 11
## Step-1

Linux Kernel has ability to load and unload arbitrary sections of Kernel code 

on demand.

_Advantages_

• Linux’s source code is free, so anybody wanting to write Kernel code is able to compile a modified Kernel and to reboot to load that new functionality.

_Disadvantage_

• Since it is covered by the GPL license Linux Kernel cannot be released with proprietary components added to it, unless those new components are also released under GPL and source code for them is made available on demand.


---

# Problem 12
## Step-1

A conflict – resolution mechanism allows different device drivers to reserve hardware resource and to protect those resources from accidental use by another driver.

Its aims are:-

• To prevent module from clashing over access to hardware resources.

• To prevent auto probes.

• To resolve conflict among multiple drivers trying to access the same hardware.


---

# Problem 13
## Step-1

Linux provides the ability to create threads using clone() system call. When clone() is invoked, it is passed a set of flags that determine how much sharing is to take place between the parent and child tasks. Thus, if clone() is passed the flags CLONE_VM, CLONE_SIGHAND, and CLONE_FILES, the parent and child tasks will share the same file-system information, the same memory space, the same signal handlers, and the same set of open files. Using clone() in this fashion is equivalent to creating a thread in another system, since the parent task shares most of its resources with its child task. 

The lack of distinction between processes and threads is possible because Linux does not hold a process’s entire context within the main process data structure; rather it holds the context within independent subcontexts. Thus, a process’s file system context, file descriptor table, signal-handler table, and virtual memory context are held in separate data structures. The process data structure simply contains pointers to these other structures, so any number of processes can easily share a subcontext by pointing to the same subcontext as appropriate

The arguments to the clone() system call tell it which subcontexts to copy, and which to share, when it creates a new process.


---

# Problem 14
## Step-1

UNIX system typically provides support for multiple Kernel – Level threads per process. But Linux Kernel offered no support for multithreading. A process may make use of and switch between multiple threads that are executed concurrently within the context of the process. Such threads are user level threads.

Threads may be at kernel level. In this case they may be treated by the operating system in much the same way as a process and receive the hardware time sharing, which includes multiprocessor scheduling. User level thread libraries include POSIX pthreads, Mach c-threads and Solaris threads. Kernel level threads may receive special treatment, such as being scheduled to execute on a different processor or using hyper-threading within a processor. This achieves real parallelism that is not achieved with user level threads. Multiple user – level threads that constitute a single – user – level process are mapped into Linux Kernel – Level process that share the same group ID.


---

# Problem 15
## Step-1

In Linux, creation of a thread involves only the creation of some very simple data structures to describe the new thread. Space must be reserved for the new thread’s execution context, its saved registers, its kernel stack page, its dynamic information such as its security profile, its signal state but no new virtual address space is created.

Creating this new virtual address space is the most expensive part of the creation of a new process. The entire page table of the parent process must be copied, with each page being examined so that copy-on-write semantics can be achieved and so that reference counts to physical pages can be updates. The parent process’s virtual memory is also affected by the process creation: any private read/write pages owned by the parent must be marked read-only so that copy-on –write can happen.

Scheduling of threads and processes also differs in this respect. The decision algorithm performed when deciding what process to run next is the same regardless of whether the process is a fully independent process or just a thread but the action of context switching to a separate process is much more costly than switching to a thread. A process requires that a CPU’s virtual memory control registers be updated to point to the new virtual address space’s page tables.

In both cases-creation of a process or context switching between processes the extra virtual memory operations have a significant cost. On many CPU’s, changing page tables or swapping between page tables is not cheap; all are part of the virtual address translation look-aside buffers in the CPU must be purged when the page tables are changed. These costs are not incurred when creating or scheduling between threads.


---

# Problem 16
## Step-1

Completely Fair Scheduler (CFS) is a scheduler used by Linux Operating System. The CFS introduced by Linux replaced the traditional concept of UNIX process scheduler. Both of them use different scheduling methods for aligning processes on processor. 

**Completely Fair Scheduler**

This scheduler provides a choice of variable time slices, depending upon the process requirement. Similarly, priority is another core variable used by this scheduler. 

Hence, instead of allotting fixed time duration to each new process the scheduler designates a specific proportion of the processors time to each process undergoing execution. 

This depends on two different variables for scheduling. One is **Target Latency** ; that is the length of time during which the process must run at least once. Other is **minimum granularity** ; that is the minimum amount of time that is assigned to the process on the CPU.

**Process Scheduler (UNIX)**

Unlike CFS, process scheduler being used by UNIX provides a fixed time-slot to each-and-every process that enters the system. The process runs for dedicated time slot and gets replaced by any of the higher prioritized process in queue. 

Thus traditional approach takes only two things in account; time and priority. 

Understanding the concepts of these two it becomes easier to analyze that how CFS gives fairer results over the traditional process scheduler used by UNIX.

## Step-2

**Fairness in Scheduling**

Completely Fair Scheduler guarantees fairness and optimum efficiency when resources are utilized in the best possible way and corresponding costs for switching contexts are also minimized. 

For this, the scheduler always takes care of weight readjustment methods each time the systems enters a multi-threaded environment, so that no process stays idle for longer times span and switching processes also gets easier. 

Moreover, the time allotted to each process stays proportional to the number of processes that are being served by the CPU. This way, each process gets optimum possible time from CPU. 


---

# Problem 17
## Step-1

**Completely Fair Scheduler:**

This scheduler provides a choice of variable time slices, depending upon the process requirement. Similarly, priority is another core variable used by this scheduler. Hence, instead of allotting fixed time duration to each new process the scheduler designates a specific proportion of the processors time to each process undergoing execution. 

**Variables in CFS**

CFS depends on two different variables for scheduling.

• First variable is **Target Latency** ; that is the length of time during which the process must run at least once. 

• Second one is **minimum granularity** ; that is the minimum amount of time that is assigned to the process on the CPU.

Depending on these two, a set of N processes that are to be executed; each process would be allotted to the processor for 1/N time duration. Whereas, priorities are to be allotted on the basis of process weight; the nice value of any process. 

The smaller it weighs, the higher becomes its priority; and vice-versa. 

## Step-2

**Problems with extreme values of variables**

This seems fair, but the problem might arise if the number of processes becomes excessively large. In that case CPU will have to switch the tasks very frequently as the target latency will be very small. This would make the process rather inefficient. 

This can be understood with a small example.

Suppose the scheduler has queued two processes of equal weight and priority; the target latency being 20 milliseconds.

In this case, initially the first process would run for 10 milliseconds and discontinue the execution and allows the second process to enter. Then the second process also runs for 10 milliseconds and it goes like this. 

Similarly, if the numbers of processes grow to 20 processes; each process would get a millisecond of execution span each time the target latency repeats itself. 

## Step-3

In the above example suppose that there are 2000 processes that need to be served. Now the target latency would be very low and consequently the switching cost would be very high. 

This disadvantage can be overcome using the second variable; **minimum granularity**. This will ensure that the process runs at least for the specified time regardless of what the target latency is. 

Thus setting target latency to a very high value will decrease the switching cost but decreases the fairness too. Setting it to a very low value would increase the switching cost. 

Same is the thing with the minimum granularity. Higher values will lead to the decreased fairness as the processes will take long time to execute. The opposite would make the switching cost higher even if the number of processes is nominally limited. 


---

# Problem 18
## Step-1

**Soft real-time scheduling:**

A scheduling technique where performance is not guaranteed and processes run out of data, when they are alarmed for optimization in preferences; such a scheduling technique is named as soft real-time scheduling. However, kernel does not give any guarantee about how quickly a real time process will be scheduled once it has come into the runnable state.

Linux offers real time task processing facility via two scheduling algorithms; First Come First Serve and Round Robin scheduling.

## Step-2

**Missing feature of real time programming**

1\. Due to the soft scheduling of tasks, the scheduling of the task cannot be guaranteed once it is in the runnable state. This might cause tasks to wait eternally in the worst case. This shortcoming might make the real time processing meaningless. 

2\. The Linux system is not capable of providing response times of those worst-case or failure cases to any external events. Again, this can be cured by introducing hard real-time scheduling.

3\. In Linux kernel the tasks like system trap, external request for resource etc. may try to access the same data structure at the same time. This could lead to data corruption and many other acute consequences. Linux, however, provides mechanisms to stop that but they are costly and might not be available to all due to their cost.

## Step-3

**Adding missing features to kernel**

The features mentioned above can be added to kernel with some extra effort and implementation cost. 

1\. Implementing a new scheduling policy would help overcome the problem of indefinite waiting of task. 

Newer versions of Linux provide scheduling classes that wrap scheduling policies and are implemented as module. These modules can be used as enhancements to the traditional system. 

2\. A few changes in the data structure will make sure that no two requests for resources be served at the same time. 

Moreover, introduction to appropriate interrupts would make sure that a system error is generated in case of system failure. 

## Step-4

**Cost/Downsides of enhancements**

The shortcomings of the system can be overcome. The implementation has been described in the previous section. Nonetheless, the implementation comes up with extra cost and sometimes might not be practical at all.

1\. Introducing the new scheduling algorithms and their implementation can be quite complex at times.

2\. Changes in data structure might be quite costly as huge changes might be required to facilitate the system with the mentioned features.

3\. Estimating the cost and risk of such implementation is quite a challenging task as the changes are related to kernel of the system itself. 

The implementations, moreover, could lead to reduced efficiency and less scalability of available resources. 


---

# Problem 19
## Step-1

The stack is created at the top of user-mode virtual memory; it grows downward towards lower-numbered addresses. It includes copies of the arguments and environment variables given to the program in the exec() system call. The other regions are created hear the bottom and of virtual memory. The sections of binary file that contain program text or read–only data are mapped into memory as a write – protected region. Writable initialized data are mapped next; then any uninitialized data are mapped in as a private demand – zero – region.

When a process tries to read a page in such (demand – zero memory) a region, it simply gives back a page of memory filled with zeros.


---

# Problem 20
## Step-1

A virtual memory region is also defined by its reaction to writes. The mapping of a region into the process’s address space can be either private or shared. If a process writes to a privately mapped region, then the pager detects that a copy-on–write is necessary to keep changes local to the process. In contrast, writes to a shared region will be visible immediately to any other process that is mapping that object.


---

# Problem 21
## Step-1

300-21-13E

Linux system libraries provide many types of functionality. At the simplest level, they allow applications to make Kernel – system – service requests. The libraries take care of collection the system – call arguments and if necessary, arranging those arguments in the special form to make the system call.

There are a number of reasons for keeping functionality in shared libraries

rather than in the kernel itself. These include:

**Reliability** Kernel-mode programming is inherently higher risk than user-mode programming. If the kernel is coded correctly so that protection between processes is

enforced, then an occurrence of a bug in a user-mode library is likely to affect only

the currently executing process, whereas a similar bug in the kernel could conceivably

bring down the entire operating system.

**Performance** Keeping as much functionality as possible in user-mode shared libraries

helps performance in two ways. First of all, it reduces physical memory consumption:

kernel memory is non-pageable, so every kernel function is permanently resident in physical memory, but a library function can be paged in from disk on demand

and does not need to be physically present all of the time. Although the library

function may be resident in many processes at once, page sharing by the virtual

memory system means that at most once it is only loaded into physical memory.

Second, calling a function in a loaded library is a very fast operation, but calling a

kernel function through a kernel system service call is much more expensive. Entering

the kernel involves changing the CPU protection domain, and once in the kernel,

all of the arguments supplied by the process must be very carefully checked for correctness: the kernel cannot afford to make any assumptions about the validity of

the arguments passed in, whereas a library function might reasonably do so. Both

of these factors make calling a kernel function much slower than calling the same

function in a library.

**Manageability** Many different shared libraries can be loaded by an application. If new functionality is required in a running system, shared libraries to provide that functionality can be installed without interrupting any already-running processes. Similarly, existing shared libraries can generally be upgraded without requiring any

system down time. Unprivileged users can create shared libraries to be run by their

own programs. All of these attributes make shared libraries generally easier to manage than kernel code. There are, however, a few disadvantages to having code in a shared library. There are obvious examples of code which is completely unsuitable for implementation in a library, including low-level functionality such as device drivers or file-systems. In general, services shared around the entire system are better implemented in the kernel if they are performance-critical, since the alternative—running the shared service in a separate process and communicating with it through interprocess communication—requires two context switches for every service requested by a process. In some cases, it may be appropriate to prototype a service in user-mode but implement the final version as a kernel routine.

Security is also an issue. A shared library runs with the privileges of the process calling the library. It cannot directly access any resources inaccessible to the calling process, and the calling process has full access to all of the data structures maintained by the shared library. If the service being provided requires any privileges outside of a normal process’s, or if the data managed by the library needs to be protected from normal user processes, then libraries are inappropriate and a separate server process (if performance permits) or a kernel implementation is required.


---

# Problem 22
## Step-1

**Journaling:**

Journaling is a feature supported by file systems in which, encountered modifications in the file system are written on a journal. These modifications include alterations in the operating system, completion of transactions and other tasks. 

Journal entries related to the transactions might later be replayed through the file system. Journaling is typically supported by Linux ext3 file system. 

## Step-2

**Benefits of journaling**

Below are listed some of the dazzling benefits of having journaling in file systems:-

• Once committed, a transaction on the journaling supported file system can be recovered even after sudden system crash or failure. This helps in keeping the data consistent and in synchronization. 

• These file system are typically faster and more reliable as compared to other file systems. The reason is that applying the updates on the in-memory journal is easier and faster than the typical file systems without journaling facility. 

• Follows sequential Input/output rather than going for any random process. That means the cost of seeking and writing as in the random I/O system is completely taken care of and is gone because of the sequential access.

• The changes can be applied asynchronously to the places where they are required in the data structures.

## Step-3

As discussed, ext3 Linux File System goes with the synchronous sequential write operations rather than the random ones. This minimizes the cost for write operations. A counterpart is played when the file system replays the modifications done in asynchronous manner and that too in random access manner. 

## Step-4

The resulting outcomes enhance the performance of metadata operations in the file system rather than being beneficial for the file data. This performance enhancement is the main reason behind ext3 supporting journal for metadata and excluding file data from this privileges.


---

# Problem 23
## Step-1

To the user, file system appears as a hierarchical directory tree that obeys UNIX semantics. Linux uses an abstraction layer to manage multiple different file system. Device – oriented, networked, and virtual file system are supported. Device oriented file system access disk storage through a page cache that is unified with the virtual memory system. Linux Extended file system (extfs) is a standard disk-file system deals with disk operations. The Linux process file system, known as the /proc file system, is an example of a file system whose contents are not actually stored anywhere but are computed on demand according to user file I/O requests. With these different file systems Linux is capable of improving the scalability, file allocation, etc.


---

# Problem 24
## Step-1

The setuid feature of Linux allows the program to run with extra privileges than that of the user programs. In this there are two different UIDs of the process. One is that of the user that runs the program and other is that’s of the owner of the file. This feature makes it possible to execute special tasks leaving the security intact. 

There are two ways in which Linux implements the setuid feature. 

• This method was initially introduced to provide a possibility of switching among most effective UID, among the available ones. For this, the operating system allows and running program to pause the process and let down to a lower level. 

This lower level helps the program in getting unique effective UIDs repeatedly as long as the program finishes execution. Hence, this method minimized the total execution time and security risks for the program, which could have been messed up if any security loopholes occurred.

• The second method was introduced to minimize the efforts of operating system in handling typical switches between several UIDs. In this method, Linux Operating System provides no access privileges to a user while execution process in going on. Hence, no processes can be suspended or killed during their execution time.

## Step-2

**Difference between Linux and svr4 setuid:**

Linux setuid feature is very much similar to the one of the svr4 as both of these implement UNIX. Nonetheless there are a few differences in the ways that they implement the feature in. 

1\. Linux uses the file system ID of the process in the setuid process. This is usually equal to the effective user ID. This sets the file system ID of the process as well. If there is a nuance between the new and the old UID, the process will be forbidden from leaving the core dumps. 

2\. The environment variables used in svr4 are slightly different from the ones that are used in Linux system. This makes the setuid syntax of Linux and working a bit different from the one that is used in svr4. 


---

# Problem 25
## Step-1

300-21-16E

The open availability of an operating system’s source code has both positive

and negative impacts on security, and it are probably a mistake to say that it is definitely a good thing or a bad thing. Linux’s source code is open to scrutiny by both the good guys and the bad guys. In its favor, this has resulted in the code being inspected by a large number of people who are concerned about security and who have eliminated any vulnerabilities they have found. On the other hand is the “security through obscurity” argument, which states that attackers’ jobs are made easier if they have access to the source code of the system they are trying to penetrate. By denying attackers information about a system, the hope is that it will be harder for those attackers to find and exploit any security weaknesses that may be present.

In other words, open source code implies both that security weaknesses can be found

and fixed faster by the Linux community, increasing the security of the system; and those attackers can more easily find any weaknesses that do remain in Linux. There are other implications for source code availability, however. One is that if a weakness

in Linux is found and exploited, then a fix for that problem can be created and distributed very quickly. (Typically, security problems in Linux tend to have fixes available to the public within 24 hours of their discovery.) Another is that if security is a major concern to particular users, then it is possible for those users to review the source code to satisfy themselves of its level of security or to make any changes that they wish to add new security measures.


---

