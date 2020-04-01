Github学习笔记

以下是git工具一些常用的指令与本地与远程仓库同步的操作步骤的记录。


git工具的一些指令操作：
git  pull   //同步服务器代码至本地
git  push   //上传代码至服务器（最终操作）
git  staus  //查看本地代码更改情况
git  log    //查看各个版本的log
git  reflog //简短表示版本log

git  reset  --hard  [hash_value]  //切换到目标哈希（git  reflog打印出来的）的版本
git  reset  --hard  HEAD^         //回退到上一版本
git  reset  --hard  HEAD~n        //回退n个版本


git  add  filename  //将filename提交至本地仓库
git  add *.扩展名    //这条命令可以添加同类型的所有文件
git  add  .         //可以探测到新增、修改、删除，并提交至本地仓库

git  diff file.c/file.h  //比较本地与远程仓库上的文件的异同
git  diff HEAD           //比较通过add指令提交的文件与本地工作区的文件的异同
git  diff HEAD^          //比较上一版本提交的文件与本地工作区的文件的异同

git  branch    [分支名]   //创建分支
git  branch    -v         //查看分支情况
git  checkout  [分支名]   //切换到目标分支名
2步合并分支操作----
a)git  checkout  [分支名]  //切换到接受合并的分支
b)git  merge     [分支名]  //将分支名（合并目标）合并到当前分支
