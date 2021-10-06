# 05_Linux使用者管理

## Linux Users and Groups

- 使用者(users)
  - 安裝Linux的過程, 安裝程式預設會建立一個系統管理者帳號, 並在安裝過程中會要求您建立一個使用者帳號
  - 系統管理者帳號
  - 一般使用者的帳號  
  - 
 

- 群組(Group)
 
 
## Creating(建立) and Deleting(刪除) User Accounts(使用者帳號)
- 不同Linux版本使用不同指令
  - Ubuntu Linux  ==> 使用 useradd
  - Kali Linux  ==> 使用adduser

## Kali Linux
```
底下兩者有何差異?
adduser --home /home/ksu20211006 ksu20211006

adduser --home /ksu2021b ksu2021b
```
```
root@kali:/home# adduser --home /home/ksu20211006 ksu20211006
Adding user `ksu20211006' ...
Adding new group `ksu20211006' (1003) ...
Adding new user `ksu20211006' (1003) with group `ksu20211006' ...
Creating home directory `/home/ksu20211006' ...
Copying files from `/etc/skel' ...
New password: 
Retype new password: 
passwd: password updated successfully
Changing the user information for ksu20211006
Enter the new value, or press ENTER for the default
	Full Name []: 
	Room Number []: 
	Work Phone []: 
	Home Phone []: 
	Other []: 
Is the information correct? [Y/n] 

```
## Kali:切換使用者身分 su
- 退出使用者身分 ==> 使用exit
```
root@kali:~# pwd
/root
root@kali:~# su ksu20211006
ksu20211006@kali:/root$ whoami
ksu20211006
ksu20211006@kali:/root$ cd
ksu20211006@kali:~$ pwd
/home/ksu20211006
ksu20211006@kali:~$ exit
exit
root@kali:~# whoami
root
root@kali:~# 
```


## U
- 指令 ==> useradd ksu2021a
- [各種參數](https://www.linode.com/docs/guides/linux-users-and-groups/)

- useradd ksu2021ab -d /home/ksu2021ab
  
| Option(選項)|	Description(敘述)|	Example(範例)|
| ----| ------| ------|
|-d <home_dir>|	使用home_dir 當作使用者登入的目錄	|`useradd <name> -d /home/<user's home>`|
| -e `<date>`|	設定帳號過期日|`useradd <name>** -e <YYYY-MM-DD>` |
|-f `<inactive>`|	the number of days before the account expires|`useradd <name> -f <0 or -1>`|
|-s `<shell>`|	sets the default shell type|`useradd <name> -s /bin/<shell>`|

- 假設要建立的帳號已被他人所佔用, 則會出現使用者已存在的訊息

- 指令 ==> passwd <username>  

- /etc/passwd 檔案格式
  - 每個使用者帳號在 passwd 檔案中都有 7 個欄位, 由左到右分別用冒號 (:) 隔開：
    - 帳號名稱
    - 使用者密碼
    - 使用者識別碼 (UID, User ID)
    - 群組識別碼 (GID, Group ID)
    - 使用者相關資訊
    - 使用者家目錄
    - 使用者環境

  - 預設的情況下, 任何使用者都可以讀取 /etc/passwd 檔案, 可用 ls指令來查看

- /etc/passwd 檔案格式
  - 每個帳號在 shadow 檔案中都有 9 個欄位, 分別用 8 個冒號 (:) 隔開
    - 1.帳號名稱
    - 2.使用者密碼
    - 3.密碼最後變動的時間
    - 4.密碼變動兩次之間, 至少需間隔的日數
    - 5.密碼變動過後, 距離下次一定要更改密碼的日數
    - 6.離下次密碼必須變動日期前多少日, 就開始警告使用者
    - 7.超過密碼必須變動日期後多少日, 就將該帳號停權
    - 8.帳號的使用期限
    - 9.最後一個欄位為保留欄位

  
- /etc/skel/ 目錄
  - /etc/skel/ (skel is derived from the “skeleton”) is used to initiate home directory when a user is first created
  - ls -lart /etc/skel 
  - cat /etc/default/useradd
  – Default permission of /etc/skel is drwxr-xr-x.
  – It is not recommended to change the permission of skel directory or its contents.

userdel <name>

userdel -r <name>
  
apt-get install adduser

## 切換帳號與變換身份

  - 使用一般帳號登入系統,若想要轉變成管理者身份,只要執行 su指令並輸入 root 帳號的密碼幾即可 
  
  
# 
newgrp <marketing>
