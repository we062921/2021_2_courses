# 3_1_2_python現代密碼實測_pycrypto(20210923)

!pip install pycrypto


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
