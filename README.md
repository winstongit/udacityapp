testapp
=======
����1 ���ɵ�ssh��Կ�Ҳ���
���������
��~/.sshĿ¼��
ssh-keygen -t rsa -C "winstongit@gmail.com" 
����C:\Documents and Settings\Administrator\.ssh�е�id_rsa.pub���key

����2 Could not open a connection to your authentication agent
���������
eval `ssh-agent -s` 
ssh-add ~/.ssh/id_rsa

����3 The authenticity of host 'github.com (192.30.252.130)' can't be established.
���������
ssh -T git@github.com
Are you sure you want to continue connecting (yes/no)? yes

git config --global user.name "winstongit"
git config --global user.email "winstongit@gmail.com"

git init
git commit -m "sunshine_homework"
git remote add origin git@github.com:winstongit/Sunshinework.git  //����Զ��github��Ŀ  

����4��fatal: remote origin already exists.
���������
git remote rm origin

git push origin master

����5��fatal: Could not read from remote repository.Please make sure you have the correct access rightsand the repository exists.
���������
github������Ӧ���ƵĲֿ�

$ git push -u origin master
����6
error: src refspec master does not match any.
error: failed to push some refs to 'https://github.com/winstongit/Sunshinework.git'

��������������о���

git commit -m 'initial commit'
git push -u origin master

git commit -m "sunshine_homework new"
git remote rm origin
git remote add origin git@github.com:winstongit/Sunshinework.git
git push -u origin master

You've successfully authenticated, but GitHub does not provide shell access.
----------------------------------------------------------------------------------------------------------------------------------
������github�����ֿ����ȷ���������ܽ᣺
1 ��װgit�������Ϣ��github��ssh key
��װGit-1.9.4-preview20140929.exe
ssh-keygen -t rsa -C "winstongit@gmail.com" 
eval `ssh-agent -s` 
ssh-add ~/.ssh/id_rsa
����id_rsa�����ݵ�https://github.com/settings/ssh
ssh -T git@github.com��֤ssh�Ƿ�ɹ�����

�����û���Ϣ
git config --global user.name "winstongit"
git config --global user.email "winstongit@gmail.com"


2 �ڷ������Ͻ���һ���ղֿ⣬��һ��˵���ļ�


3 ��¡���ͻ��ˣ�����޸Ĳ�ִ�����²�����
git config --global credential.helper wincred 			//�������룬����ÿ�����Ͷ����˻�������
git remote add testapp git@github.com:winstongit/testapp.git 	//����Զ�ֿ̲�
git commit -m "git add and git commit"  			//�ύ�޸ĵĹؼ���ʾ
git push -u testapp master 					//���͵�Զ�̷�������

4 ��ӷ�֧
���ط�֧
git branch V1
git checkout V1 <-> git checkout master (git branch �鿴branch�汾)
Զ�̷�֧
git push branch V1 (git branch -r �鿴Զ��branch�汾)

5��Ӳֿ����
git add .
���⣺The file will have its original line endings in your working directory. warning: LF will be replaced by CRLF in Gemfile.
��������� 
git config core.autocrlf true
git commit -m "weathercast main code init"
git push -u testapp master

--�޸�Զ�ֿ̲������