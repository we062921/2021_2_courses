# 破密分析常用工具


## 使用線上工具 == > 質因數分解    

http://factordb.com/

## libnum 套件
```
libnum是python模組 ,具有底下功能:

使用質數primes(生成質數、是否為質數測試)
普通數學運算（gcd、lcm、n'th root）
模運算（逆，雅可比符號，平方根，求解 CRT）
將字串轉換為數字或二進位字串
```
### 在Google Colab安裝 libnum
```
!pip install libnum
```

### 常用函式 ==> 將字串轉換為數字或二進位字串
```
s2n(s) - packed string to number
n2s(n) - number to packed string
s2b(s) - packed string to binary string
b2s(b) - binary string to packed string
```

### 範例練習
```python
import libnum

s="flag{happyCryptoDay}"
number = libnum.s2n(s)
number
```
```
print(libnum.n2s(number))
```
## [gmpy2]()

- [gmpy2’s documentation](https://gmpy2.readthedocs.io/en/latest/)

### google Colab 安裝 [GMPY2 doesn't install](https://stackoverflow.com/questions/50474091/gmpy2-doesnt-install)
```
!apt install libmpc-dev
!pip3 install --user gmpy2==2.1.0a2
```
## conda安裝
```
conda install gmpy2
```

# 學習資源

- 練習作業: 完成 https://cryptopals.com/ 的八道題組

```python

import codecs

hex = "49276d206b696c6c696e6720796f757220627261696e206c696b65206120706f69736f6e6f7573206d757368726f6f6d“

b64 = codecs.encode(codecs.decode(hex, 'hex'), 'base64').decode()
b64
```
