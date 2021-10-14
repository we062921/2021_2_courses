# agenda

- [pycryptodome](#pycryptodome)
- [安裝](#安裝)
- [測試1:RSA加解密](#RSA加解密)
- [測試2:](#測試2)
- [測試3:AES加解密](#AES加解密)
- [測試4:HASH](#HASH)

## pycryptodome

## 安裝 

GOOGLE COLAB
```
!pip install pycryptodome
```

- [PyCryptodome](https://github.com/Legrandin/pycryptodome)

## HASH
- [資料來源:Hash Functions - Examples](https://cryptobook.nakov.com/cryptographic-hash-functions/hash-functions-examples)

```python
from Crypto.Hash import keccak
import binascii

keccak256 = keccak.new(data=b"hello", digest_bits=256).digest()
print("Keccak256: ", binascii.hexlify(keccak256))
```
```
Keccak256:  b'1c8aff950685c2ed4bc3174f3472287b56d9517b9c948127319a09a7a36deac8'
```
## RSA加解密

- [Python 以 PyCryptodome 實作 RSA 非對稱式加密方法教學與範例](https://officeguide.cc/python-pycryptodome-rsa-asymmetric-encryption-tutorial-examples/)

### 使用 PyCryptodome 模組產生一組 2048 位元 RSA 金鑰(RSA-pairs)
```python
from Crypto.PublicKey import RSA

# 產生 2048 位元 RSA 金鑰
key = RSA.generate(2048)

# RSA 私鑰
privateKey = key.export_key()
with open("private.pem", "wb") as f:
    f.write(privateKey)

# RSA 公鑰
publicKey = key.publickey().export_key()
with open("public.pem", "wb") as f:
    f.write(publicKey)
```
-cat private.pem

```python
-----BEGIN RSA PRIVATE KEY-----
MIIEowIBAAKCAQEAtr3iC5yU75ZuDMsjl7vtxjXojKQI45E8Rk1fY5Xc7rphn2nv
MVsVU0pULbJMjxELxoI6W9NqKoa2bF7ZfpcmtwUw2+rSQYlcUUJY/4iowHEbX9+i
CtCH6ZaYY8Q2cb0vhvie0os9FA/fWtGxYE3PzNt31ykvxAMfZXns3Du79Vh79M/X
Olyg6mAnXqXEnm+t/sV6lzQ4QdU4zqzz90OaupfdBb3JEfxRYAcLQcQ8Kg5D8BC9
MIvdGFAzTa/Hiognriya81YFu1p8Yk3kkfsklnBhKRpGGdRrM8yl8GYSD4GjFSr2
ylLCL3gg2zW1Rh4Ae81mhRVQjTAfaZjM+UdiswIDAQABAoIBAFAUqwvanNvXaLeb
h6f1N3AebJ/BPJH5Mdg/DNe3sz88lw5EXoka+J/s2THDSlCBsE7X/9oAriwfp66a
7CXQ+CrJEA23fFcy6i1D7XthuE3I4y2i80BY/M5s67AAqrkyJjM4HWV3lhcGE6OZ
c+kXgEIuRPiZeHCly6rtANLMLISJeYyUIrvtKHwYwPou9QrXC3jIbPiKhHCe3VmP
3ykS2jG4w+LhvikqEsRRcT03emYYcpmGC3hIwcz2rKi0KiSitypS3lUqYq9lc8wW
1XibPHDWMyBuiwB+g3yyVeiRtWOqy4dcRmNWFEcGnBQNhm8yAlXmZUgzpWAAZnOj
KU7JSS0CgYEAyTl6JNa9ckW2n8vhsfHvyTwPGnfvQQNgtiEIVau4CjV7G9uKR9SM
GNWTIEXJpaS2ySaACfK47fkTZrNHAk0QDAkMrlapLDXc0gc54PI73dRGbFCOJKXI
+ECn1SgrymOqbDnKkuiXUIxQKOoo+IqrktEzJFhmbJyFcXh6VxdSX20CgYEA6Hxq
PqyONgs6Dq4uT2M2xnyEYVEf2VCMJCcK6UK72ADpfGAumhRCSwiShd+j0w3JZFDg
IG2fSWdNJof6IjnrFHuAW1tYDvdSyc/tlhHGcVNfes0mSoKMHrU/eKpjPUCLJ88e
Cb1sD52hbVW/ghYZ0yxU/yIJSNs+kHj1u9od1p8CgYARdVEpnQ/2uCGuH4xHWgxJ
01IkI7+4Tki3xInqlOl0yUsTEasfrEszZGRNaoCiRHYvYY2+TzbIPtH2GRvSEUmR
Ib/d6FrpIQs1lbbp01pqVp59i0ep2lBjaYimL8QM3TTOCv2OXWuza1kRE6/WUIGu
TUQ4pQrN5Y6WV7OVlspoyQKBgQChd4+e2d+nX2LCQW0+i+zGLEMRB/PzzcKXdVpZ
qZSnL/L6BB85uipUzK5fNnUkp2WhO55+R0SjCZEG2tf6H3nK7v+185oUQugH7FbZ
rJzDpqEgvA0FIOhKh51+o/Bq4UIEsw/sudesfNFaC30Hz2u+RAMAc9Y4+LTaSHh7
MMEahwKBgE5vAa0ghXBrSibxNGKmNEyWFRj1ZAW9BXNwwM+3rekI88gYQVnyMpwc
/W/p7Y7K3qFo98+nkYaLHhicw8IQvT1AmD24GPJDnCEkDegy+5MFxbCPZ5cZAxRO
C1W8Ddnp4LyRJGz7mJvltp10FGc8GFi3+xhEdpc6O/+xrAlg6eh0
-----END RSA PRIVATE KEY-----
```
- cat public.pem

```python
-----BEGIN PUBLIC KEY-----
MIIBIjANBgkqhkiG9w0BAQEFAAOCAQ8AMIIBCgKCAQEAtr3iC5yU75ZuDMsjl7vt
xjXojKQI45E8Rk1fY5Xc7rphn2nvMVsVU0pULbJMjxELxoI6W9NqKoa2bF7Zfpcm
twUw2+rSQYlcUUJY/4iowHEbX9+iCtCH6ZaYY8Q2cb0vhvie0os9FA/fWtGxYE3P
zNt31ykvxAMfZXns3Du79Vh79M/XOlyg6mAnXqXEnm+t/sV6lzQ4QdU4zqzz90Oa
upfdBb3JEfxRYAcLQcQ8Kg5D8BC9MIvdGFAzTa/Hiognriya81YFu1p8Yk3kkfsk
lnBhKRpGGdRrM8yl8GYSD4GjFSr2ylLCL3gg2zW1Rh4Ae81mhRVQjTAfaZjM+Udi
swIDAQAB
-----END PUBLIC KEY-----
```

## AES加解密

- [Python 以 PyCryptodome 實作 AES 對稱式加密方法教學與範例](https://officeguide.cc/python-pycryptodome-aes-symmetric-encryption-tutorial-examples/)

### AES加密
```python
from Crypto.Cipher import AES
from Crypto.Random import get_random_bytes

data =b'falg(HappyCryptoDay)'
key = get_random_bytes(16)
cipher = AES.new(key, AES.MODE_EAX)
ciphertext, tag = cipher.encrypt_and_digest(data)

file_out = open("encrypted.bin", "wb")
[ file_out.write(x) for x in (cipher.nonce, tag, ciphertext) ]
file_out.close()
```
### AES解密
```
from Crypto.Cipher import AES

file_in = open("encrypted.bin", "rb")
nonce, tag, ciphertext = [ file_in.read(x) for x in (16, 16, -1) ]

# let's assume that the key is somehow available again
cipher = AES.new(key, AES.MODE_EAX, nonce)
data = cipher.decrypt_and_verify(ciphertext, tag)
```
