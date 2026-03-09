# Problem 1
## Step-1

**File deletion**

Major advantage of deleting files when a user logs off from a system is deletion of unnecessary files. The files which are no more required are deleted automatically. This saves disk space.

## Step-2

The advantage of keeping the files unless specified by the user to delete is that there is a record of files that the user may forget to store. These files may be left out accidently; however they may be very important. Thus, a backup of data are maintained.


---

# Problem 2
## Step-1

**File:**

• A file is a collection of data or some information saved on secondary storage using a filename. 

• A file name is given to a file for faster accesses. There are many different types of files like data files, text files, program file and so on.

• The file name is given by the creator of the file. 

• A file has a well-defined structure, which depend on its _type_.

• The _file type_ is specified by splitting the name of the file into two parts,

o A name

o An extension

• For examples: program.java, address.docx, feedback.xlsm

## Step-2

The interpretation on the type of the file changes from system to system.

• There are certain systems in which operations on files depends on the type of the file. 

• There are other systems where the interpretation of a files data is left to the process and does not provide any help in the accessing the data.

• The system that is “better” depends on the needs of the processes on the system, and the demands the users place on the operating system. 

• If a system is working mostly on database applications, it is efficient for the operating system to implement a database type file and provide operations.

• Some systems do not implement multiple file types, because this keeps the operating system size smaller and it must contain code to support different file structures to support different file types. 


---

# Problem 3
## Step-1

**Files**

The **advantage** of a system supporting a variety of file structures is that there is no requirement of an application supporting each file structure. The system itself is sufficient for supporting different file structures. This also implies that the support provided by the system is much more efficient as compared to the support provided by applications.

## Step-2

A possible **disadvantage** of this approach is increased size of the system to be efficient enough to provide support for different file structures. Moreover, different applications may need some file types which are not supported by the system altogether. Thus, they may fail to run on these systems. 

## Step-3

On the other hand, an alternative approach, followed by systems such as UNIX, which treats all files as a byte stream is **advantageous** in terms of simplicity. Since all files are treated as a stream of bytes, different supports are not required for different file structures which simplify the task of the operating system. The application itself takes the charge of file definition required.


---

# Problem 4
## Step-1

2481-10-11E SA: 8683

SR: 6376

**Yes** , we can simulate a multilevel directory structure with a single-level directory structure which uses arbitrarily large file names. Each directory name can essentially be appended to the primary file name. This can be done by using the character “.” to indicate the end of a subdirectory. For example, the name _user1_ _.test.file1_ specifies that _file_ _1_ is a file in subdirectory _test_ which in turn is in the root directory _user1_. 

In contrast with the multilevel directory scheme, which doesn’t allow local user files to be accessed by other users, this scheme allows to access files of other users by specifying their complete search path. 

However, the scheme will fail if the length of the file names is restricted to seven characters. Then the answer would be no. We cannot simulate a multilevel directory structure with a single-level directory structure.****


---

# Problem 5
## Step-1

2481-10-7E SA: 8683

SR: 4460

________________________________________________________________________

**The purpose of open() and close() system call** : 

The **open()** system call can be made before a file is first used actively. The operating system keeps a small table, called the open-file table, containing information about all open files. The open() operation takes a file name and searches the directory, copying the directory entry into the open-file table. The open() call can also accept access mode information-create, read-only, read-write, append-only, and so on. This mode is checked against the file`s permissions. If the request mode is allowed, the file is opened for the process. The open() system call typically returns a pointer to the entry in the open-file table.

If the process completes its operation on a given file then it issue a **close()** system call. The **close()** call decreases the open count, which could be associated with each file to indicate how many processes have the file open. When open count reaches the zero, the file is no longer in use, and the file entry is removed from the open-file table.


---

# Problem 6
## Step-1

2481-10-3E SA: 8683

SR: 6376

a)

If a subdirectory can be read and written by an authorized user, just as ordinary files the following problems can arise.

**Consistency:** The user can either accidentally or maliciously modify entries in the directory so that the entry does not accurately reflect information about the file such as its name, size, time of creation, time of last modification etc.

It is also possible that the user can delete or create new entries in the directory which do not accurately reflect the status of the file system. For instance, the user can create/delete an entry in the directory without actually creating/deleting the file. The file would continue to exist in the file-system but would be “hidden” as it would not be visible in a directory.

**Protection:** The user can change the file permissions either accidentally or maliciously thereby authorizing unauthorized users access to the file.

## Step-2

b)

To deal with the protection problems, the operating system should ensure that the user modifies directory structures in a controlled and disciplined manner. It should**** not allow user to write directly onto the subdirectory, rather provide some system operation to do so. This could be done having specific calls such as create, delete, chmod etc to modify the entries in the directory and the information associated with each entry in the directory.


---

# Problem 7
## Step-1

2481-10-5E SA: 8683

SR: 6376

**a**)

**This can be done in two ways in UNIX:**

1\. All the 4990 user names are included in a single access control list.

2\. Group all the 4,990 users into a single group and set the access permissions accordingly.

## Step-2

**b**) 

**The following scheme can be more effective for the given purpose than the scheme provided by UNIX.**

The problem with the above scheme is the length of the access control list is large. Constructing such a list may be a tedious or unrewarding task, especially if we do not know in advance the list of users in the system. 

In the new scheme, we would create an access-control list with no access privileges allowed and then we will add remaining ten users to this list. The universal access to files applies to all users who are not listed in access control list. In this scheme the length of the list is reduced.


---

# Problem 8
## Step-1

**Control lists**

A control list can be maintained for each file to specify the authorized users of the file. Such an approach has lesser space requirements as the information is stored at one place which specifies the list of users who can access a file.

## Step-2

On the other hand, an alternative approach associates control list with all the users specifying which files they can access. Such an approach is advantageous when the better performance is demanded as it involves very less overhead to open a file as compared to the previous approach.


---

# Problem 9
## Step-1

Let file1 be the old file and file2 be the new file. A user wishing to access file1 through an existing link will actually access file2. Note that the access protection for file file1 is used rather than the one associated with file2. This problem can be avoided by ensuring that all links to a deleted file are deleted also. This can be accomplished in several ways:

a. Maintain a list of all links to a file, removing each of them when the file is deleted. 

b. Retain the links, removing them when an attempt is made to access a deleted file. 

c. Maintain a file reference list (or counter), deleting the file only after all links or ref-erences to that file have been deleted.


---

# Problem 10
## Step-1

**![](https://media.cheggcdn.com/study/d5f/d5f1fca9-1139-4bff-8c8f-09da7f411acf/13258-11-10E-i1.png) ** **,** the operating system does not maintain the separate table to maintain the files for each and every user instead it just maintain the central open-file table which contains the accessed references to files by users at present time.

## Step-2

**Reason:**

The central open-file table is used to maintain the details of currently opened files references.

• So, the files can be accessed by more than one process at same time.

• If one process removes the files then it should not be removed until all processes file accessing have stopped it.

• This verification can be done only when more than one process accessing the file.

## Step-3

![](https://media.cheggcdn.com/study/eb2/eb2d6b10-8875-4fa6-9e01-68bb7d7386cb/13258-11-10E-i2.png), the operating systems should be maintaining the separate entries for two processes in open-file table.

**Reason:**

When more than one process accessing the files, then it maintain the separate states to track the current location of files accessing by more than one process.

• So, accessing the same files by two different processes should maintain the separate states to track the details that is, which parts of files can be accessed by two processes.


---

# Problem 11
## Step-1

300-10-3E

If a lock is mandatory, then once a process acquires an exclusive lock, OS will for event any other process from accessing the locked file. If the locking scheme is mandatory, Os ensures locking integrity. 

But for advisory lacking, it is up to software developers to ensure that locks are appropriately acquired and released.

Windows employs mandatory lock where as Unix employs advisory lock.


---

# Problem 12
## Step-1

In Sequential access method, information in the file is accessed one record after the other.

Examples of applications that typically access files according to Sequential Method are as follows:

1\. Payroll Processing – Employees of the company are arranged in serial order in Payroll Application. A particular record can be accessed only after accessing the records prior to it. 

2\. In music players and video players, searching for a particular file is done after going through all the past files.

3\. Editors and compilers access files in sequential order.

## Step-2

In Random access method information is read and written in no particular order.

Examples of applications that typically access files by Random Method are as follows:

1\. Video and audio editors can access files randomly.

2\. In Magnetic Disc and Drums, a particular record can be accessed directly.

3\. Databases are example of random-access file. It is possible to retrieve information from the database directly using queries.


---

# Problem 13
## Step-1

**Advantages:**

• Automatic opening and closing of files provides an easy way to the user to invoke the functions. Because there is no need to open and close the functions for every time when the file is referenced. 

Therefore, it is more convenient way to the user to invoke the functions. 

## Step-2

**Disadvantages:**

• Implicit opening (automatic) requires more overhead than the explicit opening and closing of a file. That means opening and closing of files based on requirement is easier and simpler than automatic opening and closing. 


---

# Problem 14
## Step-1

Information in the file is processed in order, one record after other. This mode of access is by far the most common i.e., compiler and editor usually access file in this fashions. Sequential access is based on a tape model of a file and works as well a sequential access device as it does on random-access data. When the file system could prefetch the subsequent blocks in anticipation of future requests to these blocks. This

prefetching optimization would reduce the waiting time experienced by the process for future requests


---

# Problem 15
## Step-1

VMS and relative files. 

In random access, pointers are used. The file which you want to access will be searched by the pointer rand only. If the file is found, the pointer will stop there, if not found it will tell not found.

The pointers search for the particular index of the file where the file is present. 


---

# Problem 16
## Step-1

Mount point is the location within the file-structure where the file is to be attached. Typically, mount point is an empty directory.

If the file system is mounted at the mount point than the OS enables it to traverse its directory structure switching among file system as appropriate.


---

# Problem 17
## Step-1

**File sharing by maintaining a single copy:**

A user performs different modifications to the file which is a single copy of file sharing, then the user may not obtain the correct data of a file after concurrent updates.

Because, the file sharing with a single copy of the file will not be updated concurrently. It will result an incorrect information obtained by the user. Then the file is being left in incorrect state and the user may not obtain the appropriate information.

**Merits of a single copy of file sharing:**

• No wastage of memory, because the data is stored in a single file.

• More number of users can access the single file.

## Step-2

**File sharing by maintaining multiple copies:**

File sharing with multiple copies allows multiple user to access and share the files. Therefore, multiple users can perform different operations like writing to a file, deleting a file etc. 

As multiple users can access multiple copies of files, the data in the file may be inconsistent and with respect to each other. 

**Merits of multiple copies of file sharing:**

• It is more efficient than maintaining a single copy.

• Wastage of memory by maintaining multiple copies same file.

• Data is inconsistent.


---

# Problem 18
## Step-1

Remote file systems have more failure modes. If a client uses a remote file system, it perform file open operation from remote host, look up to open files, reading or writing data to files, and closing files. Now if partition of network is performed, or a crash of the server, or scheduled shutdown of server, suddenly, remote file system either terminates all operation to lost server on delay operations until the server is again reachable. These failure schema ties are defined and implemented as a part of remote-file – system protocol. Termination of all operation results in loss of data and patience. Hence, most DRS protocols either enforce or allow delaying of file-system operation to remote hosts, with the hope that remote host will because available again.


---

# Problem 19
## Step-1

Consistency semantics represent an important criterion for evaluating, any file system that supports file sharing. Consistency semantics are directly related to the process synchronization.

In UNIX semantics, a file is associated with a single physical image that is accessed as exclusive resources. Contention for this single charge causes delays in user processes 


---

