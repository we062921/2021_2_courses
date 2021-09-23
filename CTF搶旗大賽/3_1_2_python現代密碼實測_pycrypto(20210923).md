# 3_1_2_python現代密碼實測_pycrypto(20210923)

!pip install pycrypto

|模組名稱 | 說明 |
| ------| ------|
|Crypto.Cipher | Secret-key (AES, DES, ARC4) and public-key encryption (RSA PKCS#1) algorithms|
| Crypto.Hash| Hashing algorithms (MD5, SHA, HMAC)|
|Crypto.Protocol|Cryptographic protocols (Chaffing, all-or-nothing transform, key derivation functions). This package does not contain any network protocols.|
|Crypto.PublicKey|Public-key encryption and signature algorithms (RSA, DSA)|
|Crypto.Signature |Public-key signature algorithms (RSA PKCS#1)|
|Crypto.Util|Various useful modules and functions (long-to-string conversion, random number generation, number theoretic functions)|

- [Crypto.Util.number 的 常用函式](https://pythonhosted.org/pycrypto/Crypto.Util.number-module.html)

## 
```python
from Crypto.Util.number import GCD

GCD(12,18)
```



## AES對稱式加解密
### AES加密
```python

from Crypto.Cipher import AES

obj = AES.new('This is a key123', AES.MODE_CBC, 'This is an IV456')

message = "flag(HappyCrypt)"

ciphertext = obj.encrypt(message)
ciphertext
```
### AES解密
```python
obj2 = AES.new('This is a key123', AES.MODE_CBC, 'This is an IV456')

obj2.decrypt(ciphertext)
```
