# responseLayout
响应式布局 -- P2P 网站

# 什么是响应式？
---
《互联网设计之道》
1. 弹性布局（流动性、自适应性） -- 优化程度有限
2. 响应式（引入了媒介查询 media query）
3. 流动网格、弹性图片和媒介查询 -- 响应式互联网设计三大技术
---

# 响应式网站设计原则
1. 渐进增强
2. 优雅降级 - 针对用户体验来讲，适用于网站设计，尤其适用于响应式网站设计
   

```css
@media only screen and (min-device-width:320px) and (max-device-width:480px) and (-webkit-min-device-pixel-ratio:2){

}
```


## 文件目录
### 1. 为什么要组织项目目录结构？

> jhujuh

---
1. 约定优于配置（convention over configuration）
2. 约定代码结构或命名规范来减少配置数量
---
### 2. 如何组织项目目录结构
- doc
- src
  - css - 存放 `css` 样式相关文件
    - login.css
    - main.css
    - normalize.css 
  - img - 存放 `img` 图片资源
  - js - 存放 `js` 文件
    - vendor - 存放第三方库
      - jquery.js
      - jquery.min.js  
  - 404.html - 当找不到页面时
  - index.html - 首页
  - login.html - 登录页
  - robots.txt - 告诉浏览器搜索引擎哪些文件能访问，哪些不能访问（给爬虫看的）
  - humans.txt - 给人看的
- .editorconfig
- .gitignore
- LICENSE.txt - 版权声明
- README.md - 项目简介、使用方式、相关链接(webstrom → Plugins → MultiMarkdown(下载，可编辑，可预览))
- CHANGLOG.md - 项目每个版本的更新，说明版本号、更新内容、修改了哪些问题等

```txt
# Editor configuration, see http://editorconfig.org
root = true

[*]
charset = utf-8
indent_style = space
indent_size = 2
insert_final_newline = true
trim_trailing_whitespace = true

[*.md]
max_line_length = off
trim_trailing_whitespace = false

```

# 如何编写一个响应式布局
### 0. 常规编写方式
```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <title>网站标题</title>
</head>
<body>
    
</body>
</html>
```
### 1. 网页使用什么语言？
```html
    <!-- lang 是 language 的缩写 -->
    <!-- 在Chrome浏览器中，如果设置了en，Google会自定启动翻译功能 ；如果是盲人网站设置了en，可能读的不正确-->
    <html lang="en"> 
    <!-- zh-CN 支持中文简体 -->
    <html lang="zh-CN">
    <!-- zh 支持更广泛的中文字体 -->
    <html lang="zh">
```
### 2. 网页的 title 和字符集设置顺序
```html
    <title>我可能是乱码</title>
    <meta charset="UTF-8">
    <!-- 两个反过来写可能网站标题会出现乱码 -->
```
### 3. 文档兼用性
```html
    <!-- 代表 IE 的文档兼容性：ie=edge 表示强制用最新的IE浏览器模式渲染页面 -->
    <meta http-equiv="X-UA-Compatible" content="ie=edge">
    <!-- 如果可能，就使用 IE7 的规范进行显示 -->
    <meta http-equiv="X-UA-Compatible" content="ie=EmulateIE7">
    <!-- IE11已经被弃用了 -->
```


```html
<!-- 在 html 代码中，gt 代表尖括号向右，即大于号；lt 代表尖括号向左，即小于号 -->
<!-- gte e代表equal，即大于等于；lte 即小于等于 -->
<!--[if gt/lt/gte/lte IE8]> 
<p> 什么时候显示我 </p>
<![endif] -->
```