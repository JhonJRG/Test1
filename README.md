 
 # 盖世英雄到来！

 #### 以下是复习发现的重点

 ##### 注意： 
 
  1 .ssh是秘钥文件，是在本地用户名下的隐藏文件夹，如果不刷机不会消失。id_rsa.pub是公钥文件 id_rsa是私钥文件。最好备份一个位置。
  
  2 .git文件只在每个仓库里存在，可以看作是每个仓库的操作及变动日志，clone仓库要单独，暂时没看到能一下子clone的
  
  3 注意把本地文件夹变成仓库远程推送如何操作，git init命令慎用
  
  4 重要语句
  
    ```git remote -v```  查看本地库里的远程库地址（这个地址是可变的，只要是支持远程仓库的站点都可以生成地址，都能本地推送到任何远程库）```
    ```git push -f origin master```  慎用：强制推送，会覆盖别人的代码
  暂时到这里
