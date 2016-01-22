# 架设NPM私有服务器

## 创建数据库`registry`
> 首先，我们需要调用CouchDB的接口为仓库创建一个数据库，之后所有的模块包文件将作为附件保存在这个数据库中。 

```
# curl -X PUT http://admin:admin@127.0.0.1:5984/registry
{“ok”:true}
```

## 配置NPM用数据库`registry`
```
# vim /usr/local/etc/couchdb/local.ini

[couch_httpd_auth]
public_fields = appdotnet, avatar, avatarMedium, avatarLarge, date, email, fields, freenode, fullname, github, homepage, name, roles, twitter, type, _id, _rev
users_db_public = true
[httpd]
secure_rewrites = false
[couchdb]
delayed_commits = false
```

## 安装`Git`和`nodejs`

```
# yum install git
# yum install npm
# rpm --import https://fedoraproject.org/static/0608B895.txt
# rpm -Uvh http://download-i2.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm
# yum install nodejs npm --enablerepo=epel
```

## 安装`npm-registry-couchapp`
```
# git clone git://github.com/npm/npm-registry-couchapp
# cd npm-registry-couchapp/
# npm install
# npm start --npm-registry-couchapp:couch=http://admin:admin@localhost:5984/registry
# npm run load --npm-registry-couchapp:couch=http://admin:admin@localhost:5984/registry
# npm copy --npm-registry-couchapp:couch=http://admin:admin@localhost:5984/registry
```

## 查找本地`.npmrc`文件
```
# npm config ls -l

;userconfig /root/.npmrc
registry = "http://127.0.0.1:5984/registry/_design/app/_rewrite"
```

## 在本地定义`.npmrc`
> 如果本地没有.npmrc文件，则在用户目录下touch文件.npmrc

```
# vim ~/.npmrc
registry = http://127.0.0.1:5984/registry/_design/scratch/_rewrite
```