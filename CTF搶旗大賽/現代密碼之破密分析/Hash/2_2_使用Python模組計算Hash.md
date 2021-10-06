
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
```python
#!/usr/bin/python
# -*- coding: utf-8 -*-

# 載入 hashlib 模組
import hashlib

# 先建立 MD5 物件
m = hashlib.md5()

# 要 hash 的 資料
flag2 = "cTF2021{happppy Hash}"

# 記得要先設定utf-8編碼
m.update(flag2.encode('utf-8'))

# 計算 MD5 雜湊值
h = m.hexdigest()
print(h)
```

```python
#!/usr/bin/env python
# -*- coding: UTF-8 -*-
#pyversion:python3.5
#owner:fuzj

import hashlib
# ######## md5 ########
string = "beyongjie"
md5 = hashlib.md5()
md5.update(string.encode('utf-8'))     #注意轉碼
res = md5.hexdigest()
print("md5加密結果:",res)
# ######## sha1 ########
sha1 = hashlib.sha1()
sha1.update(string.encode('utf-8'))
res = sha1.hexdigest()
print("sha1加密結果:",res)
# ######## sha256 ########
sha256 = hashlib.sha256()
sha256.update(string.encode('utf-8'))
res = sha256.hexdigest()
print("sha256加密結果:",res)
# ######## sha384 ########
sha384 = hashlib.sha384()
sha384.update(string.encode('utf-8'))
res = sha384.hexdigest()
print("sha384加密結果:",res)
# ######## sha512 ########
sha512= hashlib.sha512()
sha512.update(string.encode('utf-8'))
res = sha512.hexdigest()
print("sha512加密結果:",res)
```
