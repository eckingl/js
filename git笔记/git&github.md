## github

+ SSH

  x6xH7bc4FoDNPTPS/sRRCVpoZ2M25goQ9I167OsJshD+88Y9uJqlw0CSC8mRN7RxrBOKweosDE+H6wxcm7jQcVe1YVOkPiTxXVzpRC1qoYWHHeFYh5EtOyQqWrrGPz/vf2GFs4jcU4WxpTmhDWXjk0nCaelYFnKtaKSmTGOqRjeQti+gPsaBMq1eClrebfNRXMUTOZiE/DeZYNNRP8WXnFy9Zhsm9ymCTBLmcYdUEiSKVpXSbCtXZ7S/uDJuWKhTM/yLCFQ6gLxAPkx2iW41CTmdj+KOwkx0/hhJ5OeFIUYO3MQQOtwfT5 eckingl@hotmail.com
  
+ 错误代码

  + error: failed to push some refs to 'git@github.com:eckingl/js.git'
  
    原因:远程添加README.md文件后无法push,因为本地没有README.md文件,需要将文件拉取到本地,处理代码为:
  
    `git pull --rebasa origin master`
  
    执行此代码后出现错误,错误代码为:
  
    `error: cannot pull with rebase: You have unstaged changes. error: additionally, your index contains uncommitted changes. error: please commit or stash them.`
  
    原因:有未提交的更改,无法git pull
  
    解决代码:
  
    `git stash`
  
    `git pull -rebase`
  
    ` git stash pop`
  
    无法pull问题解决
  
+ 基本操作

  1. 上传

     `git push origin master`

     



## git

+ 文件的状态

  1. modified (已修改)

     在工作目录修改git文件

  2. staged (已暂存)index

      对已修改的文件执行git暂存操作,将文件存入暂存区

  3. committed (已提交)

      将已暂存的文件执行git提交操作,将文件存入版本库 

+ 命令

  + 获取本地仓库

     `git init`
  
     `git clone`
    
  + 版本管理
  
    `git add `
  
    `git commit`
  
    `git rm`
  
  + 查看信息
  
     `git log`
  
     `git diff`
  
  + 远程协作
  
     `git pull`
  
     `git push`
  
  
  
  
  
  
  
  
  
  

## linux命令

+ 创建文件

  `mkdir local`

+ 查看git安装位置

  `which git`

+ 

+ 



