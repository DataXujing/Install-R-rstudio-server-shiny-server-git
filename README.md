# Install-R-rstudio-server-shiny-server-git

by Xujing



## 1. 你应该装一个Ubuntu系统

首先安装一个虚拟机，然后安装Ubuntu，作者使用的为Ubuntu 16.04,所有安装配置
都是在该版本下进行的，建议虚拟机安装，这样可以在Windows系统和Ubuntu下随意切换
且无障碍copy文件，不推荐U盘安装Ubuntu双系统，这样在系统切换中需要重启电脑比较麻烦。
相关安装教程可参考：[VMareUbuntu安装详细过程](http://blog.csdn.net/u013142781/article/details/50529030)



## 2. Linux安装最新版本的R

安装步骤非常简单，且基本不会出现问题

+ step1: 打开终端，在终端内输入：sudo apt-get install r-base

+ step2: 更新软件源列表并更新R软件 sudo apt-get update; sudo apt-get install r-base r-base-dev;
此时输入R 可以打开看是否为最新版本

+ step3: 提示：如果已经安装了旧版本的R-base，或许用 sudo apt-get upgrade 也可以更新到最新版本

+ step4： 在终端中输入 R，如果能正常打开，恭喜你，你已经成功安装了最新版本的R,这里需要注意的是如果只运行
step1你可能仅仅安装了一两年前的版本，并非最新的R版本。

+ step5： 安装pacakges只需打开R输入：`install.packages("packagesnames")` 或`devtools::install-github("path/packagesnames")`
稍等片刻会提示选择镜像，然后就可以安装了，在安装过程中作者踩了很多坑，大体分为三类：ubuntu分配内存不足或缺少必备的一些依赖包
或者镜像资源不稳定。具体解决办法可在问题区域得到回答。

当然除了这种在线安装之外，你也可以选择离线安装.zip文件，安装步骤分为三步，下载，解压，安装相关教程可google或Baidu解决: [点我](http://blog.sina.com.cn/s/blog_6583048d01018ac5.html)中的方法2即可离线安装。

## 3. 安装 rstudio-server

rstudio server可以让你的rstudio运行在网页上，并且很好的与git结合进行数据科学项目的协同开发。它分为普通版和满血版(rstudio server pro，收费的),
作为数据科学的发烧友可以玩一玩普通版，有条件还是要购买服务（为Rstudio打广告）其安装步骤也很简单。

+ step1:  sudo apt-get install gdebi-core
+ step2:  sudo apt-get install libapparmor1  # Required only for Ubuntu, not Debian
+ step3: wget http://download2.rstudio.org/rstudio-server-0.97.551-amd64.deb
+ step4: sudo gdebi rstudio-server-0.97.551-amd64.deb
+ step5: 查看rstudio-server: ps -aux|grep rstudio-server， 恭喜你rstudio-server的服务已启动, 8787端口被打开。
+ step6： ifconfig 查看ip地址，在浏览器中输入<http://ip:8787>或<http://localhost:8787>,跳出界面，输入你Ubuntu的登录账号和密码即可登录进你的
rstudio-server,例如我的用户名xujing

![rstudio-server登录](load.png)

+ step7：注意在登录时不要使用root权限用户，这样会出错。

+ step8: 太帅了，是不是web版的rstudio！！！

![登录成功的界面](success.png)

踩过的坑：我曾在32位ubuntu14.04版本下安装过最新版本的rstudio-server，发现安装成功后无法启动rstudio server，各种大牛咨询，最后卸掉重新安装了低版本的，问题解决了，这个故事告诉我们
在安装过程中如果无法安装，可尝试几种不同的版本，总有一个适合你。

安装好你的开源工具，就可以站在巨人的肩膀上安装各种packages，过程中你会在内心呐喊总有一天我也会写出一些牛B的packages，为开源社区尽微薄之力， 有了rstudio server和git我们就可以开发自己的packages
及时上传到世界最大的同性交友社区Github，读者可以在作者（DataXujing)中看到我开发测试的几个程序包，入门足以。让我们在享受开源的同时，也为开源社区添砖加瓦。


使用浏览器运行R的好处：

+ **你可以从任何一台能上网的计算机去操作R**
+ **共享代码、数据和其它文档**
+ **多用户共享高性能计算资源与协同工作** 
+ **集中管理R扩展包** 

## 4. Git


## 5. Shiny-server共享我的ShinyApp


## 6. Win64下安装 R server 



