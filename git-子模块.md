1.ʹ��git�������ֱ�����Submodule:

    git submodule add git@github.com:jjz/pod-library.git pod-library

    ����������ʹ���������Submodule

    git add .gitmodules pod-ibrary

    git commit -m "pod-library submodule"

    git submodule init

2.�޸���ģ��
    
    ������ģ��,�޸�,�鿴״̬
    
    git status
    
    �ύ�޸�
        
        git commit -a -m'test submodule'

    ����

      git push
    
    �ص���Ŀ¼,�ύSubmodule�ڸ���Ŀ�еı䶯

    git statuson branch master

    �ύ��ģ���ڸ�ģ���еı䶯
    
    git commit -m'update submodule'

    ���͵�����Ŀ�޸ĵ�Զ��

    git push

    没有修改成功