---

title:  "ARP Spoofing"

date:   2022-03-14 15:39:42 +0800

categories: TCP/IP

---
***ARP 協定***

位址解析協定(Address Resolution Protocol，縮寫：ARP)，被用來以 IP 位址查詢其相對應主機的 MAC 位址。如下圖，Client(192.168.1.223)，會用APR封包詢問Gateway(192.168.1.1)的MAC 位址為何。

![arp](/assets/images/arp/arp.jpg)

Client之後會更新ARP Table：

![arp](/assets/images/arp/arp-client.jpg)

---

***ARP Spoofing***
使用攻擊主機製造假的ARP封包，目的是發送不正確的Gateway MAC位址給Client並放入封包內，導致封包無法傳送到真的Gateway連到Internet。假封包的source ip設定為192.168.1.1，source MAC是攻擊主機的MAC位址；destination ip是192.168.1.223。

![arp](/assets/images/arp/arp-spoofing.jpg)

再次查看ARP Table，192.168.1.1的MAC位址已經更新成攻擊主機的MAC位址；並且Client無法連上Internet：

![arp](/assets/images/arp/arp-spoofing-client.jpg)

---

References：[ARP是什么？如何通过scapy实现ARP欺骗攻击](https://youtu.be/3oHWPrrL2Zc)
