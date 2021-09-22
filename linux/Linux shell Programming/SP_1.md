# Linux Shell programming

- [Bash Cookbook (簡體中文版)](https://www.tenlong.com.tw/products/9787115527011) [[GITHUB]](https://github.com/PacktPublishing/Bash-Cookbook) [[英文版]](https://www.packtpub.com/product/bash-cookbook/9781788629362)
```
第1章Bash速成
第2章文本與文件處理
第3章精通文件系統
第4章像【守護進程 Daemon】一樣的腳本Making a Script Behave Like a Daemon
第5章系統管理腳本
第6章高級用戶專用腳本
第7章Bash致勝之道
第8章高級腳本技術
```
# 第1章Bash速成

```bash
#!/bin/bash
# Pound or hash sign signifies a comment (a line that is not executed)
whoami 
pwd 
ls 
echo “Echo one 1”; echo “Echo two 2” 
```
```bash
#!/bin/bash
# Echo this is my first comment
echo "Hello world! This is my first Bash script!"
echo -n "I am executing the script with user: "
whoami
echo -n "I am currently running in the directory: "
pwd
exit 0
```
## 基本變數的創建和使用
```bash
#!/bin/bash

PI=3.14
VAR_A=10
VAR_B=$VAR_A
VAR_C=${VAR_B}

echo "Lets print 3 variables:"
echo $VAR_A
echo $VAR_B
echo $VAR_C
```

## 使用if、else、elseif進行條件邏輯判斷
```bash
#!/bin/bash
AGE=17
if [ ${AGE} -lt 18 ]; then
    echo "You must be 18 or older to see this movie"
fi
```
## case/switch語句和循環結構


## 使用函數和參數

```
1．1 Bash和CLI基礎知識入門
1．2基本變量的創建和使用6
1．3 Bash隱藏變量和保留字9
11
1．4．1評估數值12
1．4．2評估字符串13
1．4．3嵌套if語句14
1．5 case/switch語句和循環結構14
1．5．1基本的case語句15
1． 5．2基本循環16
1．617
1．7包含源文件19
1．8檢索返回碼和輸出20
1．9使用管道連接多個命令以及輸入/輸出重定向23
1．10獲取程序輸入參數26
1．11獲取命令相關的額外信息28
```
