# git�ķ�Χ
git config --local 
git config --global
git config --system

# git ��ǰ�ļ��е�����
git config --local user.name fanglin_yu
git config --local user.email fanglin_yu@163.com



# add �����Ѿ���git���������µĸ����ļ�
git add -u 

# ���鿴��ǰ��֧log
git log --oneline 

# ���鿴��ǰ��֧����4��log
git log --oneline -n4

# ���鿴���з�֧log
git log --oneline --all

# �鿴���з�֧log�������汾��ʷ
git log --oneline --all --graph


# �鿴git���ļ�����
git cat-file -t/-p
## -t �ļ����ͣ�tag,commit,tree��blob
## -p ��� -t��ѯ���ļ�����Ϊtag����ʹ��-p��ѯ��������tag��Ӧ�����͵����ݣ�����object,type,tag name,tagger��
	  ��� -t��ѯ���ļ�����Ϊcommit����ʹ��-p��ѯ�������Ǳ����ύ��Ӧ��tree�������ύ��parent�������ύ��author�����ε�committer
	  ��� -t��ѯ���ļ�����Ϊtree����ʹ��-p��ѯ���������ļ��б�
	  ��� -t��ѯ���ļ�����Ϊblob����ʹ��-p��ѯ���������ļ�����
	  

# ����ͷָ��
1. git checkout xxxx (���ڷ���ͷָ���״̬)
2. �޸��ļ���add��git��commit �õ�һ��uuid
3. �Ƿ���Ҫ���浱ǰ�޸ĵ��ļ���ĳ����֧
	1. �� -> git branch ��֧���� ��2���õ���uuid���������
	2. �� -> ������ᣬgit�ᵱ��������

# ɾ����֧ -d��ͨɾ����-Dǿ��ɾ��
git branch -d/-D ��֧����

# �޸ĵ�ǰ��֧���һ��commit��message
git commit --amend

# �޸ĵ�ǰ��֧�Ͼɵ�commit��message
1. git rebase -i ��Ҫ����uuid��parent��uuid
2. ѡ���������
	p,pick  ʹ��commit
	r,reword  ʹ��commit,���Ǳ༭commit��message
	e,edit ʹ��commit,����ͣ�����޸�
	s,squash ʹ��commit,���Ǻϲ�������commit��
	
# �鿴�ݴ�����HEAD�ļ�����
git diff --cached

# �鿴�������ݴ����ļ�����
git diff

# �鿴�������ݴ���ָ���ļ�����
git diff -- �ļ�λ�ã�ע�⣺--���ļ�λ��֮���пո�

# �ݴ����ָ���HEAD
git reset HEAD 

# �ݴ����ָ���HEAD  ָ���ļ�
git reset HEAD -- filename

# ���������ļ��ָ����ݴ���һ��
git checkout -- filename 

## �ݴ����仯 reset

## �������仯 checkout


# �����������commit Σ�գ�����
git reset --hard uuid

# �鿴������֧֮��Ĳ���
git diff ��֧1/commit2 ��֧2/commit2  -- filename

# ɾ���ļ�
git rm filename

# �ݴ��ļ�
git statsh 
# �鿴�ݴ��ļ�
git stash list

# ȡ���ݴ��ļ�
## 1. git stash apply  �ָ��ļ����������������ļ��� stash list
## 2. git stash pop    �ָ��ļ�����������ɾ���ļ�