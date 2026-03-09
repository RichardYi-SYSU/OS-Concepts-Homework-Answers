# Problem 1
## Step-1

**Device Controller**

When the functionality is placed in device controller then it may have some advantages and disadvantages. They are given as follows:

**Advantages:**

1\. If the functionality is placed in device rather than kernel then errors may cause system to crush.

2\. If dedicated hardware with hardcore algorithms is used then the performance of the system may increase.

3\. A kernel can be made simple if the algorithms are removed from it.

## Step-2

**Disadvantages** of placing functionality in device controller are given as follows:

1\. To fix the bugs in the devices a new hardware might be needed.

2\. To improve algorithms in devices is may require an updated hardware or an updated driver for that device.

3\. The performance of the system might get destroyed if embedded algorithms conflict with the use of application.


---

# Problem 2
## Step-1

2481-13-10E SA: 8683

SR: 4578

________________________________________________________________________

**It is possible to implement the handshaking between the host and a controller with only 1 bit, using the following algorithm.**

In this algorithm both host and controller share the same bit to indicate their status.

1\. The host repeatedly reads the status bit until that bit becomes clear. This is known as _busy waiting_ or _polling_.

2\. The host sets the write bit and writes a byte into the data-out register.

3\. The host sets the status bit.

4\. When the controller notices that the status bit is set, it reads the data-out register to get the byte, and does the I/O to the device.

5\. It clears the status bit when I/O completes successfully.

This loop is repeated for each byte.


---

# Problem 3
## Step-1

2481-13-4E SA: 8683

SR: 4578

________________________________________________________________________

Polling I/O can be very fast and efficient than interrupt-driven I/O, if both the device and the controller are fast and if there is significant data to transfer. It becomes inefficient, when it is attempted repeatedly, yet rarely finds a device to be ready for service, while other useful CPU processing remains undone. 

A **single serial port** will perform I/O relatively slow and has small buffer thereby host waits too long before returning to read the bytes. So, we use **Interrupt-driven I/O** which has hardware controller to notify the CPU when the device becomes ready for service, rather than to require the CPU to poll repeatedly for an I/O completion. In the meantime CPU will switch to another task, and it will be notified when the device becomes idle. 

But in case of **front-end processor** such as terminal concentrator can produce a lot of short I/O operations, and interrupting for each one could create a heavy load on the system. So, a well-timed polling loop could reduce that load without wasting many resources through looping with no I/O needed. So, we would use **polling I/O** in this case.


---

# Problem 4
## Step-1

2481-13-8E SA: 8683

SR: 4578

________________________________________________________________________

If I/O operation takes more time to complete, then the polling repeatedly without doing useful work is very inefficient and in the same way if I/O operation takes less time, then using Interrupt driven I/O mechanism is inefficient than polling. So, we will use a **hybrid mechanism** which will use either polling or Interrupt driven I/O depending on time taken to complete I/O operation. In this hybrid mechanism, we will do polling for specified amount of time and after that if the device is still busy, we would set an interrupt and will switch to another task. 

## Step-2

This **hybrid approach** would avoid long busy-waiting cycles. This method would be efficient for both very long and very short busy times. It would be inefficient if the I/O completes in less time after we switch from polling to Interrupt driven I/O due to the overhead of polling and setting up and catching interrupts. **Pure polling** is very fast and efficient in a computer environment where I/O operation takes less time to complete. **Interrupt driven I/O** mechanism is best suited in computer environment where I/O takes more time to complete.


---

# Problem 5
## Step-1

**Direct Memory Access (DMA)**

Direct memory access is the way of CPU to grant authority to I/O module to read from or write to memory direct without any interference. DMA monitors and controls the exchange of information from main memory to I/O devices. With the help of DMA any device can transfer information directly to memory and from memory in spite of using CPU as intermediate.

• It **increases the concurrency** of the system as it makes free the CPU to perform other activities when it itself handles the data transfer from and to the disk.

• It **complicates the system** as it needs DMA controller as a special hardware which manages the data transfer and system bus. These controllers are hard to program as they need source and destination pointers, to know the location of data to be written.


---

# Problem 6
## Step-1

2481-13-13E SA: 8683

SR: 4578

________________________________________________________________________

In general CPU operation is faster than I/O device and CPU sits idle most of the time if I/O takes more time to complete. So, if we increase the CPU speed without increasing the speed of system bus and I/O device will lead to decrease in system performance. To solve this we must increase system bus and device speeds as the CPU speed increases. 


---

# Problem 7
## Step-1

**Stream Driver and Stream Module**

**Stream interface** **driver** provides interaction with the peripherals that **produce** or **consume** **data**. The function of stream interface provides other modules of the software to interact with peripherals.

**Stream modules** are used to process messages which flow through the application and a device driver. It is a pair of **initialized** **queue** and the **kernel** **level** **processes**. Differences between stream driver and stream module are given as follows:

**S. No.** |  **Stream Driver** |  **Stream Module**  
---|---|---  
1. |  Stream drivers are at the end of the stream. Hardware interrupts are handled by device drivers. |  Stream modules are not positioned at the end of the stream and they are not used to solve hardware interrupts.  
2. |  For more than one time drivers can be at the end of the stream. |  A module can only be the part of the any stream.  
3. |  Modules cannot access the structure of user as they don’t have any user context. |  The same is true for stream drivers but it has got the exception of **close** and **open** routines.  
4. |  A stream driver can have multiple streams associated with it. |  The multiplexing technique does not apply to stream modules.


---

# Problem 8
## Step-1

In multiple interrupts, OS can distinguish between high and low – priority interrupts and can respond with the appropriate degree of urgency.

Interrupt priority level enable the CPU to defer the handling of low – priority interrupt without masking off all interrupts and makes it possible for a high – priority interrupt to pre-empt the execution of low-priority interrupt.

Interrupts that are time sensitive and urgent must be given higher priority and the events that are time consuming but not that much urgent can be given lower priority. For example, sometimes in order to use disk efficiently next pending I/O request is given priority compared to a disk read (for the same disk).


---

# Problem 9
## Step-1

A device controller can support memory – mapped I/O. The device control registers are mapped into the address space of the processor. 

_Advantages :_

• The CPU executes I/O requests using the standard data–transfer instructions to read and write the device control register. No separate assembly code is required.

• No separate protection is needed, device memory regions are protected via memory protection schemes.

• Can use all types of instructions to access memory

_Disadvantages :_

Ease of writing to memory – mapped I/O is disadvantage, because a type of software fault is a write through an incorrect pointer to an unintended region of memory, a memory–mapped device register is vulnerable to accidental modification.


---

# Problem 10
## Step-1

**Solution:**

(a)

A **mouse** used with a graphical user interface. 

• **Buffering** may be needed to record mouse movement during times when higher-priority operations are taking place.

• To retrieve buffered data from the mouse, the user needs to set the buffer.

• So that buffering is important, it can hold data in transit of data from a device.

• In mouse,**Spooling** and **caching** are inappropriate. 

• **Interrupt-driven** I/O is also most appropriate.

• Here, **Polling** is the simplest way for an I/O device that communicates with the processor.

## Step-2

(b)

A **tape drive** on a multitasking operating system.

• It is a data storage device that reads and writes data on a magnetic tape.

• A **tape storage** device is used to archive data.

• **Buffering** may be needed to manage throughput difference tape drive and the source or destination of the I/O. 

• **Caching** can be used to hold copies of data that resides on the tape, for faster access.

• **Spooling** could be used to stage data to the device when multiple users desire to read from or write to it.

• **Interrupt-driven** I/O is likely to allow the best performance.

• Also, **Polling** is a behaviour which polls the tape drives with a service.

## Step-3

(c)

A **disk drive** contacting user files.

• A disk drive is used to control the buffer data in a disk called as disk duffer.

• **Buffering** can be used to hold data while in transit from user space to the disk, and vice versa.

• **Caching** can be used to hold disk-resident data for improved performance. 

• **Spooling** is not necessary because disks are shared-access devices.

• **Interrupt-driven** I/O is best for devices such as disks that transfer data at slow rates.

• Here, **Polling** makes no sense; it does not access the external hard disk drives.

## Step-4

(d)

A **graphics card** with direct bus connection, accessible through memory-mapped I/O.

• It is a piece of computer hardware that produces the image to render it on a monitor.

• For example, the video games that are played in a system.

• **Buffering** may be needed to control multiple access and for performance.

• **Caching** and **Spooling** are not necessary due to the fast and shared-access natures of the device.

• **Polling** and **Interrupts** are only useful for input and I/O completion detection, neither of which is needed for a memory-mapped device.


---

# Problem 11
## Step-1

A system that supports multiprogramming requires virtual addresses for accessing memory space via user programs. Simultaneously the systems operating system requires physical address for accessing memory space on account of its operations. This discussion would be concentrating on how these basic Input / Output and operating system operations are carried out.

Consider the concept of operations performed by a system when a user programs requires access through the memory space. The entire process includes some steps as follows:-

• Initially the process starts up with specifying a buffer that is dedicated to transmit data from the device towards application running the program and retransmitting the obtained results to the output device. This buffer typically works on the basis of a logical or virtual address for referencing things from and to memory space.

• Similarly, the system Kernel has a separate buffer that acts as an intermediate between the introduced buffer and itself. A kernel buffer is mandatory for noting down all entries before and after an I/O operation. 

• While accessing the user buffer Kernel translates the virtual address attached with the buffer into corresponding physical address.

• In case of any fault or absence of user buffer, the pages are simultaneously fetched from the systems’ swap space.


---

# Problem 12
## Step-1

Interrupt-controller hardware detects the interrupt, dispatches it to the proper interrupt handler and assigns priority. Interrupt chaining is a technique in which each elements in the interrupt vector points to the head of a list of interrupt handlers when an interrupt is raised, the handlers on the corresponding list are called one by one until one is found that can service the request. This structure compromise between the over head of a huge interrupt table and the inefficiency of dispatching to a single interrupt handler. Another overhead is assigning priorities to the interrupts. Another is disabling interrupts while handling a critical section.


---

# Problem 13
## Step-1

Blocking I/O is necessary when the process will only be waiting for one specific event. Examples a disk, tape or keyboard read by an application program. Non-blocking I/O is useful when I/O may come from more than one source and the order of I/O arrival is not predetermined. Examples window managers that accept mouse movement as well as keyboard input and I/O management programs such as a copy command that copies data from I/O devices, etc.

Non-blocking I/O is more complicated because of the asynchronous I/Os. Also busy waiting is less efficient than interrupt-driven I/O so the overall performance would decrease.


---

# Problem 14
## Step-1

CPU hardware has a wire called the interrupt – request line that the CPU senses after executing every instruction. CPU detects that a controller has asserted a signal on the interrupt – request line, CPU performs a state save and jumps to the interrupt handler routine at a fixed address in memory. Interrupt handler determines the cause of interrupt, perform necessary processing, perform a state restore and execute a return from interrupt instruction to return the CPU to the execution state prior to interrupt. Here also the same might happened. After executing the first piece of code CPU might have detected an interrupt, handled it and then continued to execute the remaining piece of code. This is favorable for higher priority tasks.


---

# Problem 15
## Step-1

Some computer architectures use physical memory addresses for DMA, but other perform DVMA (Director Virtual Memory Access), using virtual address that undergo translation to physical addresses Due to this complexity increases in DMA with an extra translation of virtual address to physical address. . DVMA can perform a transfer between two memory–mapped devices without the intervention of CPU or the use of main memory.


---

# Problem 16
## Step-1

**UNIX:**

UNIX organizes the kernel I/O components actions by operating “shared in-kernel data structures” whereas windows uses “object-oriented message passing”.

• The variety of in-kernel data structures are used in kernel I/O components. 

o It uses the “track network connections”, “character device communications”, and other “I/O activities”.

o UNIX provides the file system access to different types of entities such as “user files”, “raw devices”, and “address space of processes”.

• UNIX encapsulates these differences within a uniform structure by using the object-oriented techniques.

o Windows uses the object-oriented message passing implementation for kernel I/O.

• The message-passing approach simplifies the structure and adds flexibility compare to procedural techniques that shared data structures. 

## Step-2

**Pros of UNIX method:**

• UNIX methods are very efficient method with less overhead and less quantity of data movement.

• The design of this method is simple. So, the loss of data is less.

• It provides quick implementation. But, there is no coordination between other kernel components.

## Step-3

**Cons of UNIX method:**

• UNIX method is difficult to debug the changes. Because, it possible have more side effects and there is no data protection.

• It has difficult “kernel I/O subsystems”, “data structure”, “access routines”, and “locking mechanisms”.

• It is difficult to implement the new kernel I/O methods. Because, it requires new data structure instead of new objects.


---

# Problem 17
## Step-1

**Virtual Clock Implementation**

A clock is an efficient version of FIFO (First In First Out) as pages don’t have to be pushed on the back of the queue. The clock algorithm keeps a track of last examined page frame in the list. If the page frame is not found then fault occurs and a new page frame is loaded in the memory.

// Define Data

// A list of interrupts which is sorted by the earliest first time order

List listOfRequest

Define the necessary variables and a timer to track the last pages examined. A timer countTimer which is interrupt based is declared. Implement while loop and till the loop is true find out the next earliest time in the given list.

// A timer which is interrupt based

Timer countTimer

while (true)

{

//find out the next earliest time in the given list

Timer.setTime = listOf Interrupt.next();

At time timer.setTime an interrupt will be found and this is the time to wait for the interrupt of timer which gives the time to expire timer. Then notify the list of next requested pages.

// At time timer.setTime an interrupt will be found and this is the time to wait for the interrupt of timer which gives the time to expire timer.

notify(listOfRequest.next());

}


---

# Problem 18
## Step-1

_Advantage :_

• It provides a frame work for a modular and incremental approach to writing device drivers and network protocol.

• Modules may be used by different streams and hence by different streams and hence by different devices.

• It support for message boundaries and control information between modules.

• Preferred method for writing protocol and device driver 

_Disadvantage:_

Message are exchanged between queues in adjacent modules, a queue in one module may overflow an adjacent queue.


---

