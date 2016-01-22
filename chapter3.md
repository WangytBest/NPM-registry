# 架设NPM私有服务器

## 创建数据库
```
# curl -X PUT http://admin:admin@127.0.0.1:5984/registry
{“ok”:true}
```

## 配置NPM用数据库
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

## 安装Git和nodejs

```
# yum install npm
# rpm --import https://fedoraproject.org/static/0608B895.txt
# rpm -Uvh http://download-i2.fedoraproject.org/pub/epel/6/i386/epel-release-6-8.noarch.rpm
# yum install nodejs npm --enablerepo=epel
```