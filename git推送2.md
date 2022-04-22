### git推送

```
 1.git init
 2.git add 要添加的文件名
 3.git commit -m  '描述内容'
 4.git log
 5.git remote add origin git@github.com:changbotong/xiangmu-.git
 6.git remote -v
 7.git pull origin master
 9.git push origin master -u
 8.git pull --rebase origin master(如果出现下面第一个报错才执行这个，之后到第二个，在执行第7条)
 
```

![1650545392011](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\1650545392011.png)

![1650545478504](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\1650545478504.png)

### git删除

````
1.git log 查看commit记录
````

![1650545813750](C:\Users\huawei\AppData\Roaming\Typora\typora-user-images\1650545813750.png)

```
2、首先找到要删除提交之前的一次提交的commit c46526d353d98992178ed2629f0e3c999fbf5642

3、执行命令git rebase -i (id)
4、编辑文件，将要删除的commit之前的单词改为drop ，然后按照提示保存退出（Ps： wq 写入保存  q! 退出不保存）

5、此已经删除了指定的commit，可以使用git log查看下，执行以下命令推送到远程仓库，没有影响后面的提交
```

