# 发布项目到NPM仓库

## 建立测试项目
```
$ mkdir testmypublish  
$ cd testmypublish 
```

## 创建`package.json`文件
```
$ vim package.json 
{  
  "name":    "testmypublish",  
  "version": "0.0.1"  
} 
```

## 添加NPM用户
```
$ npm adduser  
Username: admin 
Password:   
Email: (this IS public) admin@chinatelecom.com 
```
> 添加成功后registry数据库会增加一条记录

## 发布项目
```
$ cd testmypublish  
$ npm publish  
+ testmypublish@0.0.1
```
发布完成

## 客户端测试

```
$ npm install testmypublish
```

## 切换NPM仓库
> 在项目开发过程中，需要在官方仓库和本地仓库切换，我们可以利用bash中`alias`功能来解决这个问题。在`~/.bashrc`或者`~/.profile`文件结尾处添加如下代码：

>>```alias lnpm = npm --registry=http://127.0.0.1:5984/registry/_design/scratch/_rewrite```

>重启命令行，`npm`操作的是官方仓库，`lnpm`操作的是本地仓库，其余参数和命令均相同。