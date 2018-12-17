hello world
cd /d //进入d盘
mkdir gittest //创建gittest文件夹
cd gittest //打开文件夹
vim test.MD //文件夹下创建文件
touch readme.txt//创建文件

git config --global user.name "test name" //配置用户名
git config --global user.email "testemail@gmail.com" //配置邮箱
git init //将文件夹初始化为master
git commit -m"First commit"
git remote add origin https://github.com/xxxxxxx/gittest.git//前面远程仓库的url
git push －u origin master//第一次执行要-u



git status 查询状态 （是否发生变更）
git diff 何处发生了变更
git add < 文件名> 添加到暂存区
git commit -m "说明" 提交到当前分支（即本地的版本库）



git log 列出版本变更（时间上由近及远，head 为当前版本）
git reset -hard HEAD^回退到上一个版本(HEAD^为上个版本，HEAD^^为上上个版本)
也可以 gitreset -hard <commit id>
git reflog 查看命令历史
用git diff HEAD -- readme.txt命令可以查看工作区和版本库里面最新版本的区别




git checkout --<文件名>可以丢弃工作区的修改（把工作区的修改完全放弃）
场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令git checkout -- file。
场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令git reset HEAD <file>，就回到了场景1，第二步按场景1操作。
场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考版本回退一节，不过前提是没有推送到远程库。


rm test.txt 删除本地文件
git rm test.txt
git commit -m "remove test.txt" 两者共用便是在版本库中删除



远程库通信
第1步：创建SSH Key 
	ssh-keygen -t rsa -C "youremail@example.com" 一直回车（不然会出现failed）
	在用户主目录里找到.ssh目录，里面有id_rsa和id_rsa.pub两个文件，这两个就是SSH Key的秘钥对，
	id_rsa是私钥，不能泄露出去，id_rsa.pub是公钥，可以放心地告诉任何人。
第2步：登陆GitHub，打开“Account settings”，“SSH Keys”页面：然后，点“Add SSH Key”，填上任意Title，在Key文本框里粘贴id_rsa.pub文件的内容：
要关联一个远程库，使用命令git remote add origin git@server-name:path/repo-name.git；

关联后，使用命令git push -u origin master第一次推送master分支的所有内容；
此后，每次本地提交后，只要有必要，就可以使用命令git push origin master推送最新修改；

D/Person/E/desktop/Personnal_File/git