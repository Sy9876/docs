# docs

##添加sshkey到github的方法:
1. 在客户机生成key, 
-C中是你在github账户中关联的邮箱, 
-f用于指定生成的密钥文件名
```
ssh-keygen -t rsa -C "user@example.com" -f /home/user/.ssh/id_rsa_github
```

2. 进入github, edit profile, 进入ssh key, 选new ssh key, 
把刚才生成的id_rsa_github.pub的内容贴近去.

测试:
```
ssh -T git@github.com
```

3. 由于git命令中不能指定要用的sshkey, 所以需要在.ssh/config中配置一下:
```
Host github.com
  Hostname github.com
  User git
  IdentityFile ~/.ssh/id_rsa_github
```

