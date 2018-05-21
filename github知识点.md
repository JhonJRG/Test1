 ### 以下是复习发现的重点

 #### 注意： 
 
  1 .ssh是秘钥文件，是在本地用户名下的(隐藏)文件夹，如果不刷机不会消失。id_rsa.pub是公钥文件 id_rsa是私钥文件。最好备份一个位置。
  
  2 .git文件只在每个仓库里存在，可以看作是每个仓库的操作及变动日志，clone仓库要单独，暂时没看到能一下子clone的
  
  3 注意把本地文件夹变成仓库远程推送如何操作，先git init，再push
  
 4 本地仓库想要推送之前先git pull一下，然后在把自己修改的东西添加完，再push
   
  5 重要语句
  
    ````git remote -v````  查看本地库里的远程库地址（这个地址是可变的，只要是支持远程仓库的站点都可以生成地址，都能本地推送到任何远程库）
    
    ```git remote remove abc``` 移除某个地址

    ```git status``` 可以列出当前目录所有还没有被git管理的文件和被git管理且被修改但还未提交(git commit)的文件

    ```git push -f origin master```  慎用：强制推送，会覆盖别人的代码
    
    ```git remote set-url origin git@xxx.qq.com/Test1.git``` 修改远程推送地址，例如https地址换成ssh地址
    
    ```git remote rename gitlab newname``` 修改远程库的名字（疑）
    
  6 如何把本地空文件夹变成仓库并推送到远程仓库 关键是以下这两句

 （1）```git init``` （获取.git文件）

 （2）```git remote add origin git@github.com:JhonJRG/Test2.git``` （推送给谁）
 
 （3）```git push origin master```（注意：origin指的就是```git@github.com:JhonJRG/Test2.git```这个地址，起了个名字而已）

  *ps:github上新建空文件夹，本地新建空文件夹并推送至github，重要的语句是git init。注意git init是初始化.git信息，所以只适用于本地空文件夹推送至远程仓库，切勿在本地仓库内滥用，否则会删除掉以往操作信息及状态*
            
   7 我们设置master对应远程仓库的master分支

     ```git branch --set-upstream master origin/master```    
      
   这样在我们每次想push或者pull的时候，只需要输入 ```git push``` 或者 ```git pull```即可

   在此之前，我们必须要指定想要push或者pull的远程分支 ```git push origin master``` ```git pull origin master```
   
 
   **分支操作（分支操作可以将代码线上预览测试如无问题可以合并到master上）**

 - 分支的dev和master的关系可以认为：master属于线上预览的东西，dev属于在开发的东西。一个是样品，一个是草稿（切换不同的分支显示不同的文件内容）   
 - 查看所有分支            ```git branch -a``` （绿色代表本地分支，红色代表远程分支  * 代表当前所处分支）
 - 创建本地库dev（开发）分支  ```git branch dev```   
 - 切换到dev分支             ```git checkout dev```
 - 切换回master              ```git checkout master```
 - 推送到origin地址的dev分支  ```git push origin dev```
 - 合并  ```git merge dev``` （在master状态下，把dev的东西merge（合并）到master上）
   
 - 冲突：指的是另一个人clone文件并改变了文件而你没有pull也改了信息并上传，手动更改文件并push即可（猜测因为提交时间点的不同及时pull了也会有冲突）
 - 指定 git pull合并（自动合并） ```git pull origin master```
 
  **新增NEW**
  
 - 更改远程分支的名字  ```git remote rename ceshifork fork_dev```
 - 删除远程分支      ```git remote remove fork_dev```
 - 新建远程分支     ```git remote add dev_fetch git@github.com:JhonJRG/Web-Developer.git```
 - 删除本地分支    ```git branch -d dev

  **新知new**
  
  - 分支分远程和本地，本地的不同分支对应不同远程分支
  
    ```git pull(push) origin master```  ```git pull(push) dev_remote dev``` 
    
    注意 pull或push在不同分支要分清，例如本地主分支pull/push远程主分支，本地开发分支pull/push远程开发分支
    
    
    
