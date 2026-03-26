# 钉钉 AI 表格字段插件 — AI 生视频（文生视频 / 图生视频）

基于钉钉 AI 表格 **FaaS AI 字段**开放能力开发的插件，支持在多维表格中直接通过 AI 生成视频，结果以链接形式写回单元格。

## 功能特性

- **文生视频**：输入提示词，自动生成对应视频
- **图生视频**：上传参考图片，基于图片内容生成视频
- **灵活参数**：支持选择宽高比（16:9 / 9:16）和分辨率（1K / 2K / 4K）
- **多语言**：支持中文、英文、日文界面
- **完整错误处理**：积分不足、内容审核、网络异常等均有明确提示

## 技术栈

- Node.js (FaaS 运行时)
- TypeScript
- [dingtalk-docs-cool-app](https://www.npmjs.com/package/dingtalk-docs-cool-app) SDK
- 视频生成 API：[AIFY](https://aivip.link)

## 项目结构

```
├── src/
│   └── index.ts       # 插件入口（formItems / execute / resultType）
├── package.json
├── tsconfig.json
└── config.json        # 本地调试授权配置（不提交到仓库）
```

## 快速开始

### 安装依赖

```bash
npm install
```

### 本地调试

在根目录创建 `config.json`，填入 AIFY API Key（仅用于本地调试）：

```json
{
  "authorizations": "your_aify_api_key"
}
```

启动本地调试服务：

```bash
npm run start
```

然后在钉钉 AI 表格中打开「AI 字段开发助手」插件，选择 FaaS 调试模式即可。

### 构建打包

```bash
npm run build
```

## 获取 API Key

前往 [https://aivip.link/dashboard/apikey](https://aivip.link/dashboard/apikey) 注册并获取 API Key。

## 发布

填写[钉钉 AI 表格 AI 字段上架申请表单](https://alidocs.dingtalk.com/notable/share/form/v014j6OJ5jxepK0Eq3p_hERWDMS_Wqw4Upz)，提交后会有专员拉群沟通上架流程。
