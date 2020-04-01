Github学习笔记

以下是git工具一些常用的指令与本地与远程仓库同步的操作步骤的记录。


git工具的一些指令操作：
git  pull   //同步服务器代码至本地
git  push   //上传代码至服务器（最终操作）
git  staus  //查看本地代码更改情况
git  log    //查看各个版本的log，可以加--oneline显示简短信息
git  reflog //简短表示版本log

git  reset  --hard  [hash_value]  //切换到目标哈希（git  reflog打印出来的）的版本
git  reset  --hard  HEAD^         //回退到上一版本
git  reset  --hard  HEAD~n        //回退n个版本

git  stash

git  add  filename  //将filename提交至本地仓库
git  add *.扩展名    //这条命令可以添加同类型的所有文件
git  add  .         //可以探测到新增、修改、删除，并提交至本地仓库

git  diff file     //比较本地与远程仓库上的文件的异同
git  diff HEAD     //比较通过add指令提交的文件与本地工作区的文件的异同
git  diff HEAD^    //比较上一版本提交的文件与本地工作区的文件的异同

git  branch    [分支名]   //创建分支
git  branch    -v         //查看分支情况
git  checkout  [分支名]   //切换到目标分支名
2步合并分支操作----
a)git  checkout  [分支名]  //切换到即将接受合并的分支
b)git  merge     [分支名]  //将分支名（合并目标）合并到当前分支

git工具与远程仓库同步的操作步骤：
先要添加用户配置（告诉git来自谁的commit）
step1:(前提)
  git config --global user.name "Your Name"
  git config --global user.email "you@example.com"
step2:
  git  remote  -v  //查看远程仓库地址信息，如果已添加地址转至stp4,否则step3
step3:
  git  remote  add  origin  [仓库地址]   //添加远程推送的目标仓库地址
  git  remote  -v   //查看远程仓库地址信息是否添加成功
step4:
  git  push  origin  //如何配置一切正常，将弹出github账户、密码登录框验证身份，验证完毕后开始传送。
  
如果执行step4时出现提示
error: src refspec master does not match any.
error: failed to push some refs to 'https://github.com/Risen-Hu/myFirstRepos_test.git(仓库地址)'
可从以下原因进行排除:
1.本地git仓库目录下为空
2.本地仓库add后未commit
3.git init错误
4.是否执行step1。通过git config --global -l查看配置


