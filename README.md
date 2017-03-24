# tip-ip-learn
tip/ip-learn

http://www.linfo.org/tcp_ip.html（tcp/ip定义）
tcp/ip 在传输层 和网络层。它提供了其他网络协议的优点；使用单一寻址方案（ip寻址）；提供可靠数据传输：It provides reliable data delivery. Reliable means that it can guarantee that the data is delivered to its intended destination ；可路由协议：It is a routable protocol, which means that it can determine the most efficient path for every packet as it moves through the network. 


Packet Definition：

header，payload，trail
header（包含了 自己ip 和 目标ip，还有当前包 在message 中的顺序和标识）
payload 即是数据区，如果遇到特定的协议规定要 是  固定长度的packets，那么会用别的假数据填充以满足长度。
trail 尾巴。contains several bits that tell the receiving device that it has reached the end of the packet
