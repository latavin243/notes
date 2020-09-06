---
title: '[blog][hexo] 个人github博客搭建'
date: 2020-03-22 14:22:09
tags:
- blog
- hexo
---

## 相关文档

[hexo中文文档](https://hexo.io/zh-cn/)

## 运行环境

windows下终端使用cmder, 包管理使用chocolatey

## 安装nodejs相关以及hexo

```bash
# 使用chocolate安装 nodejs(包含npm)
choco install nodejs -y

# 确认nodejs & npm 安装 (查看版本)
node -v
npm -v

# 换npm源 (换taobao源)
npm install -g cnpm --registry=https://registry.npm.taobao.org

# 确认cnpm安装
cnpm -v

# 安装hexo
cnpm install -g hexo-cli

# 检查hexo安装
hexo -v
```

在国内因为npm的源比较慢, 所以用cnpm代替npm, 但是在国外或者有代理都可以使用npm, 下同

## 创建blog

```bash
# 创建blog目录
mkdir blog
cd !$

# hexo init (可能需要很久)
hexo init  # windows (可能需要run as administrator)
sudo hexo init  # linux

# 运行hexo
hexo server  # hexo s
# 然后访问localhost:4000即可看到初始页面(Hello World
)

# 创建post
# 可以直接在source/_post下添加md文件, 也可以用hexo new
# hexo new的会自带一些相关格式, 例如title, date, tag
hexo new "mypost"  # hexo n "mypost"
```

## 部署到github

在github上创建一个 `<username>.github.io`的repo, 例如账号是latavin243, 那么新的repo就是`latavin243.github.io`

```bash
# 安装一个git工具
cnpm install --save hexo-deployer-git

# 设置_config.yml文件, 内容见下方
vim _config.yml

# 部署
hexo deploy  # hexo d
```

`_config.yml`内容 (修改部分)

```yaml
# Deployment
## Docs: xxx
deploy:
  type: git
  repo: git@github.com:latavin243/latavin243.github.io.git
  branch: master
```

部署完成之后就可以在浏览器地址栏输入`<username>.github.io`查看个人博客了, 例如[latavin243的博客](https://latavin243.github.io/)

## 更新博文

```bash
# 添加博文
hexo n "newpost"

# 写完后更新
hexo clean; hexo generate; hexo deploy
```

## 更换主题

```bash
# git clone到主题文件夹下, 以next主题为例
git clone git@github.com:theme-next/hexo-theme-next.git themes/next

# 修改_config.yml
vim _config.yml
# 修改 theme: next

# 可以修改themes/next/_config.yml配置主题
```

