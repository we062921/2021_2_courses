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
# 第1章 快速掌握 Bash程式 語法

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

# 使用if、else、elseif進行條件判斷
| 條件判斷 | 說明 | 數學符號 |
| -------| -------| --------|
|-gt | greater than 大於| >|
|-ge | greater or equal to 大於 或 等於 | >=|
|-lt | less than 小於| <|
|-le |less than or equal t o小於 或 等於 |<=|
|-eq |equal to等於 |  |
|-nq |not equal to 不等於 ||

## if 條件
```bash
#!/bin/bash
AGE=17
if [ ${AGE} -lt 18 ]; then
    echo "You must be 18 or older to see this movie"
fi
```
## if-else 條件
```bash
#!/bin/bash
AGE=9000
if [ ${AGE} -lt 18 ]; then
 echo "You must be 18 or older to see this movie"
else
 echo "You may see the movie!"
 exit 1
fi

echo "This line will never get executed"
```

## if-elif-else條件
```
#!/bin/bash
AGE=21
if [ ${AGE} -lt 18 ]; then
 echo "You must be 18 or older to see this movie"
elif [ ${AGE} -eq 21 ]; then
 echo "You may see the movie and get popcorn"
else
 echo "You may see the movie!"
 exit 1
fi

echo "This line might not get executed"
```
## if-elif(很多個)-else條件
```
#!/bin/bash
VAR=10

# Multiple IF statements
if [ $VAR -eq 1 ]; then
    echo "$VAR"
elif [ $VAR -eq 2]; then
    echo "$VAR"
elif [ $VAR -eq 3]; then
    echo "$VAR"
# .... to 10
else
    echo "I am not looking to match this value"
fi
```
## nested_if 嵌套if語句 ==> if 條件裡還有if
```
#!/bin/bash
USER_AGE=18
AGE_LIMIT=18
NAME="Bob" # Change to your username if you want to execute the nested logic
HAS_NIGHTMARES="true"

if [ "${USER}" == "${NAME}" ]; then
    if [ ${USER_AGE} -ge ${AGE_LIMIT} ]; then
        if [ "${HAS_NIGHTMARES}" == "true" ]; then
            echo "${USER} gets nightmares, and should not see the movie"
        fi
    fi
else
    echo "Who is this?"
fi
```
## 字符串
```
#!/bin/bash
MY_NAME="John"
NAME_1="Bob"
NAME_2="Jane"
NAME_3="Sue"
Name_4="Kate"

if [ "${MY_NAME}" == "Ron" ]; then
    echo "Ron is home from vacation"
elif [ "${MY_NAME}" != ${NAME_1}" && "${MY_NAME}" != ${NAME_2}" && "${MY_NAME}" == "John" ]; then
    echo "John is home after some unnecessary AND logic"
elif [ "${MY_NAME}" == ${NAME_3}" || "${MY_NAME}" == ${NAME_4}" ]; then
    echo "Looks like one of the ladies are home"
else
    echo "Who is this stranger?"
fi
```
# case/switch語句
### case的用法(Case/switch statements)
```bash
#!/bin/bash
VAR=10 
case $VAR in
  1)
    echo "1"
    ;;
  2)
    echo "2"
    ;;
  *)
    echo "What is this var?"
    exit 1
esac
```
# 循環結構loop
## for迴圈
```bash
#!/bin/bash

FILES=( "file1" "file2" "file3" )
for ELEMENT in ${FILES[@]}
do
        echo "${ELEMENT}"
done

echo "Echo\'d all the files" 
```
## DO-while迴圈 Do while loop
```bash
#!/bin/bash
CTR=1
while [ ${CTR} -lt 9 ]
do
    echo "CTR var: ${CTR}"
    ((CTR++)) # Increment the CTR variable by 1
done
echo "Finished"
```
## until迴圈
```bash
#!/bin/bash
CTR=1
until [ ${CTR} -gt 9 ]
do
    echo "CTR var: ${CTR}"
    ((CTR++)) # Increment the CTR variable by 1
done
echo "Finished"
```
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

## 使用《管道 pipe > 與>>(附加) 》連接多個命令以及輸入/輸出《重定向 Redirection  | 》
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
## 設計具有輸入參數的 Shell程式
```bash
#!/bin/bash

HELP_STR="usage: $0 [-h] [-f] [-l] [--firstname[=]<value>] [--lastname[=]<value] [--help]"

# Notice hidden variables and other built-in Bash functionality
optspec=":flh-:"
while getopts "$optspec" optchar; do
    case "${optchar}" in
        -)
            case "${OPTARG}" in
                firstname)
                    val="${!OPTIND}"; OPTIND=$(( $OPTIND + 1 ))
                    FIRSTNAME="${val}"
                    ;;
                lastname)
                    val="${!OPTIND}"; OPTIND=$(( $OPTIND + 1 ))
                        LASTNAME="${val}"
                    ;;
                help)
                    val="${!OPTIND}"; OPTIND=$(( $OPTIND + 1 ))
                    ;;
                *)
                    if [ "$OPTERR" = 1 ] && [ "${optspec:0:1}" != ":" ]; then
                        echo "Found an unknown option --${OPTARG}" >&2
                    fi
                    ;;
            esac;;
        f)
                val="${!OPTIND}"; OPTIND=$(( $OPTIND + 1 ))
                FIRSTNAME="${val}"
                ;;
        l)
                val="${!OPTIND}"; OPTIND=$(( $OPTIND + 1 ))
                LASTNAME="${val}"
                ;;
        h)
            echo "${HELP_STR}" >&2
            exit 2
            ;;
        *)
            if [ "$OPTERR" != 1 ] || [ "${optspec:0:1}" = ":" ]; then
                echo "Error parsing short flag: '-${OPTARG}'" >&2
                exit 1
            fi

            ;;
    esac
done

# Do we have even one argument?
if [ -z "$1" ]; then
  echo "${HELP_STR}" >&2
  exit 2
fi

# Sanity check for both Firstname and Lastname
if [ -z "${FIRSTNAME}" ] || [ -z "${LASTNAME}" ]; then
  echo "Both firstname and lastname are required!"
  exit 3
fi

echo "Welcome ${FIRSTNAME} ${LASTNAME}!"

exit 0
```
```
1．1 Bash和CLI基礎知識入門
1．2基本變量的創建和使用6
1．3 Bash隱藏變量和保留字9
11
1．4．1評估數值12
1．4．2評估13
1．4．314

1．8檢索返回碼和輸出20

```
