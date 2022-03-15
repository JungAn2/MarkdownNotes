# 2.1
# THE CLIENT-SERVER PARADIGM.


Which of the characteristics below are associated with a client-server approach to structuring network applications (as opposed to a P2P approach)?


- A process requests service from those it contacts and will provide service to processes that contact it.


- There is not a server that is always on.


- > ```There is a server that is always on.```


- > ```HTTP uses this application structure.```


- > ```There is a server with a well known server IP address.```

# THE PEER-TO-PEER (P2P) PARADIGM.


Which of the characteristics below are associated with a P2P approach to structuring network applications (as opposed to a client-server approach)?


- > ```There is not a server that is always on.```


- > ```A process requests service from those it contacts and will provide service to processes that contact it.```


- HTTP uses this application structure.


- There is a server that is always on.


- There is a server with a well known server IP address.

# UDP SERVICE.


When an application uses a UDP socket, what transport services are provided to the application by UDP? Check all that apply.


- Real-time delivery. The service will guarantee that data will be delivered to the receiver within a specified time bound.


- Congestion control.  The service will control senders so that the senders do not collectively send more data than links in the network can handle.


- Throughput guarantee. The socket can be configured to provide a minimum throughput guarantee between sender and receiver.


- Loss-free data transfer. The service will reliably transfer all data to the receiver, recovering from packets dropped in the network due to router buffer overflow.


- Flow Control. The provided service will ensure that the sender does not send so fast as to overflow receiver buffers.


- > ```Best effort service.  The service will make a best effort to deliver data to the destination but makes no guarantees that any particular segment of data will actually get there.```

# TCP SERVICE.


When an application uses a TCP socket, what transport services are provided to the application by TCP?  Check all that apply.


- Throughput guarantee. The socket can be configured to provide a minimum throughput guarantee between sender and receiver.


- > ```Flow Control. The provided service will ensure that the sender does not send so fast as to overflow receiver buffers.```


- Best effort service.  The service will make a best effort to deliver data to the destination but makes no guarantees that any particular segment of data will actually get there.


- > ```Congestion control.  The service will control senders so that the senders do not collectively send more data than links in the network can handle.```


- Real-time delivery. The service will guarantee that data will be delivered to the receiver within a specified time bound.


- > ```Loss-free data transfer. The service will reliably transfer all data to the receiver, recovering from packets dropped in the network due to router buffer overflow.```

# 2.2
# “HTTP IS STATELESS.” 


What do we mean when we say “HTTP is stateless”? In answering this question, assume that cookies are not used.  Check all answers that apply.


- We say this when an HTTP server is not operational.


- An HTTP client does not remember the identities of the servers with which  it has interacted.


- > ```An HTTP server does not remember anything about what happened during earlier steps in interacting with this HTTP client.```


- An HTTP client does not remember anything about what happened during earlier steps in interacting with any HTTP server.


- The HTTP protocol is not licensed in any country.

# HTTP COOKIES. 


What is an HTTP cookie used for?


- A cookie is used to spoof client identity to an HTTP server.


- Like dessert, cookies are used at the end of a transaction, to indicate the end of the transaction.


- > ```A cookie is a code used by a server, carried on a client’s HTTP request, to access information the server had earlier stored about an earlier interaction with this Web browser. [Think about the distinction between a browser and a person.]```


- A cookie is a code used by a client to authenticate a person’s identity to an HTTP server.


- A cookies is a code used by a server, carried on a client’s HTTP request, to access information the server had earlier stored about an earlier interaction with this person. [Think about the distinction between a browser and a person.]

# THE HTTP GET.


  What is the purpose of the HTTP GET message?


- The HTTP GET request message is sent by a web server to a web client to get the identity of the web client.


- The HTTP GET request message is sent by a web server to a web client to get the next request from the web client.


- The HTTP GET request message is used by a web client to post an object on a web server.


- > ```The HTTP GET request message is used by a web client to request a web server to send the requested object from the server to the client.```

# CONDITIONAL HTTP GET. 


What is the purpose of the conditional HTTP GET request message?


- To allow a server to only send the requested object to the client if the client is authorized to received that object.


- To allow a server to only send the requested object to the client if the server is not overloaded.


- > ```To allow a server to only send the requested object to the client if this object has changed since the server last sent this object to the client.```


- To allow a server to only send the requested object to the client if the client has never requested that object before.

# A DETAILED LOOK AT AN HTTP GET (1).


Suppose a client is sending an HTTP GET request message to a web server, gaia.cs.umass.edu. Suppose the client-to-server HTTP GET message is the following:

GET /kurose_ross_sandbox/interactive/quotation2.htm ```HTTP/1.1```<br>
Host: gaia.cs.umass.edu<br>
Accept: text/plain, text/html, text/xml, image/jpeg, image/gif, audio/mpeg, audio/mp4, video/wmv, video/mp4,<br>
Accept-Language: en-us, en-gb;q=0.1, en;q=0.7, fr, fr-ch, da, de, fi<br>
If-Modified-Since: Wed, 09 Sep 2020 16:06:01 -0700<br>
User Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/535.11 (KHTML, like Gecko) Chrome/17.0.963.56 Safari/535.11<br>

What version of HTTP is the client using?
[Note: you can find additional questions similar to this here.]



- 2


- 2.1


- > ```1.1```


- 1

