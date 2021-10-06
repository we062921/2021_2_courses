#
## HASH基本觀念
- [md5(MD5 message-digest algorithm)](https://en.wikipedia.org/wiki/MD5)
  -  MD5 was designed by Ronald Rivest in 1991 to replace an earlier hash function MD4
  -  MD5 was specified in 1992 as RFC 1321.

## HASH計算
- [使用Linux指令計算HASH](#Linux指令)
- [使用Python模組計算Hash](#Python_Hashlib)
- [使用openssl模組計算Hash]

## 攻擊HASH
- Collision attack
  - [Are there two known strings which have the same MD5 hash value?](https://crypto.stackexchange.com/questions/1434/are-there-two-known-strings-which-have-the-same-md5-hash-value) 
  - [MD5 Collision Demo](http://www.mathstat.dal.ca/~selinger/md5collision/)
```
root@kali:~/ctf# cd crytpo/
root@kali:~/ctf/crytpo# ls
erase  hello
root@kali:~/ctf/crytpo# md5sum erase 
da5c61e1edc0f18337e46418e48c1290  erase
root@kali:~/ctf/crytpo# md5sum hello 
da5c61e1edc0f18337e46418e48c1290  hello
```
  - [Sha-1 collision(2017)](http://thehackernews.com/2017/02/sha1-collision-attack.html) 
    - Google Achieves First-Ever Successful SHA-1 Collision Attack 
    - [shattered:We have broken SHA-1 in practice.](https://shattered.io/)


- 長度擴充攻擊 (LEA Attack)Length extension attack ==> 攻擊[Merkle–Damgård Construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction)
  - [Merkle–Damgård Construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction)
  - [HashPump](https://github.com/bwall/HashPump)
  - [hashpumpy:Python bindings for HashPump](https://github.com/bwall/HashPump)
  - Hashpump是一個專門利用Hash Length Extension Attack的工具,支援MD5, SHA1, SHA256, SHA512幾種常見加密演算法,使用C/C++編寫,支援python拓展
  - 如何避免被LEA??
    - 避免使用Merkle–Damgård based hash:==> 使用 HMAC |keyed-hash Message authentication code |金鑰雜湊訊息鑑別碼 ==> HMAC-MD5、HMAC-SHA1
    - 使用更安全的HASH: Truncated versions of SHA-2, including SHA-384 and SHA256/512  SHA-3


## Linux指令:md5sum, sha1sum

Google Colab實測: !md5sum --help
```
Usage: md5sum [OPTION]... [FILE]...
Print or check MD5 (128-bit) checksums.

With no FILE, or when FILE is -, read standard input.

  -b, --binary         read in binary mode
  -c, --check          read MD5 sums from the FILEs and check them
      --tag            create a BSD-style checksum
  -t, --text           read in text mode (default)

The following five options are useful only when verifying checksums:
      --ignore-missing  don't fail or report status for missing files
      --quiet          don't print OK for each successfully verified file
      --status         don't output anything, status code shows success
      --strict         exit non-zero for improperly formatted checksum lines
  -w, --warn           warn about improperly formatted checksum lines

      --help     display this help and exit
      --version  output version information and exit

The sums are computed as described in RFC 1321.  When checking, the input
should be a former output of this program.  The default mode is to print a
line with checksum, a space, a character indicating input mode ('*' for binary,
' ' for text or where binary is insignificant), and name for each FILE.

GNU coreutils online help: <http://www.gnu.org/software/coreutils/>
Full documentation at: <http://www.gnu.org/software/coreutils/md5sum>
or available locally via: info '(coreutils) md5sum invocation'
```

```
Usage: sha1sum [OPTION]... [FILE]...
Print or check SHA1 (160-bit) checksums.

With no FILE, or when FILE is -, read standard input.

  -b, --binary         read in binary mode
  -c, --check          read SHA1 sums from the FILEs and check them
      --tag            create a BSD-style checksum
  -t, --text           read in text mode (default)

The following five options are useful only when verifying checksums:
      --ignore-missing  don't fail or report status for missing files
      --quiet          don't print OK for each successfully verified file
      --status         don't output anything, status code shows success
      --strict         exit non-zero for improperly formatted checksum lines
  -w, --warn           warn about improperly formatted checksum lines

      --help     display this help and exit
      --version  output version information and exit

The sums are computed as described in FIPS-180-1.  When checking, the input
should be a former output of this program.  The default mode is to print a
line with checksum, a space, a character indicating input mode ('*' for binary,
' ' for text or where binary is insignificant), and name for each FILE.

GNU coreutils online help: <http://www.gnu.org/software/coreutils/>
Full documentation at: <http://www.gnu.org/software/coreutils/sha1sum>
or available locally via: info '(coreutils) sha1sum invocation'
```
```
!echo abc > test.txt
!echo Abc > test2.txt
```
```
!md5sum test.txt  ==> 0bee89b07a248e27c83fc3d5951213c1  test.txt  ==>32*4 bits =128 bits
!md5sum test2.txt ==> 879435373481c222ca1e3346b3b4c4b1  test2.txt
```
```
!sha1sum test.txt ==> 03cfd743661f07975fa2f1220c5194cbaff48451  test.txt ==>40*4 bits =160 bits
!sha1sum test2.txt ==> b686597546683b17bdd1179f339fa32e1b4368c9  test2.txt
```


## Python_Hashlib
- [Python 計算 MD5 與 SHA 雜湊教學與範例](https://blog.gtwang.org/programming/python-md5-sha-hash-functions-tutorial-examples/)
- [python中hashlib模組詳解](https://codertw.com/%E7%A8%8B%E5%BC%8F%E8%AA%9E%E8%A8%80/615922/)

- hashlib主要提供字元加密功能，將md5和sha模組整合到了一起，支援md5,sha1, sha224, sha256, sha384, sha512等演算法
- 如何得知目前的平台上，hashlib 所支援的所有雜湊演算法 ==> print(hashlib.algorithms_available)
  - {'sha224', 'sha3_256', 'shake_256', 'sha512', 'blake2s', 'shake_128', 'sha256', 'blake2b', 'sha1', 'md5', 'sha3_512', 'sha3_224', 'sha384', 'sha3_384'}
- 如果要發展跨平台的程式，應該要以跨平台通用的雜湊演算法為主，
- 這些跨平台的演算法可以透過 hashlib.algorithms_guaranteed 查詢  ==> print(hashlib.algorithms_guaranteed)
  - {'sha224', 'sha3_256', 'shake_256', 'sha512', 'blake2s', 'shake_128', 'sha256', 'blake2b', 'sha1', 'md5', 'sha3_512', 'sha3_224', 'sha384', 'sha3_384'}
  - Google colab和[Python 計算 MD5 與 SHA 雜湊教學與範例](https://blog.gtwang.org/programming/python-md5-sha-hash-functions-tutorial-examples/)有差異

 
```python
#!/usr/bin/python3
import hashlib

m1 = hashlib.md5()
m2 = hashlib.md5()

data1 = "abc"
data2 = "Abc"

# 先將資料編碼，再更新 MD5 雜湊值
m1.update(data1.encode("utf-8"))
m2.update(data2.encode("utf-8"))

h1 = m1.hexdigest()
h2 = m2.hexdigest()

print(h1)
print(h2)
```

```python
#!/usr/bin/python
# -*- coding: utf-8 -*-
import hashlib

# 輸入檔案名稱
filename = "test.txt"

m = hashlib.md5()  # s = hashlib.sha1()

# 讀取檔案內容，計算 MD5 雜湊值
with open(filename, "rb") as f:
  buf = f.read()
  m.update(buf)

h = m.hexdigest()
print(h)
```
```
得到的答案為 0bee89b07a248e27c83fc3d5951213c1
和底下的一樣

!md5sum test.txt  ==> 0bee89b07a248e27c83fc3d5951213c1  test.txt  ==>32*4 bits =128 bits
```

- 檔案比較大的話，可分批次讀取，每次讀取一部分的內容，使用 update 來更新 MD5 雜湊值，這樣程式的效率會比較好
```python
#!/usr/bin/python
# -*- coding: utf-8 -*-
import hashlib

filename = "test.txt"
m = hashlib.md5()  # s = hashlib.sha1()

with open(filename, "rb") as f:
  # 分批讀取檔案內容，計算 MD5 雜湊值
  for chunk in iter(lambda: f.read(4096), b""):
    m.update(chunk)

h = m.hexdigest()
print(h)
```
