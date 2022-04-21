**理解计算机**

# 理解计算机





##  总体分类

Process and Essential part



| Part     | Explaination    |                                                              |
| -------- | --------------- | ------------------------------------------------------------ |
| 前端     | html/css/vue/js | 最接近内容的部分，计算机最作为工具的部分,为了内容的需要而需要各种框架和技术，实现交互 |
| 服务器端 |                 | 提供后台服务，需要管理/部署/高效利用 服务器资源， 响应       |
| 内核部分 |                 | 计算机作为主体学科，相关技术为底层二进制代码服务             |





## 我的编程能力规划



| My Essential Part | Explaination                  |        |
| ----------------- | ----------------------------- | ------ |
| Docker            | 服务器端部署核心              | 2021/4 |
| Go                | 替代C进行学习，今后作为主语言 | 2021/5 |
| html/css          | 简单学习要看懂                |        |
|                   |                               |        |
| Mysql             |                               |        |
| Redis             |                               |        |
| K8s               | 集群管理工具                  |        |





## 语言对比



编程语言和编程流程

>  什么是脚本语言

脚本语言和非脚本语言的本质区别就是c++等编程语言是经历编程变为底层机器代码，编程二进制代码，可以直接在机器上跑，而脚本语言是面对解释器进行编程的，也就是对方必须有浏览器才能解释看懂例如Js，而html和css更像就是txt文本一样，稍微渲染就能看懂，Python也是如此，对方有解释器就ok没有不行， 而解释器是必须要在系统层级上，

- 脚本语言定义度高，开发、部署、测试、调试都有大量的库文件，开发简单，自由度高
- 随时部署，速度快，修改方便， 不用编译
- 非底层代码内存占用多， 运行速度慢



PHP VS JAVA [^ 3]





## 编程流程





Source Code

Complier-> binary file

.exe 或者unix中任意可执行

打包成软件apk/dmg/ipa/exe







## 安装软件流程



> 以window为例，典型的软件安装分为以下几个步骤[^ 1]

1. 文件从安装的源位置拷贝到目标位置
2. 向系统目录中写入必要的动态连接库(DLL)
3. 向系统注册表中写入相应的设置项
4. 建立开始菜单里的程序组和桌面快捷方式
5. 其他动作



>1. 文件从下载目录，拷贝到指定的安装位置
>2. dll 和lib的区别在与lib是编译时候用，完成源码不同库文件的连接，dll是已经运行起来的程序，相互链接需要用dll动态链接
>3. 一些DLL需要向系统注册，写到注册表
>4. easy
>5. 例如有些软件安装会先把一部分解压到临时目录，安装后删除
>
>为什么一些软件需要重启
>
>​	因为DLL同名文件如果正在运行，系统不允许中途修改，需要重启













## 打包流程 

**(代码->软件)**



Q&A

- 为什么要打包

  打包实质有什么用，为什么要打包

  1. 完成对依赖环境的打包，让软件在任何机子上不缺少环境，可以直接运行

  2. 用脚本对环境变量和依赖进行处理，简化安装步骤

  3. 完成对底层代码的隔离，保护知识产权，不泄漏源码文件

     

- 打包是谁实现的
  - 现在window下面打包可以利用nsic/installshield来实现，
  - 简单的exe文件的直接打包可以通过压缩软件的自解压格式[^ 2 ]



- 打包原理：就是打包是在干什么？









## 开发维度





- 源代码实现功能
- UI用户界面设计实现调用和交互
- Web实现部署



> Example：
>
> C++开发， Qt是C++的第三方库，快速绘制用户界面，控件的设置，可以跨平台在window或者mac等使用
>
> 







## 框架与库





框架是语言搭成的，却并不针对语言，意思是，框架是针对业务的，web服务的框架，MVC的框架

大量的代码封装就像是成语对于语言一样，提供给编程人员大量的可利用的高级函数，快速部署



对于语言来说，框架的概念更接近与库，库提供各种函数

| 框架     | 面向业务 | 语言 |                 |
| -------- | -------- | ---- | --------------- |
| QT       | GUI开发  | C++  |                 |
| Angular  | 前端框架 | Js   | Js排名第一      |
| Vue.js   | 前端框架 | Js   | 轻量            |
|          |          |      |                 |
| ThinkPHP | Web框架  | PHP  | 人多 (属于后台) |
| Laravel  |          |      |                 |
|          |          |      |                 |

*PHP不是一种好语言和方法， 无法解耦的特性注定走不远*





库

- 面向对象的代码组织形式而成的库称为 类库
- 面向过程到代码组织形式而成的库称为 函数库

| 库         | 业务   | 语言 | 备注 |
| ---------- | ------ | ---- | ---- |
| React      | UI组件 | js   |      |
| jQuery     |        |      |      |
| understore |        |      |      |



框架

- 框架为解决一类问题而开发的一条龙服务，只提供框架需要的类或者函数





## 内核



### 浏览器内核



Rendering Enging(渲染引擎)



Webkit	苹果safari内核	开源

Blink		chrome 内核		Google















### 操作系统内核















# 网络通信







## HTTP





>  Http1.0: 请求一次就断开了，只能获得一次web资源

默认端口





### HTTP请求





```java
Request URL: https://www.baidu.com/
Request Method: GET    //Get不安全但是快/Post信息没有上限，安全
Status Code: 200 OK
Remote Address: 39.156.66.18:443
Referrer Policy: strict-origin-when-cross-origin
```



Request 消息头

```java
Accept:text/html,application/xhtml+xml,application/xml;	//浏览器支持类型
Accept-Encoding: gzip, deflate, br	//编码格式
Accept-Language: en-US,en;q=0.9,zh-CN;q=0.8,zh;q=0.7	//浏览器语言环境
Cache-Control: max-age=0	//缓存控制
Connection: keep-alive		//告诉浏览器请求完成是否断开链接
```







### Http响应



状态码

- 200 成功
- 300 302 重定向
- 400 404失败
- 500 服务器代码错误
  - 502 网关错误





























# MyCS Strategy





![image-20210514151509917](BasicT_CS.assets/image-20210514151509917.png)















# 路由Openwrt



- 在ikuai系统中，安装openwrt虚拟机，配置成为旁路由
- 在Openwrt 中用shadowsock 来实现翻墙













































# Reference



[^ 1]: https://blog.csdn.net/kangkanglhb88008/article/details/109129237
[^ 2 ]: https://blog.csdn.net/harvic880925/article/details/27675073
[^ 3]: https://jingyan.baidu.com/article/fdbd4277a6a3e9b89e3f48ae.html

****
