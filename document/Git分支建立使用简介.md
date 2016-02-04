#Github提交流程
<br>
##流程
1.对原项目进行fork

并在fork出来的项目中建立一个分支，你可以在该分支上任意修改，如果想将你的修改合并到原项目中时，可以pull request，这样原项目的作者就可以将你修改的东西合并到原项目的主分支上去.
   
 1.假设 A's Github repo 是原来的git上的主项目: github.com/a/project
 
 2.你先fork（可以理解为复制）到你自己的目录下：github.com/you/project

**Note**:*这是github操作*

 3.然后需要clone到本地：

**Note**:* 这是git操作*
 
 4.你修改完代码之后就可以commit 
 
 **Note**:*这是git操作*

 5.然后 push 到 github.com/you/project
 
 **Note**:*这是Git操作。使用该操作让你发送信息给GitHub。Push操作不会自动完成，直到你做了push操作，GitHub才知道你的提交。*

 6.在此分支下进行 pull request 通知原项目的管理者把修改的东西合并到github.com/a/project

 **Note**:*这是GitHub操作，使用此操作可以帮助你和a交流你的修改，并且询问a是否愿意接受你的"pull request"，如果a接受了你的pull request，他将把那些修改拉到自己的仓库。*
 
<br>
## 与原分支同步##
###参照另一篇文章"如何同步fork"
<br>
## 命令行##
你可以参阅廖雪峰老师的网站更好的理解git的使用。

对于git操作常见问题：
可以参阅网站：
<https://coding.net/help/faq/git/git.html>

git命令行 
参阅网站：
<http://www.bootcss.com/p/git-guide/>
