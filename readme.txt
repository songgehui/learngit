这是一个Notepad readme测试文件
使用git
安装
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
1.版本回退 a--b

git log (显示从最近到最远的提交日志)
git log [--pretty=online]

git reset -- hard HEAD^ (回退到上个版本)  ==>穿梭前（b-->a）
		  -- hard HEAD^^(回退到上上个版本)
		  -- hard HEAD~100(回退到往上100个版本)
		  -- hard commit id号（回退到指定版本 根据id号）
		  
git reflog (查看命令历史，以便确定要回到未来的哪个版本) ==>重返未来 （a-->b）

四、
1.工作区 Working Directory
如：learngit
2.版本库 repository
.git

创建版本库时 Git自动创建了唯一一个master分支 所以git commit 就是往master分支上提交

git diff HEAD -- readme.txt命令可以查看工作区和版本库里面最新版本的区别

五、
撤销修改
1.修改文件后 还没有提交到暂存区
git checkout -- file(要撤销修改的文件名)
2.修改文件后 提交到了暂存区
git reset HEAD <文件名>