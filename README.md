### AIX 上安装 JDK

##### 1. 确定 AIX 系统可以安装的 JDK 版本号 

```
oslevel -s 
```
我的系统系统显示结果为:
![](https://github.com/yabolu/AIX-JDK/blob/master/oslevel.png)

查看AIX版本和JDK版本支持情况表:
![](https://github.com/yabolu/AIX-JDK/blob/master/aix_jdk_list.png)

经过比对发现最高支持到JDK1.7, OK, 那就安装JDK1.7

##### 2. 安装JDK

我下载的是安装包是:

```
Java7_64.jre.7.0.0.640.tar.gz
Java7_64.sdk.7.0.0.640.tar.gz

#存放目录是
/dbtool/java_software/java_jdk/

#解压
gunzip -c Java7_64.jre.7.0.0.640.tar.gz | tar -xvpf -
gunzip -c Java7_64.sdk.7.0.0.640.tar.gz  | tar -xvpf -

#解压完成后, 出现两个文件:
Java7_64.sdk
Java7_64.jre

#执行smit命令，打开图形化安装包，分别安装jdk, jre 依次选择
选择“Software Installation and Maintenance”，Enter
下一步，选择“Install and Update Software”，Enter
下一步，选择“Install Software”，Enter
下一步，在“INPUT device / directory for software”后面，写上要安装包的路径：/dbtool/java_software/java_jdk/Java7_64.sdk，
或者: /dbtool/java_software/java_jdk/Java7_64.jre
Enter 
下一步，“accept new license agreements”把对应的"no"设置成“yes”
下一步，确认界面，Enter

#默认安装在/usr/java7_64目录下

#测试
/usr/java7_64/bin/java -version
```





