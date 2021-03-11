# HTTP缓存

### 相关地址：https://www.jiqizhixin.com/articles/2020-07-24-12

浏览器根据请求的url进行缓存处理，浏览器缓存分为**强缓存**和**协商缓存**具体缓存机制见：

![HTTP缓存机制](https://image.jiqizhixin.com/uploads/editor/4948d787-2cf7-46b7-80a4-e3adb8d2541c/640.png)

缓存相关的HTTP头：

- 请求头
1. Cache-Control
2. If-Modified-Since
3. If-None-Match
> `If-None-Match`优先于`If-Modified-Since`
- 响应头
1. Expires
2. Cache-Control
3. Last-Modified
4. ETag
> `Cache-Control`中的`max-age`优先级大于`Expires`，`ETag`优先级大于`Last-Modified`
