# 3.1
# LOCATION OF TRANSPORT-LAYER FUNCTIONALITY.


Where is transport-layer functionality primarily implemented?


- Transport layer functions are implemented primarily at the routers and switches in the network.


- ```Transport layer functions are implemented primarily at the hosts at the “edge” of the network.```


- Transport layer functions are implemented primarily at each end of a physical link connecting one host/router/switch to another one host/router/switch.

# TRANSPORT-LAYER FUNCTIONALITY.


True or False: The transport layer provides for host-to-host delivery service?


- ```True.```


- False


# TRANSPORT LAYER SERVICES USING TCP.


  Check all of the services below that are provided by the TCP protocol.


- ```A flow-control service that ensures that a sender will not send at such a high rate so as to overflow receiving host buffers.```


- ```Reliable data delivery.```


- ```In-order data delivery```


- ```A congestion control service to ensure that multiple senders do not overload network links.```


- ```A byte stream abstraction, that does not preserve boundaries between message data sent in different socket send calls at the sender.```


- A guarantee on the minimum amount of throughput that will be provided between sender and receiver.


- A guarantee on the maximum amount of time needed to deliver data from sender to receiver.


- A message abstraction, that preserves boundaries between message data sent in different socket send calls at the sender.

# TRANSPORT-LAYER SERVICES USING UDP.


  Check all of the services below that are provided by the UDP protocol.


- A guarantee on the maximum amount of time needed to deliver data from sender to receiver.


- Reliable data delivery.


- ```A message abstraction, that preserves boundaries between message data sent in different socket send calls at the sender.```


- A byte stream abstraction, that does not preserve boundaries between message data sent in different socket send calls at the sender.


- A guarantee on the minimum amount of throughput that will be provided between sender and receiver.


- A flow-control service that ensures that a sender will not send at such a high rate so as to overflow receiving host buffers.


- A congestion control service to ensure that multiple senders do not overload network links.


- In-order data delivery


# NETWORK-LAYER FUNCTIONALITY.


The transport layer sits on top of the network layer, and provides its services using the services provided to it by the network layer.  Thus it’s important that we know what is meant by the network layer’s “best effort” delivery service.  True or False:

The network layer’s best-effort delivery service means that IP makes its “best effort” to deliver segments between communicating hosts, but it makes no guarantees. In particular, it does not guarantee segment delivery, it does not guarantee orderly delivery of segments, and it does not guarantee the integrity of the data in the segments.



- ```Correct!  The network layer’s best effort service doesn’t really provide much service at all, does it?```


- Nope. The network layer’s best effort service doesn’t really provide much service at all, does it?

# 3.2
# TRANSPORT-LAYER DEMULTIPLEXING.


What is meant by transport-layer demultiplexing?


- Receiving a transport-layer segment from the network layer, extracting the payload, determining the destination IP address for the data, and then passing the segment and the IP address back down to the network layer.


- Taking data from one socket (one of possibly many sockets), encapsulating a data chuck with header information – thereby creating a transport layer segment – and eventually passing this segment to the network layer.


- ```Receiving a transport-layer segment from the network layer, extracting the payload (data) and delivering the data to the correct socket.```


- Taking data from multiple sockets, all associated with the same destination IP address, adding destination port numbers to each piece of data, and then concatenating these to form a transport-layer segment, and eventually passing this segment to the network layer.

#TRANSPORT-LAYER MULTIPLEXING.


What is meant by transport-layer multiplexing?


- Receiving a transport-layer segment from the network layer, extracting the payload (data) and delivering the data to the correct socket.


- Taking data from multiple sockets, all associated with the same destination IP address, adding destination port numbers to each piece of data, and then concatenating these to form a transport-layer segment, and eventually passing this segment to the network layer.


- ```Taking data from one socket (one of possibly many sockets), encapsulating a data chuck with header information – thereby creating a transport layer segment – and eventually passing this segment to the network layer.```


 -Receiving a transport-layer segment from the network layer, extracting the payload, determining the destination IP address for the data, and then passing the segment and the IP address back down to the network layer.

 # MULTIPLEXING/DEMULTIPLEXING: UDP PORT NUMBERS.


True or False:  When multiple UDP clients send UDP segments to the same destination port number at a receiving host, those segments (from different senders) will always be directed to the same socket at the receiving host.


- False


- ```True```


# MULTIPLEXING/DEMULTIPLEXING: TCP PORT NUMBERS.


True or False:  When multiple TCP clients send TCP segments to the same destination port number at a receiving host, those segments (from different senders) will always be directed to the same socket at the receiving host.


- True


- ```False```

# MULTIPLEXING UDP WITH IDENTICAL PORT NUMBERS.


True or False:  It is possible for two UDP segments  to be sent from the same socket with source port 5723 at a server to two different clients.


- False


- ```True```

# MULTIPLEXING TCP WITH IDENTICAL PORT NUMBERS.


True or False:  It is possible for two TCP segments with source port 80 to be sent by the sending host to different clients.


- False


- ```True```

# 3.3
# DOES UDP PRESERVE APPLICATION-LAYER MESSAGE BOUNDARIES?


True or False:  On the sending side, the UDP sender will take each application-layer chunk of data written into a UDP socket and send it in a distinct UDP datagram. And then on the receiving side, UDP will deliver a segment’s payload into the appropriate socket, preserving the application-defined message boundary.


- False


- ```True```

# UDP header fields. Which of the fields below are in a UDP segment header? [Hint: note the use of the word "header" in this question statement.]


- Source IP address


- ```Internet checksum```


- Data (payload)


- ```Destination port number```


- ```Length (of UDP header plus payload)```


- Upper layer protocol


- ```Source port number```


- Sequence number


# UDP SEGMENT LENGTH FIELD.


Why is the UDP header length field needed?


- Because this field is needed in TCP as well.


- To make the header and even number of bytes


- ```Because the payload section can be of variable length, and this lets UDP know where the segment ends.```


- (a) and (b) above

# INTERNET CHECKSUM AND UDP.


Over what set of bytes is the checksum field in the UDP header computed over?


- The entire UDP segment, except the checksum field itself.


- ```The entire UDP segment, except the checksum field itself, and the IP sender and receive address fields```


- Just the UDP header but not the payload.


# COMPUTING THE INTERNET CHECKSUM (1).


Compute the Internet checksum value for these two 16-bit words: 11110101 11010011 and 10110011 01000100
[Note: you can find more problems like this one here.]

    Just add them up and flip

- 01101110 11010101  


- 01011110 11000101  


- 01010110 11101000


- ```01010110 11100111```


# COMPUTING THE INTERNET CHECKSUM (2).


Compute the Internet checksum value for these two 16-bit words: 01000001 11000100 and 00100000 00101011
[Note: you can find more problems like this one here.]



- 01101110 11010101  


- ```10011110 00010000```


- 10011110 00001111 


- 10011110 00010001

# UDP CHECKSUM: HOW GOOD IS IT?


True or False:  When computing the Internet checksum for two numbers, a single flipped bit (i.e., in just one of the two numbers) will always result in a changed checksum.


- False


- ```True```

# UDP CHECKSUM: HOW GOOD IS IT?


True or False: When computing the Internet checksum for two numbers, a single flipped bit in each of the two numbers will always result in a changed checksum.


- True


- ```False```

# IP ADDRESSES AND PORT NUMBERS IN A UDP SEGMENT SENT IN REPLY. 


Suppose a UDP segment (A in the figure below) arrives at a host with an IP address of 128.119.40.186. The source port in the UDP segment is 4829 and the destination port is 3546. The IP address of the sending host is 60.54.75.24.
![](./chapter3photo/3.3.9.jpg)


Now consider the UDP datagram (and the IP datagram that will encapsulate it) sent in reply by the application on host 128.119.40.186  to the original sender host, labeled B in the figure above.  Complete the sentences below ...

What are the source and destination port numbers and IP addresses? (Enter the integer port number or the 4-part dotted decimal IP address, included the period)

The source port number of the UDP segment (B) sent in reply is: 

The source IP address of the IP datagram containing the UDP segment (B) sent in reply is: 

The destination port number of the UDP segment (B) sent in reply  is:

The destination IP address of the IP datagram containing the UDP segment (B) sent in reply is: 

[Note: you can find more problems like this one here.]


- The source port number of the UDP segment (B) sent in reply is: 

- The source IP address of the IP datagram containing the UDP segment (B) sent in reply is: 

- The destination port number of the UDP segment (B) sent in reply  is:

- The destination IP address of the IP datagram containing the UDP segment (B) sent in reply is: 
