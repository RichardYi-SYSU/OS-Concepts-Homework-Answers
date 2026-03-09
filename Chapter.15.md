# Problem 1
## Step-1

**Hardware Support**

A hardware support is one that places a guarantee regarding the buffer overflow attack that it doesn’t take place and prevents the code execution that is located within the segment of stack of the address space of the process.

Next recall the attack of the buffer-overflow which is performed by the overflow of the buffer that is present on the frame of the stack, next it jumps on to the another frame of the stack where the malicious executable code is present and returns the address of the function thus result in the buffer overflow. Thus, by code execution prevention from the stacks segment this problem could be eliminated.

Most of the approaches use various methodologies of programming that are built typically around the use of validation of bounds that guard it against the overflow of buffer. The condition of buffer overflows doesn’t occur in the languages like the java where each of the array access is confidential and guaranteed with the software check bounds. 

Thus, these types of approaches don’t require the support of hardware but results in the costs runtime.


---

# Problem 2
## Step-1

Password is one of the secure means to provide security to the unauthorized access of the highly confidential and secure documents. Thus its security is a high mean to its author but sometimes this security measure could become known to some unauthorized user in various ways but such type accessing can be detected by authentication tools and etc.

## Step-2

**Alternative way to detect the unauthorized users:**

The best method to detect the user who is logged on to the system is record of time and date when such an event has occurred.

When a user logs into the system, it record some events like log-in time, date etc. Then the computer gives the last login details including the date and time to the authorized user. Therefore authorized user can detect some body logged into my system at this time.


---

# Problem 3
## Step-1

UNIX system use a well-known encryption algorithm, a cracker might keep a cache of passwords that have been cracked previously. Hence new version of UNIX store the encrypted password entries in this file read by super user, but other user cannot read this file. ‘Salt’ is included or recorded random number in the encryption algorithm. The salt is added to the password to ensure that if two plain text passwords are the same, they result in different cipher texts.


---

# Problem 4
## Step-1

**Password Protection**

To keep the passwords secure and protected from an unauthorized access just internally encrypt all the passwords so that the passwords can be accessed only in their encrypted and coded form.

Next only the authorized person or user that is who have knowledge and is a master of decrypting the password or an administrator must be allowed to access the passwords.


---

# Problem 5
## Step-1

By using watchdog, implementations can quickly detect transport and application layer failures and with watchdog messages they can enable failover from a peer that has failed. Watchdog is designed to detect failures of the immediate peer.

If any watchdog response is pending then failover is initiated to the connection. As failover mechanism initiates, all queued messages are sent using alternate connection, and therefore duplicate connection is needed.


---

# Problem 6
## Step-1

One method of improving system security is periodically to scan the system for security holes. A scan can check a variety of aspects of the system.

The COPS program itself could be modified by an intruder to disable some of its features or even to take advantage of its features to create new security flaws. Even if COPS is not cracked, it is possible for an intruder to gain a copy of COPS, study it, and locate security breaches which COPS does not detect. Then that intruder could prey on systems in which the management depends on COPS for security, when all COPS is providing is complacency. COPS could be stored on a read only media or file system to avoid its modification. It could only be provided to prevent it from falling into the wrong hands. Neither of these is a foolproof solution, however.


---

# Problem 7
## Step-1

A worm is a process that uses the spawn mechanism to ravage system performance. The worm spawns copies of itself, using up system resources and perhaps locking out all other processes. On computer network, worms are particularly potent, since they may reproduce themselves among systems and thus shutdown the entire network.

The worm was made up of two programs, a grappling look (also called as bootstrap or vector) program and main program.

A firewall is a computer or router that sits between the systems and internet. It limits network access between the two security domains and monitors and logs all connection. It can also limit connections based on source or destination address, source or destination part or direction of the connections. It filters the packets moving from one side to the other, assuring that only valid packets owned by authorized users are allowed to access the protect systems. Such firewalls usually make use of the system less convenient.


---

# Problem 8
## Step-1

The action has been characterized as both a harmless prank gorse awry and a serious criminal off course. Based on the complexity of starting the attack, it is unlikely that the worm’s release or the scope of its spread was unintentional. The warm program took elaborate steps to cover its tracks and to repel efforts to stop its spread. Yet the program contained no code aimed at damaging or destroying the systems on which it ram.


---

# Problem 9
## Step-1

* Password security (unauthorized data transfer prevention): human, operating system

* Security from virus or warms: human, OS

* Transaction security: physical, human, OS

* Backup media protected and guarded: physical, human

* Protection against accidental loss of data consistency, to protect against malicious access to the data 

* Method of preventing or detecting security incidents include 

intrusion detection systems auditing and logging of system events, monitoring of system software changes, and system – call monitoring.


---

# Problem 10
## Step-1

**Encryption**

The two main advantages of encrypting data that is stored in the computer system are that:

1\. First advantage is that it provides **confidentiality** that is only the authorized user is allowed to access the encrypted data that is only the user or the receiver of that data had access to decrypt it using the authorized decryption key.

2\. The second advantage is that it acts as the safeguard and provides **authenticity** by the various facilities of protection that is provided by the operating system.


---

# Problem 11
## Step-1

**Man-in-the-middle attacks:**

Any **protocol** that requires a sender and a receiver to agree on a session key before they start communicating are prone to the man-in-the-middle attacks.

• **For instance,** if the two communicating systems is communicating with a common session key.

• If the protocol messages for exchanging the session key are not protected by the appropriate authentication mechanism, then it is possible for an attacker to manufacture a session key and get access to the data being communicated between the two parties.

• And also it is possible by using the fake session keys with the client and server interaction.

• When the attacker receives the data from the client, it can decrypt the data, re-encrypts it with the original key from the server, and transmit the encrypted data to the server without alerting either the client or the server about the attacker’s presence.

## Step-2

**For example, the most known attacks is a Virus,**

Virus is a self-replicating and is designed to infect other programs. 

• A virus is a fragment of code embedded in a legitimate program.

• **Virus** is borne via email, with spam the most common vector. 

• They can also spread when users download viral program from the internet, file-sharing services or exchange infected disks.

## Step-3

**Methods to prevent the man-in-the-middle attacks:**

The methods to remove attacks are,

• Port Scanning

• Denial of service attacks

**For instance,**

• The person who wants to send out the public key, but attackers also sends the “bad” public key. 

• The person who wants to send the encrypted message knows no better and so uses the bad key to encrypt the message. 

• Thus, the attacker then happily decrypts it.

## Step-4

The problems can be solved by using **Digital Signature**.

**Digital Signature** is used to authenticate messages from the server.

• If the server could communicate the session key and its identity in a message that is guarded by a digital signature granted by a certifying authority.

• So, the attacker would not able to forge the session key.

**Therefore, the man-in-the-middle attacks could be avoided by using digital signatures.**


---

# Problem 12
## Step-1

**Encryption Schemes**

The comparison between the Symmetric and Asymmetric Encryption Schemes is given as:

**S.No.** |  **Symmetric Encryption** |  **Asymmetric Encryption**  
---|---|---  
1. |  In this encryption scheme only single and same key is used for both encryption and decryption purposes. |  In this encryption scheme different keys are used for both encryption and decryption.  
2. |  It includes commonly used encryption standard algorithm called as DES that is data-encryption standard and includes an advanced encryption standards (AES). |  It includes an asymmetric algorithm named as RSA or Rivest, Shamir, and Adleman algorithm.   
3. |  Symmetric encryption includes a 64-bit chunk that includes messages that are broken into 64 bits thus include block cipher. |  Asymmetric encryption algorithm includes two keys namely a public key and a private key for encryption and decryption.  
  
## Step-2

Asymmetric schemes of key cryptography are based basically on the foundation of mathematics that helps in providing the guarantee for the reverse engineering intractability of the encryption schemes. As these schemes is expensive as compared to the symmetric encryption scheme.

Thus, due to the vast superiority usage of Asymmetric schemes, this scheme is used for various other purposes of providing the security that is confidentiality, key distribution, and authentication, thus a distributed system will use asymmetric encryption scheme much more.


---

# Problem 13
## Step-1

Constraining the set of potential senders of a message is called authentication. If ![](https://media.cheggcdn.com/study/ab9/ab95030c-4507-451a-9055-c7b57206c690/300-15-13e-i1.png) produces a valid message, then we know that the creator of the message must hold![](https://media.cheggcdn.com/study/756/756b8b31-febb-4b9c-a7de-a0987612bf7d/300-15-13e-i2.png). But given is![](https://media.cheggcdn.com/study/f82/f82f34e2-fe89-41e1-9cf5-0003351b4051/300-15-13e-i3.png), this means that ![](https://media.cheggcdn.com/study/159/1590d4c3-b6e3-4ff6-b360-675bae8a19bb/300-15-13e-i4.png) is not held by the sender. Thus it does not provide authentication of the sender. This is used when both sender and receiver know each others keys.


---

# Problem 14
## Step-1

The use of asymmetric encryption begins with the publication of the public key of the destination. For bidirectional communication, the source also must publish its public key. The private key must be guarded, as anyone holding that key can decrypt any message created by matching public key. Asymmetric algorithms are used only for the purpose of small amounts of data but also for authentication, confidentially, and key distribution.

The critical property that an authentication algorithm must possess is as follows:

For a message _m,_ a computer can generate an authenticator _a_ _![](https://media.cheggcdn.com/study/e16/e16d22a3-ad12-477c-b64e-00baf3f48dd8/300-15-14e-i1.png)__A_ such that V(_k_)(_m_ ,_a_)=_true_ only if it possesses S(_k_) where K is a set of keys, M is a set of messages, A is a set of Authenticators. Thus a computer holding S(_k_) can generate authenticators on messages so that any other computer possessing V(_k_) can verify them. This states that the receiver knows that only the sender could have generated the message and only the receiver can decrypt the massage.

Thus both Authentication and Secrecy are obtained.


---

# Problem 15
## Step-1

Audit record per day = 10 million

Attacks / day = 10 reflected in no. of record = 20

True intrusion – detection alarm rate = 0.6

False alarm rate = 0.0005

Probability of occurrence of intrusive records 

P(I) =![](https://media.cheggcdn.com/study/cde/cdeb7226-0065-4c3c-9b0c-f25323ec54eb/300-15-15e-i1.png)

=0.0002

By

Baye’s Theorem

P(I/A) = ![](https://media.cheggcdn.com/study/bc3/bc3d4327-baf5-4776-b379-4fb7d26a95a2/300-15-15e-i2.png)

= ![](https://media.cheggcdn.com/study/7dd/7dddbb2f-e911-4e6f-a42b-e66516b2fc37/300-15-15e-i3.png)

= 0.19(approx.)


---

