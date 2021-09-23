# 使用線上工具 == > 質因數分解    

http://factordb.com/

# libnum : python套件

!pip install libnum

```
s2n(s) - packed string to number
n2s(n) - number to packed string
s2b(s) - packed string to binary string
b2s(b) - binary string to packed string
```
```python
import libnum

s="flag{happyCryptoDay}"
number = libnum.s2n(s)
number
```
```
print(libnum.n2s(number))
```
# gmpy2

https://gmpy2.readthedocs.io/en/latest/

```
!apt install libmpc-dev
!pip3 install --user gmpy2==2.1.0a2
```

# 學習資源

- 練習作業: 完成 https://cryptopals.com/ 的八道題組

```python

import codecs

hex = "49276d206b696c6c696e6720796f757220627261696e206c696b65206120706f69736f6e6f7573206d757368726f6f6d“

b64 = codecs.encode(codecs.decode(hex, 'hex'), 'base64').decode()
b64
```
