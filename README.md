# 注意：此仓库仅仅为一个测试git工具功能的仓库！！

# Github学习笔记

以下是git工具一些常用的指令与本地与远程仓库同步的操作步骤的记录。


**git工具的一些指令操作：===============================================================**<br>
git  pull   //同步服务器代码至本地<br>
git  push   //上传代码至服务器(最终操作)<br>
git  staus  //查看本地代码更改情况<br>
git  log    //查看各个版本的log，可以加--oneline显示简短信息<br>
git  reflog //简短表示版本log<br>
<br>
git  reset  --hard  [hash_value]  //切换到目标哈希（值为git  reflog打印出来的）的版本<br>
git  reset  --hard  HEAD^         //回退到上一版本<br>
git  reset  --hard  HEAD~n        //回退n个版本<br>
<br>
git  stash<br>

git  add  filename  //将filename提交至本地仓库<br>
git  add *.扩展名    //这条命令可以添加同类型的所有文件<br>
git  add  .         //可以探测到新增、修改、删除，并提交至本地仓库<br>

git  diff file     //比较本地与远程仓库上的文件的异同<br>
git  diff HEAD     //比较通过add指令提交的文件与本地工作区的文件的异同<br>
git  diff HEAD^    //比较上一版本提交的文件与本地工作区的文件的异同<br>
<br>
git  branch    [分支名]   //创建分支<br>
git  branch    -v         //查看分支情况<br>
git  checkout  [分支名]   //切换到目标分支名<br>
2步合并分支操作----<br>
a)git  checkout  [分支名]  //切换到即将接受合并的分支<br>
b)git  merge     [分支名]  //将分支名（合并目标）合并到当前分支<br>
**=======================================================================================**<br>

**git工具与远程仓库同步的操作步骤：---------------------------------------------------------------------------------**<br>
先要添加用户配置（告诉git来自谁的commit）<br>
step1:(前提)<br>
  git config --global user.name "Your Name"<br>
  git config --global user.email "you@example.com"<br>
step2:<br>
  git  remote  -v  //查看远程仓库地址信息，如果已添加地址转至stp4,否则step3<br>
step3:<br>
  git  remote  add  origin  [仓库地址]   //添加远程推送的目标仓库地址<br>
  git  remote  -v   //查看远程仓库地址信息是否添加成功<br>
step4:<br>
  git  push  origin  //如何配置一切正常，将弹出github账户、密码登录框验证身份，验证完毕后开始传送。<br>
  <br>
如果执行step4时出现提示<br>
error: src refspec master does not match any.<br>
error: failed to push some refs to 'https://github.com/Risen-Hu/myFirstRepos_test.git(仓库地址)'<br>
<br>
解决方法：<br>
1.到本地仓库目录下查看是否有.git文件，若无，先到控制面板打开文件夹选项  打开隐藏文件和文件夹显示，仍然没有则执行命令git init;<br>
2.看.git文件夹下是否有之前提交的文件，若无则重新 git commit (如果之前已执行git add，没有就要重新 add commit);<br>
3.确认是否已执行step1。通过git config --global -l查看配置;<br>
**---------------------------------------------------------------------------------------------------------------------**<br>

