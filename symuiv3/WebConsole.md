# WebConsole 实现方案

### 前端使用xterm库

https://github.com/yudai/gotty

Demo见gotty前端代码，加以修改

### 后端使用Gotty

https://github.com/yudai/gotty

### 鉴权问题

同其他接口一样，使用`cookie`中`ACCESS_TOKEN`或者`AUTH_TOKEN`校验。
