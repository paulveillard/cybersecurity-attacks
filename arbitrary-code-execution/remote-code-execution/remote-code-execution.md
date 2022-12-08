# Remote Code Execution (RCE) Exploits


## Table of Contents
- [Introduction](#introduction)
- [Vulnerabilities required for Remote Code Execution](#)
- [How do remote code execution attacks work?](#)
- [Remote code execution attack examples](#)
- [How to protect against RCE attacks](#)
- [Conclusion](#)

## Introduction
RCE attacks explained
Remote code execution (RCE) is more of a category of attacks than a single defined attack. Remote code execution can have many faces, in that the term applies to many different kinds of attacks. However, on a basic level, all of the attacks that can be subsumed under the RCE umbrella share a commonality: RCE attacks are all achieved by exploiting vulnerabilities in the configuration of remote computers/servers in order to run arbitrary code on the target system.

If an attacker can pull that off, the consequences can be more than significant. Having the server execute arbitrary code (i.e., code supplied by the attacker) could enable the attacker to steal confidential information, modify or destroy files, perform a distributed denial of service (DDoS) attack, or worse yet, actually take over the entire system.

So the issue clearly merits some attention.

## Vulnerabilities required for Remote Code Execution
For an attacker to pull off a remote code execution attack, the target system must have a pre-existing vulnerability for the attacker to exploit. Various vulnerabilities could open the door to a RCE attack – too many to name. However, the following types of vulnerabilities are the most commonly used to perpetrate RCE attacks.

### Unsanitized user input
> If your web site/application allows for user input without having proper sanitizing measures in place, you’re opening the door to all sorts of unintended behavior on behalf of your server, such as arbitrary code execution. Don’t trust user input – ever. This point also ties in to type confusion, explained below.

### Broken authentication
> This first vulnerability is a bit obvious, but if care isn’t taken to configure authentication mechanisms correctly, the consequences could be disastrous. In fact, this vulnerability ranks second in OWASP’s vulnerability top ten list – it’s a doozy.

If your web site/application’s authentication and session management functions are incorrectly implemented, attackers could compromise passwords, keys, or session tokens. They could also attempt to exploit other vulnerabilities in the application in order to assume other users’ identities with potentially sensitive permissions. Once the attacker is in, they could execute arbitrary code and possibly take over your server with the proper permissions.

### Poor access control
> Access control lists (ACL) limit the permissions of your users to only those that are necessary for them to complete their work. Without properly segmented permissions, if an attacker hijacks a user account that has root privileges because of poorly implemented access control, the damage the attacker could do is considerable. Conversely, if an attacker compromises a user account with limited permissions, the damage the attacker can do is limited to the permissions they have. They may still be able to cause you trouble, but much less than is they had escalated or root privileges.

### Buffer overflows
> Software is typically programmed to use buffers. In the world of programming, a buffer is a fixed amount of physical memory (RAM) that’s used to store temporary information until it’s needed or moved to another location. Because the buffer constitutes a fixed amount of RAM, bounds-checking measures need to be written into the code to ensure that the buffer’s capacity is not exceeded. If no bounds-checking measures are present (that’s the vulnerability), the amount of data written to the buffer can exceed its capacity. When that happens, the overflowing data will overwrite the legitimate data of neighboring buffers. Buffer overflows can destroy essential data, crash the system, and overwrite memory locations with arbitrary code (malware) that the system later executes.

### Type confusion
> Another commonly exploited vulnerability is type confusion. In software, whenever part of the program passes an object (a file, a string, a link, etc.) over to another part of the program, the object type needs to be checked, so the program knows what to do with it and how. However, if this check is not written into the code, it becomes possible to leverage this oversight to exploit the system. By writing an object to memory as one ‘type pointer’ (let’s say A) and then reading it as another ‘type pointer’ (let’s say B), an attacker could trick the system into executing arbitrary code. If proper checks were in place, pointer type A could not be read as pointer type B, and the malicious code would not run.

### Deserialization manipulation
> Whenever an object is passed from one part of the program to another, that object must first be serialized (i.e., converted into binary). Once the serialized object arrives at its destination, it needs to be deserialized (converted back into the original object). Attackers can exploit the deserialization process to produce anomalous objects that can manipulate the system to execute unintended commands.
