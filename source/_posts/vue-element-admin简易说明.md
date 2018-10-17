---
title: vue-element-admin简易说明
date: 2018-10-16 19:44:24
tags:
---
> 本文档主要是为了本团队后端人员可以更加方便编写基于vue的前段代码，项目选取的是vue-element-admin，为我们的项目提供后台管理页面，关于vue的基本语法可以参考vue的官方文档的前半部分，关于此项目结构可以参考本文档，后续如有需要会添加更多使用指南
## 1-页面写在哪里？
![src文件夹结构](../img/1.png)


写在项目文件里的source > views下

## 2-页面怎么写？-如何写一个vue文件
参考vue官方文档里有关的相关内容
* < template > 标签里写html
* < script > 标签里写vue相关js
* < style > 标签里写这个页面的css

## 3-如何给这个页面一个可以访问的地址？
在src->router->index.js里去配置你的页面地址
```js
  {
    path: '/',
    component: Layout,
    redirect: '/dashboard',
    name: 'Dashboard',
    hidden: true,
    children: [{
      path: 'dashboard',
      component: () => import('@/views/dashboard/index')
    }]
  },
```
## 4-如何在页面中发起ajax请求
引用utils->request.js，使用其返回的promise对象添加回调函数

## 5-如何将项目运行
`npm install`

`npm run dev`