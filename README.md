# tcp-ip-learn
tcp/ip-learn

http://www.linfo.org/tcp_ip.html（tcp/ip定义）
tcp/ip 在传输层 和网络层。它提供了其他网络协议的优点；使用单一寻址方案（ip寻址）；提供可靠数据传输：It provides reliable data delivery. Reliable means that it can guarantee that the data is delivered to its intended destination ；可路由协议：It is a routable protocol, which means that it can determine the most efficient path for every packet as it moves through the network. 


Packet Definition：

header，payload，trail
header（包含了 自己ip 和 目标ip，还有当前包 在message 中的顺序和标识）
payload 即是数据区，如果遇到特定的协议规定要 是  固定长度的packets，那么会用别的假数据填充以满足长度。
trail 尾巴。contains several bits that tell the receiving device that it has reached the end of the packet



The short answer: TCP is a transport-layer protocol, and HTTP is an application-layer protocol that runs over TCP. Keep reading for the long answer.

To understand the difference (and a lot of other networking topics), you need to understand the idea of a layered networking model. Essentially, there are different protocols that let a computer talk at different distances and different layers of abstraction.

At the very bottom of the network stack is the physical layer. This is where electrical signals or light pulses or radio waves actually transmit information from place to place. The physical layer doesn't really have protocols, but instead has standards for voltages, frequencies, and other physical properties. You can transmit information directly this way, but you need a lot of power or a dedicated line, and without higher layers you won't be able to share bandwidth.

The next layer up is the link layer. This layer covers communication with devices that share a physical communications medium. Here, protocols like Ethernet, 802.11a/b/g/n, and Token Ring specify how to handle multiple concurrent accesses to the physical medium and how to direct traffic to one device instead of another. In a typical home network, this is how your computer talks to your home "router."

The third layer is the network layer. In the majority of cases, this is dominated by Internet Protocol (IP). This is where the magic of the Internet happens, and you get to talk to a computer halfway around the world, without needing to know where it is. Routers handle directing your traffic from your local network to the network where the other computer lives, where its own link layer handles getting the packets to the right computer.

Now we are getting somewhere. We can talk to a computer somewhere around the world, but that computer is running lots of different programs. How should it know which one to deliver your message to? The transport layer takes care of this, usually with port numbers. The two most popular transport layer protocols are TCP and UDP. TCP does a lot of interesting things to smooth over the rough spots of network-layer packet-switched communication like reordering packets, retransmitting lost packets, etc. UDP is more unreliable, but has less overhead.

So we've connected your browser to the web server software on the other end, but how does the server know what page you want? How can you post a question or an answer? These are things that application-layer protocols handle. For web traffic, this is the HyperText Transfer Protocol (HTTP). There are thousands of application-layer protocols: SMTP, IMAP, and POP3 for email; XMPP, IRC, ICQ for chat; Telnet, SSH, RDP for remote administration; etc.

These are the five layers of the TCP/IP networking model, but they are really only conceptual. The OSI model has 7 layers. In reality, some protocols shim between various layers, or can work at multiple layers at once. TLS/SSL for instance provides encryption and session information between the network and transport layers. Above the application layer, Application Programming Interfaces (APIs) govern communication with web applications like Quora, Twitter, and Facebook.
