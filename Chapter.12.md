# Problem 1
## Step-1

**a.**

**The block is added at the beginning:**

**Contiguous allocation:**

The file contains 100 blocks. If the user wants to add a block at the beginning, it requires to move the 100 blocks and write the new block at the beginning. It means, it requires 100 reads and 101 writes.

100 reads+101 writes=201 operations  
---  
  
**Therefore, the total 201 disk I/O operations required to add a block at the beginning.**

**Linked allocation:**

In linked list allocation, a new block is added at the beginning by just create a new entry and initialize the pointer to null. It represents an empty file and file-management system finds a free block. The free block is written and linked to the end. 

If the user wants to add a block at the beginning, it just creates a single file at starting. 

**Therefore, 1 I/O operation is required for the Linked allocation.**

**Indexed allocation:**

In index allocation, an _i_ th entry of the index represents _i_ th block of the file. The file currently contains 100 blocks. If the user wants to add a new block at the beginning, add an index at the beginning. 

**Therefore, 1 disk I/O operation is required for the Indexed allocation.**

![Picture 1](https://media.cheggcdn.com/media/377/s583x147/37774785-9a40-4f3b-a2c7-f98be75b2362/13258-12-1PE-i1.png)

## Step-2

**b.**

**The block is added in the middle:**

**Contiguous allocation:**

The file contains 100 blocks. If the user wants to add a block at middle, it requires to move the 50 blocks and write the new block in the middle. It means, it requires 50 reads and 51 writes.

50 reads+51 writes=101 operations  
---  
  
**Therefore, the total 101 disk I/O operations required to add a block at the middle.**

**Linked allocation:**

If the user wants to add a block at the middle, it required to move the first 50 blocks, add the block and set the pointer to null. It represents an empty block in the memory, a write causes a free-space management allocates new block and linked to the end of the file.

Therefore, 50 read operations and add a new block requires 1 operation, 1 operation to points to the next block.

Therefore, total 52 disk I/O operations are required.

**Indexed allocation:**

In this allocation, one operation is required to write a new block and update the index value in the middle.

Therefore, only 1 I/O operation is required.

## Step-3

![Picture 11](https://media.cheggcdn.com/media/f3c/s583x155/f3c67877-1a99-42d9-a86b-bda4ea3a71ec/13258-12-1PE-i2.png)

## Step-4

**c.**

**The block is added at the end:**

**Contiguous allocation:**

If the user wants to add a new block at the end, it just accesses the last block and add the new block.

Therefore, only 1 disk I/O operation is required.

**Linked allocation:**

If the user wants to add a block at the end, it moves to end of the linked list. Then add the new block and set the pointer to null. It represents an empty block in the memory, a write causes a free-space management allocates a new block and linked to the end of the file.

## Step-5

Therefore, 1operation required to move the end of the list and adding of new block requires 1 operation, 1 operation to points to the next block.

Therefore, total 3 disc I/O operations are required.

**Indexed allocation:**

In this allocation, one operation is required to add new block at end. Therefore, only 1 I/O operation is required.

## Step-6

![Picture 12](https://media.cheggcdn.com/media/674/s588x156/6740d306-96c9-4cc6-96f7-165e4f88edea/13258-12-1PE-i3.png)

## Step-7

**d.**

**The block is removed from the beginning:**

**Contiguous allocation:**

If the user wants to remove a block at the beginning, it requires to move the 100 blocks. It requires 100 I/O operations. The user wants to remove one block at the end, it means the user start from the second block and remove the last block. It requires 98 I/O operations.

**Therefore, total 198 disk I/O operations are required to remove the block at beginning.**

**Linked allocation:**

Only 1 disk I/O operation is enough to remove the block at the beginning, because the pointer in the linked allocation shows the first block.

**Therefore, 1 disk I/O operation is required to remove the block at beginning.**

**Indexed allocation:**

Indexed allocation of a file doesn’t require any I/O operations because, it directly removes the index of the first block.

![Picture 13](https://media.cheggcdn.com/media/8f6/s583x155/8f66a3b3-378d-4a9d-930d-0c5de209e8a6/13258-12-1PE-i4.png)

## Step-8

**e.**

**The block is removed from the middle:**

**Contiguous allocation:**

The user needs to move the first 50 blocks to remove one block in the middle. It requires 50 I/O operations. Now, start from the second block and remove the middle block. It reduces the I/O operations to 48. 

**Therefore, total 98 disk I/O operations are required to remove the block at the middle.**

**Linked allocation:**

The user needs to move the list from first to middle means 50. It requires 50 I/O operations. Now, the user reads the address of the 52nd block and place that address into the 50th block. 1 I/O operation is required to read the 52nd block and 1 operation required to set the address into 50th block.

**Therefore, total 52 disk I/O operations are required to remove the block at the middle.**

**Indexed allocation:**

Indexed allocation of a file doesn’t require any I/O operations, because it directly removes the index of the middle block.

![Picture 14](https://media.cheggcdn.com/media/d60/s584x153/d6072be2-5ab9-4b07-95f8-4e3e45734a70/13258-12-1PE-i5.png)

## Step-9

**f.**

**The block is removed from the end:**

**Contiguous allocation:**

It does not require I/O operations to remove at the end. It updates the information of the memory.

**Linked allocation:**

As the current file has 100 blocks, the pointer in the linked list must move through the 100 blocks and remove the last block.

**Therefore, it requires 100 disk I/O operations.**

**Indexed allocation:**

## Step-10

In this allocation, the last block is directly removed because the blocks can be accessed directly in the indexed accessing. 

Therefore, it doesn’t require any operations. 

![Picture 15](https://media.cheggcdn.com/media/393/s583x155/3932f576-3d37-4226-9fbf-e22564945a48/13258-12-1PE-i6.png)


---

# Problem 2
## Step-1

**File system**

If a file system is mounted at multiple locations simultaneously, then there would be multiple paths that would lead to a file. Multiple paths can create confusion among users. Also, when a file is removed, all the paths that lead to that file are deleted.


---

# Problem 3
## Step-1

2481-11-9E SA: 8683

SR: 6376

The bit map used for file allocation must be kept on mass storage, rather than in main memory, **because bit vectors are inefficient unless the entire vector is kept in main memory.** Keeping it in main memory is possible for smaller disks, such as on microcomputers, but not for larger ones. A 1.3 GB disk with 512-byte blocks would need a bit map of over 332 KB to track its free blocks and 1-TB disk with 4-KB blocks requires 32 MB to store its bit map. As disk size constantly increases, the size of the bit map file increases. So, we will store bit map file on mass storage, rather than in main memory.


---

# Problem 4
## Step-1

**Allocation methods**

**Contiguous Allocation** : under this approach, files on the disk occupy contiguous blocks. This type of allocation is well suited when a file needs to be accessed sequentially. The access time would be small as the file would be stored in a set of contiguous blocks. This allocation scheme is useful for smaller files.

## Step-2

**Linked allocation** : using this approach, a linked list of blocks scattered over the disk is used to store a file. This approach should be followed to store large files which are to be accessed in a sequential manner since each block is linked to another block in the linked list of blocks.

## Step-3

**Indexed allocation** : This scheme uses an index block for each file containing the block addresses on the disk. This approach is useful for random access. File which need large disk space and need random access should be stored using this approach.


---

# Problem 5
## Step-1

2481-11-15E SA: 8683 SR: 6376

• This method of implementing a file is efficient and requires more overhead than the standard contiguous allocation.

• When compared to the standard linked allocation it is less efficient and requires less overhead.


---

# Problem 6
## Step-1

**Cache**

Caches improve performance by holding the data which are frequently used. They allow enable communication between different components which may have variable speeds. The communication is more effective using caches as the data from the device with a lower speed is temporarily stored in the cache.

## Step-2

The cache size is usually limited because caches are much more expensive than other storage devices. Hence, as the size of the cache increases, the cost increases as well. Thus, using larger caches would increase the cost of the system.


---

# Problem 7
## Step-1

2481-11-11E SA: 8683

SR: 6376

**Advantages to user by creating internal tables dynamically by operating system are:**

1) It is more flexible to add new entries into the table as and when required.

2) No need to allocate enough space for each file before it is opened. 

**Penalties to operating system:**

1) Operating system must have appropriate data structures and algorithms to support dynamic allocation of internal tables.

2) There is more potential for bugs, as the kernel structures are more complicated.


---

# Problem 8
## Step-1

**Virtual file systems**

A virtual file system (VFS) layer separates the operations specific to file systems from their respective implementations using the VFS interface. It is used to represent a file uniquely over a network. It achieves this indirection in a fashion similar to the object-oriented techniques in programming. 

Generic system calls can be made to different file systems. The data structures and function calls of all file systems are provided to the VFS layer. Then, when a system call is made, it is translated first into functions which are specific to the desired file system. The program which initiated this system call does not use any code specific to a file-system. Thus, the structures are independent of the file-system. When the system call is translated at the virtual file system layer, they are translated specific to their respective file systems.

This is how a VFS layer supports multiple file systems-types.


---

# Problem 9
## Step-1

a) Total amount of space needed for a file is known in advance, pre-allocation may be inefficient. A file that will grow slowly over a long period must be allocated enough space for its final size, enough though must of that space will be unused for a long time. The file therefore has a large amount of **internal fragmentation**. 

Advantage is for sequential access, the file system remembers the disk address of the last block referenced and when necessary, reads the next block. For direct access to block _i_ of a file that starts at block _b_ , we can immediately access block _b_ +_i_. 

## Step-2

b) Dynamic storage allocation involves how to satisfy, a request of size _n_(process size) from a list of free holes. Advantage is there will be no internal fragmentation. But first-fit and best-fit strategies used for selecting a free hole suffers from **external fragmentation**.

## Step-3

c) External fragmentation becomes a problem when largest contiguous chunks are insufficient for a request; storage is fragmented into a number of holes, no one of which is large enough to store the data. Depending on total amount of disk storage and the average file size.


---

# Problem 10
## Step-1

The following table shows the performance of **contiguous, linked, indexed** technique for allocating disk blocks for both random and sequential file access. 

**Contiguous Disk Allocation** |  **Linked-List Allocation** |  **Indexed Allocation**  
---|---|---  
The name contiguous disk allocation suggests itself; a contiguous disk memory allocation technique provides an immediate way of storing file blocks.  |  In this technique, the file blocks on a disk come up with a pointer towards successor block.  .  |  As the name suggests, this technique makes use of a unique index that helps in locating any file block with a single glance.   
The allocation is performed speedily, and hence the user has to mention file size in advance.  |  In this pointer has nothing else than address for the next file block on the disk, so it forms up a linked-list |  Similar, as contiguous allocation method user here needs to specify the file size in advance and the file mapping system runs a search for the location that is bigger enough to handle current file.   
Contiguous allocation method provides faster **sequential access**. |  Being far different from contiguous disk allocation method, linked-list has a dark side for **sequential access.** |  In this allocation technique, **sequential and random** accesses both take minimum time span to locate a file block.  
The efforts for calculating **random disk** location is minimized in this technique; as all it needs is just adding an offset entry to the first block location of the file. |  The reason behind failure towards sequential access lies beneath the lack of contiguous blocks. Similarly, the need of performing several sequential searches makes **random access** complex. |  In this allocation technique, **sequential and random** accesses both take minimum time span to locate a file block. Any increase in file size is adaptable but may particularly require updating the index array.  
  
****


---

# Problem 11
## Step-1

An important variant on linked allocation is the use of a file-allocation table (FAT). A section of disk at the beginning of each volume is set a side to contain the table. The table has one entry for each disk block and is indexed by block number. The directory entry contains the block number of the first block of file. The table entry indexed by that block number contains the block number of the next block in file. This chain continues until the last block, which has a special-end-of file value as the table entry. Unused blocks are indicated by a 0 table value. Advantage is that random-access time is improved, because the disk head can find the location of any block by reading the information in FAT.


---

# Problem 12
## Step-1

a) Free – space allocation methods also influence the efficiency of disk-space use, the performance of the file system, and reliability of secondary storage. If the pointer to the free-space list is lost, the system can reconstruct the list by implementing any technique like bit-vector, linked list, etc. But the disadvantage is previously freed space may not be considered completely.

## Step-2

b) If the file is present at the pointer in any of the first 12 pointers, as they point to direct blocks no extra I/O operations are required except for reading.

If the file is at the pointer pointing to single indirect block, then I/O operations to find the direct block and to read file are needed.

If the file is at the pointer pointing to double indirect block, then 3 I/O operations are required.

## Step-3

c) UNIX also provides unified buffer cache. Firstly to use memory mapping secondly use of system calls to read() and write(). Due to this caching, disk latency time will be reduced as well as if any failure in the main memory occurs the pointer as it is cached won’t be lost.


---

# Problem 13
## Step-1

If disk space is used as eight 512-byte blocks or single 4-KB block, the file system memory is swapping in and out, means the internal fragmentation can be reduced. 

## Step-2

To improve the performance of flexibility to the file system. The first memory is allocated as a single 4-KB block and two contiguous 512-bye blocks. In addition to the blocks, there is a bitmap of a free block to maintain the state of the subblocks which is currently used inside the block.

## Step-3

The modifications to be done to support the file allocate system feature is the file allocator block is examining the extra state to allocate subblocks and then combine to form the subblocks to obtain the single larger block when all the subblocks become free.


---

# Problem 14
## Step-1

The virtual memory system does not interface with buffer, cache; the contents of the file in the buffer cache must be copied into the page cache. Double-caching, requires caching file-system data twice. It wastes memory and also wastes significant CPU and I/O cycles due to extra data movement within system memory. Inconsistencies between two caches result in corrupt files. Hence double caching benefits are avoided. Another say Solaris used page-caching algorithms that share unused memory with processes. Another version Solaris 7 implemented priority paging that gives priority to process pages over the page cache. Solaris 9 and 10 changed the algorithms to maximize memory use and minimize thrashing. This shows the complexities of performance optimizing and caching.


---

# Problem 15
## Step-1

**a.**

Consider the logical and physical block size of a file system is 512 bytes.

General procedure to map the logical address to the physical address is an addition of logical address with the displacement address. The resultant will give the location of the physical memory.

Procedure of mapping the logical address to physical address system by the three allocation techniques is as follows:

**Note: Assume the starting address of the file be the Z.**

**Contiguous allocation technique:**

• Divide the logical address by the block size of 512 bytes with R as the remainder and Q as the quotient respectively.

• Now, add the quotient Q to Z. This will give the location of the physical block number.

• The remainder R is the displacement number into the block.

## Step-2

**Linked Allocation technique:**

• In linked allocation, each block contains a pointer (address) to the next block. Therefore, user can simply read the blocks by following the pointers to access the files. Each block has a free-space to store the data as well as pointer. But, the pointer is not visible to the user.

• The mapping of logical to physical address is divide the logical physical address by the block size of 511 bytes (assume the pointer size is 1 byte and it is not visible) with Q as the quotient and R as the remainder.

• Uncover the linked list to getting the Q+1 block. This means, Q+1 will give the address of the next block.

• The remainder R+1 will give the displacement into the last physical block number.

## Step-3

**Indexed Allocation technique:**

• Index file allocation has an index which maintains an array of disk-block addresses to access the required file.

• Mapping of logical to physical address is divide the logical address by the block size of 512 bytes with Q as the quotient and R as the remainder.

• First, place the index block into the memory. This has an array of address.

• The location of the quotient Q in the index will give the location of the physical block address.

• The remainder R is the displacement into the desired physical block location.

## Step-4

**b.**

The calculation of number of physical blocks read from the disk is shown as follows:

**Contiguous allocation technique:**

The contiguous allocation defines the addresses in linear order on the disk. As the current logic block is 10 and wants to access the logical block 4, simply 1 physical block accessing is needed to read form the disk. 

Therefore, there is a need of **1****** physical block to read from the disk.

## Step-5

**Linked Allocation technique:**

It uses pointers to move from one block to another block. The current logical block is 10 and wants to access logical block 4, it simply moves the 4 locations in the linked list.

Therefore, there is a need of **4** physical blocks to read from the disk.

## Step-6

**Indexed Allocation technique:**

It maintains an index of addresses to access the blocks. The last block accessed is 10 and wants to access the block 4, it just checks the index of 10 and 4.

Therefore, there is a need of **2** physical blocks to read from the disk.


---

# Problem 16
## Step-1

2481-11-6E SA: 8683

SR: 6376

Given size of each disk block = 8 KB

There are 12 direct disk blocks, and single, double, and triple indirect disk blocks. So,

12 direct disk blocks size = 12 x 8 KB

= 96 KB

As a disc block is 8 KB (8192 bytes), and pointer requires 4 bytes, each disc block can hold up to 2048 (8192 / 4) addresses. 

Single indirect block size = 2048 x 8 KB

= 16 MB

Double indirect block size = 2048 x 2048 x 8 KB

= 32 GB

Triple indirect block size = 2048 x 2048 x 2048 x 8 KB

= 64 TB

Maximum size of a file can be stored = 96 KB + 16 MB + 32GB + 64 TB

= 64.0312653 TB

≈ 64.1 TB

**Maximum size of a file that can be stored in the given file system is ≈ 64.1 TB**  
---


---

# Problem 17
## Step-1

## Step-2


---

# Problem 18
## Step-1

For remote operation, there are two caches, the file-attributes (in ode information) cache and file-block cache. When a file is opened, the kernel checks with the remote server to determine whether to fetch on revalidate the cached attributes. The cached file-blocks are used only if the corresponding cached attributes are up to date. The attributes are up to date. The attribute cache is updated whenever new attributes arrives from the server. Cached attribute are, by default, discarded after 60 seconds. Both read ahead and delayed-write techniques are used between the server and the client. Clients do not free delayed-write blocks until the server confirms that the data have been written to disk


---

# Problem 19
## Step-1


---

# Problem 20
## Step-1

A user may notice that a particular file is either missing or corrupted long after the damage was done. Hence a plan is done to take a full backup from time to time that will be saved forever rather than reusing that backup medium. It is good to store these permanent backups far away from the regular backups to protect against hazard. It is not possible to restore any data from backups. This contrasts to the schedule given in Section 11.7.2 by having all subsequent backups.

## Step-2

To minimize the copying needed, we can use information from each file’s directory entry. For instance, if the backup program knows when the last backup of a file was done, and the file’s last written date in the directory indicates that the file has not changed since that date, then the file does not need to copy again.

Restore is easier because we can go to the last backup, rather than the full tape. More tape is used as more file changes, no intermediate tapes to need be read. 


---

# Problem 21
## Step-1

The inode numbers of file1.txt and file2.txt are - 1053017. 

The inode numbers of file1.txt and file2.txt are same. 

The contents are the also same of file1.txt and file2.txt.

## Step-2

Modifying file2.txt changes the contents of file1.txt. This is as they are linked to the same inode.

## Step-3

Removing file1.txt still leaves file2.txt around because the reference count of the inode is 2.

## Step-4

The unlink system call is used to remove file2.txt.

## Step-5

The inodes of file3.txt and file4.txt are different as one is a hard link and the other is a soft link. 

Editing the contents of file4.txt changes the contents of file3.txt. 

After deleting file3.txt on Linux, editing file4.txt with the vi editor makes it think it is editing a new file.

## Step-6

**Sample Output:**

12$ fortune | tee file1.txt

Volley Theory:

It is better to have lobbed and lost than never to have lobbed at all.

12$ ls -li file1.txt

1053017 -rw-rw-r--. 1 user1 user1 87 Dec 2 18:38 file1.txt

12$ ln file1.txt file2.txt

12$ ls -li file1.txt file2.txt

1053017 -rw-rw-r--. 2 user1 user1 87 Dec 2 18:38 file1.txt

1053017 -rw-rw-r--. 2 user1 user1 87 Dec 2 18:38 file2.txt

12$ vi file2.txt

12$ cat file2.txt

It is better to have lobbed and lost than never to have lobbed at all.

12$ cat file1.txt 

It is better to have lobbed and lost than never to have lobbed at all.

12$ ls -li file1.txt file2.txt 

1053017 -rw-rw-r--. 2 user1 user1 72 Dec 2 18:38 file1.txt

1053017 -rw-rw-r--. 2 user1 user1 72 Dec 2 18:38 file2.txt

12$ rm file1.txt

12$ ls -li file2.txt

1053017 -rw-rw-r--. 1 user1 user1 72 Dec 2 18:38 file2.txt

12$ strace rm file2.txt

execve("/usr/bin/rm", ["rm", "file2.txt"], [/* 71 vars */]) = 0

brk(0) = 0xe15000

mmap(NULL, 4096, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_ANONYMOUS, -1, 0) = 0x7f1ffe7f9000

access("/etc/ld.so.preload", R_OK) = -1 ENOENT (No such file or directory)

open("/etc/ld.so.cache", O_RDONLY|O_CLOEXEC) = 3

fstat(3, {st_mode=S_IFREG|0644, st_size=122428, ...}) = 0

mmap(NULL, 122428, PROT_READ, MAP_PRIVATE, 3, 0) = 0x7f1ffe7db000

close(3) = 0

open("/lib64/libc.so.6", O_RDONLY|O_CLOEXEC) = 3

read(3, "\177ELF\2\1\1\3\0\0\0\0\0\0\0\0\3\0>\0\1\0\0\0p\36\"e=\0\0\0"..., 832) = 832

fstat(3, {st_mode=S_IFREG|0755, st_size=2096496, ...}) = 0

mmap(0x3d65200000, 3920480, PROT_READ|PROT_EXEC, MAP_PRIVATE|MAP_DENYWRITE, 3, 0) = 0x3d65200000

mprotect(0x3d653b4000, 2093056, PROT_NONE) = 0

mmap(0x3d655b3000, 24576, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_DENYWRITE, 3, 0x1b3000) = 0x3d655b3000

mmap(0x3d655b9000, 16992, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_FIXED|MAP_ANONYMOUS, -1, 0) = 0x3d655b9000

close(3) = 0

mmap(NULL, 4096, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_ANONYMOUS, -1, 0) = 0x7f1ffe7da000

mmap(NULL, 8192, PROT_READ|PROT_WRITE, MAP_PRIVATE|MAP_ANONYMOUS, -1, 0) = 0x7f1ffe7d8000

arch_prctl(ARCH_SET_FS, 0x7f1ffe7d8740) = 0

mprotect(0x60d000, 4096, PROT_READ) = 0

mprotect(0x3d655b3000, 16384, PROT_READ) = 0

mprotect(0x3d64c1f000, 4096, PROT_READ) = 0

munmap(0x7f1ffe7db000, 122428) = 0

brk(0) = 0xe15000

brk(0xe36000) = 0xe36000

brk(0) = 0xe36000

open("/usr/lib/locale/locale-archive",O_RDONLY|O_CLOEXEC)=3

fstat(3, {st_mode=S_IFREG|0644, st_size=106070960, ...}) =0

mmap(NULL, 106070960, PROT_READ, MAP_PRIVATE, 3, 0) = 0x7f1ff82af000

## Step-7

close(3) = 0

ioctl(0, SNDCTL_TMR_TIMEBASE or SNDRV_TIMER_IOCTL_NEXT_DEVICE or TCGETS, {B38400 opost isig icanon echo ...}) = 0

newfstatat(AT_FDCWD, "file2.txt", {st_mode=S_IFREG|0664, st_size=72, ...}, AT_SYMLINK_NOFOLLOW) = 0

geteuid() = 1000

newfstatat(AT_FDCWD, "file2.txt", {st_mode=S_IFREG|0664, st_size=72, ...}, AT_SYMLINK_NOFOLLOW) = 0

faccessat(AT_FDCWD, "file2.txt", W_OK) = 0

unlinkat(AT_FDCWD, "file2.txt", 0) = 0

lseek(0, 0, SEEK_CUR) = -1 ESPIPE (Illegal seek)

close(0) = 0

close(1) = 0

close(2) = 0

exit_group(0) = ?

+++ exited with 0 +++

12$ fortune | tee file3.txt

"The question is rather: if we ever succeed in making a mind 'of nuts and

bolts', how will we know we have succeeded?

\-- Fergal Toomey

"It will tell us."

\-- Barry Kort

12$ ln -s file3.txt file4.txt

12$ ls -li file*.txt

1051337 -rw-rw-r--. 1 user1 user1 169 Dec 2 18:40 file3.txt

1053017 lrwxrwxrwx. 1 user1 user1 9 Dec 2 18:41 file4.txt -> file3.txt

12$ vi file4.txt

2 files to edit

12$ cat file4.txt

bolts', how will we know we have succeeded?

\-- Fergal Toomey

"It will tell us."

\-- Barry Kort

12$ cat file3.txt

bolts', how will we know we have succeeded?

\-- Fergal Toomey

"It will tell us."

\-- Barry Kort

12$ rm file3.txt

12$ vi file4.txt 

12$ ls -li file4.txt 

1053017 lrwxrwxrwx. 1 user1 user1 9 Dec 2 18:41 file4.txt -> file3.txt


---

