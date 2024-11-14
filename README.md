# PrivacyIDEA_docker

# 使用
git clone 本项目下来
执行 docker compose up -docker

## 添加radius 客户端
修改./radius/data/raddb/clients.conf

## 其它
若修改privacyIDEA的容器名称，请同时修改 ./radius/etc/freeradius/rlm_perl.ini文件中

URL = http://privacyidea/validate/check

将privacyidea修改为对应的容器名称
