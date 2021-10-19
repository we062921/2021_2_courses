# 計算機網路
```
A.1. 電腦通訊概說
   A.1.1.電腦與網路:基本觀念
   A.1.2.資訊傳輸模式
   A.1.3.網路傳輸速度
   A.1.4.電腦網路的類型
A.2. 網路的組成與架構
   A.2.1. 電腦網路的功能
   A.2.2. 區域網路的拓樸
          拓撲(Topology)==網路連接的型態

   A.2.3. 電腦網路分享架構:Client/server與P2P
```


## 網路標準與通訊協定
```
A.3.1.通訊協定與標準

A.3.2. OSI通訊標準
A.3.3. TCP/IP協定
A.3.4. [IEEE 802](https://en.wikipedia.org/wiki/IEEE_802)
   
A.3.4. 傳輸層重要協定:TCP vs UDP
        A.3.4.1 TCP vs UDP
        A.3.4.2 TCP的三向交握

A.3.5. IP與DNS(網域名稱)
        A.3.5.1. IP協定與IP位址
        A.3.5.2. DNS
```

![通訊協定](通訊協定.png)


## 經典教科書 Computer Networks電腦網路 第五版

- [經典教科書 Computer Networks, 5/e (IE-Paperback)Andrew S. Tanenbaum , David J. Wetherall(2010)](https://www.tenlong.com.tw/products/9780132553179)
- [中譯本 電腦網路, 5/e (Computer Networks, 5/e) (授權經銷版)(2012,896頁)](https://www.tenlong.com.tw/products/9789862800973) 
```
第一章 緒論

第二章 實體層 THE PHYSICAL LAYER

第三章 資料鏈結層 THE DATA LINK LAYER
 3.2 ERROR DETECTION(錯誤偵測) AND CORRECTION(錯誤更正)
第四章 媒介存取控制層THE MEDIUM ACCESS CONTROL SUBLAYER

第五章 網路層THE NETWORK LAYER
  6.3 CONGESTION CONTROL(壅塞控制)

第六章 傳輸層THE TRANSPORT LAYER  ==> UDP vs TCP


6.4.1 UDP (User Datagram Protocol) ==> a connectionless(無須連結) transport protocol
6.4.2 RPC(Remote Procedure Call)
6.4.3 RTP(Real-Time Transport Protocols)| RTCP(The Real-time Transport Control Protocol) ==> 多媒體網路

6.5.TCP (Transmission Control Protocol)
     6.5.8 TCP Sliding Window
     6.5.10 TCP Congestion Control


第七章 應用層
7.1 DNS(THE DOMAIN NAME SYSTEM) ==>  dns(53) 
     ==> [dnssec()1999,2005](https://www.ithome.com.tw/tech/92685)  [DNSSEC安全技術簡介(2012)](https://www.cc.ntu.edu.tw/chinese/epaper/0022/20120920_2206.html)
          Domain Name System Security Extensions (DNSSEC)

7.2 ELECTRONIC MAIL
    SMTP(Simple Mail Transfer Protocol)
    IMAP(Internet Message Access Protocol)是用來從本地郵件收發軟體（如Microsoft Outlook、Outlook Express、Mozilla Thunderbird）存取遠端伺服器上的郵件。
    POP3(Post Office Protocol - Version 3，郵局協定第三版)是郵件存取最為普遍的Internet標準協定

7.3 THE WORLD WIDE WEB ==> http(80) | https(443)

7.4 STREAMING AUDIO AND VIDEO


第八章 網路安全
第九章 閱讀書單與參考書目
```

## CCNA認證

- [CCNA國際認證班(資展國際)](https://www.iiiedu.org.tw/ccna/)

## 延伸閱讀

- [圖解 TCP/IP 網路通訊協定 (涵蓋IPv6)(2021修訂版) 井上直也,村山公保,竹下隆史,荒井透,苅田幸雄 著(2021) ](https://www.tenlong.com.tw/products/9789865027063)
- [COMPUTER NETWORKS[R15A0513]LECTURE NOTES](https://mrcet.com/downloads/digital_notes/CSE/III%20Year/COMPUTER%20NETWORKS%20NOTES.pdf)
