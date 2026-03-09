# Problem 1
## Step-1

The disk scheduling other than FCFS scheduling is useful in a single user environment. 

• In a single-user environment, only one process will be executing. 

• Requests for I/O devices will arrive only from single process. 

• Therefore, the queues for I/O devices will be usually empty.

• In such case, the FCFS scheduling an economical method of disk scheduling.

• However, LOOK scheduling algorithm is a better and easy method for disk scheduling.

• It is easy to program a LOOK scheduling algorithm. In addition, it will give much better performance when multiple processes are performing I/O operations concurrently.


---

# Problem 2
## Step-1

**SSTF Scheduling:**

In order to maximize the throughput, the following should be done in Shortest Seek Time First (SSTF) Scheduling.

• To have the service request possible per unit time.

• To maximize the response meantime that is to provide the response rapidly to most of the interactive users.

• To minimize the response time variance that is to provide the predictability.

## Step-2

SSTF scheduling algorithm is basically biased towards the middle of the cylinders same as the SCAN algorithm.

As in the SSTF algorithm, the closest value of cylinder is selected first, then it is followed by the middle cylinder and at last, the end of the cylinder disk is served.

The head of the disk do tend to be placed away from the disk edge since the center of the disk is probably the location that consists of the smallest average distance to the other tracks.

## Step-3

Thus, due to this the current position of the head divide the cylinders of the disk into two groups.

• If some new request arrives and the head is not in the center, thus the new request switches into the group that basically includes the center of the disk.

• Thus, the head of the disk moves in its direction.


---

# Problem 3
## Step-1

**A timing problem arises:** the program that would do the latency-time orderingneeds to know the number of the sector that would be underneath the head at the timeof I/O service. This information would have to come immediately before servicing theI/O request in order to be accurate. This would require extra communication with theperipheral which would take time, canceling some of the benefit.

The disk scheduling algorithms consider only seek times because for modern disks, **the rotational latency can be nearly as large as average seek time**. It is difficult for the operating system to schedule for improved rotational latency because modern disks do not disclose the physical location of logical blocks. The mapping between logical blocks and physical locations is very complex. 

We would **optimize both seek time and rotational latency** by modifying the implementation of disk-scheduling algorithms (such as SSTF, SCAN, and C-SCAN ) as the controller hardware built into the disk drive. If the operating system sends a batch of requests to the controller, the controller can queue them and then schedule them to improve both the seek time and rotational latency.


---

# Problem 4
## Step-1

• Computer system could only perform at the slowest possible speed. 

• The controllers of the disks and the disks are much more frequent bottleneck in the todays modern systems as the individual performance of such systems couldn’t keep with the system bus and the CPU’s. 

• By balancing I/O among disks and controllers, neither an individual disk nor a controller is overwhelmed, so that bottleneck is avoided.


---

# Problem 5
## Step-1

2481-12-24E SA: 8683

SR: 4578

________________________________________________________________________

**Various tradeoffs involved in rereading code pages from the file system versus swap space** : 

1\. It is more efficient to reread a page from the file system than first write it to swap space and then reread it from swap space when page is selected for page-out by virtual memory.

2\. It is efficient to write a page to swap space and reread it from there when the page is forced out of physical memory rather than when the virtual memory page is first created. 

3\. Swap space is only used as a backing store for pages of anonymous memory, which includes memory allocated for the stack, heap and uninitialized data of a process. 

4\. Swap space is used for regions of memory shared by several processes.

5\. Swap space is limited compared to file system space. So, it is difficult to store both code and data pages in swap space.


---

# Problem 6
## Step-1

**Truly Stable Storage**

**Yes** , a truly stable storage is one that will never lose the data. Thus, the technique to maintain the multiple copies of the data is called as the stable storage.

Next, if one copy of the data is destroyed then some other copy of the data is available for the usage. But all copies of the data could be destroyed if an uncertain large disaster arrives.


---

# Problem 7
## Step-1

**Given data** : 

**Media** |  **Streaming Transfer Rate** |  **Latency**  
---|---|---  
Level-2 cache |  800 MB/sec |  8 nano seconds  
Main memory |  8 MB/sec |  60 nano seconds  
Magnetic disk |  5 MB/sec |  15 milli seconds  
Tape drive |  2 MB/sec |  60 seconds  
  
## Step-2

a. Calculate the Effective Transfer Rate (ETR), the formulas for finding effective transfer rate is given below:

![](https://media.cheggcdn.com/study/74a/74ae04e5-b236-46fb-b835-487aa9c1e0d2/2481-12-2e-i1.png)

Where ![](https://media.cheggcdn.com/study/98b/98b907cd-b8f3-4e46-bea6-c09659a3a71e/2481-12-2e-i2.png)

## Step-3

(1) For 512 bytes, the effective transfer rate is calculated as shown in below:

![](https://media.cheggcdn.com/study/d78/d78194e4-6e4f-4727-a5c3-b70a1014f573/2481-12-2e-i3.png)

![](https://media.cheggcdn.com/study/d6f/d6f88f0c-59b4-47cf-80b5-ef6b8af2ad80/2481-12-2e-i4.png)

## Step-4

![](https://media.cheggcdn.com/study/325/32557410-a30a-4c73-87eb-a95b8858ce84/2481-12-2e-i5.png)

![](https://media.cheggcdn.com/study/6b7/6b786849-941e-46ac-9846-4a40c23dcc3a/2481-12-2e-i6.png)

## Step-5

(2) For 8 kilobytes, the effective transfer rate is calculated as shown in below:

![](https://media.cheggcdn.com/study/325/3257dc81-cca6-4046-a740-ed184223582f/2481-12-2e-i7.png)

![](https://media.cheggcdn.com/study/c72/c7284a0a-eb7e-4ec8-a88a-ffd85bba5ae0/2481-12-2e-i8.png)

## Step-6

![](https://media.cheggcdn.com/study/1cf/1cf08dcf-163e-4468-9070-ef0d2005e32c/2481-12-2e-i9.png)

![](https://media.cheggcdn.com/study/769/76975dad-f8c9-40d7-afd5-58558e0c76aa/2481-12-2e-i10.png)

(3) 

## Step-7

For 1 megabyte, the effective transfer rate is calculated as shown in below:

![](https://media.cheggcdn.com/study/9c7/9c79fc0f-c4b6-4386-8261-30009b86d447/2481-12-2e-i11.png)

![](https://media.cheggcdn.com/study/245/24550a38-81dd-4914-903c-78f57db1e8c9/2481-12-2e-i12.png)

## Step-8

![](https://media.cheggcdn.com/study/c9f/c9fbcfd8-1f7c-4cd7-9d8d-22f343edb903/2481-12-2e-i13.png)

## Step-9

(4) For 16 megabytes, the effective transfer rate is calculated as shown in below:

![](https://media.cheggcdn.com/study/cd3/cd3fcc4e-7bde-455f-a89f-4636af237a30/2481-12-2e-i14.png)

![](https://media.cheggcdn.com/study/492/49257d18-d0f5-4d76-8a9a-2facd27e33f6/2481-12-2e-i15.png)

## Step-10

![](https://media.cheggcdn.com/study/262/26267ee5-cc18-4de0-af97-007fa94bc922/2481-12-2e-i16.png)

![](https://media.cheggcdn.com/study/964/9644bb10-06ee-4adb-8cfe-2737dae5f97e/2481-12-2e-i17.png)

## Step-11

b. Calculation the utilization of the disk drive for each of the four transfer sizes. The formula for utilization of disk drive device is given below: 

![](https://media.cheggcdn.com/study/89a/89a7033a-6fd7-4306-a54b-479764a3d5e3/2481-12-2e-i18.png)

## Step-12

(1) For 512 bytes, Utilization of disk drive device is calculated as shown in below:

![](https://media.cheggcdn.com/study/879/8793887a-ddd5-466b-98fc-063a36062eed/2481-12-2e-i19.png)

![](https://media.cheggcdn.com/study/72a/72aa43df-af00-4ed4-b1ad-77d165c42da2/2481-12-2e-i20.png)

## Step-13

(2) For 8kilobytes,Utilization of disk drive device is calculated as shown in below:

![](https://media.cheggcdn.com/study/acd/acd87e0d-6e14-43d8-8f95-02892813c984/2481-12-2e-i21.png)

![](https://media.cheggcdn.com/study/25c/25c8c014-0ad3-4e3b-864d-0f601917a8a7/2481-12-2e-i22.png)

![](https://media.cheggcdn.com/study/3d2/3d2da399-4fd5-4f25-bbef-ce788f49c1d7/2481-12-2e-i23.png)

(3) For 1megabytes,Utilization of disk drive device is calculated as shown in below:

![](https://media.cheggcdn.com/study/d14/d14ee17c-3f36-4f8c-b856-7ab73c21a0ae/2481-12-2e-i24.png)

![](https://media.cheggcdn.com/study/430/430911a5-3c5a-43c8-b0f4-c1ea567ceb7e/2481-12-2e-i25.png)

![](https://media.cheggcdn.com/study/cfa/cfa62dfa-10ca-420d-8eca-e7f8d41cea51/2481-12-2e-i26.png)

## Step-14

(4) For 16megabytes, Utilization of disk drive device is calculated as shown in below:

![](https://media.cheggcdn.com/study/f4f/f4fa1cda-17f9-432e-984c-43c769a29ac2/2481-12-2e-i27.png)

![](https://media.cheggcdn.com/study/3ad/3ad55adf-cfe1-4685-8e5f-e988c1f9103b/2481-12-2e-i28.png)

![](https://media.cheggcdn.com/study/19d/19dfc631-4165-489e-b6e9-1aa9b7db57c3/2481-12-2e-i29.png)

## Step-15

C.As given in the question, utilization of 25 percent (0.25) is acceptable. We know that

![](https://media.cheggcdn.com/study/6e9/6e9f4ddb-89a2-4f4f-98cd-03f95204ed59/2481-12-2e-i30.png)

![](https://media.cheggcdn.com/study/ff3/ff3b1e8a-3322-4f8d-a5c2-28c1524f4cf5/2481-12-2e-i31.png)

Where Streaming Transfer Rate=5MB

![](https://media.cheggcdn.com/study/46d/46d4f67f-8358-41e1-83e4-99e6d284e823/2481-12-2e-i32.png)

## Step-16

![](https://media.cheggcdn.com/study/a64/a648f5ea-d2a6-47a9-97e0-508fe139a76b/2481-12-2e-i33.png)

![](https://media.cheggcdn.com/study/6ee/6ee0bc2f-e145-46d7-b236-f63dbed58c75/2481-12-2e-i34.png)

![](https://media.cheggcdn.com/study/2ab/2aba2e50-eeb6-476f-b078-d6111832aa18/2481-12-2e-i35.png)

![](https://media.cheggcdn.com/study/f30/f30b85e2-4860-40f2-b9b0-6cda555c2a46/2481-12-2e-i36.png)

## Step-17

d.A disk is a random-access device for transfers larger than _**k-bytes**_ (where k >block size of disk device) and is a sequential access device for smaller transfers.

## Step-18

e. computing the minimum transfer sizes for acceptable utilization of cache memory:

![](https://media.cheggcdn.com/study/cda/cda1fb33-5734-4630-9fcd-01206f95d64f/2481-12-2e-i37.png)

We know that the acceptable utilization is 0.25 or more is accepted.

![](https://media.cheggcdn.com/study/cb0/cb09071f-82ce-4198-b4e6-deceb04bf1f3/2481-12-2e-i38.png)

## Step-19

![](https://media.cheggcdn.com/study/159/15958783-7deb-49b3-b300-009215ce1454/2481-12-2e-i39.png)

## Step-20

![](https://media.cheggcdn.com/study/692/692aa97f-b754-405f-b46d-37d0ec8d39cd/2481-12-2e-i40.png)

Therefore, the minimum transfer size for acceptable utilization of cache memory is **2.08 bytes.**

Computing the minimum transfer sizes for acceptable utilization of main memory:

![](https://media.cheggcdn.com/study/d23/d2376843-0c89-49c1-b18b-6d2087b0ab26/2481-12-2e-i41.png)

We know that the acceptable utilization is 0.25 or more is accepted.

![](https://media.cheggcdn.com/study/fd8/fd8c2f1a-8fe0-4e66-9aed-8e1f241af456/2481-12-2e-i42.png)

## Step-21

![](https://media.cheggcdn.com/study/511/51195e9e-1f42-46ea-877f-3d8596e058f5/2481-12-2e-i43.png)

## Step-22

![](https://media.cheggcdn.com/study/128/128465f3-d467-4daa-94bc-11148a20aef5/2481-12-2e-i44.png)

Therefore, the minimum transfer size for acceptable utilization of main memory is **1.68 bytes.**

## Step-23

Computing the minimum transfer sizes for acceptable utilization of tape device:

![](https://media.cheggcdn.com/study/738/7389e361-3a2b-4a10-9d40-c57395f6e038/2481-12-2e-i45.png)

We know that the acceptable utilization is 0.25 or more is accepted.

![](https://media.cheggcdn.com/study/5d2/5d207011-3a8a-4b4e-beaf-9fdb7f0283b1/2481-12-2e-i46.png)

## Step-24

![](https://media.cheggcdn.com/study/426/426ca3bb-d58b-4fa8-a8c7-e842d0bfc1f5/2481-12-2e-i47.png)

## Step-25

![](https://media.cheggcdn.com/study/384/384e86fc-d652-4d5e-aefa-60603f7e4025/2481-12-2e-i48.png)

Therefore, the minimum transfer size for acceptable utilization of tape device is **40 MB.**

## Step-26

f. It depends on what situation we are using the device. If the device is access the records at some fixed length then the device is random access. If the device is accessing the same records sequentially then it is called sequential access.


---

# Problem 8
## Step-1

RAID level 0 – it refers to disk arrays with striping at the level of blocks but without any redundancy. Since redundancy is not there any data lost can’t be overcomed. So, it is used in high-performance applications where data loss is not critical.

RAID level 1 – It refers to disk mirroring. So, it is popular for applications that require high reliability with fast recovery.

Mirroring provides high reliability, but it is expensive. Stripping provides high data transfer rate, but it does not improve reliability.


---

# Problem 9
## Step-1

a) None of the disk – scheduling disciplines, except FCFS, is truly fair.

This assertion is true because it is based on first – come, first – served it does not provide the fastest services. It is because as this algorithm serves the request that come first it won’t give any priority for new requests though they are less spaced. Thus no starvation.

## Step-2

b) SCAN is modified to C-SCAN i.e., circular SCAN(C-SCAN). It is designed to provide a more uniform wait time. It essentially treats the cylinders as a circular list that wraps around from the final cylinder to the first one.

## Step-3

c) Fairness is an important goal in a time-sharing system because it increases the performance of the system. The performance depends heavily on the number and type of requests. Also in order to serve all the requests within less time with respect to newly arriving requests.

## Step-4

d) Operating system is unfair in servicing I/O request.

(i) Demand paging may take priority over application I/O.

(ii) If the cache is running out of the pages, then writes are more urgent than reads.

(iii) It guarantees the order of a set of disk writes to make the file system robust in the face of system crashes.


---

# Problem 10
## Step-1

SSDs stands for **Solid State Disks**. This is a non-volatile memory and it is working just like a hard drive. SSDs**** have no head to move. SSDs have no seek time and latency. So, they are very fast and chomps less power. 

• There are many disk scheduling algorithms are there such as **FCFS** , SSTF,SCAN,C-SCAN,LOOK,C-LOOK. The different disk scheduling algorithms are used to minimize the head movements. 

• FCFS stands for First come First Serve. This is a very simple scheduling algorithm. It performs according to the request order. There is no starvation found here. 

• The other scheduling algorithms are based on seek time, variance, latency. Though, **SSDs** have no head, seek time and latency, it uses the simplest general purpose scheduling algorithm FCFS. 

If **SSDs** will use another disk scheduling algorithm, Then, its performance may decrease. So, FCFS is the right scheduling algorithm for SSDs**.**


---

# Problem 11
## Step-1

In this problem the given data are as follows:-

Number of cylinders:-5000

Currently head position:-2150

**Queue:** -2069, 1212,2296,2800,544,1618,356,1523,4965,3681

## Step-2

**FCFS Disk Scheduling algorithm:-** In FCFS is an operating system process scheduling algorithm, the requests are managed by the order of their arrival. in other words, First come, first serve basis. 

Consider the following diagram of FCFS disc scheduling:

![D:\\Akash documents\\akash9884\\2016\\August\\12.08.2016\\Bibek\\1.png](https://media.cheggcdn.com/study/7d4/7d455006-abc2-44a9-99c6-292e24e67e51/13258-10-11E-i1.png)

Distance of head movement in FCFS disk scheduling algorithm is as follows:

![](https://media.cheggcdn.com/study/bc6/bc6c88e5-794f-4bf2-84a2-39829a7faec1/13258-10-11E-i2.png)

**Hence, the toatal distance moved= 13011cycles.**

## Step-3

**SSTF disk scheduling algorithm:-** In SSTF disk scheduling algorithm, request is selected with the minimum seek time from the current position of head.

Consider the following diagram of SSTF disc scheduling:

**![D:\\Akash documents\\akash9884\\2016\\August\\12.08.2016\\Bibek\\2.png](https://media.cheggcdn.com/study/d6d/d6d499cc-c709-4113-9fe8-14ce00c25a5f/13258-10-11E-i3.png) **

Distance of head movement in SSTF disk scheduling algorithm is as follows:-

![](https://media.cheggcdn.com/study/67c/67c3968d-3f88-4e88-babf-cc791c259b5a/13258-10-11E-i4.png)

**Hence, the toatal distance moved=7586cycles.**

## Step-4

**SCAN disk scheduling algorithm:-** This algorithm is also known as an Elavator algorithm. In which, the disc arm is started from one of the disk end and move towards the other end and servicing the requests until it approaches to the other end of the disk. At the end the movement, head is reversed and continue the services. 

Consider the following diagram of SCAN disc scheduling:

**![D:\\Akash documents\\akash9884\\2016\\August\\12.08.2016\\Bibek\\3.png](https://media.cheggcdn.com/study/f30/f306df6d-1c02-4a7d-80b1-26461790c726/13258-10-11E-i5.png) **

![](https://media.cheggcdn.com/study/7d9/7d9683a0-8456-43e8-a957-21a7f1a0c0f7/13258-10-11E-i6.png)

**Hence, the toatal distance moved=7492cycles.**

## Step-5

**C-SCAN disk scheduling algorithm:-** In C-SCAN disk scheduling algorithm, the disc arm is started from one of the disk end and move towards the other end and servicing the requests until it approaches to the other end of the disk. 

At the end of the movement, the head immediately returns to the beginning of the disk and continue the services.

Consider the following diagram of CSCAN disc scheduling:

**![D:\\Akash documents\\akash9884\\2016\\August\\12.08.2016\\Bibek\\4.png](https://media.cheggcdn.com/study/00f/00f07855-3030-4d0f-b03b-40228690b13f/13258-10-11E-i7.png) **

Distance of head movement in C-SCAN disk scheduling algorithm is as follows:-

![](https://media.cheggcdn.com/study/5f7/5f758e29-b33f-4c95-aef3-a00fcc517ee6/13258-10-11E-i8.png) **Hence, the toatal distance moved= 9917 cycles.**

## Step-6

**e.**

**LOOK disk scheduling algorithm:** **** **LOOK** is a **disk scheduling algorithm** used to determine the order in which new **disk** read and write requests are processed.

Consider the following diagram of LOOK disc scheduling:

![D:\\Akash documents\\akash9884\\2016\\August\\12.08.2016\\Bibek\\5.png](https://media.cheggcdn.com/study/ecb/ecb96863-0b6d-4fc7-a092-91d3cadcd6fc/13258-10-11E-i9.png)

Distance of head movement in LOOK disk scheduling algorithm is as follows:-

![](https://media.cheggcdn.com/study/125/125c4837-bdc4-4a74-b663-64f6989581c5/13258-10-11E-i10.png)

**Hence, the toatal distance moved= 7424 cycles**

## Step-7

**f.**

**C-LOOK disk scheduling algorithm:**

Consider the following diagram of C-LOOK disc scheduling:

![D:\\Akash documents\\akash9884\\2016\\August\\12.08.2016\\Bibek\\6.png](https://media.cheggcdn.com/study/326/32639064-62ae-4143-b6c0-80a398f1a67b/13258-10-11E-i11.png)

Distance of head movement in C-LOOK disk scheduling algorithm is as follows:

![](https://media.cheggcdn.com/study/43a/43a3b885-a46b-4ac3-8d42-e83d8c4ae83c/13258-10-11E-i12.png) **Hence, the toatal distance moved=9137** **cycles**


---

# Problem 12
## Step-1

a)

According to the Elementary physics it is found that 

![](https://media.cheggcdn.com/study/628/628d2ae6-1952-4ffe-82b3-7d96366086f9/13258-10-12E-i1.png)

where **d** = Distance

**a** =acceleration

**t** =Time

Now, solving the above equation, user obtained:

![](https://media.cheggcdn.com/study/1a9/1a9547c9-8720-427b-a8dc-55f1ad885410/13258-10-12E-i2.png)

As it is already known that the acceleration is constant. Therefore, the above expression is ![](https://media.cheggcdn.com/study/a02/a02f565c-2dd0-45fe-90ea-b4b9950dfddb/13258-10-12E-i3.png)is also constant.

Hence, ![](https://media.cheggcdn.com/study/436/4363e9df-7a9e-4f59-af4c-8e6b307dbae8/13258-10-12E-i4.png)

## Step-2

b)

Given Data is as follows:-

Total distance d=4999

Time t=18 milli second

Now from the above equation ![](https://media.cheggcdn.com/study/296/2962bfed-515e-4a93-8979-116bd508b8b1/13258-10-12E-i5.png)the acceleration can be find out

![](https://media.cheggcdn.com/study/c7c/c7c087af-4be5-4e8c-a08f-57c9e4418c68/13258-10-12E-i6.png)

Now, the resulting equation is,

![](https://media.cheggcdn.com/study/084/084c97d7-01e8-4335-9a3b-e726ebb4c5fe/13258-10-12E-i7.png)

**Hence,** ![](https://media.cheggcdn.com/study/4c9/4c9ffe2f-79cf-43e0-a6a6-49c583e2e6ee/13258-10-12E-i8.png)

## Step-3

c)

**The Seek time** is defined as the time required for the movement of the disk arm to the required track. Rotational delay or latency is the time it takes for the starting of the required sector to reach the head.

The seek time for all the scheduling algorithm is as follows:-

****

**FCFS**

=![](https://media.cheggcdn.com/study/784/7843ce35-d119-4b48-9731-77d5265765cc/13258-10-12E-i9.png) ![](https://media.cheggcdn.com/study/b90/b900da02-d0d4-4e47-885d-6b126b1dcc5e/13258-10-12E-i10.png)

Hence, for FCFS the seek time is ![](https://media.cheggcdn.com/study/04e/04edd382-40c3-43af-bc37-4bf284ed7664/13258-10-12E-i11.png).

**SSTF** = ![](https://media.cheggcdn.com/study/01e/01e31d80-cb93-4f60-9eef-9eb0def0c84e/13258-10-12E-i12.png)

![](https://media.cheggcdn.com/study/e18/e1872f90-d3dc-40b1-b105-ec9460af18b2/13258-10-12E-i13.png)

Hence, for SSTF the seek time is ![](https://media.cheggcdn.com/study/a66/a66127e1-7fde-4461-8f7e-a60afa4e71a3/13258-10-12E-i14.png)**.**

**SCAN** ![](https://media.cheggcdn.com/study/268/268e6e42-c3a5-4696-98a7-252c9b48ff00/13258-10-12E-i15.png)

![](https://media.cheggcdn.com/study/1a3/1a33f54a-1d14-4a0c-9311-b337653948ac/13258-10-12E-i16.png)

Hence, for SCAN the seek time is ![](https://media.cheggcdn.com/study/797/797ba1c4-209c-433a-8f89-cfb4f0e38108/13258-10-12E-i17.png)**.**

**CSCAN** ![](https://media.cheggcdn.com/study/9c9/9c9846ce-1974-40d4-8d11-0a122e9327ac/13258-10-12E-i18.png)

![](https://media.cheggcdn.com/study/11b/11b38582-664c-4b73-adf3-cd74e72be0be/13258-10-12E-i19.png)

Hence, for C-SCAN the seek time is ![](https://media.cheggcdn.com/study/a01/a016b46c-f0e1-4f2d-843e-b1b7bf7db236/13258-10-12E-i20.png)**.**

**LOOK** ![](https://media.cheggcdn.com/study/f5f/f5f46634-7234-494e-b17f-a4b67d7bf9ab/13258-10-12E-i21.png)

![](https://media.cheggcdn.com/study/501/5013bb20-777e-42ee-98ae-b56391762f21/13258-10-12E-i22.png)

Hence, for LOOK the seek time is ![](https://media.cheggcdn.com/study/692/692ebc98-ac0d-45be-a4b7-d32fb74a221b/13258-10-12E-i23.png)**.**

**C-LOOK** ![](https://media.cheggcdn.com/study/8d2/8d2eb405-52d7-4c4b-83a4-a6557f12f6ab/13258-10-12E-i24.png)

![](https://media.cheggcdn.com/study/99c/99c0ef7b-8818-49f0-abdd-6070a41ad4cf/13258-10-12E-i25.png)

Hence, for C-LOOK the seek time is ![](https://media.cheggcdn.com/study/89d/89d8ae1a-9142-4bbf-8e0f-f5af8945168a/13258-10-12E-i26.png)**.**

Now, from the above result it can be said that**** Seek time is minimum in LOOK disk scheduling algorithm. **So LOOK disk scheduling algorithms is faster** . 

## Step-4

d) speedup of fastest schedule over FCFS is as follows:- as the seek time of the FCFS is ![](https://media.cheggcdn.com/study/f8a/f8a4958b-f720-45d0-90f7-ac12fc520f74/13258-10-12E-i27.png)and the seek time for LOOK is ![](https://media.cheggcdn.com/study/f95/f9593012-5db5-4a3f-b780-f6faf1ce204c/13258-10-12E-i28.png)then;

![](https://media.cheggcdn.com/study/16c/16ce2990-0887-4e70-ba08-903b00fbcfd6/13258-10-12E-i29.png)

![](https://media.cheggcdn.com/study/a7f/a7fbe954-5a1d-4af2-8d7e-5f0c00272af0/13258-10-12E-i30.png) **faster.**


---

# Problem 13
## Step-1

The data given in the problem are:-

Disk rotates =7200 revolution per minute.

So, in one second the disk rotates= ![](https://media.cheggcdn.com/study/9ed/9edf6103-f728-4fff-9bcf-57f0847f4be3/13258-10-13E-i1.png)

=![](https://media.cheggcdn.com/study/13f/13fce3b9-ced7-4ebd-b300-ababce09245a/13258-10-13E-i2.png) rotations.

Now, one rotation will take = ![](https://media.cheggcdn.com/study/511/51149085-0f9a-4c43-9a5d-8bb40b6f8d4a/13258-10-13E-i3.png)ms

= ![](https://media.cheggcdn.com/study/06c/06cba68b-8268-4754-95c8-2d4b9b2a1f7a/13258-10-13E-i4.png)ms

From the definition of latency, it is aready known that latency is half of the rotation. Therefore, **Latency = half of the rotation**

=![](https://media.cheggcdn.com/study/cbc/cbc9ce82-56a9-496f-9161-df4c3f143ff8/13258-10-13E-i5.png)

=![](https://media.cheggcdn.com/study/0fa/0fadc98e-6b09-4f3f-bf22-f4b7f426e6dc/13258-10-13E-i6.png)ms

Hence, the **average rotational time latency** of the disc drive is ![](https://media.cheggcdn.com/study/b53/b53025f1-3185-4575-b83f-d24b226f9577/13258-10-13E-i7.png)

## Step-2

According to the equation t is given as:

![](https://media.cheggcdn.com/study/55e/55ebffa3-1552-4aeb-8101-2433dabb38a1/13258-10-13E-i8.png)

Now from the above part as described, the value of ![](https://media.cheggcdn.com/study/78f/78fa87a6-e685-404e-b95d-6ecfbd16d36d/13258-10-13E-i9.png) is equals to ![](https://media.cheggcdn.com/study/ef5/ef5f6e61-7460-447c-8357-c69ad06c52a2/13258-10-13E-i10.png)ms. Hence, after putting this value in the equation which is given above, the value obtained is :

![](https://media.cheggcdn.com/study/f7c/f7cc851c-1030-4eb3-8dfd-aa19f6c167c1/13258-10-13E-i11.png)

![](https://media.cheggcdn.com/study/59e/59ec0ba5-43a8-4c6b-9c77-cd791a9e5399/13258-10-13E-i12.png)

![](https://media.cheggcdn.com/study/2dd/2dd438e6-1b8f-4944-a026-d4a2e00ca797/13258-10-13E-i13.png) cylinders

Hence, **the Distance covered** in the time ![](https://media.cheggcdn.com/study/d81/d8170593-e76a-423b-9414-4ae4e8b40dd1/13258-10-13E-i14.png) is equals to ![](https://media.cheggcdn.com/study/a8a/a8ace7e7-9349-44d5-b389-94c88794edae/13258-10-13E-i15.png).


---

# Problem 14
## Step-1

**The advantages of using SSDs over magnetic disk drives are given below:**

• Data Access is faster on SSDs compared to the hard disk drives.

• It uses flash memory and don’t use any moving head. So, it is more consistent and provide enhanced performance than hard disk drives.

• It consumes less power.

• The Solid State Disks have no moving head. So, this is less noisy. Hard disk drives are somewhat noisy as they have read/write moving head.

• It generates less heat than that of the hard disk drives. So. Its lifespan is more and will not damage.

• It has no magnetic parts. So, it is not affected by magnetism, but hard disk drives has magnetic parts. So some time data may lost due to magnetism effect.

## Step-2

**The disadvantages of using SSDs over magnetic disk drives are given below:**

• It has limited storage capacity than that of HDD.

• This is very expensive as comapared to magnetic disk drives.

• If SSDs are severely used then data maintenance capacity will be minimized.


---

# Problem 15
## Step-1

In SCAN algorithm, the disk arm starts at one end of the disk, and moves towards the other end, servicing requests as it reaches each cylinder, until it gets to the other end of the disk. At the other end, the direction of head movement is reversed, and servicing continues. The head continuously scans back and forth across the disk. 

C-SCAN is designed for more uniform wait. Like SCAN, C-SCAN moves the head from one end of the disk to the other, servicing requests along the way. When the head reaches the other end, it immediately returns to the beginning of the disk, without servicing any requests on return trip. It treats the cylinder as a circular list that wraps around from the final cylinder to the first one.

C-SCAN has an average response time just a few percent higher than SCAN but C_SCAN has an significantly lower variance in response time for medium and heavy workloads. The intuitive reason for this variance is that SCAN tend to favor requests in middle cylinders where as C-versions do not have this imbalance.

These algorithms do not schedule to improve rotational latency; therefore, as seek times decrease relative to rotational latency, the performance differences between the algorithms decrease.


---

# Problem 16
## Step-1

**Shortest Seek Time First**(SSTF): It select the request that is nearest to the current head position.

**Ageing** is the mechanism where the priority of the process increases gradually on the basis of its waiting time. If a process does not receive CPU for a long time then aging will occur.

## Step-2

• **Shortest Seek Time First** is the best scheduling algorithm as it serves the request that are nearer to the current head position and would be able to take the advantage of the given situation. 

• Other scheduling algorithm like first come first serve (FCFS) could cause head movement that are unnecessary when frequently visited cylinder were placed far apart from each other.

## Step-3

• One of the solution can be to place the**hot spot** in or near the middle of the disk, so that it can be nearer to all the data on average cases. 

• **Modified shortest seek time first scheduling algorithm** can be used to avert starvation.

• Also, some policy can be added to let the operating system generate a seek to the hot spot whenever the disk sits idle for more than 50ms, as the next request might be there. 

• This helps in making the operating system busy. Even this helps in preventing ageing for the older request. 

• With the help of Hotspot each and every request gets an equal importance.


---

# Problem 17
## Step-1

RAID level 5 – It is also called as block inter leaved distributed parity, differs from level 4 by spreading data and parity among all N + 1 disks, rather than storing data in N disks and parity in one disk. 

A parity block cannot store parity for blocks in the same disks, because a disk failure would result in loss of data as well as of parity and hence the loss would not be recoverable.

## Step-2

RAID 5 avoids the potential over use of a single parity disk that can occur with RAID 4. RAID 5 is most common parity system.

a)

In order to perform a write operation, parity bits must be changed. Process the following steps:

1) Read the parity block. 

2) Write the new data.

3) XOR the old data with the new data.

4) Read the old parity from the array.

5) Compute the parity for the next set of blocks.

6) Write the updated parity back to the array.

## Step-3

b) In order to perform a write to seven continuous blocks of data, the following are the steps:

1) Read the old data.

2) Write the new data.

3) XOR the old data with the new data.

4) Read the old parity from the array for the seven blocks.

5) Compute the parity for the next set of blocks.

6) write the updated parity back to the array (for seven blocks).


---

# Problem 18
## Step-1

RAID 1 performance can actually be slightly better than a standard disk implementation for read operations. Because the contents of both drives are identical, the array management software is free to select the drive which can most quickly satisfy the request.

Since RAID 5 systems work with independent spindles, random I/O is naturally load balanced, making them capable of read performance approaching that of RAID\x110, but with much better reliability. RAID 5 requires only one additional drive to add parity protection, resulting in similar economics.


---

# Problem 19
## Step-1

RAID level 1 is popular for applications that require high reliability with fast recovery. Due to RAID 1’s high space overhead, RAID 5 is often preferred for staring large volumes of data. Any write to RAID level 1 requires operations twice in order to modify actual and mirrored data. In RAID level 5, no need.


---

# Problem 20
## Step-1

Rebuilding is earliest for RAID 1, since data can be copied from one to another disk, where as rebuild time can be in hours for RAID 5 rebuilds of large disk sets.

RAID level 1 is for applications that require high reliability with fast recovery. Due to high space overhead at RAID 1, RAID level 5 is often preferred for storing large volumes of data except for multimedia database storage and video applications. Where as RAID level 1 is suitable for small database where reliability is more important.


---

# Problem 21
## Step-1

300-12-14E

![](https://media.cheggcdn.com/study/18a/18a0ed33-23c6-4643-8eec-b71e09744c5b/300-12-14e-i1.png)

a) Disk drives = 1,000

Each has 750,000 hour MTBF

Mean time for disks drives = ![](https://media.cheggcdn.com/study/a07/a07e15e7-e5cd-4782-883e-f6a4a39b0826/300-12-14e-i2.png)

= 750 hrs per failure about 31 days or once per month

## Step-2

b) 1: 000 chances of dying between ages 20 & 21 years.

Human-hours per failure is 8760(hrs in a year) divided by 0.001 failure, giving a value of about 8,760,000 hours for the MTBF. 8760000 hours equals 1000 years. This tells us nothing about the expected lifetime of a person of age 20.

## Step-3

c) The MTBF tells nothing about the expected lifetime. Hard disk drives are generally designed to have a lifetime of 5 years. If such a drive truly has a million-hour MTBF, it is very unlikely that the drive will fail during its expected lifetime.


---

# Problem 22
## Step-1

Sector sparing can cause an extra track switch and rotational latency, causing an unlucky request to require an extra 8ms of time. Sector slipping has less impact during future reading, but at sector remapping time it can require the reading and writing of an entire track’s worth of data to slip the sectors past the bad spot.


---

# Problem 23
## Step-1

An Operating System (OS) does the following things while allocating the blocks:

• If an Operating System has more information regarding to the physical location of blocks on the disks, then it could allocate the blocks for a file geometrically which are close by on the disk.

• OS allocates a first block of data to the disk by the above procedure, then allocates the second block of data to the same cylinder of the disk but the surface is different. Because, the disk is rotationally optimal.

## Step-2

**Performance improvement of the file-system:**

The OS allocates blocks of data on the same cylinder of disk with different surfaces because, the disk is rotationally optimal place.

As the OS allocates blocks of data on the same cylinder, the data can be accessed easily. Therefore, the cost is minimized, and the file-system performance is improved.


---

# Problem 24
## Step-1

**FCFS Scheduling algorithm:** In FCFS is an operating system process scheduling algorithm, the requests are managed by the order of their arrival. in other words, First come, first serve basis.

Consider the following program:

#include

#include

#include

#include

int main**()**

**{**

// Initialize the variables 

int Que**[** 20**],** n**,** Head**,** a**,** b**,** Seek_Time**=** 0**,** Maximum**,** Difference**;**

float Avg**;**

//Enter the maximum range of the disk

printf**(** "Enter the maximum range of disk"**);**

scanf**(** "%d"**, &**Maximum**);**

//Enter the maximum size of the request queue.

printf**(** "Enter the size of Request Queue"**);**

scanf**(** "%d"**, &**n**);**

//Enter the request in the queue.

printf**(** "Enter the request in queue"**);**

//For() loop is used to iterate through the queue.

**for****(** a**=** 1**;** a**< =**n**;** a**++)**

**{**

scanf**(** "%d"**, &**Que**[** a**]);**

**}**

//Enter the first head position.

printf**(** "enter the first head position"**);**

scanf**(** "%d"**, &**Head**);**

//Initialize the head queue to zero

Que**[** 0**]=** Head**;**

//For() loop is used to take the absolute value of 

//the difference between the consecutive queue.

**for****(** b**=** 0**;** b**< =**n**-** 1**;** b**++)**

**{**

Difference**=** abs**(** Que**[** b**+** 1**]-** Que**[** b**]);**

Seek_Time**+=** Difference**;**

printf**(** "Head move is from %d to %d with Seek_Time 

%d\n"**,** Que**[** b**],** Que**[** b**+** 1**],** Difference**);**

**}**

//Print the total seek time

printf**(** "total seek time is%d\n"**,** Seek_Time**);**

//calculate the average seek time

Avg**=** Seek_Time**/(** float**)** n**;**

printf**(** "avrage seek time is %f\n"**,** Avg**);**

getch**();**

**}**

## Step-2

**Output:**

Enter the maximum range of disk180

Enter the size of Request Queue8

Enter the request in queue78

90

87

56

34

66

42

23

enter the first head position130

Head move is from 130 to 78 with Seek_Time 52

Head move is from 78 to 90 with Seek_Time 12

Head move is from 90 to 87 with Seek_Time 3

Head move is from 87 to 56 with Seek_Time 31

Head move is from 56 to 34 with Seek_Time 22

Head move is from 34 to 66 with Seek_Time 32

Head move is from 66 to 42 with Seek_Time 24

Head move is from 42 to 23 with Seek_Time 19

total seek time is195

avrage seek time is 24.375000

**SSTF disk scheduling algorithm:** In SSTF disk scheduling algorithm, request is selected with the minimum seek time from the current position of head.

Consider the following program:

#include

#include

#include

void main()

{ 

//Initialize the variables.

int Queue[130],t[30],Head,Seek_Time=0,n,a,b,temp;

float Avg;

//Enter the size of the queue.

printf("Enter the size of Queue\t");

scanf("%d",&n;);

//Enter the initial head position

printf("Enter the initial head position\t");

scanf("%d",&Head;);

//Enter the request in queue.

printf("Enter the request in Queue\t");

//Fro() loop is used to take the value of the queue.

for(a=0;a

{

scanf("%d",&Queue;[a]);

}

for(a=1;a

{

t[a]=abs(Head-Queue[a]);

}

//Nested for() loop is used to copy.

for(a=0;a

{

for(b=a+1;b

{

if(t[a]>t[b])

{

temp=t[a];

t[a]=t[b];

t[b]=temp;

temp=Queue[a];

Queue[a]=Queue[b];

Queue[b]=temp;

}

}

}

for(a=1;a

{

Seek_Time=Seek_Time+abs(Head-Queue[a]);

Head=Queue[a];

}

printf("\nTotal Seek Time is%d\t",Seek_Time);

//Calculate the average seek time

Avg=Seek_Time/(float)n;

printf("\nAverage Seek Time is %f\t",Avg);

getch();

}

## Step-3

**Sample Output:**

Enter the size of Queue 8

Enter the initial head position 1234

Enter the request in Queue 456

789

1456

2000

1500

900

500

678

Total Seek Time is2766

Average Seek Time is 345.750000

**SCAN** **disk scheduling algorithm: :-** This algorithm is also known as an Elavator algorithm. In which, the disc arm is started from one of the disk end and move towards the other end and servicing the requests until it approaches to the other end of the disk. At the end the movement, head is reversed and continue the services.

Consider the following program**:**

#include

#include

int main**()**

**{**

//Initialize the variables.

int a**[** 20**],** b**[** 20**],** n**,** i**,** j**,** temp**,** pre**,** seek_time**,** max**,** x**,** t**=** 0**;**

//Enter the head position

printf**(** "Enter head pointer position:"**);**

scanf**(** "%d"**, &**a**[** 0**]);**

//Initialize the seek_time as the head of the queue.

seek_time**=** a**[** 0**];**

//Enter the previous head position.

printf**(** "\nEnter previous head position:"**);**

scanf**(** "%d"**, &**pre**);**

//Enter the queue size.

printf**(** "\nEnter Queue size:"**);**

scanf**(** "%d"**, &**max**);**

//Enter the number of request.

printf**(** "\nEnter number of Requests:"**);**

scanf**(** "%d"**, &**n**);**

//Enter the request in the queue.

printf**(** "\nEnter requests in queue"**);**

//for() loop is used to take the input in the queue.

**for****(** i**=** 1**;** i**< =**n**;** i**++)**

**{**

scanf**(** "%d"**, &**a**[** i**]);**

**}**

a**[** n**+** 1**]=** max**;**

a**[** n**+** 2**]=** 0**;**

//Nested loop is used to swap the values.

**for****(** i**=** n**+** 1**;** i**>=** 0**;** i**\--)**

**{**

**for****(** j**=** 0**;** j**< =**i**;** j**++)**

**{**

//check if a[j]>a[j+1]

**if****(** a**[** j**]>** a**[** j**+** 1**])**

**{**

//swapping performed here.

temp**=** a**[** j**];**

a**[** j**]=** a**[** j**+** 1**];**

a**[** j**+** 1**]=** temp**;**

**}**

**}**

**}**

//check for seek_time==a[i]

**for****(** i**=** 1**;** i**< =**n**+** 1**;** i**++)**

**{**

**if****(** seek_time**==** a**[** i**])**

x**=** i**;**

**}**

j**=** 0**;**

c//check if seek_time is less than pre

**if****(** seek_time**<** pre**)**

**{**

**for****(** i**=** x**;** i**>** 0**;** i**\--)**

**{**

t**+=(** a**[** i**]-** a**[** i**-** 1**]);**

b**[** j**++]=** a**[** i**];**

**}**

t**+=** a**[** x**+** 1**]-** a**[** 0**];**

b**[** j**++]=** a**[** 0**];**

**for****(** i**=** x**+** 1**;** i**<** n**+** 1**;** i**++)**

**{**

t**+=(** a**[** i**+** 1**]-** a**[** i**]);**

b**[** j**++]=** a**[** i**];**

**}**

b**[** j**++]=** a**[** i**];**

**}**

// else exccute this part

**else**

**{**

**for****(** i**=** x**;** i**<** n**+** 2**;** i**++)**

**{**

t**+=(** a**[** i**+** 1**]-** a**[** i**]);**

b**[** j**++]=** a**[** i**];**

**}**

t**+=** a**[** n**+** 2**]-** a**[** x**-** 1**];**

b**[** j**++]=** a**[** n**+** 2**];**

**for****(** i**=** x**-** 1**;** i**>** 1**;** i**\--)**

**{**

t**+=(** a**[** i**]-** a**[** i**-** 1**]);**

b**[** j**++]=** a**[** i**];**

**}**

b**[** j**++]=** a**[** i**];**

**}**

printf**(** "\nRequests order:"**);**

**for****(** i**=** 0**;** i**< =**n**+** 1**;** i**++)**

printf**(** "\t%d"**,** b**[** i**]);**

printf**(** "\nTotal Head Movement:%d"**,** t**);**

getch**();**

**}**

## Step-4

**Sample Output:**

Enter head pointer position:122

Enter previous head position:90

Enter Queue size:199

Enter number of Requests:6

Enter requests in queue33

49

97

123

156

30

Requests order: 122 123 156 199 97 49 33 30

Total Head Movement:246

## Step-5

**C-SCAN** **disk scheduling algorithm: :** In C-SCAN disk scheduling algorithm, the disc arm is started from one of the disk end and move towards the other end and servicing the requests until it approaches to the other end of the disk. At the end of the movement, the head immediately returns to the beginning of the disk and continue the services.

Consider the following program:

#include

#include

#include

#define max 20

#define cymax 199

// Initialize and declare the variables.

int i**,** j**,** req**,** ttl_tracks**=** 0**,** cp**,** np**,** cposn**,** nposn**;**

int cyposn**[** max**],** temp**;**

//Input() method is created

void input**()**

**{**

**do**

**{**

//Enter the header position

printf**(** "\n Enter the current header position : "**);**

scanf**(** "%d"**, &**cposn**);**

**}****while****(** cposn**>** cymax **||** cposn **< =**0**);**

printf**(** "\n Enter the %d Requests : "**,** req**);**

cyposn**[** 0**]** **=** cposn**;**

**for****(** i**=** 1**;** i**< =**req**;** i**++)**

scanf**(** "%d"**, &**cyposn**[** i**]);**

**}**

void CSCAN**()**

**{**

//Nested for() loop is used to perform swapping

**for****(** i**=** 0**;** i**< =**req**;** i**++)**

**{**

**for****(** j**=** 0**;** j**<** req**-** i**;** j**++)**

**{**

**if****(** cyposn**[** j**]** **>** cyposn**[** j**+** 1**])**

**{**

//Swapping performed here.

temp **=** cyposn**[** j**];**

cyposn**[** j**]** **=** cyposn**[** j**+** 1**];**

cyposn**[** j**+** 1**]** **=** temp**;**

**}**

**}**

**}**

cp**=** 0**;**

**do**

**{**

//Check if cypon[cp]==cposn

**if****(** cyposn**[** cp**]** **==** cposn**)**

**break****;**

cp**++;**

**}****while****(** cp**!=** req**);**

printf**(** "\nS.No. Current Position 

Next Position Displacement \n"**);**

printf**(** "----------------------------------------------- 

\----------- \n\n"**);**

i**=** 0**,** j**=** cp**;**

cposn **=** cyposn**[** cp**];**

**do**

**{**

**if****(** cposn **==** cyposn**[** req**])**

**{**

//Set the values

nposn **=** 199**;** cp **=** **-** 1**;**

**}**

**else**

//Increamet the position

nposn **=** cyposn**[++** cp**];**

printf**(** " %d\t\t%d\t\t%d\t\t%d\n"**,**

**++** i**,** cposn**,** nposn**,** abs**(** cposn**-** nposn**));**

ttl_tracks **+=** **(** abs**(** cposn**-** nposn**));**

cposn **=** nposn **==** 199 **?** 0 **:** nposn**;**

**}****while****(** nposn **!=** cyposn**[** j**-** 1**])**

printf**(** "-----------------------------------------------

\----------- \n\n"**);**

printf**(** " Total Tracks Displaced : %d"**,** ttl_tracks**);**

**}**

Main() method called here.

int main**()**

**{**

**do**

**{**

printf**(** "\n Enter the number of requests : "**);**

scanf**(** "%d"**, &**req**);**

**}****while****(** req**>** max **||** req **< =**0**);**

//Calling input() method

input**();**

//Calling CSCAN()

CSCAN**();**

getch**();**

**}**

## Step-6

**Sample Output:**

Enter the number of requests : 6

Enter the current header position : 45

Enter the 6 Requests : 56

88

90

23

77

88

S.No. Current Position Next Position Displacement

\----------------------------------------------------------

1 45 56 11

2 56 77 21

3 77 88 11

4 88 88 0

5 88 90 2

6 90 199 109

7 0 23 23

\----------------------------------------------------------

Total Tracks Displaced : 177

## Step-7

Consider the following program which is used to perform**LOOK****disk scheduling:**

#include

#include

#include

#define max 20

#define cymax 199

int i**,** j**,** req**,** ttl_tracks**=** 0**,** cp**,** np**,** cposn**,** nposn**;**

int cyposn**[** max**],** temp**;**

//input() function is created.

void input**()**

**{**

//Enter the current header position.

printf**(** "\n Enter the current header position : "**);**

scanf**(** "%d"**, &**cposn**);**

//Enter the IO request.

printf**(** "\n Enter the %d I/O Requests : "**,** req**);**

cyposn**[** 0**]** **=** cposn**;**

**for****(** i**=** 1**;** i**< =**req**;** i**++)**

scanf**(** "%d"**, &**cyposn**[** i**]);**

**}**

// Look() method is created.

void LOOK**()**

**{**

int ind **=** 0**;**

//Nested for() loop is used to perform swapping.

**for****(** i**=** 0**;** i**< =**req**;** i**++)**

**{**

**for****(** j**=** 0**;** j**<** req**-** i**;** j**++)**

**{**

**if****(** cyposn**[** j**]** **>** cyposn**[** j**+** 1**])**

**{**

//Swapping

temp **=** cyposn**[** j**];**

cyposn**[** j**]** **=** cyposn**[** j**+** 1**];**

cyposn**[** j**+** 1**]** **=** temp**;**

**}**

**}**

**}**

cp**=** 0**;**

**do**

**{**

//Check if cyposn[cp]==cposn

**if****(** cyposn**[** cp**]** **==** cposn**)**

**break****;**

cp**++;**

**}****while****(** cp**!=** req**);**

int tmp **=** cp**;**

printf**(** "\nS.No. Current Position Next Position

Displacement \n"**);**

printf**(** "----------------------------------------

\---------------- \n\n"**);**

i**=** 0**;**

cposn **=** cyposn**[** cp**];**

**do**

**{**

**if****(** ind **==** 0**)**

**{**

**if****(** cp **==** 0**)**

**{**

//assignment

cp **=** tmp**;**

nposn **=** cyposn**[++** cp**];** ind **=** 1**;**

**}**

**else**

nposn **=** cyposn**[--** cp**];**

**}**

**else**

nposn **=** cyposn**[++** cp**];**

printf**(** " %d\t\t%d\t\t%d\t\t%d\n"**,**

**++** i**,** cposn**,** nposn**,** abs**(** cposn**-** nposn**));**

ttl_tracks **+=** **(** abs**(** cposn**-** nposn**));**

cposn **=** nposn**;**

**}****while****(** nposn**!=** cyposn**[** req**]);**

printf**(** "----------------------------------

\------------------------ \n\n"**);**

printf**(** " Total Tracks Displaced : %d"**,** ttl_tracks**);**

**}**

//Main() method is called.

int main**()**

**{**

**do**

**{**

//Enter the number of request.

printf**(** "\n Enter the number of requests : "**);**

scanf**(** "%d"**, &**req**);**

**}****while****(** req**>** max **||** req **< =**0**);**

//input() method called.

input**();**

//Look() method is called here.

LOOK**();**

getch**();**

**}**

## Step-8

**Sample Output:**

Enter the number of requests : 6

Enter the current header position : 44

Enter the 6 I/O Requests : 23

99

76

56

87

33

S.No. Current Position Next Position Displacement

\----------------------------------------------------------

1 44 33 11

2 33 23 10

3 23 56 33

4 56 76 20

5 76 87 11

6 87 99 12

\----------------------------------------------------------

Total Tracks Displaced : 97

Consider the following program which is performed**C-LOOK** **disk scheduling:**

#include

#include

#include

//Initialize and declare the variables.

int cymax**,** i**,** j**,** req**,** ttl_tracks**=** 0**,** cp**,** np**,** cposn**,** nposn**;**

int cyposn**[** 20**],** ind**[** 20**],** temp**;**

//CLOOK() function is used to perform CLOOK Scheduling.

void CLOOK**()**

**{**

int t**;**

//Nested for() loop is used to perform swapping

**for****(** i**=** 0**;** i**< =**req**;** i**++)**

**{**

**for****(** j**=** 0**;** j**<** req**-** i**;** j**++)**

**{**

**if****(** cyposn**[** j**]** **>** cyposn**[** j**+** 1**])**

**{**

//Swapping

temp **=** cyposn**[** j**];**

cyposn**[** j**]** **=** cyposn**[** j**+** 1**];**

cyposn**[** j**+** 1**]** **=** temp**;**

**}**

**}**

**}**

cp**=** 0**;**

**do**

**{**

//Check if cyposn[cp]==cposn

**if****(** cyposn**[** cp**]** **==** cposn**)**

**break****;**

cp**++;**

**}****while****(** cp**!=** req**);**

printf**(** "\nS.No. Current Position Next Position 

Displacement \n"**);**

i**=** 0**,** j**=** cp**;**

cposn **=** cyposn**[** cp**];**

**do**

**{**

**if****(** cp **==** req**)**

**{**

nposn **=** cyposn**[** 0**];** cp **=** 0**;**

**}**

**else**

nposn **=** cyposn**[++** cp**];**

t**=** abs**(** cposn**-** nposn**);**

printf**(** "%d\t\t%d\t\t%d\t\t\%d\n"**,**

**++** i**,** cposn**,** nposn**,** t**);**

ttl_tracks **+=** **(** abs**(** cposn**-** nposn**));**

cposn **=** nposn **==** cyposn**[** req**]** **?** cyposn**[** 0**]** **:** nposn **;**

**}****while****(** nposn **!=** cyposn**[** j**-** 1**]);**

printf**(** "total track displaced=%d"**,** ttl_tracks**);**

**}**

//Main() method is called.

int main**()**

**{**

//Enter the number of request.

printf**(** "Enter the number of requests"**);**

scanf**(** "%d"**, &**req**);**

//Enter the maximum range of request.

printf**(** "Enter the maximum range of requests"**);**

scanf**(** "%d"**, &**cymax**);**

//Emter the current head position

printf**(** "Enter current Head position"**);**

scanf**(** "%d"**, &**cposn**);**

//Enter the request

printf**(** "Enter th requests"**);**

cyposn**[** 0**]** **=** cposn**;**

**for****(** i**=** 1**;** i**< =**req**;** i**++)**

scanf**(** "%d"**, &**cyposn**[** i**]);**

//CLLOK is called here.

CLOOK**();**

system**(** "pause"**);**

**return** 0**;**

**}**

Sample Output:

Enter the number of requests6

Enter the maximum range of requests100

Enter current Head position0

Enter th requests24

62

38

12

80

25

S.No. Current Position Next Position Displacement

1 0 12 12

2 12 24 12

3 24 25 1

4 25 38 13

5 38 62 24

6 62 80 18

7 0 0 0

total track displaced=80


---

