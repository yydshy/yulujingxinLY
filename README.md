# 雨潞净心 · 官网

雨潞净心品牌官网——以禅修、正念与自然疗愈为核心，陪伴每一颗疲惫的心找到宁静。

## 项目简介

这是一个静态单页网站，展示雨潞净心的品牌故事、疗愈服务、学员蜕变故事以及旅修光影记录。设计风格以温暖、自然、宁静为主调，采用宋体搭配大地色系，营造沉浸式的疗愈氛围。

## 技术栈

- **纯静态 HTML5** — 无构建工具，零依赖
- **内联 CSS** — 减少 HTTP 请求，首屏加载更快
- **原生 JavaScript** — 无框架，轻量可控
- **WebP 图片格式** — 画廊采用 `<picture>` 标签实现 WebP / JPG 双格式降级

## 文件结构

```
.
├── index.html          # 主页面（单页应用）
├── images/
│   ├── avatar-ting.jpg # 创始人头像
│   ├── hero-bg.jpg     # 社交分享预览图
│   ├── favicon.png     # 站点图标（建议准备）
│   ├── apple-touch-icon.png  # 苹果设备图标（建议准备）
│   └── gallery/
│       ├── 01.jpg ~ 16.jpg   # 画廊 JPG 原图
│       └── webp/
│           ├── 01.webp ~ 16.webp  # 画廊 WebP 压缩图
```

## 本地预览

由于本项目是纯静态 HTML，无需任何构建步骤：

```bash
# 方式一：直接用浏览器打开
open index.html

# 方式二：使用本地服务器（推荐，可验证路径正确性）
python3 -m http.server 8000
# 然后访问 http://localhost:8000
```

## 部署

本项目基于 GitHub Pages 部署。推送代码到仓库后，GitHub Pages 会自动发布。

## 近期优化记录

### 可访问性（Accessibility）
- 添加 `Skip Navigation` 跳过导航链接，方便屏幕阅读器用户直达主内容
- 为 Lightbox、电话弹窗、移动端菜单实现焦点陷阱（Focus Trap）
- 支持 `prefers-reduced-motion` 媒体查询，尊重用户减弱动画的系统偏好
- 改进画廊 16 张图片的 `alt` 文本，从笼统的"旅修瞬间"改为具体场景描述

### 性能
- 服务卡片 3D tilt 效果添加 `requestAnimationFrame` 节流
- WebP 支持检测改为页面加载时单次执行并缓存结果，避免每次点击画廊都重复检测
- Tilt 效果仅在支持精细指针（鼠标）的设备上启用，触屏设备自动跳过

### SEO
- 添加 Twitter Card、Open Graph、Canonical URL、theme-color
- 补充 Schema.org 结构化数据（`priceRange`、`openingHours`、`geo` 坐标）
- 添加 `apple-touch-icon` 支持

### 代码质量
- 移除 32 处内联 `onclick` / `onkeydown`，改为事件委托统一处理
- 画廊 Lightbox 直接从 `<source>` 读取 WebP 路径，移除冗余 `data-*` 属性
- 修复故事展开/收起时的 `maxHeight` 动画跳变问题
- 进度条添加除以零兜底，避免极短页面出现 `NaN`

### 打印与兼容性
- 添加 `@media print` 打印样式，隐藏导航和交互元素
- Favicon 从 JPG 格式改为 PNG 格式，提升浏览器兼容性

## 注意事项

- 当前 `favicon.png` 与 `apple-touch-icon.png` 需自行准备并放入 `images/` 目录
- 画廊图片建议同时维护 `gallery/` 下的 JPG 和 `gallery/webp/` 下的 WebP 两个版本
- 所有外部链接和资源路径均基于 GitHub Pages 域名配置，如需迁移请批量替换 `og:image`、`canonical` 等地址

## 联系方式

- 微信公众号：雨潞净心
- 预约电话：139 2888 2211（微信同号）
- 所在城市：广州
