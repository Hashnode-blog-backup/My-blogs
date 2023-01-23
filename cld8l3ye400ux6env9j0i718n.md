# Internet

# **What is the Internet?**

The Internet is the global system of interconnected computer networks that use the Internet protocol suite (TCP/IP) to link devices worldwide. It is a network of networks that consists of private, public, academic, business, and government networks of local to global scope, linked by a broad array of electronic, wireless, and optical networking technologies. Internet was started as a project of US Military project named ARPANET directed by Robert Taylor and managed by Lawrence Roberts.

## **CLIENT AND SERVER**

Your browser relies on the internet, which is a network of computers that send messages to each other. We call these messages packets. Packets include the data you’re sending and information about where that data is coming from and where it’s going. Every computer on the internet has an address for sending packets to it. But some computers only accept certain types of packets, and others only allow packets from a restricted list of other computers. It’s then up to the receiving computer to determine what to do with the packets and how to respond.

The computer initiating requests is typically referred to as the **client** regardless of whether the request is initiated by a browser, command line, or so on.

**Servers** refer to the websites and web applications receiving the requests.

Because the internet can include any number of computers talking to each other, we need guidelines for how computers should communicate over the internet. This takes the form of **Request for Comment (RFC)** documents, which define standards for how computers should behave. For example, the **Hypertext Transfer Protocol (HTTP)** defines how your internet browser communicates with a remote server using Internet Protocol (IP). In this scenario, both the client and server must agree to implement the same standards so they can understand the packets each is sending and receiving.

## **What is an HTTP?**

**Hypertext Transfer Protocol (HTTP)** is an application layer protocol for transmitting hypermedia documents, such as HTML. It was designed for communication between web browsers and web servers, but it can also be used for other purposes. HTTP follows a classical **client-server model**, with a client opening a connection to make a request, then waiting until it receives a response. HTTP is a **stateless protocol**, meaning that the server does not keep any data (state) between two requests.

## **What happens when you visit a website?**

1. **Extracting the domain name.**
    
    Once you enter http://www.google.com, your browser determines the domain name from the URL. A domain name identifies which website you’re trying to visit, in this case, the domain name is ***www.google.come***. The domain serves as one way to find the server's address.
    
2. **Resolving an IP address.**
    
    After determining the domain name, your browser uses IP to look up the IP address associated with the domain. This process is referred to as resolving the IP address, and every domain on the internet must resolve to an IP address to work. To look up an IP address using just the domain name, your computer sends a request to Domain Name System (DNS) servers, which consist of specialized servers on the internet that have a registry of all domains and their matching IP addresses. The preceding IPv4 and IPv6 addresses are Google DNS servers. In this example, the DNS server you connect to would match [www.google.com](http://www.google.com) to the IPv4 address **216.58.201.228** and send that back to your computer.
    
3. **Establishing a TCP connection.**
    
    Next, the computer attempts to establish a Transmission Control Protocol (TCP) connection with the IP address on port 80 because you visited a site using http://. The details of TCP aren’t important other than to note that it’s another protocol that defines how computers communicate with each other. TCP provides two-way communication so that message recipients can verify the information they receive and nothing is lost in transmission.
    
4. **Sending an HTTP request.**
    
    Continuing with [http://www.google.com/](http://www.google.com/) as an example, if the connection in step 3 is successful, your browser should prepare and send an HTTP request.
    
    A correctly composed HTTP request contains the following elements:
    
    1. A request line.
        
    2. A series of HTTP headers, or header fields.
        
    3. A message body, if needed.
Each HTTP header is followed by a carriage return line feed (CRLF). After the last of the HTTP headers, an additional CRLF is used (to give an empty line), and then any message body begins.
    
    **Request line**
The request line is the first line in the request message. It consists of at least
three items:
    
    1.  A **method**. The method is a one-word command that tells the server what it should do with the resource. For example, the server could be asked to send the resource to the client.
        
    2.  The path component of the URL for the request. The path identifies the resource on the server.
        
    3.  The HTTP version number shows the HTTP specification to which the client has tried to make the message comply.
        
5. **Server response.**
    
    An HTTP response is made by a server to a client. The response aims to provide the client with the resource it requested, inform the client that the action it requested has been carried out, or else inform the client that an error occurred in processing its request.
    
    An HTTP response contains:
    
    1. A status line.
        
    2. A series of HTTP headers, or header fields.
        
    3. A message body is usually needed.
 As in a request message, each HTTP header is followed by a carriage return line feed (CRLF). After the last of the HTTP headers, an additional CRLF is used (to give an empty line), and then the message body begins.

**Status line**
 The status line is the first line in the response message. It consists of three items:
     1. The HTTP version number shows the HTTP specification to which the server has tried to make the message comply.
      2. A **status code**, which is a three-digit number indicating the result of the request.
      3. A **reason phrase**, also known as status text, is human-readable text that summarizes the meaning of the status code.

  An example of a response line is:
    
    In this example:
    
    the HTTP version is `HTTP/1.1`
        
    the status code is `200`
        
    the reason phrase is `OK`
        
6. **Rendering the Response.**
    
    If the server's response status code is 200 and the response content type is text/html, our browser will begin rendering the contents it received. The response’s body tells the browser what should be presented to the user.
    
    The server can return other content, such as XML, but we’ll stick to the basics for this example.
    

## **HTTP is stateless.**

HTTP requests are stateless, which means that every request sent to a server is treated as a brand-new request. The server knows nothing about its previous communication with your browser when receiving a request. This is problematic for most sites because the sites want to remember who you are. Otherwise, you’d have to reenter your username and password for every HTTP request sent. This also means that all the data required to process an HTTP request must be reloaded with every request a client sends to a server.

To clarify this confusing concept, consider this example: if you and I had a stateless conversation before every sentence was spoken, I’d have to start with “I’m Patrick Muhire we were just discussing the internet.” You’d then have to reload all the information about what we were discussing about the internet.

To avoid having to resend your username and password for every HTTP request, websites use cookies or basic authentication, which we’ll discuss in details in the coming series.

## **Summary.**

You should now have a basic understanding of how the internet works. Specifically, you learned what happens when you enter a website into your browser’s address bar: how the browser translates that to a domain, how the domain is mapped to an IP address, and how an HTTP request is sent to a server. You also learned how your browser structures requests and renders responses and how HTTP request methods allow clients to communicate with servers.