# Remote Code Execution (RCE) Exploits


## Table of Contents

## Introduction
RCE attacks explained
Remote code execution (RCE) is more of a category of attacks than a single defined attack. Remote code execution can have many faces, in that the term applies to many different kinds of attacks. However, on a basic level, all of the attacks that can be subsumed under the RCE umbrella share a commonality: RCE attacks are all achieved by exploiting vulnerabilities in the configuration of remote computers/servers in order to run arbitrary code on the target system.

If an attacker can pull that off, the consequences can be more than significant. Having the server execute arbitrary code (i.e., code supplied by the attacker) could enable the attacker to steal confidential information, modify or destroy files, perform a distributed denial of service (DDoS) attack, or worse yet, actually take over the entire system.

So the issue clearly merits some attention.

## Vulnerabilities required for Remote Code Execution
For an attacker to pull off a remote code execution attack, the target system must have a pre-existing vulnerability for the attacker to exploit. Various vulnerabilities could open the door to a RCE attack – too many to name. However, the following types of vulnerabilities are the most commonly used to perpetrate RCE attacks.

### Unsanitized user input
> If your web site/application allows for user input without having proper sanitizing measures in place, you’re opening the door to all sorts of unintended behavior on behalf of your server, such as arbitrary code execution. Don’t trust user input – ever. This point also ties in to type confusion, explained below.
