## 前端项目升级HTTP/2实践

> 参考文章：https://zhuanlan.zhihu.com/p/29609078

### 1. 确认环境版本

目前前端代码通过docker镜像打包，基于内部已有的nginx镜像层，首先需要确认nginx版本号和openssl版本号。

```bash
// 运行镜像
> docker run --name=ydf-test -it --network=host dockerhub.nie.netease.com/frosty/nginx /bin/bash
// 查看nginx版本
> nginx -v
// 查看openssl版本
> openssl version
```

### 2. 环境升级

启用HTTP/2需要服务器openssl支持ALNP

```bash
> openssl s_client -alpn h2 -servername imququ.com -connect imququ.com:443 < /dev/null | grep 'ALPN'
```

如果提示`unknown option -alpn`，说明本地的 OpenSSL 版本太低，请升级到 1.0.2+。

升级openssl过程见：

https://lework.github.io/2020/01/03/openssl-update/

https://github.com/lework/Ansible-roles/tree/master/openssl

自签名证书生成过程见：

https://www.liaoxuefeng.com/article/990311924891552

Nginx配置见：

https://zhuanlan.zhihu.com/p/29609078




