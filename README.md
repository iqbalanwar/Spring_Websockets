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
- Websockets require the use of STOMP and SockJS
- In the config, it requires the application destination to be the same in the client 