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


- Receiving a transport-layer segment from the network layer, extracting the payload (data) and delivering the data to the correct socket.


- Taking data from multiple sockets, all associated with the same destination IP address, adding destination port numbers to each piece of data, and then concatenating these to form a transport-layer segment, and eventually passing this segment to the network layer.