---
title: 快速搭建个人博客流程
---
博主主要使用Hexo框架快速搭建博客，再通过配置Github Pages发布的。


## [Hexo](https://hexo.io/)

是一个快速、简单且功能强大的博客框架。你用Markdown（或其他标记语言）写博客，Hexo 会在几秒钟内生成带有漂亮主题的静态文件。[395种主题](https://hexo.io/themes/) 选到眼花~

### 初始化

```shell
# 安装hexo博客框架
npm install hexo-cli -g
# 新建blog文件夹，并初始化博客
hexo init blog
# 忘记要不要安装依赖了
npm install
# 启动/预览项目
hexo s
```

### 主题

```shell
# 博客项目中安装butterfly主题
git clone -b master https://gitee.com/immyw/hexo-theme-butterfly.git themes/butterfly
# 安装插件（pug以及stylus渲染器）
npm install hexo-renderer-pug hexo-renderer-stylus --save
# 修改配置文件的主题
## 在根目录下找到_config.yml文件，修改主题为butterfly（注意yml**文件格式）
theme: butterfly
# 本地预览
hexo clean //执行此命令后继续下一条
hexo g //生成博客目录
hexo s //本地预览
```

## Github Pages

**GitHub Pages**是一种由**GitHub**中的仓库/项目直接创建的网页。管理简单，在本地编辑仓库中的内容，上传到GitHub上，GitHub Pages就能快速完成更新，重点是**不花钱，不花钱，不花钱**。

1. 新建仓库，注意仓库状态为public，名称设定为：你的用户名.github.io

2. 本地配置git

   - 注意若为首次配置，需设定SSH公钥；

3. 本地博客修改网站部署设置，在根目录下的_config.yml文件中修改deploy相关字段，修改为如下；并将博客项目推送至线上

   ```yml
   deploy:
     type: git
     repo: https://github.com/wangleihuha/wangleihuha.github.io.git
     branch: main #
   ```

   - 这里注意branch分支名要和你线上的分支名一致

4. 在本地根目录下依次执行

   ```bash
   hexo clean //执行此命令后继续下一条
   hexo g //生成博客目录
   hexo s //本地预览
   hexo d //部署项目
   ```

5. 在github中该仓库中找到Settings，在侧边栏中找到Pages，找到Build and deployment，Branch下选择相应分支，点击Sava

6. 执行完毕后，所有人就能通过**你的用户名+github.io**这个域名访问你的网站了。到这儿，我们就成功上线了自己的网站。

## 部署




## 参考文档
- [快速搭建个人博客](https://pdpeng.github.io/2022/01/19/setup-personal-blog/)
- [Quickstart for GitHub Pages](https://docs.github.com/en/pages/quickstart)
