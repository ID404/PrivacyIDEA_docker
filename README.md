# PrivacyIDEA_docker

# 使用
git clone 本项目下来

如果当前为root用户则执行
```
mkdir privacyidea-db
chown -R 1001:1001 privacyidea-db
```
由于Bitnami PostgreSQL容器是非根容器，因此id为1001的用户需要在您挂载的本地文件夹中拥有写权限。

执行 docker compose up -docker


## 添加radius 客户端
修改./radius/data/raddb/clients.conf

## 其它
若修改privacyIDEA的容器名称，请同时修改 ./radius/etc/freeradius/rlm_perl.ini文件中

URL = http://privacyidea:8080/validate/check

将privacyidea修改为对应的容器名称


## 创建本地用户（非privacyidea管理员）
进入privacyidea容器后执行
/opt/privacyidea/bin/privacyidea-create-pwidresolver-user -u ljc -i 10 -p 123456.com -d 'User LJC' >> /etc/privacyidea/privacyidea_user

管理员登录web后-config-Users-New passwdresolver
Resolver name随便填（例如local_user）
File name 填写/etc/privacyidea/privacyidea_user

在 config-Realms新建realms并引用local_user