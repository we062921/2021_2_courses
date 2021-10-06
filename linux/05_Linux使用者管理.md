# 05_Linux使用者管理

## Linux Users and Groups

- 使用者(users)
  - 系統管理者
  - 一般使用者的帳號  
  - 
 

- 群組(Group)
 
 
# Creating(建立) and Deleting(刪除) User Accounts(使用者帳號)

useradd <name>
  
| Option(選項)|	Description(敘述)|	Example(範例)|
| ----| ------| ------|
|-d <home_dir>|	使用home_dir 當作使用者登入的目錄	|useradd <name> -d /home/<user's home>|
| -e <date>|	設定帳號過期日|	useradd <name>** -e <YYYY-MM-DD> |
|-f <inactive>|	the number of days before the account expires|	useradd <name> -f <0 or -1>
|-s <shell>|	sets the default shell type| 	useradd <name> -s /bin/<shell>|
