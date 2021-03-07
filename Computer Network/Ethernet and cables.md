Ethernet and cables 

# Cabling Types

## Ethernet Standards

Ethernet is a collection of network protocols/standards. They are defined in the IEEE 802.3 standards in 1983.
 IEEE means the Institute of Electrical and Electronics Engineers

 Speed | Common Nsme | IEEE Standards | Informal name | Max Length
 ---- | ---- | ---- | ---- | ----
10 Mbps | Ethernet | 802.3i | 10BASE-T | 100m
100 Mbps | Fast Ethernet | 802.3u | 100BASE-T | 100m
1 Gbps | Gigabit Ethernet | 802.3ab | 1000BASE-T | 100m
10 Gbps | 10 Gig Ethernet | 802.3an | 10GBASE-T | 100m


## Unshielded Twisted Pair (UTP) cables

The circuits in the cable is twisted to reduce the electromagnetic interference (EMI). The structure of an UTP cable is as follows:

``` symbol
-----|	    Outer Conductor   Dielecric core
     |-----|  |               |          
     |     |----_____  _____ 
     |     |   |_____\//____----
     |     |   |_____//\____
     |     |   |_____/\_____----
	 |     |----              |
	 |-----|		Inner Conductor
-----|	  \
Cable     Barrier Tape
Jacket	

```



unshielded Twisted Pair cables have eight pins

>10BASE-T & 100BASE-T used 2 pairs(4 wires)
>
>1000BASE-T & 10G BASE-T used four pairs (8 wires)

### 10BASE-T & 100BASE-T UTP cables

10 & 100BASE-T UTP cable send/transmit data through pin 1 and 2 and receive data at pin 3 and 6. If the device transmitting is either a router or PC and the receiving side is a switch, a straight-through cable can work. This is because the switch has a different function in its ethernet pin as data is received at pin 1 & 2 instead of 3 and 6. While 3 and 6 will be transmitting data to another device instead of receiving.

Straight-through cables are cables with wires that connects two devices from one pin to another pin of the same position at the other end.


#### switch

- receive data at pin 1 & 2
- transmit data at pin 3 & 6


#### Routers, Firewalls, and PC 

- receive data at pin 3 & 6
- transmit data at pin 1 & 2


If two same device needs to be connected through ethernet cable (router with another router, or a switch with another switch), another cable is needed to connect them both. It is called cross-[over cables. 

This type of cable is different from straight-through cable where the wire that connects from 1 & 2 are crossed and connects to the 3 and 6 pin at the other end of the cable. While pin 3 & 6 will be crossed and connected to the 1 & 2 pins at the other end.

### Auto MDI-X

In the newer version of network devices, thy normally would have an auto MDI-X feature. This would automatically adjust which pins will be used to transmit data and receive data.


### 1000BASE-T & 10GBASE-T UTP cables

1000BASE-T & 10GBASE-T UTP cables used all pairs of wires in data transmission and receiving. The pairs will now be:

1-2, 3-6, 4-5, 7-8

The biggest difference between these cables with the 10BASE-T and 100BASE-T cable is that each pair of wire is bidirectional. This means that each pair of wire can receive and transmit data at the same time. This is why they are faster than the previous two cables.


## Fiber-Optic Connections

Instead of sending data using electricity to transmit data, fibre optic cables uses light to transmit data over glass fibre. Fibre optic used two cables used for transmitting to, and the other is for receiving data from another device.

The structure of an fiber-optic cable is as below:


``` 
-----|       Cladding
     |-----|  |
     |     |----______
	 |     |   |______
	 |     |----   |
	 |-----|     Fiberglass core
-----|	  \
Outer     Protective Buffer
Jacket	

```

There are two types of fibre-optic mode:

1. Single-mode
2. multimode


### Multimode Fiber
- Wider core than single-mode
- allowing multiple angles (modes) of light waves entering the fibreglass
- Longer cables than UTP but shorter than single-mode fibre
- Cheaper than single-mode fibre (Cheaper LED-based SFP transmitter)

### Single-mode fiber 
- More narrow core than multimode fibre cables
- light enters at a single angle using a laser-based transmitter
- longer cablese than UTP and multimode


 Speed | Cable Type | IEEE Standards | Informal name | Max Length
 ---- | ---- | ---- | ---- | ----
1 Gbps | Multimode / Single-Mode | 802.3z | 1000BASE-LX | 550M (MM), 5km (SM)
10 Gbps | Multimode | Fast Ethernet | 802.3ae | 10GBASE-SR | 400m
10 Gbps | Single-Mode | 802.3ae | 10GBASE-LR | 10km
10 Gbps | Single-Mode| 802.3ae | 10GBASE-ER | 30km

## UTP vs Fiber-optic

### UTP

- Lower cost
- Shorter Max length
- vulnerable to EMI (Electromagnetic Interference).
- RJ45 ports cheaper than SFP ports
- leak faint signal outside of the cable, making it vulnerable to a security risk by copying the signals

### Fiber Optic

- Higher cost
- Longer max length
- not vulnerable to EMI
- SFP ports are more expensive than RJ45 ports (single mode will be more expensive than multimode)
- Does not leak signals