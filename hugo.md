# hugo 使用
Hugo是由Go语言实现的静态网站生成器。简单、易用、高效、易扩展、快速部署。

## 1. install hugo
* Mac: brew install hugo
* Linux: 

## 2. 创建一个站点
hugo new site matata
```
matata/
├── archetypes
│   └── default.md
├── config.toml
├── content
├── data
├── layouts
├── static
└── themes
```

### 配置你的 config.toml

## 3. 挑选一款主题
在Hugo的 主题网站 中挑选一款你喜欢的主题，克隆到 themes 目录下
```
    cd themes
    git clone https://xxxx
```

## 4. 创建一篇文章
 hugo new post/my_first_blog.md


## 5. 本地调试
hugo server --theme=xxx --buildDrafts(包括标记为草稿)

http://localhost:1313 浏览


## 6. 部署到github
创建与用户名相同到仓库

hugo --theme=xxx --baseUrl=“https://xxx.github.io”

```
cd public
git init
git remote add origin git@github.com:xxx/xxx.github.io.git
git add -A
git commit -m “first commit”
git push -u origin master
```
https://xxx.github.io 浏览博客

### 发布新博客
```
hugo new post/hugo.md
–生成静态页面
hugo --theme=xxx  --baseUrl=“https://xxx.github.io/”
cd public
git add .
git commit -m “add hugo ”
git push
```
