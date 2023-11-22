这是用于自己记录的github的使用方法（纯命令行linux）

1.生成个人令牌
git官网->setting->Devoloper Setting->personal access tokens->tokens(classic)->generator new token->(我会选择永久)

保存生成的密码，这里我假设为abc

2.生成密钥
在linux上执行一下命令：
```bash
ssh-keygen -t rsa -b 4096 -C your_email@example.com
````
然后不断回车，就能在~/.ssh/id_rsa.pub中生成密钥，打开这个文件，复制的内容

进入官网setting->ssh and GPG keys ->new ssh key->将复制的内容填充后生成


3.生成仓库
在github上生成仓库，进入仓库，里面会有如下显示：
```bash
…or create a new repository on the command line
echo "# github-" >> README.md
  git init
  git add README.md
  git commit -m "first commit"
  git branch -M main
  git remote add origin https://github.com/NuaaMtz/github-.git
  git push -u origin main
…or push an existing repository from the command line
git remote add origin https://github.com/NuaaMtz/github-.git
  git branch -M main
  git push -u origin main
```

4.上传
进入需要上传的文件夹内，以此执行:

```
git config --global user.name "username"
git config --global user.email "study@user.com"
git config --global credential.helper store
````

```
git init
git add .
git commit (进入的文件内写上自己要的注释，保存关闭编辑器即可)
git remote add origin git@github.com:NuaaMtz/-.git( 这里的NuaaMtz/-.git需要按照第三步的结果进行替换)
git remote set-url origin https://github.com/NuaaMtz/-.git(同上)
git push -u origin master(第一次需要加上-u,输入git账号，密码输入的是第一步的结果,也就是我假设的abc)

```
除了第一次外，其他时候都不需要在最后一步输入账号密码了（单个仓库）
经过上面的操作，应该已经完成了第一次的整个项目的上传，之后就是每次对自己的代码进行更新后上传操作：
```
git add .
git commit (同上)
git push origin master
```

 对于新手，这样的操作应该已经足够了。如果还需要其他的功能，比如不上传某些文件，回退保本，更改分支之类的，这些功能都建立了上面的步骤都实现后才能实现。


5. 上传第二个仓库的方法
在按照前面的步骤完成第一个仓库的上传之后，如果想要进行第二个仓库上传，只需要按照第四步的以下步骤完成：

```

git init
git add .
git commit (进入的文件内写上自己要的注释，保存关闭编辑器即可)
git remote add origin git@github.com:NuaaMtz/-.git( 这里的NuaaMtz/-.git需要按照第三步的结果进行替换)
git remote set-url origin https://github.com/NuaaMtz/-.git(同上)
git push -u origin master(第一次需要加上-u,输入git账号，密码输入的是第一步的结果,也就是我假设的abc)

```

6.两台电脑管理一个仓库
在完成前面的所有步骤后，在一台新电脑上对同一账号同一仓库进行更新和上传
同样的，你得先把前面的1和2完成，保存密码，假设为abc

6.1 在你需要保存项目的地方克隆你的项目：
```
  git clone https://github.com/NuaaMtz/geant4VscodeSetting.git
```
然后开始修改你的代码

6.2 修改全局变量

```
git config --global user.name "username"
git config --global user.email "study@user.com"
git config --global credential.helper store
````
6.3 上传
因为是克隆下来的，因此不需要初始化，自带了.git

```
  git add .
  git commit 

  git push origin master
```

6.4 更新
当其他的电脑对其更新后，你本地的电脑也需要进行更新。
```
 git push origin master
```
这样就完成了更新


7. 保存密码
!!!! 重要提示：密码需要保存！！！！！（里面的abc的这个密码需要保存，否则在每次）
如果需要自己自动保存密码的话，在第一次输入密码成功上传/更新后，运行下列：
```
  git config --global credential.helper store
```
 之后就可以用了。就算忘了也没关系，再生成一个直接使用就行。



