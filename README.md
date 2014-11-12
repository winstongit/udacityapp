testapp
=======
问题1 生成的ssh秘钥找不到
解决方法：
在~/.ssh目录下
ssh-keygen -t rsa -C "winstongit@gmail.com" 
复制C:\Documents and Settings\Administrator\.ssh中的id_rsa.pub里的key

问题2 Could not open a connection to your authentication agent
解决方法：
eval `ssh-agent -s` 
ssh-add ~/.ssh/id_rsa

问题3 The authenticity of host 'github.com (192.30.252.130)' can't be established.
解决方法：
ssh -T git@github.com
Are you sure you want to continue connecting (yes/no)? yes

git config --global user.name "winstongit"
git config --global user.email "winstongit@gmail.com"

git init
git commit -m "sunshine_homework"
git remote add origin git@github.com:winstongit/Sunshinework.git  //连接远程github项目  

问题4：fatal: remote origin already exists.
解决方法：
git remote rm origin

git push origin master

问题5：fatal: Could not read from remote repository.Please make sure you have the correct access rightsand the repository exists.
解决方法：
github建立对应名称的仓库

$ git push -u origin master
问题6
error: src refspec master does not match any.
error: failed to push some refs to 'https://github.com/winstongit/Sunshinework.git'

这个问题明天再研究。

git commit -m 'initial commit'
git push -u origin master

git commit -m "sunshine_homework new"
git remote rm origin
git remote add origin git@github.com:winstongit/Sunshinework.git
git push -u origin master

You've successfully authenticated, but GitHub does not provide shell access.
----------------------------------------------------------------------------------------------------------------------------------
关于在github建立仓库的正确完整流程总结：
1 安装git及添加信息到github的ssh key
安装Git-1.9.4-preview20140929.exe
ssh-keygen -t rsa -C "winstongit@gmail.com" 
eval `ssh-agent -s` 
ssh-add ~/.ssh/id_rsa
复制id_rsa的内容到https://github.com/settings/ssh
ssh -T git@github.com验证ssh是否成功配置

配置用户信息
git config --global user.name "winstongit"
git config --global user.email "winstongit@gmail.com"


2 在服务器上建立一个空仓库，带一个说明文件


3 克隆到客户端，添加修改并执行以下操作：
git config --global credential.helper wincred 			//保存密码，避免每次推送都输账户和密码
git remote add testapp git@github.com:winstongit/testapp.git 	//连接远程仓库
git commit -m "git add and git commit"  			//提交修改的关键提示
git push -u testapp master 					//推送到远程服务器端

4 添加分支
本地分支
git branch V1
git checkout V1 <-> git checkout master (git branch 查看branch版本)
远程分支
git push branch V1 (git branch -r 查看远程branch版本)

5添加仓库代码
git add .
问题：The file will have its original line endings in your working directory. warning: LF will be replaced by CRLF in Gemfile.
解决方法： 
git config core.autocrlf true
git commit -m "weathercast main code init"
git push -u testapp master

--修改远程仓库的名称