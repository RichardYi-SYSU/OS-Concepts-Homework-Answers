# Problem 1
## Step-1

**Virtualization** means creating abstract hardware of a single computer and allowing multiple OS to run in separate environment. **Virtual Machine** is one such method of achieving virtualization. 

Virtual machine implementation involves several components. At the base is **the host** , underlying hardware system that runs the virtual machines. The **Virtual machine manager (VMM)** runs virtual machines by providing an interface that is identical to the host. 

Several VMM software tools like VMware ESX or Citrix XenServer are available which runs virtual machines on the host. VMM is commonly known as **Hypervisor**.

## Step-2

There are different ways to implement virtual machines.

1\. Hardware based support that provides support for virtual machine creation and management. These are generally known as **type 0 hypervisors**

Example: - IBM LPRS, Oracle LDOMs generally found on mainframes and such large servers

2\. Operating system like software built to provide virtualization. These VMMs are called **type 1 hypervisors**

Example: - VMware ESX or Citrix XenServer or Joyent SmartOS

3\. Applications that run on standard operating system but provide VMM features to guest operating system are called **type 2 hypervisors**

Example: - VMware Workstation, Parallels Desktop or Oracle VirtualBox

## Step-3

Explanation of three types of traditional virtualizatiuon:

**Type 0 Hypervisors**

These types of Virtualization are essentially a hardware feature. Operating system don’t need to anything special to use virtualization features. The VMM is loaded in the firmware and loaded at boot time. 

Some characteristics are as below:

1\. Hardware is available as partitions or domains and each OS runs in its own partition. For example if a hardware is split into four partitions each with dedicated CPUs , memory and I/O Devices, four virtual systems can be created.

2\. In case of limited I/O devices, hypervisor manages shared access or grants all devices to control partition. In control partition guest operating system provides services via daemons to other guests. 

3\. Since the type 0 hypervisor can run multiple guest operating system, one in each partition, all the guest operating system can in turn serve as VMMs. This is because each guest OS is itself running on native hardware i.e. partition. This is called virtualization-within-virtualization, which is unique to type 0 hypervisors and not available in any other hypervisors. 

The same can be depicted in the figure below:

Guest |  Guest |  Guest |  Guest |  Guest |  I/O Devices  
---|---|---|---|---|---  
Guest OS1 |  Guest OS2 |  Guest OS3 |  Guest OS4 |   
CPU and Memory |  CPU and Memory |  CPU and Memory |   
Firmware ( VMM / Hypervisor 0) |   
  
## Step-4

**Type 1 Hypervisors**

These types of virtual memory managers are commonly used in data centers and are called data center operating systems. Such operating systems run on native hardware but do not provide system calls and other interfaces for the running programs. Instead, they create, run, and manage guest operating system.

Some features are as mentioned below:

1\. Type 1 hypervisors run in kernel mode. They use multiple modes to give guest operating system their own control and improved performance, where ever host CPU allows. 

2\. They implement device drivers for the hardware they run on and also provide OS features like CPU Scheduling, memory management, I/O management, protection and security.

3\. These are usually closed source and commercially available. Hypervisors 1 have ability to consolidate more operating systems and applications onto fewer systems. 

In place of using ten systems with 10 % utilization, hypervisor 1 makes it possible to use one system that manages the entire load. 

4\. When the utilization increases guest and applications can be moved to other system live, which is less used. It uses snapshots and cloning to save the states of guests and duplicate those states. 

This is much easier than taking backups and restoring each guest’s state and installing the same via scripts or tools.

## Step-5

**Type 2 Hypervisors**

Type 2 hypervisors are application level virtual managers. This type of VMM is simply another process run and managed by the host. The features of this type are as below:

1\. The host here is unaware of the visualization taking place. They can run on variety of general purpose operating system and running them requires no changes to the host operating system.

2\. These hypervisors can be used to test non-native operating system without replacing the native operating system. 

3\. While running type 2 hypervisors the user needs administrative privileges to access the hardware assistance features of CPUs.

Some examples of tools that provide this kind of virtualization are Oracle VirtualBox and VMWare. 


---

# Problem 2
## Step-1

**Virtualization** means creating abstract hardware of a single computer and allowing multiple OS to run in separate environment. **Virtual Machine** is one such method of achieving virtualization. 

There are different ways to implement virtual machine. Most traditional techniques are Type 0, 1 and 2 hypervisors. 

Apart from these, there are few other virtualization techniques that provide virtualization like execution environment but are not virtualization techniques indeed. They are para-virtualization, programming environment virtualization, Emulators, and application containment. 

## Step-2

These techniques are used to provide the virtualization like environment, but do not actually implement virtualization in true sense. They are described in details below:

1\. **Para-virtualization** is a technique in which the guest operating system is modified to work in sync or cooperation with the VMM.

• Here, instead of tricking the guest OS into thinking that it has the system to itself, the para-virtualization offers a system identical to the guest OS. The guest must be modified to run on a para-virtualized system. 

• In such systems the resource utilization is very efficient. For the I/O devices the VMM and guest use shared memory buffer, where the read and write data are placed. The memory management in this technique is done using hypercall. 

• Each guest has its own set of page tables and hypercall is sent from guest OS to VMM whenever the host page table requires update. This is not true virtualization because the guest OS. 

2\. **Programming environment virtualization** refers to the technique in which the VMMs do not virtualize or abstract the real hardware but instead they create an optimized virtual system.

Example: - Oracle Java, Microsoft .Net

• In this method, the programming environment is virtualized not the hardware. Here the programming language is designed to run within a custom built virtualized environment. 

• Virtual environment can be defined as based on APIs, that provide set of features that we want to have available for particular language and programs written in that language.

• The above means that Java programs are written and compiled on Java Virtual Machine (JVM) and then JVM is compiled to be a host program. Thus once a java code is written and compiled on JVM, it can run on any machine which has a JVM available on it. 

3\. **Emulators** allow applications written in one hardware environment to run on a totally different environment or another CPU.

Virtualization means running applications designed for one operating system to run on different operating system, but on the same CPU.

• If an application needs to run on a different CPU, then it becomes necessary to translate all source CPU’s instructions and convert them into equivalent instructions of target CPU. This type of environment is called **Emulated environment**.****

• Emulation is very useful when the host system has different architecture than the guest in terms of hardware and software. So if a company’s old hardware is replaced by a new one the old programs can still be used using an emulator. This increases the life of program.****

Creating an emulator is a challenging deal, because it involves writing an entire CPU in software that can read, parse and simulate all instructions from old system.

4\. **Application Containment** provides virtualization like features by segregating applications from the operating system. Thus they contain applications, making them more secure and manageable.

Example: - Oracle Solaris Zones, BSD Jails, IBM AIX WPARs

• If the applications are all compiled for the same operating system, then a full virtualization is not needed. In such cases one only needs to provide a means or method for various tasks in system. 

• These might be to segregate applications, manage their resource use, application performance and create an easy way to start, stop and manage processes. This is exactly what is done using Application containment.

• In application containment, there are several **containers** or**zones** that create a virtual layer between operating system and applications. In this technique, the hardware is not virtualized. 

Also there is only one kernel installed. But operating system and devices are virtualized. Thus processes within a zone have an impression of being the only process on the system.

## Step-3

As a recapitulation it can be said that the above defined techniques do not conform to all the requirements that are needed to make them true virtualization environments. They simulate the virtualization very closely though. That is why they are not virtualization techniques indeed.


---

# Problem 3
## Step-1

The Term **Virtualization** has many meanings and all aspects of computation are covered in virtualization. **Virtual Machine** is one such method of achieving virtualization. There are three different ways to implement virtual machines.

1\. Add Virtual machine support to the kernel

2\. Providing Hardware features by the CPU

3\. Supporting virtual machine implementation using I/O Devices 

Generally with virtualization guest operating system and applications run in an environment that appears to them as native hardware. Thus virtualization creates abstract hardware of single computer and thus creating an illusion that each of the environments is running using its own dedicated hardware. 

There are several benefits of virtualization; most of them are somehow relevant to the ability to share the same hardware yet run different operating system.

## Step-2

**Benefits of virtualization**

The benefits of virtualization can be detailed as below

1\. The biggest advantage of virtualization is that the host system is isolated from virtual machines and virtual machines are isolated from each other. This means that a virus in the guest virtual machine can affect or damage its operating system but not the host or any other virtual machine. 

As a whole, there is insulation between either two virtual machines and that is why they are safe from each other in terms of work. 

2\. Another advantage of virtualization is that a developer’s workstation can concurrently run multiple operating systems. Such virtual machine facilitates fast porting and testing of the programs across different operating system. 

Moreover, multiple versions of program can run on the same system under different isolated environment. Other than that QA engineers can create their test environment on the same system, where the developers system has been installed and can test their applications.

3\. A dazzling advantage of virtualization is in production data center. These centers make use of system consolidation, which include running two or more autonomous systems in virtual machines on the same system. This is a kind of recourse optimization since there is a physical to virtual conversion.

4\. Cloud computing is possible due to virtualization. In this case CPU, memory and I/O is provided as service to the customers via internet. By using APIs a program can create thousands of virtual machines , all running a specific guest operating system and application , which others can access via internet.


---

# Problem 4
## Step-1

**Virtualization** means creating abstract hardware of a single computer and allowing multiple OS to run in separate environment.

**Virtual Machine** is one such method of achieving virtualization. There are three different ways to implement virtual machines,

1\. Add Virtual machine support to the kernel

2\. Providing Hardware features by the CPU

3\. Supporting virtual machine implementation using I/O Devices 

**Virtual machine implementation** involves several components. At the base is **the host** , underlying hardware system that runs the virtual machines. The **Virtual machine manager (VMM)** runs virtual machines by providing an interface that is identical to the host. 

Several VMM software tools like VMware ESX or Citrix XenServer are available which runs virtual machines on the host.

However the ability to virtualize depends on the features provided by the CPU. If the CPU supports virtualization then only it is possible to write a VMM otherwise it is impossible to achieve virtualization.

## Step-2

VMMs use **trap-and-emulate technique** or **binary translation technique** to implement virtualization. In either technique a **Virtual CPU (VCPU)** is implemented. 

The VCPU does not execute code; it just maintains the current CPU state of the guest operating system. When the guest is context switched on to CPU by VMM, the information from the VCPU is used to load the right context.

**Problems with trap-and-emulate based virtualization**

In a typical dual mode system, there are two modes – user mode and kernel mode. Consequently the guest operating system must also have virtual user mode and virtual kernel mode. 

• But, since it is not safe to allow user level code to run in the kernel, hence both virtual user mode and virtual kernel mode both run in the physical user mode.

• Whenever there is a system call or interrupt or an attempt to execute privileged instructions, there is a transfer from user mode to kernel mode on a real machine. Now the same should also be true for virtual environment. This is achieved using the Trap-and-emulate Technique.

• Whenever a kernel in the guest OS tries to execute a privileged instruction, it results in an error or a **trap** to the VMM on real machine, since the guest OS is in the user mode. 

The VMM gains control and **emulates** or executes the action attempted by the guest kernel and then returns the control to the virtual machine. This is called Trap-and-Emulate method.

Thus it can be seen that privileged instructions create an overhead, which causes the guest to run slowly. Also since CPU is multi-programmed among several virtual machines, it further slows down the virtual machines. Thus time becomes an issue.

Also some CPUs do not have clear cut separation about the privileged and non-privileged instructions making it impossible to implement virtualization on such CPUs for example x86.

## Step-3

**Alternate technique used by VMMs to implement virtualization**

The above problem can be solved by implementing **binary translation technique**. In this technique, if the guest VCPU is in user mode then guest can run its instructions on physical CPU and if guest VCPU is in kernel mode, then VMM examines every instruction. 

Instructions other than special instructions are run natively and special instructions are translated into new set of instructions that perform equivalent tasks.

Binary translation is implemented by translating code within the VMM. The code reads native binary instructions from the guest, on demand and generates native binary code that executes in place of original code.

The replacement code for instructions are cached and if the cache is large enough, this method can greatly improve the performance.


---

# Problem 5
## Step-1

**Virtualization** means creating abstract hardware of a single computer and allowing multiple OS to run in separate environment.

**Virtual Machine** is one such method of achieving virtualization. There are three different ways to implement virtual machines,

1\. Add Virtual machine support to the kernel.

2\. Providing Hardware features by the CPU.

3\. Supporting virtual machine implementation using I/O Devices.

## Step-2

Without some level of hardware support, it is impossible to implement virtualization. The more hardware support available, the more stable virtual system can be built.

Modern CPUs can provide hardware assistance for virtualization in the following ways:

• CPUs can implement special instructions so that binary translations are not needed. 

For example Intel x 86 CPU families has set of instructions called VT-x instructions.

• Modern CPUs can move from Dual mode to multimode processor. For example AMD virtualization technique (AMD-v) is implemented in AMD processors. It defines two modes of operation –host and guest-. 

The VMM can enable the host mode, define all the virtual machine’s characteristics and then switch to guest mode. In guest mode, the guest operating system can see all the devices that are included in the host’s definition of guest.

• The CPUs can also provide guest VCPU with state data structures to load and save guest CPU state, automatically when guest contexts are switched.

• CPUs can also provide Virtual machine control structures (VMCSs). They can manage the guest and host state. Also they are useful during various guest execution controls and exit controls.

• CPUs can also address memory management in virtual environment. CPUs can implement nested page tables in hardware , which allows VMM to fully control the paging , thus accelerating CPU’s translation from virtual to physical addresses

• I/O is another area improved by hardware assistance from CPU.CPUs can provide hardware –assisted DMA (Direct Memory Access). In such case VMM sets up protection domains to tell the CPU which physical memory does belongs to the guest. Next the I/O devices are assigned to these protection domains. 

The hardware transforms the address in the DMA request issued by the I/O Device to the Host physical memory associated with the I/O. Thus the DMA transfers are passed between guest and device without the use of VMM.

• CPUs provide interrupt remapping feature, so that the CPU can automatically deliver the interrupt destined for a guest, to the core of that is running the thread of the concerned guest. 

If interrupt remapping is not provided, then unexpected guest can generate interrupt thereby gaining the control of host system.


---

# Problem 6
## Step-1

If a guest operating system is running on one system and it needs to be migrated from one system to another. If this migration is done without shutting down the process, it is called 

**Live Migration**. 

This kind of live migration is very easily implemented in VMMs as against to general purpose operating system. Firstly a copy of the running guest is made on another system running the same VMM.

This copy occurs with very little noticeable interruption. 

So the logged in users has very little impact. Also the network connections to the guest have least impact.

## Step-2

**Problems with Systems without virtualization**

Following might be the problems which the user would face with the systems without virtualization:

1\. In a general purpose operating system, where virtualization is not implemented, it is impossible to switch. This switching requires warning the users, shutting down the running processes. This also requires moving the binaries and then restarting of processes on new system.

So, with live migration, load of an overloaded system is decreased live and without any disruption. This is not possible without virtualization.

2\. Another thing happens in cases of hardware changes, firmware upgrade, hardware addition, hardware removal or even hardware repair. With virtualization, all the guest operating systems can be migrated off. 

The work can be done and then systems can be migrated back to system. This would not make any major impact on user or remote connections. 

This task would be a tough deal with the systems that do not implement virtualization. 

Thus it can be seen that live migration is possible in systems that have virtualization implemented. That is possible because such systems have well defined interfaces between guests and VMMs.


---

