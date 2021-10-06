# 攻擊HASH

## Collision attack
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


## 長度擴充攻擊 (LEA Attack)Length extension attack 
- 攻擊[Merkle–Damgård Construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction)
- [Merkle–Damgård Construction](https://en.wikipedia.org/wiki/Merkle%E2%80%93Damg%C3%A5rd_construction)
- [HashPump](https://github.com/bwall/HashPump)
- [hashpumpy:Python bindings for HashPump](https://github.com/bwall/HashPump)
- Hashpump是一個專門利用Hash Length Extension Attack的工具,支援MD5, SHA1, SHA256, SHA512幾種常見加密演算法,使用C/C++編寫,支援python拓展

- 如何避免被LEA??
  - 避免使用Merkle–Damgård based hash:==> 使用 HMAC |keyed-hash Message authentication code |金鑰雜湊訊息鑑別碼 ==> HMAC-MD5、HMAC-SHA1
  - 使用更安全的HASH: Truncated versions of SHA-2, including SHA-384 and SHA256/512  SHA-3
