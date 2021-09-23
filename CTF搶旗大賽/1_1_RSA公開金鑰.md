# RSA

### Key generation(產生key pair)
- 隨意選擇兩個大的質數p和q[p不等於q]
- 計算n=pq
- 根據歐拉函數，求得 φ(n)=(p-1)(q-1)
- 選擇一個小於φ(n)的整數e，使e與φ(n)互質
- 求得e關於φ(n)的模反元素(module inverse)，命名為d {d*e mod φ(n) =1 }(模反元素存在，若且唯若e與 φ(n)互質）
- 公鑰pub={e,n}    私鑰pri={d,n}

## RSA加解密

- 加密 使用公鑰pub={e,n}加密
- ciphertext = (plaintext)^e mod n

- 解密 使用私鑰pri={d,n}解密
- plaintext = (ciphertext )^d mod n

<img src="https://render.githubusercontent.com/render/math?math=plaintext = (ciphertext )^{d} mod n">
<img src="https://render.githubusercontent.com/render/math?math=e^{i \pi} = -1">

## 範例說明
### Key generation(產生key pair)
```
(1)Select primes隨意選擇兩個大的質數p和q，p不等於q    p=17, q=11
(2)Compute n=pq=187
(3)Compute φ(n)=(p-1)(q-1)=160
(4)Select e=7  such that GCD(7,160)=1
(5)Compute d: d=23 ==> 7*23 mod 160=1 (use the extended Euclid’s algorithm)

公鑰pub={e,n}={7,187}
私鑰pri={d,n}={23,187}
```
### RSA加解密
```
明文M=88
加密(Encrypt): 88^7mod 187
88^7mod 187 =  11(密文C)

解密Decrypt C=11: 11^23mod 187
M=11^23 mod 187=88
```

# 攻擊RSA

# 小n攻擊
- n太小 可很容易被質因數分解出
- n = p*q   15 =5*3  187 =17*11


### CTF YANG_RSA-1
```
RSA加密演算法是一種非對稱加密演算法，在公開金鑰加密和電子商業中RSA加密被廣泛使用。

RSA的安全性是建立在大數分解的困難上，如果n不夠大就無法保證其安全性，
對一極大整數做因數分解愈困難，RSA演算法愈可靠。

你了解RSA的基本加解密了嗎?
請解密附件檔案

提示1 : n很小可以使用 http://factordb.com/ 先分解出p和q質數
提示2 : 分解出p和q質數後算出d，用d去解c

附件：RSA-1.txt
```
附件：RSA-1.txt
```
n = 83092583783534841000145280642003842283533340442637642451258941907393275732996256523893438356692786223410880194199043046345864683398238392329295750150314289824255749149834103

e = 11

c = 32392151763267291269610586564983347951891395196084251182633225594245167922176424232164117237142038355860036871811244158149537196288428230971760474130300660929743492107190512
```

解題步驟
1.使用線上工具 == > 質因數分解  http://factordb.com/
  n=p*q*r
2.撰寫python解題程式
```
#!/usr/bin/env python
from Crypto.Util.number import *
import gmpy2

p =質因數分解 得到的
q =質因數分解 得到的
r =質因數分解 得到的

n = 題目給的
e =題目給的
c =題目給的


phi = (p-1)*(q-1)*(r-1)

d = int(gmpy2.invert(e, phi))

m = pow(c,d,n)

print(long_to_bytes(m))
```


