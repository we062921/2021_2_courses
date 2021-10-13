# 


# linux-1

# linux-2
# linux-3
# linux-4


# linux-5

- 搜尋檔案  find, whch ,locate,.....
- 上網肉搜  linux find
  - [](https://blog.gtwang.org/linux/unix-linux-find-command-examples/)
  - [在 Linux 下使用 find 指令查詢目錄與檔案的速查筆記](https://blog.miniasp.com/post/2010/08/27/Linux-find-command-tips-and-notice) 

# linux-6


ps aux w | grep socat


root       24408  0.0  0.0  24360  2888 pts/0    S    Oct12   0:00 socat TCP-LISTEN:2111,reuseaddr,fork EXEC:/bin/flag


socat  TCP-LISTEN:2111,reuseaddr,fork EXEC:/bin/flag


# linux-7

- 網路服務==>  netstat
 
- netstat -ano
  - a
  - n
  - 0

- 提示 : 80 Port  ==> 怎模看網頁? 指令列? ==> curl
- 上網肉搜  linux curl
  - 
 
- curl 127.0.0.1

# linux-8

- 下載並解壓縮ForYou檔案
- 下載 ==> wget
- 解壓縮 ==> tar
  - tar zxvf ForYou.tar.gz


# linux-9
```
file TobeExe

TobeExe: ELF 32-bit LSB executable, Intel 80386, version 1 (SYSV), dynamically linked, 
interpreter /lib/ld-linux.so.2, for GNU/Linux 2.6.32, BuildID[sha1]=10558357d3700c05f1426a6d2a09b920bda2e464, not stripped
```

```
ls -al TobeExe

-rw-r--r-- 1 lab lab 7348 Nov 15  2017 TobeExe
```

```
chmod +x TobeExe


ls -al TobeExe
-rwxr-xr-x 1 lab lab 7348 Nov 15  2017 TobeExe
```

```
./TobeExe
```
# linux-10
