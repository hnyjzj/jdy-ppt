# 金斗云客户宣讲 PPT

基于 Slidev 制作的在线客户演示项目。内容覆盖仓库现有的产品需求、业务模块、工程架构、部署、安全、域名、外部平台适配与测试资料，并按客户宣讲逻辑重新组织。

## 本地启动

要求 Node.js `>= 20.12.0`。

```bash
cd ppt
npm install
npm run dev
```

浏览器访问终端输出的地址。演示时可使用：

- `F`：进入或退出全屏。
- `O`：打开幻灯片总览。
- `P`：打开演讲者模式。
- 方向键或空格：翻页。

同一局域网内向客户设备开放预览时使用：

```bash
npm run dev:network
```

## 构建在线版本

```bash
npm run build
```

静态文件输出到 `dist/`。项目已使用 Hash 路由，可部署至 Vercel、Netlify、对象存储或任意静态 Web 服务器。`vercel.json` 已包含默认构建配置。

## 导出文件

```bash
npm run export:pdf
npm run export:pptx
```

PPTX 为 32 页逐页图片型演示文稿，适合离线播放；导出命令会折叠点击动画步骤，在线版仍保留逐步出现和价值测算器等交互能力。

## 内容维护

- 主演示稿：`slides.md`
- 全局视觉：`styles/index.css`
- 可交互组件：`components/`
- 原始文档覆盖表：`SOURCE_MAP.md`

宣讲中的“建议实施路径”和“价值测算”明确标记为建议或示意，不代表已承诺的交付周期或收益。
