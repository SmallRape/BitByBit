   Http协议的开销导致不适用于低延迟应用，为了解决这些问题，WebSocket将网络套接字引入了客户端和服务端，浏览器和服务器之间
可以通过套接字建立持久的连接。
### Http协议的弊端
>* 半双工协议
>* http消息冗长而繁琐
>* 针对服务器推送的黑客攻击：长时间轮询  

WebSocket的目的是取代轮询和Comet技术(使用AJAX, 全双工通信，但是采用长连接)。浏览器通过JS向服务器发出建立WebSocket连接的请求，连接建立后，客户端和服务器可以通过TCP
连接直接交换数据。相比于传统AJAX轮询方案，WebSocket有了很大的性能优势。     
为了建立一个WebSocket连接，客户端浏览器首先要向服务器发一个Http请求，附加一些头信息：Upgrade：WebSocket，服务端解析后生成
应答信息返回，这样就建立起来了，直到某一方主动关闭连接。   
为关闭WebSocket连接，客户端和服务端需要通过一个安全的方法关闭底层TCP连接以及TLS会话。

ps: 得知道WebSocket和http一样，是应用层协议。