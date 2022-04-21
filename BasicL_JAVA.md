**JAVA**







# 基础



- Java的安装和环境变量的配置
- Java所用IDE 的InteliJ IDEA的安装和配置
- Java 基本命令的操作java(运行.java文件)和javac(生成class文件)





# Java基础全覆盖

特点

1. 强类型语言









## 变量声明





命名规则

- 类成员变量：首字母小写后单词首字母大写
- 局部变量： 和上面一样
- 常量： 全字幕大写， MAX_VALUE
- 类名： 首字母大写，驼峰
- 方法名： 首字母小写，驼峰 maxRun()





运算符中的类型转换 float > long > int

- 如果有Long 都是Long
- 如果有Double 都是Double
- 如果没有都是int
- 



自增和自减

- a++先用a，再加1
- ++a先加1，再用a







## 包机制

本质就是文件夹

- 一般用公司域名倒置作为包名  com.baidu.www

- package必须在最上面，引入用import
- import com.baidu.* 倒入下面所有的类



## JavaDoc

用来生成自己的API文档

```java
@author
@version
@return
@
```





```bash
javadoc -encoding UTF-8 -charset UTF-8 Doc.java

```









## Java 流程控制



## Scanner对象

```java
import java.util.Scanner
    
    
// next() 不能得到带有空格的字符串
//nextLine() 只要不enter都可以
```









## Java 方法



```java
public static int add(int a, int b){
   
   
    return 0; //只要碰到return 方法就结束
}



```





方法重载

*相同的方法名称，不同的参数类型，实现同名方法可以计算各种类型输入*





main()函数传入参数称为命令行传参数

- 运行class要走到包的基本地址，java com.baidu.www.scr.method.Demo02，才能执行，但是编译必须在method里面

- 可变参数：

  ```java
  public void test(int... i){
      
  }
  ```

  只能最后一个参数是可变，而且输入类型要一致，都是int或者都是double这样



## 递归



**递归就是A调用自己**可以很简单的解决一些大问题， 但是不注意会产生栈溢出，StachOverflowError，产生大量函数的调用，能不用就不用；换其他算法



- 递归头：什么时候不调用自己，来确定程序什么时候结束

- 递归体：什么时候调用自己， 进行递归计算

```java
public static int f(int n){
    if (n==1){
        return 1;
    
    }else{
        return n*f(n:n-1);
    }
    
}
```





## 数组



声明：

```java


psvm{
	int[] nums;	//常用
    int nums2[];

    nums = new int[10]; //new关键字来声明nums[]可以存储10个
}
```



- 数组类型一致，声明之后不可改变长度





## 对象





## 类











## JDK和JRE目录



















# Java技术主线



*对于我来说*

- 各种语言所适应的领域和功能
- 对于语言的学习路线



1. 我需要什么功能，应用在什么领域
2. 根据功能和领域选择主要语言
3. 根据功能为核心发散需要的技术
4. 及时停止扩展，不要进入技术的深水中无限度，知识无穷



































# Java Web







## 什么是web服务器



> 刚开始只有静态web 所有用户看到都是同一个页面
>
> - 为了加入特效等， 使用js称为伪动态
> - 不能和数据库交互





动态web：![image-20210513165805797](JAVA.assets/image-20210513165805797.png)



- 加入服务器的web动态资源出现错误，需要重新编写后台程序，就会停机维护



优点：

- 动态更新web
- 直接和Database交互，java可以直接和db交互
- 因为可以交互，数据可以持久化，redis实现



## WEB服务器



ASP

- 微软，国内最早流行
- 在HTML中间直接嵌入VB代码，ASP+COM 非常复杂，重构成本高昂
- C#语言编写
- IIS



PHP

- 开发速度快/跨平台/代码简单
- 无法承载高访问/局限性很大
- 中小企业可以快速部署（WP大火带动php）56



JSP/Servlet

- B/S架构，砍掉客户端/都用浏览器
- 基于JAVA，承载高并发/高可用/高性能
- 语法类似ASP



具体使用的服务器





***IIS***

- 微软





**Tomcat**

- 利于初学者 apache基金会
- 运行jsp和*servlet*





## Maven（工具）



> 快速导入大量的jar包/ 是一种项目架构管理工具
>
> 现在用就是方便导入jar包

maven是约定俗称的Java代码规范





环境变量

- M2_HOME  /maven/bin
- MAVEN_HOME /maven
- PATH %MAVEN_HOME%\bin



> 后面spring会用到M2_HOME的变量



1. 配置aliyun的Maven的镜像 maven/conf/setting.xml
2. 修改localrepository的地址，要不默认很远//配置本地仓库















## TOMCAT



### 文件结构

```java
/conf/conf.xml 修改端口/等所有配置


--webapps			网站存储目录
	--ROOT
	--kaungstudy	 网站目录名称
		-WEB-INF	网站程序
			-web.xml
    		-classes: java程序
            -lib: web 应用 依赖的jar包
			
		-index.jsp/html  默认的网页
        -static
              -css
                -style.css
              -js
              -img



```



- 默认端口8080
- 默认主机localhost
- 默认网站应用存放位置 webapps































# 术语表格

| 技术   | 适用方面                 | 从属语言等类型 | 分类    |
| ------ | ------------------------ | -------------- | ------- |
| JQuery | 快速部署js页面和动态效果 | JS库/ JS框架   | 库/框架 |
| Ajax   | 网页局部刷新             |                | 技术    |
|        |                          |                |         |























