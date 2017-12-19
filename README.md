 #### 以下是复习发现的重点

 ##### 注意： 
 
  1 .ssh是秘钥文件，是在本地用户名下的隐藏文件夹，如果不刷机不会消失。id_rsa.pub是公钥文件 id_rsa是私钥文件。最好备份一个位置。
  
  2 .git文件只在每个仓库里存在，可以看作是每个仓库的操作及变动日志，clone仓库要单独，暂时没看到能一下子clone的
  
  3 注意把本地文件夹变成仓库远程推送如何操作，先git init，再push
  
  4 本地仓库想要推送之前先git pull一下，然后在把自己修改的东西添加完，再push
  
  5 重要语句
  
    ````git remote -v````  查看本地库里的远程库地址（这个地址是可变的，只要是支持远程仓库的站点都可以生成地址，都能本地推送到任何远程库）
    
    ```git remote remove abc``` 移除某个地址

    ```git status``` 可以列出当前目录所有还没有被git管理的文件和被git管理且被修改但还未提交(git commit)的文件

    ```git push -f origin master```  慎用：强制推送，会覆盖别人的代码
    
    ```git remote set-url origin git@xxx.qq.com/Test1.git``` 修改远程推送地址，例如https地址换成ssh地址
    
    ```git remote rename gitlab newname``` 修改远程库的名字
    
    
    
   6 我们设置master对应远程仓库的master分支

   
    >      git branch --set-upstream master origin/master

      这样在我们每次想push或者pull的时候，只需要 输入git push 或者git pull即可。

      在此之前，我们必须要指定想要push或者pull的远程分支。

      git push origin master

      git pull origin master
   
   
   
   **分支操作（分支操作可以将代码线上预览测试如无问题可以合并到master上）** 
   
     分支的dev和master的关系可以认为：master属于线上预览的东西，dev属于在开发的东西。一个是样品，一个是草稿（切换不同的分支显示不同的文件内容）
