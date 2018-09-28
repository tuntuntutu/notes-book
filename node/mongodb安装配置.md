# mongodb安装配置

[下载地址](https://www.mongodb.com/dr/fastdl.mongodb.org/win32/mongodb-win32-x86_64-2008plus-ssl-3.2.9-signed.msi/download)

[文档地址](http://www.runoob.com/mongodb/) 

## 可视化工具
* [Robomongo](https://robomongo.org/)（最新版本收费）
* [mongodbvue](http://www.mongovue.com/)（收费）
* [MongoBooster](http://www.softpedia.com/get/Internet/Servers/Database-Utils/MongoBooster.shtml)
* idea插件

## 安装

 * 傻瓜式安装
 * 在根目录新建一个data文件夹作为mongodb的数据库文件存放地址
 * `/data`中新建一个db一个log


## 启动mongodb

切换到 `mongodb` 安装目录的`bin/`文件夹下

* 命令行启动mongodb
```
mongod.exe --dbpath c:\data\db --logpath "D:\data\log\mongdb.log" --logappend

```

* 注册到windows服务中

```
mongod.exe --bind_ip yourIPadress --logpath "C:\data\dbConf\mongodb.log"   --logappend --dbpath "C:\data\db" --port yourPortNumber --serviceName "YourServiceName" --serviceDisplayName "YourServiceName" --install

```

参数 | 描述
---|---
bind_ip | 绑定服务IP，若绑定127.0.0.1，则只能本机访问，不指定默认本地所有IP
logpath | 定MongoDB日志文件，注意是指定文件不是目录
logappend | 使用追加的方式写日志
dbpath | 指定数据库路径
port | 指定服务端口号，默认端口27017
serviceName | 指定服务名称
serviceDisplayName | 指定服务名称，有多个mongodb服务时执行。
install | 指定作为一个Windows服务安装。

启动windows的services.msc，启动对应服务。


## 启动 mongo

* 新建一个bat批处理文件，双击运行
    ```
    cd C:\Program Files\MongoDB\bin
    mongo
    ```

* 系统变量注册，支持全局命令行
    1. 进入到高级系统设置；
    2. 进入到环境变量；
    3. 在系统变量里面找到变量名为Path；
    4. 在变量值的结尾处加入;C:\Program Files\MongoDB\bin（这个就是mongo安装目录的bin目录， win10以下 别漏掉了分号），保存；
    5. 命令行输入mongo



    

