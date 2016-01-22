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