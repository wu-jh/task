## HTTP

​          HTTP是一个简单的请求相应协议，他通常运行在TCP之上。它指定了客户端可能发送给服务器什么样消息以及得到什么样的响应。请求响应的消息头以ASCII码形式给出；而消息内容则是具有有一个类似MIME的格式。

### 工作原理

HTTP是基于客户/服务器模式，且面向连接的。HTTP处理过程如下：

1. 客户与服务器建立连接
2. 客户向服务器提出请求
3. 服务器接受请求，并且根据请求返回相应的文件作为应答
4. 客户与服务器关闭连接

​         客户与服务器之间的HTTP连接是一种一次性连接，它限制每次连接只处理一个请求，当服务器返回本次请求的应答后便立即关闭连接，下次请求再重新建立连接。这种一次性连接主要考虑到WWW服务器面向的是Internet中成干上万个用户，且只能提供有限个连接，故服务器不会让一个连接处于等待状态，及时地释放连接可以大大提高服务器的执行效率。 

​		HTTP是一种无状态协议，即服务器不保留与客户交易时的任何状态。这就大大减轻了服务器记忆负担，从而保持较快的响应速度。HTTP是一种面向对象的协议。允许传送任意类型的数据对象。它通过数据类型和长度来标识所传送的数据内容和大小，并允许对数据进行压缩传送。当用户在一个HTML文档中定义了一个超文本链后，浏览器将通过TCP/IP协议与指定的服务器建立连接。 

## TCP/IP协议

TCP/IP（Transmission Control Protocol/Internet Protocol，传输控制协议/网际协议）是指能够在多个不同网络间实现信息传输的协议簇。TCP/IP协议不仅仅指的是[TCP](https://baike.baidu.com/item/TCP/33012) 和[IP](https://baike.baidu.com/item/IP/224599)两个协议，而是指一个由[FTP](https://baike.baidu.com/item/FTP/13839)、[SMTP](https://baike.baidu.com/item/SMTP/175887)、TCP、[UDP](https://baike.baidu.com/item/UDP/571511)、IP等协议构成的协议簇， 只是因为在TCP/IP协议中TCP协议和IP协议最具代表性，所以被称为TCP/IP协议。

### TCP/IP协议的组成

TCP/IP分四个层次

应用层：应用层是TCP/IP协议的的第一层，是直接为应用进程提供服务的

1. 对不同种类的应用程序它们会根据自己的需要来使用应用层的不同协议，邮件传输应用使用了[SMTP](https://baike.baidu.com/item/SMTP/175887)协议、万维网应用使用了[HTTP](https://baike.baidu.com/item/HTTP/243074)协议、远程登录服务应用使用了有[TELNET](https://baike.baidu.com/item/TELNET/810597)协议。
2. 应用层还能加密、解密、格式化数据
3. 应用层可以建立或解除与其他节点的联系，这样可以充分节省网络资源。

运输层：作为TCP/IP协议的第二层，运输层在整个TCP/IP协议中起到了中流砥柱的作用。且在运输层中，TCP和UDP也同样起到了中流砥柱的作用。

网络层：网络层在TCP/IP协议中的位于第三层。在TCP/IP协议中网络层可以进行网络连接的建立和终止以及IP地址的寻找等功能。

网络接口层：在TCP/IP协议中，网络接口层位于第四层。网络接口层既是传输数据的物理媒介，也可以为网络层提供一条准确无误的线路。

### 特点

1. 协议标准是完全开放的，可以供用户免费使用，并且独立于特定的[计算机硬件](https://baike.baidu.com/item/计算机硬件/5459592)与[操作系统](https://baike.baidu.com/item/操作系统/192)。

2. 独立于网络硬件系统，可以运行在[广域网](https://baike.baidu.com/item/广域网/422004)，更适合于[互联网](https://baike.baidu.com/item/互联网/199186)。

3. 网络地址统一分配，网络中每一设备和终端都具有一个唯一地址。

4. 高层协议标准化，可以提供多种多样可靠网络服务。

### 缺陷

1. 该模型没有明显地区分服务、接口和协议的概念。因此，对于使用新技术来设计新网络，TCP/IP模型不是一个太好的模板。
2. TCP/IP模型完全不是通用的，并且不适合描述除TCP/IP模型之外的任何[协议栈](https://baike.baidu.com/item/协议栈/3155224)。
3. 链路层并不是通常意义上的一层。它是一个接口，处于网络层和数据链路层之间。接口和层间的区别是很重要的。
4. TCP/IP模型不区分物理层和数据链路层。这两层完全不同，物理层必须处理铜缆、光纤和无线通信的传输特征；而数据链路层的工作是确定帧的开始和结束，并且按照所需的可靠程度把帧从一端发送到另一端。

### IP协议

网络层引入了IP协议，制定了一套新地址，使得我们能够区分两台主机是否同属一个网络，这套地址就是网络地址，也就是所谓的IP地址。IP协议将这个32位的地址分为两部分，前面部分代表网络地址，后面部分表示该主机在局域网中的地址。如果两个IP地址在同一个子网内，则网络地址一定相同。为了判断IP地址中的网络地址，IP协议还引入了子网掩码，IP地址和子网掩码通过按位与运算后就可以得到网络地址。

### UDP协议

UDP协议定义了端口，同一个主机上的每个应用程序都需要指定唯一的端口号，并且规定网络中传输的数据包必须加上端口信息，当数据包到达主机以后，就可以根据端口号找到对应的应用程序了。UDP协议比较简单，实现容易，但它没有确认机制，数据包一旦发出，无法知道对方是否收到，因此可靠性较差，为了解决这个问题，提高网络可靠性，TCP协议就诞生了。

### TCP协议

TCP即传输控制协议，是一种面向连接的、可靠的、基于字节流的通信协议。简单来说TCP就是有确认机制的UDP协议，每发出一个数据包都要求确认，如果有一个数据包丢失，就收不到确认，发送方就必须重发这个数据包。为了保证传输的可靠性，TCP协议在UDP基础之上建立了三次对话的确认机制，即在正式收发数据前，必须和对方建立可靠的连接。TCP数据包和UDP一样，都是由首部和数据两部分组成，唯一不同的是，TCP数据包没有长度限制，理论上可以无限长，但是为了保证网络的效率，通常TCP数据包的长度不会超过IP数据包的长度，以确保单个TCP数据包不必再分割。

## socket（套接字）

套接字（socket）是一个抽象层，应用程序可以通过它发送或接收数据，可对其进行像对文件一样的打开、读写和关闭等操作。套接字允许应用程序将I/O插入到网络中，并与网络中的其他应用程序进行通信。网络套接字是IP地址与端口的组合。

套接字Socke = IP地址：端口号

### 分类

为了满足不同的通信程序对[通信质量](https://baike.baidu.com/item/通信质量/22548449)和性能的要求，一般的网络系统提供了三种不同类型的套接字，以供用户在设计网络应用程序时根据不同的要求来选择。这三种套接为流式套接字（SOCK-STREAM）、数据报套接字（SOCK-DGRAM）和原始套接字（SOCK-RAW）。

（1）流式套接字。它提供了一种可靠的、面向连接的双向数据传输服务，实现了数据无差错、无重复的发送。流式套接字内设[流量控制](https://baike.baidu.com/item/流量控制/3441910)，被传输的数据看作是无记录边界的字节流。在TCP/IP协议簇中，使用TCP协议来实现字节流的传输，当用户想要发送大批量的数据或者对数据传输有较高的要求时，可以使用流式套接字。

（2）数据报套接字。它提供了一种无连接、不可靠的双向数据传输服务。[数据包](https://baike.baidu.com/item/数据包/489739)以独立的形式被发送，并且保留了记录边界，不提供可靠性保证。数据在传输过程中可能会丢失或重复，并且不能保证在接收端按发送顺序接收数据。在TCP/IP协议簇中，使用[UDP](https://baike.baidu.com/item/UDP/571511)协议来实现数据报套接字。在出现差错的可能性较小或允许部分传输出错的应用场合，可以使用数据报套接字进行数据传输，这样通信的效率较高。

（3）原始套接字。该套接字允许对较低层协议（如IP或[ICMP](https://baike.baidu.com/item/ICMP/572452)）进行直接访问，常用于网络协议分析，检验新的网络协议实现，也可用于测试新配置或安装的网络设备。

## 长连接

长连接，指在一个连接上可以连续发送多个[数据包](https://baike.baidu.com/item/数据包/489739)，在连接保持期间，如果没有数据包发送，需要双方发链路检测包。

### 定义

[短连接](https://baike.baidu.com/item/短连接)是指通讯双方有数据交互时，就建立一个连接，数据发送完成后，则断开此连接，即每次连接只完成一项业务的发送。

长连接多用于操作频繁，点对点的通讯，而且连接数不能太多情况。每个TCP连接都需要三步握手，这需要时间，如果每个操作都是短连接，再操作的话那么处理速度会降低很多，所以每个操作完后都不断开，下次处理时直接发送数据包就OK了，不用建立TCP连接。例如：数据库的连接用长连接，如果用短连接频繁的通信会造成socket错误，而且频繁的socket 创建也是对资源的浪费。

而像WEB网站的http服务一般都用[短链接](https://baike.baidu.com/item/短链接)，因为长连接对于服务端来说会耗费一定的资源，而像WEB网站这么频繁的成千上万甚至上亿客户端的连接用[短连接](https://baike.baidu.com/item/短连接)会更省一些资源，如果用长连接，而且同时有成千上万的用户，如果每个用户都占用一个连接的话，那可想而知吧。所以并发量大，但每个用户无需频繁操作情况下需用短连好。

### 长连接短连接操作过程

短连接的操作步骤是： 建立连接——数据传输——关闭连接…建立连接——数据传输——关闭连接 

长连接的操作步骤是： 建立连接——数据传输…（保持连接）…数据传输——关闭连接