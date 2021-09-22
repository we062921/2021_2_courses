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
```bash
#!/bin/bash
FILES=( "file1" "file2" "file3" ) # This is a global variable

function create_file() {
    local FNAME="${1}" # First parameter
    local PERMISSIONS="${2}" # Second parameter
    touch "${FNAME}"
    chmod "${PERMISSIONS}" "${FNAME}"
    ls -l "${FNAME}"
}

for ELEMENT in ${FILES[@]}
do
        create_file "${ELEMENT}" "a+x"
done

echo "Created all the files with a function!"
exit 0
```
## 載入與使用 另外程式 Including source files

library.sh
```bash
#!/bin/bash

function create_file() {
    local FNAME=$1
    touch "${FNAME}"
    ls "${FNAME}" # If output doesn't return a value - file is missing
}

function delete_file() {
    local FNAME=$1
    rm "${FNAME}"
    ls "${FNAME}" # If output doesn't return a value - file is missing
}
```

```bash
#!/bin/bash

source library.sh # You may need to include the path as it is relative
FNAME="my_test_file.txt"
create_file "${FNAME}"
delete_file "${FNAME}"

exit 0
```

## 使用《管道 pipe > >> 》連接多個命令以及輸入/輸出《重定向 Redirection  | 》
```bash
#!/bin/sh

# Let's run a command and send all of the output to /dev/null
echo "No output?"
ls ~/fakefile.txt > /dev/null 2>&1

# Retrieve output from a piped command 
echo "part 1"
HISTORY_TEXT=`cat ~/.bashrc | grep HIST`
echo "${HISTORY_TEXT}"

# Output the results to history.config
echo "part 2"
echo "${HISTORY_TEXT}" > "history.config"

# Re-direct history.config as input to the cat command
cat < history.config

# Append a string to history.config
echo "MY_VAR=1" >> history.config

echo "part 3 - using Tee"
# Neato.txt will contain the same information as the console
ls -la ~/fakefile.txt ~/ 2>&1 | tee neato.txt
```
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
1．923
1．10獲取程序輸入參數26
1．11獲取命令相關的額外信息28
```
