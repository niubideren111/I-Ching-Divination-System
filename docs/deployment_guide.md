# 周易排盘源码部署指南 | 纯静态网页一键部署
## Yi-Jing Fortune Telling Source Code Deployment Guide

本指南帮助你快速部署周易排盘系统。由于项目是**纯静态前端**（HTML + JavaScript），无需任何后端服务器，部署方式非常灵活。

---

## 目录 | Table of Contents

1. [本地运行](#本地运行)
2. [GitHub Pages 部署（推荐）](#github-pages-部署推荐)
3. [其他静态托管部署](#其他静态托管部署)
4. [自定义配置](#自定义配置)
5. [常见问题](#常见问题)

---

## 本地运行

### 方法一：直接打开（最简单）


# 1. 克隆仓库
git clone https://github.com/pokercode88/Yi-Jing-Fortune-Telling-Source.git

# 2. 进入目录
cd Yi-Jing-Fortune-Telling-Source

# 3. 直接用浏览器打开 index.html
# Windows: 双击 index.html
# Mac: 双击 index.html 或用浏览器打开
# Linux: 使用浏览器打开文件
⚠️ 注意：部分浏览器因安全策略可能限制本地文件的某些功能（如跨域请求）。如果遇到问题，请使用方法二（本地服务器）。

方法二：使用本地 HTTP 服务器（推荐）
Python 3 版本

# 在项目根目录下执行
python3 -m http.server 8080

# 然后访问 http://localhost:8080
Python 2 版本

# 在项目根目录下执行
python -m SimpleHTTPServer 8080

# 然后访问 http://localhost:8080
Node.js 版本（需要安装 live-server）

# 安装 live-server（全局）
npm install -g live-server

# 在项目根目录下执行
live-server --port=8080
VS Code 用户
安装 Live Server 插件

右键点击 index.html → Open with Live Server

GitHub Pages 部署（推荐）
GitHub Pages 是免费的静态网站托管服务，部署后你的排盘系统会有一个公网链接，方便分享和演示。

操作步骤
进入仓库设置

打开你的 GitHub 仓库

点击 Settings 标签页

配置 Pages

在左侧菜单找到 Pages（或直接向下滚动）

在 Branch 下拉菜单中，选择 main（或 master）

文件夹选择 / (root)

点击 Save

等待部署

部署通常需要 1-3 分钟

部署成功后，页面会显示绿色提示框，包含你的网站链接

链接格式为：https://你的用户名.github.io/仓库名/

访问演示

例如：https://pokercode88.github.io/Yi-Jing-Fortune-Telling-Source/

开启强制 HTTPS（推荐）
在 GitHub Pages 设置中，勾选 Enforce HTTPS，让网站通过加密连接访问，提升安全性和 SEO 排名。

自定义域名（可选）
如果你有自己的域名（如 https://yijing.example.com）：

在 Pages 设置中，在 Custom domain 输入你的域名

在你的域名 DNS 设置中添加一条 CNAME 记录，指向 你的用户名.github.io

等待 DNS 生效（通常 10-30 分钟）

其他静态托管部署
Netlify（推荐）
Netlify 提供更简单的部署体验和更好的性能。

方法一：拖拽部署

访问 netlify.com 注册账号

将项目文件夹直接拖拽到 Netlify 部署区域

完成！你会得到一个 https://xxxx.netlify.app 的链接

方法二：Git 连接

点击 New site from Git

连接你的 GitHub 仓库

保持默认配置（Build command 留空，Publish directory 填 /）

点击 Deploy site

Vercel
访问 vercel.com 注册账号

点击 Add New → Project

导入你的 GitHub 仓库

保持默认配置（Framework Preset 选择 Other）

点击 Deploy

Cloudflare Pages
访问 pages.cloudflare.com

点击 Create a project → Connect to Git

连接你的 GitHub 仓库

保持默认配置（Build command 留空）

点击 Save and Deploy

阿里云 OSS / 腾讯云 COS
如果你的项目面向中国大陆用户，可以使用云存储托管：

阿里云 OSS 步骤：

创建 Bucket（选择公共读权限）

开启静态网站托管功能

上传所有文件到 Bucket 根目录

绑定自定义域名（可选）

自定义配置
修改网站标题
编辑 index.html，找到 <title> 标签：

html
<title>周易排盘系统 | 八字紫微奇门六壬</title>
修改默认语言
系统内置简体/繁体切换。如需修改默认语言，编辑 index.js 中的配置：

javascript
// 默认语言：'zh-CN' 简体中文，'zh-TW' 繁体中文
var defaultLanguage = 'zh-CN';
添加 Google Analytics（可选）
在 index.html 的 </head> 标签前添加：

html
<!-- Google Analytics -->
<script async src="https://www.googletagmanager.com/gtag/js?id=你的GA-ID"></script>
<script>
  window.dataLayer = window.dataLayer || [];
  function gtag(){dataLayer.push(arguments);}
  gtag('js', new Date());
  gtag('config', '你的GA-ID');
</script>
修改样式
CSS 样式内嵌在 index.html 的 <style> 标签中。如需大幅调整，建议创建独立的 style.css 文件。

常见问题
Q1: 本地打开 index.html 时，某些功能不工作？
原因：浏览器的跨域安全策略限制了本地文件的某些 JavaScript 功能。

解决方案：使用本地 HTTP 服务器运行（参考上文“本地运行 - 方法二”）。

Q2: GitHub Pages 部署后，页面显示空白？
排查步骤：

检查仓库根目录是否有 index.html 文件

确认 Pages 设置中 Branch 选择正确

等待 1-3 分钟后强制刷新浏览器（Ctrl + F5）

检查浏览器控制台是否有报错（F12 → Console）

Q3: 排盘结果不准确？
可能原因：

时区设置不正确（中国使用 UTC+8）

输入日期格式错误

节气交界点处理（如立春分年）

解决方案：请参考 docs/algorithm_api.md 了解算法细节，或联系技术支持。

Q4: 如何更新到最新版本？

# 拉取最新代码
git pull origin main

# 如果使用 GitHub Pages，推送后会自动重新部署
git push origin main
Q5: 可以部署到自己的服务器吗？
可以。将整个项目文件夹上传到服务器的 Web 目录（如 htdocs、wwwroot）即可。支持 Nginx、Apache、IIS 等任何 Web 服务器。

Nginx 配置示例：

nginx
server {
    listen 80;
    server_name yijing.example.com;
    root /var/www/Yi-Jing-Fortune-Telling-Source;
    index index.html;
}
Q6: 如何导出排盘结果为图片或 Excel？
系统内置了导出功能：

图片导出：点击界面上的截图/导出图片按钮

Excel 导出：使用 xlsx.full.min.js 库，点击导出 Excel 按钮

联系支持
如遇到部署问题，可通过以下方式联系我们：

联系方式	账号
Telegram	@alibabama401
Email	ttpoker733@gmail.com
请在联系时附上：部署方式（GitHub Pages / 本地 / 其他）、浏览器版本、错误截图。

*最后更新：2026-06-12 | 版本：v1.0*