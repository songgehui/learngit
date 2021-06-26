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
1.当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时
修改文件后 还没有提交到暂存区
git checkout -- file(要撤销修改的文件名)
2.当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。
修改文件后 提交到了暂存区
git reset HEAD <文件名>
3.已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。

六、删除文件
一是确实要从版本库中删除该文件，那就用命令
git rm删掉，并且git commit

如 rm test.txt
   git add .
   git commit -m "删除test"
   
另一种情况是删错了，因为版本库里还有呢，所以可以很轻松地把误删的文件恢复到最新版本
git checkout -- test.txt

七、远程仓库（github 仓库）
把已有本地仓库与远程仓库github关联,然后把本地内容推送到GitHub仓库
1.在本地learngit仓库下运行命令
git remote add origin git@github.com:michaelliao(自己的GitHub账户名)/learngit.git

远程库的名字就是origin

2.把本地库的所有内容推送到远程库上
git push -u origin master（第一次推送）
git push origin master

八、 先创建远程库 再从远程库克隆 
git clone 克隆一个本地库 
git clone git@github.com:michaelliao[账户名]/gitskills.git
cd gitskills
ls

九、分支管理
1.创建分支,然后切换到dev分支
git checkout -b song <==> git branch song  git checkout song


git branch 查看当前分支

1)在分支song操作文件
2)提交修改文件 git add readme.txt
git commit -m "说明"

3)切换回主分支master
git checkout master

把song分支的工作成果合并到master分支上
git merge song

SWITCH
1)创建并切换到新的dev分支
git switch -c dev
2)直接切换到已有的master分支
git switch master




