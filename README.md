testapp
=======
1 服务器建立仓库 ，客户端推送尝试
git commit -m 'initial commit'
git remote add origin git@github.com:winstongit/testapp.git
git push -u origin master

失败

2应该是没有添加关联远程仓库

git remote add testapp git@github.com:winstongit/testapp.git
git push -u testapp master

git config --global credential.helper wincred
没解决每次都要输密码的问题。


git commit -m "git add and git commit"