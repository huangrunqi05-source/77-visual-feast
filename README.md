# 77的视觉盛宴

一个中文动态视觉灵感展厅，从 React Bits、Remotion Bits、MotionKit 和 Codrops 各精选 10 个案例，共 40 个。

## 打开网页

公开网站：[77的视觉盛宴](https://seventy-seven-visual-feast.runqihuang193.chatgpt.site)。

交付目录的 `index.html` 是构建后的单文件网页，下载后用现代浏览器打开即可。MotionKit 官方视频和外部字体需要联网；字体加载失败时使用系统字体。网页可以放在任意静态托管服务上。

GitHub 公开仓库存储网页、完整源码包和来源说明。当前公开网站由 Sites 托管；GitHub Pages 尚未配置。

## 功能

- 动态卡片、6 类效果筛选、4 个来源筛选、中英文关键词搜索。
- 当前浏览器内的收藏持久化、精选/名称排序、随机灵感。
- 大屏预览、来源与使用说明、原站链接、部分视频参数展示。
- Remotion 和视频播放器支持时间进度与播放速度调整。
- 离屏效果卸载以减少 GPU 和内存占用；提供全局暂停开关。
- 响应式桌面/手机布局、键盘搜索快捷键 `/`、Escape 关闭详情。

## 效果来源与预览类型

| 来源 | 数量 | 集成方式 |
| --- | ---: | --- |
| React Bits | 10 | 原开源组件，展示文字、颜色与容器适配 |
| Remotion Bits | 10 | 官方示例组件，由 Remotion Player 在网页中播放 |
| MotionKit | 10 | 官方 MP4 预览外链，不提供模板源码或再授权 |
| Codrops | 10 | 根据所选案例交互思路独立制作的轻量演绎，原创抽象画面；附完整官方演示 |

Codrops 演绎版不声称与原作视觉或源码完全一致。所有模式均在卡片、详情及关于页面标明。完整条目清单在 `CATALOG.md`。来源许可见 `THIRD_PARTY_NOTICES.md`。

## 开发

完整源码在 `77-visual-feast-source.zip` 中。解压进入项目目录，使用 Node.js 20.19+ 或 22.12+：

```sh
npm ci
npm run dev
```

验证及构建：

```sh
npm run check
npm run build
```

构建输出 `dist/index.html`，JS/CSS 已内联。上传该文件即可部署，无需数据库、密钥或后端。

## 项目结构

- `src/catalog.json`：40 条效果信息、分类与来源。
- `src/components/Effects.jsx`：开源组件和官方视频预览。
- `src/components/Experiments.jsx`：Codrops 案例的独立交互演绎。
- `src/vendor/`：用于本网站的上游组件与示例。
- `src/main.jsx`、`src/styles.css`：展厅界面与响应式样式。
- `scripts/check-catalog.mjs`：目录完整性校验。
- `scripts/inline-build.mjs`：把构建产物整理为单文件网页。

## 边界

收藏仅保存在当前浏览器，不跨设备同步。MotionKit 预览依赖原站资源，失效时可通过官方链接访问。本站不包含视频导出、在线修改 MotionKit 模板、下载第三方组件包或重新售卖组件的功能。
