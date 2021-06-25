这是一个Notepad readme测试文件
使用git
一、
1.mkdir learngit
2.cd learngit
3 pwd  (显示当前目录)
二、
1.git init  (创建仓库)
2.git add readme.txt  (将文件readme.txt添加到仓库)
3.git commit -m "提交说明"   (把文件提交到仓库)

commit 可以一次提交很多文件 则可以多次add不同的文件

4.git status (查看当前仓库状态)
5.git diff (查看上次readme修改内容) git diff readme.txt

6.修改完文件后 再次将文件添加到仓库 git add 

7.将新添加到仓库的文件提交至仓库 git commit -m "提交简要说明"

三、
1.版本回退

git log (显示从最近到最远的提交日志)
git log [--pretty=online]