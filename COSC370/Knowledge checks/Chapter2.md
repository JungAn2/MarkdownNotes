# 2.1
# THE CLIENT-SERVER PARADIGM.


Which of the characteristics below are associated with a client-server approach to structuring network applications (as opposed to a P2P approach)?


- A process requests service from those it contacts and will provide service to processes that contact it.


- There is not a server that is always on.


- ```There is a server that is always on.```


-  ```HTTP uses this application structure.```


-  ```There is a server with a well known server IP address.```

# THE PEER-TO-PEER (P2P) PARADIGM.


Which of the characteristics below are associated with a P2P approach to structuring network applications (as opposed to a client-server approach)?


-  ```There is not a server that is always on.```


-  ```A process requests service from those it contacts and will provide service to processes that contact it.```


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


-  ```Best effort service.  The service will make a best effort to deliver data to the destination but makes no guarantees that any particular segment of data will actually get there.```

# TCP SERVICE.


When an application uses a TCP socket, what transport services are provided to the application by TCP?  Check all that apply.


- Throughput guarantee. The socket can be configured to provide a minimum throughput guarantee between sender and receiver.


-  ```Flow Control. The provided service will ensure that the sender does not send so fast as to overflow receiver buffers.```


- Best effort service.  The service will make a best effort to deliver data to the destination but makes no guarantees that any particular segment of data will actually get there.


-  ```Congestion control.  The service will control senders so that the senders do not collectively send more data than links in the network can handle.```


- Real-time delivery. The service will guarantee that data will be delivered to the receiver within a specified time bound.


-  ```Loss-free data transfer. The service will reliably transfer all data to the receiver, recovering from packets dropped in the network due to router buffer overflow.```

# 2.2
# “HTTP IS STATELESS.” 


What do we mean when we say “HTTP is stateless”? In answering this question, assume that cookies are not used.  Check all answers that apply.


- We say this when an HTTP server is not operational.


- An HTTP client does not remember the identities of the servers with which  it has interacted.


-  ```An HTTP server does not remember anything about what happened during earlier steps in interacting with this HTTP client.```


- An HTTP client does not remember anything about what happened during earlier steps in interacting with any HTTP server.


- The HTTP protocol is not licensed in any country.

# HTTP COOKIES. 


What is an HTTP cookie used for?


- A cookie is used to spoof client identity to an HTTP server.


- Like dessert, cookies are used at the end of a transaction, to indicate the end of the transaction.


-  ```A cookie is a code used by a server, carried on a client’s HTTP request, to access information the server had earlier stored about an earlier interaction with this Web browser. [Think about the distinction between a browser and a person.]```


- A cookie is a code used by a client to authenticate a person’s identity to an HTTP server.


- A cookies is a code used by a server, carried on a client’s HTTP request, to access information the server had earlier stored about an earlier interaction with this person. [Think about the distinction between a browser and a person.]

# THE HTTP GET.


  What is the purpose of the HTTP GET message?


- The HTTP GET request message is sent by a web server to a web client to get the identity of the web client.


- The HTTP GET request message is sent by a web server to a web client to get the next request from the web client.


- The HTTP GET request message is used by a web client to post an object on a web server.


-  ```The HTTP GET request message is used by a web client to request a web server to send the requested object from the server to the client.```

# CONDITIONAL HTTP GET. 


What is the purpose of the conditional HTTP GET request message?


- To allow a server to only send the requested object to the client if the client is authorized to received that object.


- To allow a server to only send the requested object to the client if the server is not overloaded.


-  ```To allow a server to only send the requested object to the client if this object has changed since the server last sent this object to the client.```


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


- ```1.1```


- 1

# A DETAILED LOOK AT AN HTTP GET (2).


Again, suppose a client is sending an HTTP GET request message to a web server, gaia.cs.umass.edu.  The client-to-server HTTP GET message is the following (same as in previous problem):

GET /kurose_ross_sandbox/interactive/quotation2.htm HTTP/1.1<br>
Host: gaia.cs.umass.edu<br>
Accept: text/plain, text/html, text/xml, image/jpeg, image/gif, audio/mpeg, audio/mp4, video/wmv, video/mp4,<br>
Accept-Language: ```en-us, en-gb```;q=0.1, en;q=0.7, fr, fr-ch, da, de, fi<br>
If-Modified-Since: Wed, 09 Sep 2020 16:06:01 -0700<br>
User Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/535.11 (KHTML, like Gecko) Chrome/17.0.963.56 Safari/535.11<br>

What is the language in which the client would least prefer to get a response?  [You may have to search around the Web a bit to answer this.]

[Note: you can find additional questions similar to this here.]

    Aprrently en-US does not equal US English

- ```United Kingdom English```


- Farsi


- US English


- Mandarin


- French


- Hindi


- Finnish


- Spanish

#A DETAILED LOOK AT AN HTTP GET (3).


Again, suppose a client is sending an HTTP GET request message to a web server, gaia.cs.umass.edu. Suppose the client-to-server HTTP GET message is the following (same as in previous problem):

GET /kurose_ross_sandbox/interactive/quotation2.htm HTTP/1.1<br>
Host: gaia.cs.umass.edu<br>
Accept: text/plain, text/html, text/xml, image/jpeg, image/gif, audio/mpeg, audio/mp4, video/wmv, video/mp4,<br>
Accept-Language: en-us, en-gb;q=0.1, en;q=0.7, fr, fr-ch, da, de, fi<br>
```If-Modified-Since: Wed, 09 Sep 2020 16:06:01 -0700```<br>
User Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/535.11 (KHTML, like Gecko) Chrome/17.0.963.56 Safari/535.11<br>

Does the client have a cached copy of the object being requested?

[Note: you can find additional questions similar to this here.]





- ```Yes, because this is a conditional GET, as evidenced by the If-Modified-Since field.```


- No, because a client would not request an object if it had that object in its cache.


- Yes, because HTTP 1.1 is being used.


- There's not enough information in the header to answer this question.


# A DETAILED LOOK AT AN HTTP REPLY.


Suppose now the server sends the following HTTP response message the client:

```HTTP/1.0 200 OK```<br>
Date: Wed, 09 Sep 2020 23:46:21 +0000<br>
Server: Apache/2.2.3 (CentOS)<br>
Last-Modified: Wed, 09 Sep 2020 23:51:41 +0000<br>
ETag:17dc6-a5c-bf716880.<br>
Content-Length: 418<br>
Connection: Close<br>
Content-type: image/html<br>

Will the web server close the TCP connection after sending this message?
[Note: you can find more questions like this one here.]



- ```Yes, the server will close this connection because version 1.0 of HTTP is being used, and TCP connections do not stay open persistently.```


- There's not enough information in the response message to answer this question.


- No, the server will leave the connection open as a persistent HTTP connection.


- Yes, because the HTTP response indicated that only one object was requested in the HTTP GET request.

# WHY WEB CACHING?


Which of the following are advantages of using a web cache? Sselect one or more answers.


- Caching allows an origin server to more carefully track which clients are requesting and receiving which web objects.


- ```Caching uses less bandwidth coming into an institutional network where the client is located, if the cache is also located in that institutional network.```


- Overall, caching requires  fewer  devices/hosts to satisfy a web request, thus saving on server/cache costs.


- ```Caching generally provides for a faster page load time at the client, if  the web cache is in the client’s institutional network, because the page is loaded from the nearby cache rather than from the distant server.```

# HTTP/2 VERSUS HTTP/1.1.


  Which of the following are changes between HTTP 1.1 and HTTP/2? Note: select one or more answers.


- ```HTTP/2 allows a large object to be broken down into smaller pieces, and the transmission of those pieces to be interleaved with transmission  other smaller objects, thus preventing a large object from forcing many smaller objects to wait their turn for transmission.```


- HTTP/2 provides enhanced security by using transport layer security (TLS).


- HTTP/2 has many new HTTP methods and status codes.


- ```HTTP/2 allows objects in a persistent connection to be sent in a client-specified priority order. ```

# WHAT'S IN AN HTTP REPLY?


Which of the following pieces of information will appear in a server’s application-level HTTP reply message? (Check all that apply.)


- The server's IP address


- A sequence number


- ```A response code```


- ```A response phrase associated with a response code```


- A checksum


- The name of the Web server (e.g., gaia.cs.umass.edu)



# IF-MODIFIED-SINCE.


What is the purpose of the If-Modified-Since field in a HTTP GET request message


- To indicate to the server that the client wishes to receive this object, and the time it until it which it will cache the returned object


- To indicate to the server that the server should replace this named object with the new version of the object attached to the GET, if the object has not been modified since the specified time


- To inform the HTTP cache that it (the cache) should retrieve the full object from the server, and then cache it until the specified time.


- ```To indicate to the server that the client has cached this object from a previous GET, and the time it was cached.```


- To allow the server to indicate to the client that it (the client) should cache this object.

# COOKIES.


What is the purpose of a cookie value in the HTTP GET request?


- ```The cookie value itself doesn't mean anything.  It is just a value that was returned by a web server to this client during an earlier interaction.```


- The cookie value indicates whether the user wants to use HTTP/1, HTTP/1.1, or HTTP/2 for this GET request.


- The cookie value encodes the format of the reply preferred by the client in the response to this GET request.


- The cookie value encodes a default set of preferences that the user has previously specified for this web site.


- The cookie value is an encoding of a user email address associated with the GET request.

# HTTP GET (EVEN MORE).


Suppose a client is sending an HTTP GET message to a web server, gaia.cs.umass.edu. Suppose the client-to-server HTTP GET message is the following:

GET /kurose_ross_sandbox/interactive/quotation2.htm HTTP/1.1<br>
Host: gaia.cs.umass.edu<br>
Accept: text/plain, text/html, text/xml, image/jpeg, image/gif, audio/mpeg, audio/mp4, video/wmv, video/mp4,<br>
Accept-Language: en-us, en-gb;q=0.1, en;q=0.7, fr, fr-ch, da, de, fi<br>
```If-Modified-Since: Wed, 09 Sep 2020 16:06:01 -0700```<br>
User Agent: Mozilla/5.0 (Windows NT 6.1; WOW64) AppleWebKit/535.11 (KHTML, like Gecko) Chrome/17.0.963.56 Safari/535.11<br>

Does the client have a cached copy of the object being requested?



- No, because the client would not request an object if it were cached.


- There’s not enough information to answer this question.


- ```Yes, because this is a conditional GET.```

# WHAT HAPPENS AFTER AN HTTP REPLY?


Suppose an HTTP server sends the following HTTP response message a client:

```HTTP/1.0 200 OK```<br>
Date: Wed, 09 Sep 2020 23:46:21 +0000<br>
Server: Apache/2.2.3 (CentOS)<br>
Last-Modified: Wed, 09 Sep 2020 23:51:41 +0000<br>
ETag:17dc6-a5c-bf716880.<br>
Content-Length: 418<br>
Connection: Close<br>
Content-type: image/html<br>

Will the web server close the TCP connection after sending this message?


- No, this is a persistent connection, and so the server will keep the TCP connection open.


- ```Yes, because this is HTTP 1.0```


- There’s not enough information to answer this question.