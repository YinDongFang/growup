## 项目背景

目前项目采用Angular8+Material开发，希望嵌入React+Antd开发部分页面。

## 接入前

在antd(v4)官网可以看到：antd 基于最新稳定版本的 TypeScript（>=4.0.0），请确保项目中使用匹配的版本。

查看antd`v3.26.19`文件`package.json`发现`typescript`版本号为`~3.8.3`

> **结论1：`typescript`版本至少需要升级到`3.8.3`以上**

在项目内执行`ng version`查看本地项目`angular`版本：
```
Angular CLI: 8.3.7
Node: 10.16.3
OS: win32 x64
Angular: 8.0.3
```
查看项目内`package.json`文件，`typescript`版本号为：`"typescript": "3.4.5"`

单独升级`typescript`后运行项目会提示错误：

`ERROR in The Angular Compiler requires TypeScript >=3.4.0 and <3.5.0 but 3.8.3 was found instead.`

所以当前`angular8`版本太低，需要对`angular`进行升级，升级步骤可以参阅`angular`升级指南：

https://update.angular.io/?l=3&v=8.0-9.0

升级至`angular9`的过程中会将`typescript`自动升级至`3.8.3`

```
    "@angular/cdk": "8.2.3",
    "@angular/material": "8.2.3",
    "@angular/flex-layout": "8.0.0-beta.27",
    "@angular/http": "7.2.15",
    // 这些包不会通过ng update自动更新，需要手动更新
```

通过`ng update @angular/material@9 @angular/flex-layout@9.0.0-beta.31 --force`升级`material`依赖

更新后运行`npm run start`可以编译打开项目，但是项目报错：

![image](https://user-images.githubusercontent.com/16241981/113394461-e0da1e80-93ca-11eb-9e97-8247a4a0ad30.png)

执行`ng add @angular/localize`

## 接入react, antd

目前`typescript`版本为`3.8.3`，支持`antd@3`，所以安装时安装`antd@3`

`npm install react react-dom antd@3 @types/react @types/react-dom`

### jsx支持

ts支持`jsx`需要在`tsconfig.json`中配置`"jsx": "react"`将`jsx`编译输出为`ReactDom.render`。

文件后缀名需要改为`.tsx`
