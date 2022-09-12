# Redis Viewer

#### 介绍

一款超棒的redis客户端工具
支持Windows、MacOS、Linux，方便不同平台开发者们使用！

##### JDK序列化查看器
JDK字节码解码展示，全网唯一😎，老项目有救了
基础类型、包装对象（list、set、map等等），展示类似IDEA的debug模式，不仅看得到还要合理好看
![JDK序列化](https://foruda.gitee.com/images/1662602932900645594/474a2a84_968935.png "屏幕截图")

##### JSON编辑器
JSON格式专业编辑器，实时语法提示、语法检查
![输入图片说明](https://foruda.gitee.com/images/1662603092583364293/1ce522fb_968935.png "屏幕截图")

##### 大数据列表
针对大数据量做了优化使用DOM虚拟滚动分片加载，千万数据量无压力渲染，解决同类软件痛点。（实测可见83.8w行，行高40px达到浏览器高度上限33554432px，剩余数据可通过关键字快速过滤出来，作者也在寻找完美显示方案，欢迎秀儿讨论）
![输入图片说明](https://foruda.gitee.com/images/1662603298234763181/9a727658_968935.png "屏幕截图")

##### 归类分组
常见使用树形来展示归类分组，大数据量情况下的树形将会卡爆，深有体会的小伙伴儿应该蛮多的吧
软件另辟蹊径使用了页签导航的展现形式，充分发挥大数据列表的优势，完美解决大数据量分组树形的渲染问题
![输入图片说明](https://foruda.gitee.com/images/1662603364908166350/1d229ada_968935.png "屏幕截图")

##### 控制台
支持「直接模式」命令的控制台，再也不用ssh登录到服务器上面敲命令了
![输入图片说明](https://pic4.zhimg.com/v2-5f1d98f7ca2f833c06f60ee707fc8867_r.jpg "屏幕截图")

##### 导入导出
开发人员最想干什么？当然是把现网（或另一环境）的数据导入到本地快速定位问题。特别推出导出导入功能，可谓是研发利器！
![输入图片说明](https://foruda.gitee.com/images/1662603483025666312/38ab8045_968935.png "屏幕截图")

##### 支持SSH：单机&集群
同时支持单机与集群的SSH ，不少类似软件的支持度也相对欠缺。
![输入图片说明](https://foruda.gitee.com/images/1662603540964783981/adf9738e_968935.png "屏幕截图")

##### 自动识别集群
只需要录入一个redis节点的IP、PORT，软件将自动识别集群或单机

##### JSON自动格式化展示
string类型的数据：展示时如果是JSON格式则将自动格式化方便阅读，保存时会进行JSON格式再校验、压缩、提交

##### 极速索引—不分页
关键字极速过滤（内存），相比同类软件更便捷、更快的索引数据，消灭丑陋的分页组件
![输入图片说明](https://pic4.zhimg.com/v2-8a20d3fbae16725a7102d4ab2efc313b_r.jpg)

#### 软件架构

Electron 9.x、
Golang 18.x

#### 安装教程

通过本仓库的 [Releases页面](https://gitee.com/onefineday/redisviewer/releases) 下载Redis Viewer-xxx安装包，运行就可以安装Redis Viewer。 目前只支持x64平台。
```
Windows --> Redis Viewer-x.x.x.exe
MacOS --> Redis Viewer-x.x.x.dmg
Linux --> Redis Viewer-x.x.x.deb、Redis Viewer-x.x.x.AppImage
```

#### 使用说明

##### 1. 远程模式
远程模式即分离模式，程序将优先访问远程RedisViewer的后端，本地后端将被自动屏蔽。
带来的好处是：即使居家办公或redis服务器部署在公网，也能够以极高的速度访问、响应数据量比较多的redis服务器（远程RedisViewer需要跟redis服务器是局域网，二者网络通信效率要高）。
###### 1.1 远程服务器要打开Redis Viewer（若远程为无界面的server系统，则需要执行`./redismanager -conf configs`这里需要提取目标系统版本的相关文件自己部署，对动手能力有一定的要求）。
###### 1.2 本地HOSTS添加如下域名：（注意替换远程RedisViewer所在主机IP ==> 192.168.36.230）
```
# Redis Viewer 远程模式域名优先
192.168.36.230 redis-viewer-remote
```
###### 注意：
远程RedisViewer与本地的网络必须是通畅：办公网络的话有时候需要拨VPN连接公司内网。
远程RedisViewer需要跟Redis服务器是局域网，二者网络通信效率要高。
配置完HOSTS需要重启程序才能生效。

##### 2. SSH隧道
本质上就是端口转发。它能够将其他 TCP 端口的网络数据通过 SSH 链接来转发，并且自动提供了相应的加密及解密服务。这一过程也被叫做“隧道”（tunneling），这是因为 SSH 为其他 TCP 链接提供了一个安全的通道来进行传输而得名。 SSH 端口转发能够提供两大功能： 1.加密 SSH Client 端至 SSH Server 端之间的通讯数据。 2.突破防火墙的限制完成一些之前无法建立的 TCP 连接。
###### 开启SSH隧道并正确填写
![输入图片说明](https://foruda.gitee.com/images/1662603540964783981/adf9738e_968935.png "屏幕截图")

#### 打赏支持
![打赏支持](https://foruda.gitee.com/images/1662602721400259841/0f2c822e_968935.png "请作者喝咖啡")