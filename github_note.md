Github学习笔记

以下是git一些常用的指令与本地与远程仓库同步的操作步骤的记录。


git的一些指令操作：
git  pull   //同步服务器代码至本地
git  push   //上传代码至服务器（最终操作）
git  staus  //查看本地代码更改情况
git  log    //查看各个版本的log

git  add  filename  //将filename提交至本地仓库
git  add *.扩展名    //这条命令可以添加同类型的所有文件
git  add  .         //可以探测到新增、修改、删除，并提交至本地仓库

git  diff file.c/file.h  //比较本地与远程仓库上的文件的异同
git  diff HEAD           //比较通过add指令提交的文件与本地工作区的文件的异同
git  diff HEAD^          //比较上一版本提交的文件与本地工作区的文件的异同
