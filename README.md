# Spring Websockets
Learning Websockets using the Spring Framework

I'm using the tutorial as listed here:
https://www.youtube.com/watch?time_continue=3&v=4Hyv4M1kFeM&feature=emb_logo

The dependencies I'm using are:
- Websocket 
- Spring Web
- JPA
- JDBC
- Reactor Netty
    - This was added directly to the pom.xml, and is needed to use the full Websocket functionality with STOMP

## Notes:
- Process of a WebSocket architecture:
    - When a message is sent to an endpoint, a request channel handles the message
    - The request channel sends it to the Message Handler, which defines the type of message this is
        - This could be entering (registering into) a message session, or just sending a message
    - The message is then sent to the Simple Broker
        - This handles to message to be sent
        - Either the request channel goes to the simple broker, or the message handler
    - Last, the response channel takes the message from the Simple Broker and the end user receives the message
    - Note: The endpoints for the request channel and response channel need to be consistent
        - This is the @SendTo, in your controller, which takes the endpoint from SimpleBroker in your WsConfig
- WebSockets require the use of STOMP and SockJS
- In the config, the endpoint made requires the application destination in the server to be the same in the client
    - In this case, it is the /topic endpoint