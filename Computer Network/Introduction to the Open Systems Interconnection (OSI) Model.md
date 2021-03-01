# Introduction to the Open Systems Interconnection (OSI) Model

The Open System Interconnection model or OSI model is a conceptual model that describes how telecommunication between computers and how they communicate over a network to other devices on the network.

There is a total of 7 layers in the OSI model:

1.  Physical layer
2.  Data link layer
3.  Network layer
4.  Transport layer
5.  Session layer
6.  Presentation layer
7.  Application layer

The order shown here is the representation of when a computer receives a message that needs to be transmitted to an application in the application layer.

When sending a message/data to another computer, the order of the layers will be inverted.

---

## Sending message from an application to another computer's application.


Let's say an application that's running on computer_1's would like to communicate with another application on computer_2. The initial flow of the message initiated by computer_1 are as follows:

```
    A[Application] --> B[Application layer]
    B --> C[Presentation layer]
    C --> D[Session layer]
    D --> E[Transport layer]
    E --> F[Network layer]
    F --> G[Data Link layer]
    G --> H[Physical layer]
    H --> I[physical medium]
```

After the message has gone through many works to be processed and changed the format to comply with the lower layer in the model, the message will then be sent to computer_2 through a physical transmission medium.

Once computer_2 receives the message, the message/data will then be transferred to the intended application. The flow is just as when computer_1 sends the message to computer_2, just that the flow order is inverted now.

```mermaid
    A[physical medium] --> B[Physical layer]
    B --> C[Data Link layer]
    C --> D[Network layer]
    D --> E[Transport layer]
    E --> F[Session layer]
    F --> G[Presentation layer]
    G --> H[Application layer]
    H --> I[Application]
```

---
## Describing the seven layers of the OSI model

### 1. Physical layer

The physical layer is the lowest in the OSI model, and its role is to transmit and receives unformatted/unstructured raw data to and from a transmission medium. 

Since our computer's components communicate using bits and bytes, the communication that needs to be transmitted to the computer's external needs a transmission medium that can converts the bits and bytes into transferable signals like electrical, radio or optical signals. The mode of transmission (simplex, half and full-duplex) will also be determined by this layer.

This layer is also in charge of the characteristic of the transmission. For example, voltage level, data rates, modulation scheme, channel access, and etc.

More info on transmission medium at the section below.

---

### 2. Data Link Layer 

This layer will be in charge of establishing and terminating the connection between two physically connected nodes on a network. We can imagine it as there will be a link between this two computer.

This layer could detect and, when possible, fix the errors that occurred in the physical layer. Besides correcting errors, this layer could also define a protocol for the transmission flow later.

This layer is divided into two sublayers:
- MAC or Medium access control (MAC) layer
- Logical link control (LLC) layer

#### MAC layer

This layer will controls how devices in a network could gain permission to access a transmission medium to transmit data.


#### LLC layer

This layer will be responsible for transferring the packets retrieved from the Network layer above it. This is also the layer that provides the error checking as well as frame synchronization.

#### Functions of Data-link layer (more in depth)

- Framing 
> This layer will add a header to the end of the frames (packets that have been broken down into frames received from the Network layer). After adding the header, the frame will then be transmitted to the address's destination.

- Flow control
> Main function of this layer is to control the flow of data transmission. It is so that the data rate in the transmission will be constant and preventing the data from being corrupted. It is also to prevent the transmitting computer (like a server) does not transmit the data exceeding the data rate of the receiving station (like a client)

- Error Control
>Achieved by adding a calculated value CRC (Cyclic Redundancy Check), which is added to the frame of the message before sending it to the physical layer. If any error seems to occur when transmitting the data, the receiver can then send an acknowledgement for the frames retransmission.

- Access control
>To make sure that only one device can have control over the link in a single communication at a time.

- Physical Addressing

> Data Link layer would add a header to the frame containing a destination address, which the frame will be transported to the destination with the header's help.

---
### 3. Network Layer

Network Layer in charge of locating the device's location in a network. It will also determine the best route to move data from the source to the destination based on the network condition. After finding the best route, the data will then be routed by the Data Link layer. 

This layer is also used to provide routing services within an internetwork. Protocols such as IPv4 and IPv are two well-known network-layer protocols.

In this layer, the data to be transmitted is called a packet (without the header included in the Data-link layer). Protocols used to route the network traffic are IPv4 and IPv6.


#### Functions of this layer

- Internetworking
> Provides logical connections between devices

- Addressing
> Adding source and the destination address to the segments (segments are what we call the data to be transmitted in the next layer, transport layer)

- Routing
> Determining the best optimum path for routing the packet to the destination

- Packetizing
> This layer would receive the segments from the transport layer and converts them/break them down into packets. The packets are reassembled on the receiving devices.


---
### 4. Transport Layer

This layer would take the data from the session layer and breaks them into "segments". While on the receiving devices, they're required to reassemble the segments once they received the segments. The primary function of this layer is to transfer the data completely. This layer would provide an end-to-end layer as it will provide p2p connections between source and destination.

Two protocols are used in this layer:

- Transmission Control Protocol
	- allow systems to communicate over the internet.
	- establish and maintains connections between hosts
	- break data into segments; each segment will only be transmitted on the same single path to the destination in a different order.
	- The TCP at the receiving side will then reorders these packets to the corrects order.

- User Datagram protocol
	- Unreliable transport protocol
	- receiver will not send an acknowledgement when the packet is received at the receiving end
	- sender will also not waiting for the acknowledgement. It will just keep on sending the segments
	- The packets in this protocol can be the route through a different path, unlike TCP.

#### Function of transport layer

- Service-point addressing
> Add headers that contain the address known as service-point address or port address.
> Network layer would transmit the data from one device to another, while the transport layer would transmit it to the correct process.

- Segmentation and reassembly
> break down the message received by the higher level into multiple segments. Each of them will have its sequence number, which is used to reassemble them on the receiving side according to their sequence number.

- Flow control
> Provide end-to-end flow controls

- Error control
> Provide end-to-end error control

---
### 5. Session Layer

This layer would establish, maintain and synchronizes the interaction between communicating devices. A session is started and ended using TCP. 

Both TCP and UDP will need this feature. Although UDP is connectionless, we need some way to maintain the connection between the devices, establishing and terminating those connections.

#### Function of Session layer

- Dialog Control
> Create a dialogue between two processes, allowing communications between two processes that are either simplex, half-duplex, or full-duplex.

- Synchronization
> This layer would also add checkpoints when transmitting the data in a sequence.
> Error occurred will quickly trigger this layer on the transmitting side, and then the transmitting device will transmit the data identified from the checkpoint again.

---
### 6. Presentation Layer

This layer prepares the data for the application layer. It defines how should the two devices encode, encrypt, compress the data received. It is something like a data translator for a network. This layer could also convert the data from one format to another.

#### Function of presentation layer.

- Translation
> Converting data from sender data format into a common format which can then be converted into a format that the receiver can accept.

- Encryption
> To maintain privacy, encryption is used to converts the sender's information into another form and sending that resulting message over the network to its destination.

- Compression
> Compressing the data can reduce the number of bits that needs to be transmitted. (important in multimedia)

---
### 7. Application Layer

This layer is the nearest layer to the end-user. User will use the application to communicate with the network services. This layer provides a protocol that allows the software to send and receive information and displaying them in a meaningful way to the users. 

This layer would also in charge of resource allocation, network transparency and many more. This layer is not an application but an interface for software to use the functions to perform communications using the network services.


#### Function of application layer.

- File Transfer, access and management(FTAM)
> Allow user to access, retrieve and manage files in a remote computer

- Mail services
> Facilities for email forwarding and storage.

- Directory services
> Provided distributed database to provide information about various objects

- Network Virtual terminal
> Software version of a physical terminal
> allow the user to log onto a remote host
