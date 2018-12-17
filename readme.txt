hello world
cd /d //进入d盘
mkdir gittest //创建gittest文件夹
cd gittest //打开文件夹
vim test.MD //文件夹下创建文件
touch readme.txt//创建文件













git config --global user.name "test name" //配置用户名
git config --global user.email "testemail@gmail.com" //配置邮箱
git init //将文件夹初始化为master
git add test.MD //
git commit -m"First commit"
git remote add origin https://github.com/xxxxxxx/gittest.git//前面远程仓库的url
git push －u origin master//第一次执行要-u
