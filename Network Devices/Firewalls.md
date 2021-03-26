# Firewalls

## What is A Firewalls?

Firewalls are special network devices that monitor and filter network traffic entering or exiting a network based on certain set rules. A firewall could be placed both behind a router or before routers. What is important is that it protects the end hosts inside the network from outside attackers. Firewalls will need to be configured with rules to determine which traffic could enter or exit the network. 

A properly configured firewall will keep a network safe as long as no attacks are made behind the firewall. 

A firewall is called a "Next-generation Firewalls" if they provide modern and advanced filtering capabilities. 

## Why do we need them in the first place?

Well, using a firewall has many advantages. Some of them are:
 - Preventing remote access by an unauthorized user.
 - Help to secure old devices.
 - Block a specific type of content.
 - Preventing the System from going down because of DoS/DDoS attacks.
 - Keeping some crucial private information safe online.

## Type of firewall

Firewall, like many other networking devices, also has several types. Some of them are:

 1. Packet-filtering Firewall
 2. Network Address Translation (NAT) Firewalls
 3. Proxy Firewalls
 4. Web Application Firewalls 
 5. NGFW Firewalls

### Packet-filtering Firewall

This type of firewall is a management program that would block traffic based on their protocols, IP address and port number. This type of firewall is also the most common firewall found in small networks system. They do not require an intensive amount of resources to operate and rarely affect the system performance. The only downside of a packet filtering firewall is that they only provide basic protection for the network and can be bypassed easily by attackers.

#### Type of Packet-filtering Firewall

Packet-filtering firewall is also divided into two different types of firewall; stateful and stateless. A stateless packet-filtering firewall will only examine one packet individually. While Stateful packet-filtering firewall would take account of the content from the previously examined packets into consideration when inspecting a newly received packet.

### Network Address Translation (NAT) Firewalls 

A NAT firewall enables the devices to communicate with devices outside of the network with one single public address. This keeps the devices hidden by providing them with private addresses. This also prevents outsiders from scanning for specific details on a device, which could expose the system to attacks.

### Proxy Firewalls

Filter network traffic at the application layer, which functions to filter incoming traffic between the network and the traffic source. Which somewhat similar to a gateway. Instead of directly letting the traffic connect, the proxy firewall would first connect to the traffic source to check if it is safe or not. If it is safe, the proxy firewall will then send the traffic to continue with its connection to its destination.

Unlike the stateful inspection provided in the stateful firewall, the proxy firewall can filter traffic at other OSI layers, which checks the packet's content to verify if it contains malware.

The most obvious disadvantage of this type of firewall is the slowdown that the firewall has created when checking the packets, as it needs to perform extra steps to check the packets at multiple layers.

### Web application firewalls

This type of firewall is used to secure websites or web applications. Web application firewalls or WAF can be used to prevent DoS attacks, Cross-site scripting, SQL injections and many more.

### NGFW Firewalls 

The New-Generation-Firewalls is the most modern and powerful firewall as of today. Not just these firewalls are built on top of traditional firewalls, and they also added other security feature like anti-malware and Intrusion prevention systems (IPSs) which can stop the attack from moving any further into the system. 