# Problem 1
## Step-1

2481-16-2E AID: 268

RID: 944 

**Broadcast in Gateways**

If all the broadcast packets are passed between all the routers, it causes a lot of network traffic and increases the burden on network. This is the reason; it would be a bad idea for gateways to pass broadcast packets between networks. So the broadcast packet is not re-send by gateways.

## Step-2

The main advantage for gateways to pass broadcast packets between networks is to save the gateway from having to run special software to watch for broadcast packets (such as network routing information processing software). This can be adopted if broadcast traffic were limited to important data.


---

# Problem 2
## Step-1

**Name Translation Cache for Remote Domains**

**Advantage** : The DNS maintains a local cache of translated names for remote domains. The primary advantage of using name translation caches for systems in remote domains is **performance**. Caching a translated name allows the DNS to resolve the remote domain without requiring a new look up for every access. This speeds up the process and allows the name server to resolve names for systems on other remote domains.

## Step-2

**Disadvantage** : The primary disadvantage of using name translation caches for systems in remote domains is the lack of **consistency**. When a system name on the remote domain is updated, the change is not reflected in the local cache. This results in incorrect or invalid requests to a system which has moved to a new address. The inconsistency can be resolved by adding either invalidation or automatic updates to the name resolution cache process.

A real world example of such an inconsistency is a contact list on a personal cellphone. Consider that a number is saved against a name in the local cellphone. But if the person changes his or her number, the cellphone will now have an invalid number. In this case, the consistency is resolved by the owner of the old number informing the user about change in his number.


---

# Problem 3
## Step-1

**Advantages of circuit switching:**

1\. Circuit switching provides reliable service means that during transmission packets may not loss.

2\. It guarantees that the network resources required for a transfer are reserved before the transmission takes place.

3\. Circuit switching has less overhead for shipping each message.

## Step-2

**Disadvantages of circuit switching:**

1\. Circuit switching requires substantial set-up time and may waste network bandwidth.

2\. It requires a round-trip message to set-up the reservations.

3\. It also might require overprovision resources.

## Step-3

**Application of circuit switching:**

When network resources are used for long time period applications, then the circuit switching is viable strategy because two parties want to communicate each other, establish permanent communication circuit. No one use that circuit until the communication is terminated by two parties.


---

# Problem 4
## Step-1

**Issues in Network – Transparent Systems**

A network transparent system is essentially a distributed system that isn’t biased for local resources against remote resources. Such a system must appear as a single centralized unit to the user. Implementation of such a system faces multiple issues at design stage.

## Step-2

Some major issues encountered are described below:

**Resource Transparency** – The system must avail all resources such as storage devices and processors to all users. Any user cannot simply use a locally located resource of the system, instead using the entire system as a single unit. This allows complete **user mobility** where a user connects to the entire system at any location, instead of a local machine. The **Network File System (NFS)** and the **Andrews File System** can successfully implement transparency for fairly large systems.

## Step-3

**Resource Scalability** – The system must be scalable to allow for fault tolerance, and increasing load on the system while maintaining the centralized appearance for the users. Such a scalable system must adjust for all scalability requirements, such that the performance to load ratio of the entire system remains virtually the same. Some inherent issues within scalability are service demand and centralization.


---

# Problem 5
## Step-1

_**Heterogeneous Process Migration** _:

Several networks contain a variety of machines running different operating systems and provide other resources available on machines which have different architectures than the current machine where the process is executing. Using this computational power requires heterogeneous process migration. Heterogeneous process migration**** is process migration across machine architectures and operating systems. Obviously, it is more complicated than the homogeneous case because it must consider machine and operating specific structures and features, as well as transmitting the same information as homogeneous process migration including process state, address space, and file and communication information. Heterogeneous process migration is especially applicable in the mobile environment where is highly likely that the mobile unit and the base support station will be different machine types. It would be desirable to migrate a process from the mobile unit to the base station and vice versa during computation.

## Step-2

In same operating system, process migration is easy, as the state of the process needs to migrate from one processor to another. This involves moving the address space, state of the CPU registers, and open files from the source system to the destination. However, it is important that identical copies of the operating system are running on the different systems to ensure compatibility. If the operating systems are the same, but perhaps different versions are running on the separate systems, then migrating processes must be sure to follow programming guidelines that are consistent between the different versions of the operating system. Java applets provide a nice example of process migration between different operating systems. To hide differences in the underlying system, the migrated process (i.e., a Java applet) runs on a virtual machine rather than a specific operating system. All that is required is for the virtual machine to be running on the system the process migrates to.


---

# Problem 6
## Step-1

2481-16-17E AID: 76

RID: 944 

**Robust Distributed System**

a) **Failures in a distributed system:**

The distributed system is suffered from various types of hardware failures:

1\. Link failure.

2\. Site failure.

3\. Loss of messages.

To ensure a distributed system is robust, any of the above failures must be detected and system is to be reconfigured so that computation can continue.

## Step-2

b) **Centralized system:**

The centralized system is the I/O, file, process and memory management system. So, the site failure and lost data from storage medium failures can occur in the system. The link failure can occur in the network distributed system only.


---

# Problem 7
## Step-1

**Message Acknowledgements in Distributed Systems**

Distributed Systems in real time scenarios actually are spread over large geographical areas and actually implement the system over a TCP-IP based network such as the internet. Since TCP is primarily implemented using message-acknowledgement-message technique, most distributed systems can easily be implemented using existing protocols instead of designing new and unreliable ones. Hence,![](https://media.cheggcdn.com/study/c1b/c1ba56f7-7979-4f4c-8751-1ff83668ad75/5644-16-9PE-i1.png) it is highly crucial to acknowledge messages in distributed systems for reliability and to avoid redundancy.

## Step-2

The importance of acknowledgements can be easily demonstrated using real world examples. Consider a case where two individuals – John and Jane agree to meet up for lunch, with John informing Jane about the venue later on. Suppose John sends the message to Jane, but it never reaches her. Now, if there is an acknowledgement protocol in place, Jane can simply call and inform John about non-receipt of his message after time-out. Now, if there is no acknowledgement protocol, John will simply assume that Jane has received the message and will probably turn up at the lunch alone.

## Step-3

Another example can be gleaned from simply using the internet. In case a website is active, the request to access is granted and the web-page requested is downloaded to the user’s browser. Now assume that the website is experiencing technical difficulties and is offline. Now, if there is an acknowledgement protocol in place, the browser receives a no-acknowledgement and informs the user of non-receipt of the request message after time-out. Now, if there is no acknowledgement protocol, the browser will simply assume high server load and keep sending blind requests to the website.


---

# Problem 8
## Step-1

If a link fails, this information must be broadcasted to every site in the system, so that the various routing tables can be updated accordingly.

Suppose that a link between A and B has failed. When it is repaired both A and B must be notified.

One can accomplish this notification by continuously repeating the handshaking procedure that is

• Site B is down

• The direct link from A to B is down

• Alternative path from A to B is down

• Message has been lost.

Site A cannot determine which of these events has occurred.

Suppose that site B has failed. When it recovers, it must notify all other sites that is up again, site B then may have to receive information from the other sites to update its local tables


---

# Problem 9
## Step-1

In computation migration, the file that is requested by a process is accessed at home site and could be initiated by an RPC. An RPC uses a datagram protocol to execute a routine on a remote system.

A logical extension of computation migration is process migration. When a process is submitted for execution it is not always executed at the site at which it is initiated. The entire, or parts of it, may be executed at different sites. Computation migration is easy to implement since there is only need to invoke RPC. But in process migration come properties such as load balancing, computation speedup, etc., must be achieved. 

Web server and web client also provides computation migration. Java, it provides a process migration.


---

# Problem 10
## Step-1

Most widely adopted protocol stack is TCP/IP model, which has been adopted virtually by all internet sites. The TCP/IP protocol stack has fewer layers than ISO model. Theoritically, because it combines several function in each layer, it is more difficult to implement but more efficient than ISO working. TCP/IP application layer identifies several protocols in widespread use in internet, including HTTP, FTP, Telnet, DNS, and SMTP. The transport layer identifies the unreliable, connectionless User Data Protocol and reliable, connection – oriented transmission control Protocol (TCP). The Internet Protocol (IP) is responsible for routing IP Datagram through the Internet. The TCP/IP model does not formally identify a link or physically layer, allowing TCP/IP traffic to run across any physically network.

Thus a model with few layers is difficult to implement but efficient by abstracting functions of several layers into few layers.


---

# Problem 11
## Step-1

2481-16-18E AID: 76

RID: 944 

**Network Performance**

Doubling the speed of the systems on an Ethernet segment results in decreased network performance because, the systems with more speed will send more number of packets in short amount of time (For example, a system can send 1000 packets in 1 unit of time, if the speed of the system is doubled then the system can send 1000 packets in 0.5 units of time).

As the number of packets travelling in the network increases the rate of collisions increases. If the rate of collisions in the network increases, the performance of the network decreases. 

So, if the increase in the speed of the systems on an Ethernet segment will result in decrease of network performance.

## Step-2

The problem can be solved by increasing the number of networks with fewer systems per network (because the rate of collision decrease as the number of packets travelling in the network will be reduced with fewer systems on the network). 


---

# Problem 12
## Step-1

300-16-5E

Gateways and routers have dedicated hardware device that run code out of firmware because gateway uses dynamic routing method to reach any hosts on the rest of the network. Dynamic routing is the most complicated to set up and run; however, it is the best way to manage routing in complicated environments.

A router is the entity within the computer network responsible for routing messages. A router can be a host computer with routing software or a special - purpose device. Either way, a router must have atleast two network connections, or else it would have nowhere to route message. A router decides whether any given message needs to be passed from the network on which it is received to any other network connected to the router

Due to the use of dedicated hardware devices for routers and gateways, the main purpose of routing and message passing is served within less time. But they won’t serve like general-purpose computers(computations, processing applications, etc).


---

# Problem 13
## Step-1

Name-server doesn't require local tables to be updated when a machine enters or leaves the system. Because all information is centralized it is easier to maintain the look-up table.

Name-server is a problem if the name-server crashes or is cut-off from the network. 

Suppose if a primary name server crashed. It is possible that no host would be able to have their addresses resolved, making them all unreachable. The solution is to use secondary, backup name servers that duplicate the contents of the primary server. Caches can be used to store frequently requested host information to cut down on network traffic. This method also requires less network traffic. 


---

# Problem 14
## Step-1

This is by far the preferred option for the majority of websites. It is flexible,

expandable and easier to manage on a day-to-day basis. Hierarchical organization uses a number of sub-directories stored at the next level down from the website’s root directory. Connected files, grouped either by their file type (for example GIF, PDF) or by their relevance to each other (e.g. business plan 2001), are stored together in their own directory. On the left is an example of a simple architecture for a website. The root file (index.htm) is the homepage that is automatically served when the user requests a web URL containing only the website’s DNS name. The files listed underneath the homepage’s title are also stored in the root directory but are accessed by links from other pages. In the example, other directories have been set up to contain related files. Within the library directory, there are a number of sub-directories for HTML, PDF, RTF and plain-text documents. All images for the website have been grouped together. Within this directory could be many subdirectories for specific areas within the website. It is a good idea to establish a section of the directory structure as a central images repository to ensure that images used through the website are only saved once. Such images could include the organization’s logo graphic, navigational button images, and so on.


---

# Problem 15
## Step-1

One of the most important features of TCP is reliable end-to-end data delivery. In order to provide reliability, TCP must recover from data that is damaged, lost, duplicated, or delivered out of order by the Network layer. TCP uses the Positive Acknowledgment Retransmission (PAR) scheme for achieving reliability. Figure 2, below, shows the PAR scheme, where all data and acknowledgments are received as expected. Data is sent only after previously sent data has been acknowledged. 

****

****

****

****

****

**Figure 2:** PAR scheme illustrating recovery from lost data.

TCP implements PAR by assigning a sequence number to each octet that is transmitted and by requiring a positive acknowledgment (ACK) from the receiving TCP module. If the ACK is not received within a time-out interval, the data is retransmitted. At the receiver TCP module, the sequence numbers are used to correctly order segments that may have arrived out of order and to eliminate duplicates. Corruption of data is detected by using a checksum field filled in the TCP packet header. Data segments that are received with a bad checksum field are discarded. 

Disadvantage is more overhead.


---

# Problem 16
## Step-1

Dynamic routing is the most complicated to setup and run, it is best way to manage in complicated environments. UNIX provides both fixed routing for use on hosts within sample networks and dynamic routing for complicated network environments. It is also possible to mix the two. Within a site, the hosts may just need to know how to reach the system that connects the local networks to other networks such node known as gateway. Each individual host has a static route to the gateway, although the gateway itself uses dynamic routing to reach any host on the rest of the network.

## Step-2

When network path A to B is fixed for long time period of applications, then use virtual routing is beneficial instead of dynamic routing, because the virtual routing fixed routing messages from A to B will be delivered in the order in which they are sent.


---

# Problem 17
## Step-1

Import **java.lang** , **java.net** , **java.io** packages into the program.

The IP addresses of the following host names:

• [www.wiley.com](http://www.wiley.com/) 208.215.179.146

• [www.cs.yale.com](http://www.cs.yale.com/) 128.36.229.30

• [www.javasoft.com](http://www.javasoft.com/) 192.18.97.48

• [www.ietf.org](http://www.ietf.org/) 209.173.53.180


---

# Problem 18
## Step-1

In general, originators of request/response transactions are free to use the transport they assume is the best in a given situation. However, since TCP has a larger footprint on resource usage than UDP, engines using HTTP over TCP may choose to switch back to UDP by refusing new TCP connections whenever necessary (e.g. too many open TCP connections).

TCP is a stream protocol, while UDP is a datagram protocol. That is to say, TCP establishes a continuous open connection between a client and a server, over which bytes may be written--and correct order guaranteed--for the life of the connection. However, bytes written over TCP have no built-in structure, so higher-level protocols are required to delimit any data records and fields within the transmitted bytestream. 

UDP, on the other hand, does not require that any connection be established between client and server; it simply transmits a message between addresses. A nice feature of UDP is that its packets are self-delimiting--each datagram indicates exactly where it begins and ends. A possible disadvantage of UDP, however, is that it provides no guarantee that packets will arrive in-order, or even at all. Higher-level protocols built on top of UDP may, of course, provide handshaking and acknowledgements. 


---

# Problem 19
## Step-1

Making processors and storage device transparent to the user are.

• The user interface of a transparent distributed system should not distinguish between local and remote resources.

• User mobility i.e. a transparent distributed system facilitates user mobility by bringing over the user’s environment to whenever she log in.

_Disadvantage_

* Fault Tolerance: - It may be communicate fault, machine failure storage –

device crashes, and decays of storage media.

* Scalability: - The capability of a system to adapt to increased service 

load. Systems have bounded resources and can become 

completely saturated under increased load.


---

# Problem 20
## Step-1

**Distributed File System**

A DFS allows the following advantages over file system in centralized system:

• DFS allows sharing physically and logically on separate systems. It allows data to be accesses at any place of the world.

• DFS is a **classical** model of **file** **system** and its purpose is to enhance sharing of files.

• It supports **location** **independent** systems.

• It does not support **automatic** **migration** of a file from one system to another file.

• It separates the **naming** **hierarchy** from that of the hierarchy of the storage devices.

• It provides better file abstraction.


---

# Problem 21
## Step-1

A DFS is a file system whose clients, servers, and storage devices are dispersed among the machines of a distributed system. Both NFS and AFS deal with multiclient database applications but AFS possesses features like uniform name space, location-independent file sharing, client-side caching with cache consistency, and secure authentication via Kerberos. It is scalable. It also includes server-side caching in the form of replicas, with high availability through automatic switch over to a replica if the source server is unavailable.


---

# Problem 22
## Step-1

AFS is a featured - rich DFS characterized by location independence and location transparency. AFS and NFS both provide a single uniform namespace that is independent of storage location, thus providing location independence.

A client workstation can access any file in the AFS namespace using the same name thus providing location transparency .But in NFS file names may be different on each client depending on where the exported directory is mounted on each client.


---

# Problem 23
## Step-1

Most of the current DFS provide a static, location – transparent mapping for user – level name. These systems however do not support file migration; i.e. changing the location of a file automatically is impossible. Hence location independence is irrelevant for these systems.

Location-transparent DFS is good enough in systems in which files are not replicated. Location-independent DFS is necessary when any replication is done.


---

# Problem 24
## Step-1

Since the system is totally reliable, a stateful approach would make the most sense. Error recovery would seldom be needed, allowing the features of a stateful system to be used. If the network is very fast as well as reliable, caching can be done on the server side. On a slower network caching on both server and client will speed performance, as would file location independence and migration. In addition, RPC-based server is not needed in the absence of failures, since a key part of its design is recovery during networking errors. Virtual-circuit systems are simpler and more appropriate for systems with no communication failures.


---

# Problem 25
## Step-1

A stateful server loses all its volatile state in a crash. Ensuring the graceful recovery of such a server involves restoring this state, usually by a recovery of such a server involves restoring this state, usually by recovery protocol based on a dialog with clients

The Cache Manager maintains local copies of remotely accessed files. This is accomplished in the cache by breaking files into chunks of up to 64k (default chunk size). So, for a large file, there may be several chunks in the cache but a small file will occupy a single chunk (which will be only as big as is needed). A "working set" of files that have been accessed on the client is established locally in the client's cache (copied from fileserver(s)).

If a fileserver crashes, the client's locally cached file copies remain readable but updates to cache files fail while the server is down.

Also, if the AFS configuration has included replicated read-only volumes then alternate fileservers can satisfy requests for files from those volumes.


---

# Problem 26
## Step-1

The local cache can handle a substantial number of the remote accesses efficiently when caching is used. Capitalizing on locality in file-access pattern makes caching even more attractive. Thus most of the remote accesses will be served as fast as local ones. Servers are contacted occasionally. Hence server load and network traffic are reduced, and potential for scalability is enhanced.

Client side caching needs dynamic data replication, whereby each client dynamically defines its own data space of interest. Caching aims to avoid disk-traffic and is done on the server-side only, based on buffering of frequently accessed disk blocks are pages.

_Disadvantages_

• The cache consistency problem is the major drawback of caching.

• Caching will confer a benefit, execution should be carried out on machines that have either local disks or large main memories. Remote access on diskless small-memory-capacity machines should be done through the remote-service method.

• In caching, since data are transferred in masses between the server and client rather than in response to specific needs of a file operation; the lower inter machine interface is different from the upper-user interface. The remote service paradigm is just an extension of the local file-system interface across the network. Thus, the inter machine interface mirrors the local user-file-system interface.


---

# Problem 27
## Step-1

**Andrew File System**

AFS was designed to provide support to a lot of clients. Three techniques which make this system scalable are described as follows:

1\. **Caching** : It performs caching on files and provides name translations and thus limits the number of operations which is sent to the server.

2\. **Total File Caching:** Whenever a file is opened the contents of the file is sent to the client and then no interactions with the server are required.

3\. **Callbacks** : The responsibility of the server is to revoke the old copies of files. Clients can use the cached data as many times as they want without making any request to the server for files again and again.


---

# Problem 28
## Step-1

**Mapping Objects to Virtual Memory**

A portion of virtual memory which is assigned a **byte-for-byte** association with some parts of any file is called as memory mapped file. **Benefits** of mapping an object to virtual memory are given as follows:

1\. The mapping **increases the I/O performance** when used for large files and for small files it may be wastage as it increases the slack space.

2\. Memory mapped file access is **faster** than direct accessing the files.

3\. Another benefit of this is that it does lazy loading which in turn uses the **small** amount of **RAM** even if the size of the file is larger.

4\. The files which are loaded one entire page at a time by using memory mapped files. So, it provides **file management of pages**.

## Step-2

Memory mapped files have some **drawbacks** also which are described as follows:

1\. **I/O** **performance** is costly because it increases memory copying and system call overhead.

2\. Memory mapped files causes minor **page faults** whenever the cache loads a block of data which in turn increases the cost.

3\. Another drawback is that files larger than given **address space** can map only some portions at a time which makes it complicated to read the file.


---

# Problem 29
## Step-1

**Andrew File System (AFS) and Network File System (NFS)**

Andrew file system has the servers of files and client computers whereas the network file system maintains the client and server aspect of AFS. The differences between the two are given as follows:

**S. No.** |  **AFS** |  **NFS**  
---|---|---  
1. |  It contains the client computers and file servers. |  NFS requires large space to access large files.  
2. |  File server run a process which is called **vice**. |  NFS is less efficient as it requires more traffic in general to access the files.  
3. |  It uses its own customized protocol for the transfer of files and that protocol is referred as virtue. |  In NFS a directory is mounted during boot process from the server.  
4. |  AFS has multiple set of features and more advanced. |  NFS has less features and much simpler in designs.  
5. |  AFS differentiate between client and server and finds out the dedicated servers. |  NFS permits a system to work as either a client or as a server.  
6. |  AFS maintains the state of updating of files and is **stateful**. |  NFS is **stateless** and does not maintain the status of updating files.


---

