##ע��
 1 ����Ȼ�������ϱ��زֿ��������ļ��Ƿ���һ��ģ����Ƿ�֧֮���ǻ����ܷ����Լ�������
 2 ���ڱ��ص�ÿ��commit������index�ģ��ϴ���github���Բ�����ôƵ�������������м�¼��
 3�� ��github���޸�����Ŀ�󣬻����Ժ��Ǻͱ���һ�𿪷�����Ҫ��git pull origin ��master���������£�
	�ٽ���git push -u origin master ������ȷ�ύ���룬�����pull���ύ��ע��ʧ�ܵ�
4����github���޸��ļ��������������ı仯����ʱ��û��pull���޸��ļ���commitҲ�ǻ���push��ʱ����鷳
	����ǣ���github���޸��˾��ڱ���pull֮�����޸��ļ�����һ�����˻���Ҳ��
5�������˳�ͻ���Ӷ��޷��Զ�merge��
	git pull �Է��ķ�֧
	git checkout �Լ��ķ�֧
	git merge --no-ff �Է��ķ�֧
	git push ���Լ���Դ+��֧��origin master
##��git commit��
git commit �����������VI�༭��
	��һ�У���һ�����ּ����ύ�ĸ�������
	�ڶ��У�����
	�����У��������ĵ�ԭ�����ϸ����
	ʹ�����淽���ر��˳�
##��git reset���÷�ʽ��
###��1�����ع�add����
		edit  (1)
		git add a.txt b.txt
		���ʼ�(2)
		git reset(3) 
		git pull URL
	1.1 �༭�������ļ��������ӵ���index
	1.2 �����ʼ�������ĳ��Ҫ��pull����һЩ�ı���Ҫ��merge ����
	1.3 Ȼ�����Ѿ���index���ı��ˣ���Ϊ��ǰ��index �� HEAD commit��ƥ���ˣ�������֪��������pull�Ķ�������Ӱ��
		��a.txt �� b.txt����������revert�������ļ��ĸı䣬revert����Щ�ı���Ȼ��working directory�У������Ҫִ��git reset
	1.4 Ȼ��ִ����pull�� �Զ�merge�������ļ���Ȼ��working directory��
####��2�����ع����һ��commit
		git commit ...
		git reset --soft HEAD^(1)
		edit (2)
		git commit -a -c ORIG_HEAD(3)
	2.1 ���ύ���㷢���ύ�Ĵ��벻���ƣ���Ҫ���±༭һ�£�ִ�� 1 �����working directory��reset֮ǰһ���������ı�
	2.2 ��working tree�µ��ļ����޸�
	2.3 Ȼ��ʹ��reset֮ǰ�Ǵ�commit��ע�͵������Ϣ�������ύ��ע���ϵ�HEAD�ᱻ���ݵ��ļ�.git/ORIG_HEAD�У������о�������������ϵ������Ϣ
		-a ��ʾ�Զ������е��޸ĵĺ�ɾ�����ļ����Ž� stage area������Ϊ��������δ��git���ٵ��ļ�����Ӱ�죩
		-c ��ʾ ���Ѿ��ύ��commit�����е���Ϣ������ε��ύ
	����������ǣ������и��ĵ��ļ����뵽stage area�У���ʹ���ϴε��ύ��Ϣ���ύ
####��3�����ع�������ε�commit�������ӵ�һ���½��ķ�֧��ȥ
		git branch myth/test (1)
		git reset --hard HEAD^3 (2)
		git checkout myth/test (3)
	3.1 ���Ѿ��ύ�˺ü���commit�����Ǿ��ò�����������ƣ����������ӵ�master��֧�ϣ������ڵ�ǰHEAD����һ���·�֧
	3.2 Ȼ��ع�����������ύ��ɾ����
	3.3 �л����·�֧�Ͼ��ܶԴ��������ɫ�ˣ��ȴ�֮���merge
####��4��������ɾ���������
		commit git reset --hard HEAD~3
####��5�����ع�merge��pull����
		git pull URL (1)
		git reset --hard (2)
		git pull .topic/branch (3)
		git reset --hard ORIG_HEAD (4)
	5.1 ��origin��������һЩ���£����ǲ����������ͻ����ʱ��ûʱ��ȥ�����Щ��ͻ�������볷��pull�������ȴ��Ժ���pull
	5.2 ����pull���������˳�ͻ���������pull�����ĸı���δ�ύ����Ȼ��stage area�У���������� git reset --hard �� git reset --hard HEAD Ч��һ��
			���������Щʹindex��working directory���׵Ķ���
	5.3 ��topic/branch �ϲ�����ǰ��branch�����û�г�ͻ�����Һϲ���ĸ����Զ��ύ
	5.4 ���Ǵ�ʱ�־��ý�topic/branch�ϲ�������̫���ˣ������ع�merge������ִ��4���  ֮ǰ��˵����git reset�����ᱸ��һ��ORIG_HEAD��
			pull��merge����ͬ���ᣬΪ�˻ع�����
####��6�����ڱ���Ⱦ��working tree�лع�merge����pull
		git pull (1)
		git reset --merge ORIG_HEAD (2)
	6.1 ��ʹ�ڱ����Ѿ�������tree��������index�ı仯��Ҳ���Է��ĵ�pull��ǰ������֪����Ҫpull�����ݲ��Ḳ�����working tree�е�����
	6.2 git pull ֮���㷢�����pull�������⣬��Ҫ�������������ʹ��git reset --hard ORIG_HEADҲ���ԣ��������ɾ��add�Ĵ���
			ʹ�� git reset --merge ORIG_HEAD �Ϳ��Ա���ع�����ʱɾ��add�Ĵ���
####��7�������жϵĹ�������
		��ʵ�ʿ����о����������������Σ������ڿ���һ�����feature����ʱ����һ��������BUG��Ҫ�޸�������Ŀǰ��working tree �е����ݻ�������commit
		�������ֱ����л��������branchȥ fix bug
		git checkout feature;
		�����
		git commit -a -m "��ʱ�ж�OO" (1)
		git checkout master 
		�޸�bug
		git commit ;
		git checkout feature
		git reset --soft HEAD^ #go back to OO's state (2)
		git reset (3)
	7.1 ������ʱ�ύ�����ӵ�ע��
	7.2 ���resetɾ����OO��commit�����Ұ�working tree���ó��ύOO֮ǰ��״̬
	7.3 ��ʱ����index����Ȼ����OO�ύʱ������uncommit changes��git reset ��������index��Ϊ��δ�ύʱ��״̬������֮��Ĺ���
####��8����Reset һ���������ļ�
		git reset -- a.txt (1)
		
git commit -am "Commit files inindex"  (2)
		git add a.txt  (3)
	8.1 ���ļ�������index��ȥ��
	8.2 ��index�е��ļ��ύ
	8.3 �ٴ����ӻ��ļ�

####��9��������working tree ���Ҷ���һЩcommit
		git tag start
		git checkout -b branch 1
		��д
		git commit .... (1)
		��д
		git checkout -b branch2 (2)
		git reset --keep start (3)
	9.1 ����ǰ�branch1�еĸı��ύ��
	9.2 ��ʱ���֣�֮ǰ���ύ���������branch����ʱ���½���branch2�����л����˸�branch��
	9.3 ��ʱ�����ʹ��reset --keep ����start֮���commit����������Ǳ�����working tree�Ĳ���

##��VI�༭����ʹ�á�

 git ��pull���ߺϲ���֧��ʱ����ʱ�������� VI�༭�� ��״̬  ���Բ���(ֱ������3,4��)
 ���Ҫ������͵Ļ�����Ҫ:

	1.��������ĸ i ����insertģʽ
	2.�޸����������л�ɫ�ϲ���Ϣ,���Բ��޸�
	3.���������Ͻ�"Esc"
	4.����":wq",ע����ð��+wq,���س������� 
	Ctrl + Z +Z Ҳ���˳�

##��GitHub �� 

��Markdown�﷨��:  
	@�û����� @��֯�� ��#��� �����ӵ��òֿ��Ӧ��Issue��� ��
	ͨ�� �û���/�ֿ��� #��� ��ָ���ֿ��ָ��Issue
����Bash��GitHub����������
	1.��GItHub������SSH key�� ��һ������
	2.$ssh-keygen -t rsa -C "Kuangchengping@outlook.com" �س� 
	3.�������� ad14293366
	4.����SSH $ssh -T git@github.com  ����yes ���� ����  ****


#------Git Bash�µĲ���------
###��git��ʼ���� 
	$git config --global user.name " "
	$git config --global user.email " "
	$git config --global color.ui  auto 
	
###�������ļ�����������ʱ������  .gitingnore ���ļ������ļ��������� :
		test.txt  ���Ը��ļ�
		*.html  ��������HTML�ļ�
		*[o/a]  ��������o��a��׺���ļ�
		!foo.html  �����Ը��ļ�

####��¡��Ŀ�� $git clone URL 

##���ӿհ׽����ֿ⣺��

	1.����GitHub�ϴ���һ���ֿ⣬����ѡInitialize...��ԭ���ǵȻ���Զ�ֿ̲⻹��pullһ�²���push��
	2.����ĳ���вֿ��£����Ǹ�Ŀ¼������Git Bash
		2.1 mkdir ���� ����һ���ļ��У���ú�Զ�̵Ŀ�ͬ��
		2.2 git init ��ʼ��������  .git  ����ļ��� touch һ��README.md
		2.3 git remote add origin master URL ����Զ�ֿ̲�
		2.4 git push -u origin master �����û��������루����Ϊû�����νڵ�Ͱ���ʾ�����������ʼ�ڵ㼴�ɣ�

#��������� 

	git touch file1 file2  �½������ļ�
	echo "  ">>file1  �޸��ļ�file1
	git rm �ļ���  �� ɾ���ļ���������
	vi �ļ���  �� ʹ��VI�༭�����½��ļ�  Ҫ�ر�ע�����˳�

	git commit -am " " �ӻ����ύ���м�Ҫ�� commit ���� push��
	git diff  �� �鿴��ǰ���������ݴ����Ĳ��
	git diff --cached ���鿴�������ļ��޸ĵĺۼ��ͶԱ� ����q �˳�
	git log --graph ���鿴��ͼ�λ����ύ��־ ����q�˳�
	git banrch ��֧�� �������µķ�֧
	git branch -a �鿴��ǰ��֧��Ϣ
	git checkout -b������һ����֧���������л�
	git checkout -b feature-D origin/feature-D �½�һ����֧������ͬ�������Ǹ�Զ�ֿ̲�ķ�֧
	git pull ����ȡ���µ�Զ�ֿ̲��֧
	git pull origin feature-D ��ֻ�ѱ��ص�feature-D��֧���µ�����
	git merge--no-ff feature-D ����ǰ��֧���֧feature-D �ϲ�
	git reset --hard ��ϣֵ�����ݿ�Ļع������Ƶ�
	git reflog �鿴�ֿ�Ĳ�����־
	git mv -k oldName  newName :�����ļ�����

	usage: git [--version] [--help] [-C <path>] [-c name=value]
           [--exec-path[=<path>]] [--html-path] [--man-path] [--info-path]
           [-p | --paginate | --no-pager] [--no-replace-objects] [--bare]
           [--git-dir=<path>] [--work-tree=<path>] [--namespace=<name>]
           <command> [<args>]
###API�ĵ�
These are common Git commands used in various situations:

start a working area (see also: git help tutorial)
   clone      Clone a repository into a new directory
   init       Create an empty Git repository or reinitialize an existing one

work on the current change (see also: git help everyday)
   add        Add file contents to the index
   mv         Move or rename a file, a directory, or a symlink
   reset      Reset current HEAD to the specified state
   rm         Remove files from the working tree and from the index

examine the history and state (see also: git help revisions)
   bisect     Use binary search to find the commit that introduced a bug
   grep       Print lines matching a pattern
   log        Show commit logs
   show       Show various types of objects
   status     Show the working tree status

grow, mark and tweak your common history
   branch     List, create, or delete branches
   checkout   Switch branches or restore working tree files
   commit     Record changes to the repository
   diff       Show changes between commits, commit and working tree, etc
   merge      Join two or more development histories together
   rebase     Forward-port local commits to the updated upstream head
   tag        Create, list, delete or verify a tag object signed with GPG

collaborate (see also: git help workflows)
   fetch      Download objects and refs from another repository
   pull       Fetch from and integrate with another repository or a local branch
   push       Update remote refs along with associated objects

'git help -a' and 'git help -g' list available subcommands and some
concept guides. See 'git help < command>' or 'git help < concept>'
to read about a specific subcommand or concept.

##��Ŀǰʹ�õķ����� 

	1.��GitHub���½�һ����Ŀ������ѡ��ʼ����������URL
	2.��eclipse�½���Ŀ��git������ĳ�ļ�����
	3 Ȼ����eclipse������git remote
	4.commit -��push ���
	5.��Git Bash ʹ���������ٲ鿴һ�£���Ȼ��ʱ������Ƚ���֣�����һ�㲻����ɶ����
=========ִ����1��2�����ֱ��
git remote add origin https://github.com/Kuangcp/StudentManager.git
git push -u origin master
========���ߣ�
echo "# StudentManager" >> README.md
git init
git add README.md
git commit -m "first commit"
git remote add origin https://github.com/Kuangcp/StudentManager.git
git push -u origin master