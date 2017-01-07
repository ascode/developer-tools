##Testing which key you are sending
You can test which user account your agent presents to Bitbucket using the ssh-add command:  
$ ssh -T git@bitbucket.org   
conq: logged in as atlassian_tutorial.  

##生成ssh key
ssh-keygen -t rsa -C "ascode@msn.cn"


ssh是一种网络协议，用于计算机之间的加密登录。ssh原理及应用可参考：  

SSH原理与运用（一）：远程登录   

生成ssh key步骤  

##这里以配置github的ssh key为例：  
###1. 配置git用户名和邮箱  

git config user.name "用户名"  
git config user.email "邮箱"  
在config后加上 --global 即可全局设置用户名和邮箱。  

###2. 生成ssh key

ssh-keygen -t rsa -C "邮箱"
然后根据提示连续回车即可在~/.ssh目录下得到id_rsa和id_rsa.pub两个文件，id_rsa.pub文件里存放的就是我们要使用的key。

###3. 上传key到github

clip < ~/.ssh/id_rsa.pub
复制key到剪贴板
登录github
点击右上方的Accounting settings图标
选择 SSH key
点击 Add SSH key
###4. 测试是否配置成功

ssh -T git@github.com
如果配置成功，则会显示：
Hi username! You’ve successfully authenticated, but GitHub does not provide shell access.

##解决本地多个ssh key问题
有的时候，不仅github使用ssh key，工作项目或者其他云平台可能也需要使用ssh key来认证，如果每次都覆盖了原来的id_rsa文件，那么之前的认证就会失效。这个问题我们可以通过在~/.ssh目录下增加config文件来解决。

##下面以配置搜狐云平台的ssh key为例。

###1. 第一步依然是配置git用户名和邮箱

git config user.name "用户名"   
git config user.email "邮箱"  
###2. 生成ssh key时同时指定保存的文件名  

ssh-keygen -t rsa -f ~/.ssh/id_rsa.sohu -C "email"  
上面的id_rsa.sohu就是我们指定的文件名，这时~/.ssh目录下会多出id_rsa.sohu和id_rsa.sohu.pub两个文件，id_rsa.  sohu.pub里保存的就是我们要使用的key。  

###3. 新增并配置config文件

添加config文件

如果config文件不存在，先添加；存在则直接修改

touch ~/.ssh/config
在config文件里添加如下内容(User表示你的用户名)

Host *.cloudscape.sohu.com
    IdentityFile ~/.ssh/id_rsa.sohu
    User test
###4. 上传key到云平台后台(省略)

###5. 测试ssh key是否配置成功

ssh -T git@git.cloudscape.sohu.com   
成功的话会显示：   

Welcome to GitLab, username!  
至此，本地便成功配置多个ssh key。日后如需添加，则安装上述配置生成key，并修改config文件即可。   