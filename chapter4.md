# 发布项目到NPM仓库

## 建立测试项目
```
$ mkdir testmypublish  
$ cd testmypublish 
```

## 创建package.json文件
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
> 添加成功后registry数据库会增加一天记录