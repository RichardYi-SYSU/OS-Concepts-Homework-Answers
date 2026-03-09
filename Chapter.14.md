# Problem 1
## Step-1

**Access List and Capability list**

A list containing the set of rights which are used to access the object of any domain is known as **access** **list**. For each object there is a different access list.

A list containing the set of operations which are used to access the object of any domain and object list is known as **capability** **list**. User is not allowed to make any changes in the list.

The best example to understand these lists is lock- key system in which the key values are never modified by the user of the system.


---

# Problem 2
## Step-1

**Security of sensitive data**

When a file is containing sensitive data, it is marked as sensitive file. The overwritten scheme is used to protect that file. A sensitive data should never be accessed by any unauthorized person or program. Thus, to provide extra security to any file containing sensitive data, this scheme is used.

By the overwrite operation, the old data of that file is removed and new data is stored in that file. If this is not done, the new file will acquire extra space and security of old file will increase the cost. This scheme is mostly use with extremely secret information.


---

# Problem 3
## Step-1

**Ring protection system**

It is given that the ring system the access of objects is provided according to the levels. As the level of access is increased, the rights to access any object is decreased.

The capabilities of domain ![](https://media.cheggcdn.com/study/a6d/a6dbb759-67af-4d52-90ab-e7bce31cb164/5644-14-3PE-i1.png) are specified at ![](https://media.cheggcdn.com/study/18b/18b2c1a4-e163-4e5f-95b2-229ad20a659b/5644-14-3PE-i2.png) level and![](https://media.cheggcdn.com/study/1ae/1ae6ee6c-70ba-4f04-a0d8-8b2d0d0b2ba7/5644-14-3PE-i3.png) level specifies the object of domain ![](https://media.cheggcdn.com/study/a26/a26f9a65-c1dc-4c15-8f11-d72f969c20e0/5644-14-3PE-i4.png). The value of level ![](https://media.cheggcdn.com/study/86a/86a7df7c-700c-4bdd-bb56-493ee73ead62/5644-14-3PE-i5.png) is greater than level ![](https://media.cheggcdn.com/study/429/429d0bb9-229e-4189-bd3c-616dd8aab7a3/5644-14-3PE-i6.png). It means that ![](https://media.cheggcdn.com/study/988/98891e6f-a989-443e-993f-c58e9a3bb904/5644-14-3PE-i7.png) contains less access rights of that domain ![](https://media.cheggcdn.com/study/c2d/c2d3d637-19e2-46fc-85bc-3585ae7488a6/5644-14-3PE-i8.png). So, it can be said that ![](https://media.cheggcdn.com/study/7ec/7ecbd3bc-203f-457b-91c3-b2f857a4def5/5644-14-3PE-i9.png) is the subset of ![](https://media.cheggcdn.com/study/6fa/6fa19ca1-dfdf-4415-8ba0-24c13e32854c/5644-14-3PE-i10.png).


---

# Problem 4
## Step-1

2481-14-2E SA: 8683

________________________________________________________________________

**A(x , y) is a subset of A(z , y)**.

**Explanation:**

Given x is descendant of z, and descendant can never have the ability to do anything that its ancestors cannot do. Suppose if A(z , y) has only Read and Write access rights to object y, then A(x , y) must be either Read or Write or both or no access at all to object y but not have execute permission which is not in A(z , y). From this we can conclude, A(x , y) is subset of A(z , y). 


---

# Problem 5
## Step-1

2481-14-12E SA: 8683

SR: 6376

Every process has an associated stack of its ongoing method invocations. In some cases, we would pass access rights along with the method parameters to get access to a protected resource. If that stack is shared among processes, then the contents of stack could be compromised by other processes. That means, the processes which don’t have access to a protected resource can also get access to that which means protection is violated. 


---

# Problem 6
## Step-1

2481-14-15E SA: 8683

SR: 6376

The protection structure is called as **Ring (or Hierarchical) structure**. In this structure, if an object must be accessible in domain Dj but not accessible in domain Di, then we must have j < i.

Example: MULTICS – it uses a ring structure


---

# Problem 7
## Step-1

**Counting the total accesses**

The access to that object is provided to ![](https://media.cheggcdn.com/study/d8e/d8eb3ccd-6352-41bc-9980-310cfa1ede64/5644-14-7PE-i1.png) times. Declare a variable count of int data type and set it to zero. The value of variable count is increased by one at each time when the object is accessed.

Thus when the value of count variable is equal to ![](https://media.cheggcdn.com/study/cc9/cc9db849-4c2b-4a15-878a-6e504d6cfc59/5644-14-7PE-i2.png), no more accesses are permitted for that object.


---

# Problem 8
## Step-1

2481-14-13E SA: 8683 

SR: 4460 

________________________________________________________________________

The **access list** of an object which is an efficient mechanism to keep track of access rights of an object, has been checked periodically to see whether the object has any access rights or not. The object may be **hardware object** (such as CPU, memory segments, printers, disks and tape drives) (or) **software object** (such as files, programs and semaphores). If access list of corresponding object contains no access rights, then that object is no longer accessible to any process. Thus, this object will be added to list of garbage collectable objects, and periodically this list can be deleted from memory and the freed space will be returned to the system. 


---

# Problem 9
## Step-1

**Security issues**

The input/output operations are performed in the kernel mode. The kernel is answerable for maintaining the input/output.

When any user performs the input/output operation, it will require some software and hardware resources. This is done, to maintain the integrity of the system. When any user performs its own input/output operations, the user will require resources. If the resources are allocated to the user, the integrity of the system will not be maintained.

If the integrity of the system is not maintained, the security of that system will never be maintained. Thus, the protection of system with multiple users is very difficult.


---

# Problem 10
## Step-1

**Capability list**

A list containing the set of operations which are used to access the object of any domain and object list is known as **capability** **list**.

The capability list is protected object. User is not allowed to make any changes in the list because the direct access to the list is not allowed. The user can access the list indirectly. The operating system of the computer is responsible to ensure that any user can not directly access the capability list.


---

# Problem 11
## Step-1

Ring field of a segment descriptor holds the ring number associated to that segment. Actually, as the higher-numbered ring is the subset of ring 0, it can’t access the procedures of ring 0.

To allow controlled domain switching, one can modify the ring field of the segment descriptor to include access bracket, limit and list of gates.

If a process executing in ring i calls a procedure (or segments) with access bracket (b1, b2) then the call is allowed if b1 ![](https://media.cheggcdn.com/study/9e1/9e18e706-7c98-457b-80fa-51ff5d37c8da/300-14-1e-i1.png) _i_![](https://media.cheggcdn.com/study/7a0/7a09e64e-59ee-4ff2-a95b-d47b7ba5ece8/300-14-1e-i2.png) b2 , and the current ring number on the process remains i.


---

# Problem 12
## Step-1

Processes execute in domains and may use any of the access rights in the domain to access and manipulate objects. During its lifetime, a process may be either bound to a protection domain or allowed to switch from one domain to another.

The access matrix is a general model of protection that provides a mechanism for protection without imposing a particular protection policy on the system or its users. 

The process switching from domain A to domain B can enjoy the privileges of domain B. But vice versa is possible only if both have same type of operations on same objects.


---

# Problem 13
## Step-1

**Dynamic allocation**

The computer game is played by different users. The users of the game are divided into three different categories.

A dynamic method can be used, so that, all the users can plays the game on their respective time. When the time segment of any group is over, the revocation process is occurred. The revocation process must be temporary, immediate and selective so the users can play the game on the next day.

By the revocation process, the scheduling of the game for different users can be done to divide the time segment between different users.


---

# Problem 14
## Step-1

Capabilities scheme that implement revocation are:-

i) Reacquisition: - Periodically, capabilities are deleted from each domain.

ii) Back – Pointers: - A list of pointers is maintained with each object, pointing to all capabilities associated with that object.

iii) Indirection: - The capabilities point indirectly, not directly, to the objects. Each capability points to a unique entry in a 

global table, which in turn points to the object

iv) Key: - A key is a unique bit – pattern that can be associated 

with each capability. This key is defined when the 

capability is created, and it can be neither modified nor 

inspected by the process owning that capability.


---

# Problem 15
## Step-1

_Strength:_

Access privileges are stored along with the object; thus, it is easier to revoke or expand privileges associated with that object.

_Weakness:_

Requires overhead in checking whether the requesting domain has access rights for this object. Depending upon the number of domains allowed, this can be time consuming.


---

# Problem 16
## Step-1

The capability list associated with a domain, but it is never directly accessible to a process executing in that domain. Capability list is itself a protected object, maintained by OS and accessed by user only indirectly. Capability never allowed to migrate into any address space directly accessible by a user process. If all capabilities are secure, the object they protect is also secure against unauthorized access.

_Strengths:_

• It provides an efficient means of enforcing access control at runtime.

• It allows a user to grant access to other users by providing a copy of required capability.

_Weaknesses:_

• Since there are several domains it is difficult to determine which domain corresponds to which object. This can complicate revocation of access rights.

• Due to several users propagation of access rights is more complicated to control.

• Requires numerous entries per user for typical and has difficulty with establishing who has access to individual files.


---

# Problem 17
## Step-1

Hydra provides considerable flexibility. It also provides right amplification. This scheme allows to a procedure to be certified as trustworthy to act on a formal parameter of a specified type on behalf of any process that holds a right to execute the procedure. Hydra provides a large library of system-defined procedures that can be called by user programs. It is user friendly.


---

# Problem 18
## Step-1

HYDRA also provides right amplification this scheme allows a procedure to be certified as trustworthy to act on a formal parameter of a specified type on behalf of any process that holds a right to execute the procedure. 

In some capability systems (e.g., Hydra), the internal representation of an object is only accessible within the object. If a process is executing outside the object, it has no access to the internal structure of the object. However, when the process is within the object, it must have access. Using amplification, the act of executing within the object automatically provides the process with additional rights, namely the ability to access the internal representation. The rights to be added are specified in an object template.


---

# Problem 19
## Step-1

2481-14-16E SA: 8683

SR: 6376

The **need-to-know principle** states that at any time, a process should be able to access only those resources that it currently requires to complete its task. 

The principle is an important safeguard for a protection system. It is useful in limiting the amount of damage a faulty process can cause in the system by restricting access to the unnecessary resources. For example, when process p invokes procedure A, the procedure should be allowed to access only its own variables and the formal parameters passed to it; it should not be able to access all the variables of process p.


---

# Problem 20
## Step-1

a) In the MULTICS system, the protection domains are organized hierarchically into a ring structure. Each sing corresponds to a single domain the rings are numbered from 0 – 7.

_Disadvantage:_

• It does not allow to enforce the need to know principle.

## Step-2

b) Hydra’s Capability:- It provides considerable flexibility. A fixed set of possible access rights is known to and interpreted by the system. These right includes

basic access of right ie read write or execute a memory segment. The interpretation of user—defined rights is performed by user’s program, but the system provides access protection for these rights. These facilities constitute a significant development in protection technology.

## Step-3

c) Every thread in JVM has an associated stack of its ongoing method invocation when its called may not be trusted, a method executes an access request within a do-privileged block to perform the access to protected resource directly or indirectly 


---

# Problem 21
## Step-1

If a Java program is allowed to directly alter the annotations of its stack frame, there is no encapsulation. Then no abstraction of data or methods. Then total protection system will be ruined.


---

# Problem 22
## Step-1

Our model of protection can be viewed abstractly as a matrix called an access matrix. The rows represent domains and the columns represent objects. The access matrix provides an appropriate mechanism for defining and implementing strict control for both static and dynamic association between processes and domain.

Role Based Access Control (RBAC) is a facility revolves around privileges. A privilege is a right to execute a system call or to use an option within that system call. Privileges can be assigned to processes, limiting them to exactly the access they need to perform their work. Privileges and programs can also be assigned to roles. Users are assigned roles or can take roles based on passwords to the roles. In this way a user can take role that enables a privilege, allowing the user to run a program to accomplish a specific task.

RBAC decreases the security risk associated with superusers .


---

# Problem 23
## Step-1

A key time-tested guiding principle for protection is the principle of least privilege. An OS following the principle of least privilege implements its features, programs, system calls and data structure so that failure or compromise of a component does the minimum damage and allows the minimum damage to be done. Principle of least privilege can produce a more secure comporting environment.


---

# Problem 24
## Step-1

Consider the anology of a security guard with a pass key. If this key allows the guard into just the public areas that she guards, then misuse of key will result in minimal damage. If however, the pass key allows access to all areas, then damage from its being lost, stolen, misused, copied or otherwise compromised will be much greater.

Some of the most famous violations of the principle of least privilege exist in UNIX systems. For example, on UNIX systems, you generally need to have root privileges to run a service on a port number less than 1024. So, to run a mail server on port 25 -- the traditional SMTP port -- a program needs the privileges of the root user. However, once a program has set up shop on port 25, there is no compelling need for it to ever use root privileges again. A security-conscious program would give up root privileges and let the operating system know that it should never require those privileges again (at least, not until the next run of the program). One large problem with some e-mail servers is that they don't give up their root permissions once they have grabbed the mail port (Sendmail is a classic example). Therefore, if someone finds a way to trick such a mail server into doing something nefarious, it will succeed. For example, if a malicious attacker were to find a suitable stack overflow in Sendmail, then that overflow could be used to trick the program into running arbitrary code. Because Sendmail runs with root permissions, any valid attempt by the attacker will succeed. 


---

