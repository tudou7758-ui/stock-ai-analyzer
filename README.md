# 股票基本面 AI 分析器 📈

基于 DeepSeek 深度思考模式的股票基本面分析网站。

## 项目信息

| 项目 | 信息 |
|------|------|
| 名称 | Stock AI Analyzer |
| 描述 | AI 驱动的股票基本面分析工具 |
| 作者 | Janson (for Boss) |
| 创建时间 | 2026-02-01 |

## 在线访问

**GitHub Pages:** https://tudou7758-ui.github.io/stock-ai-analyzer/

**GitHub 仓库:** https://github.com/tudou7758-ui/stock-ai-analyzer

## 功能特性

- 🔍 **股票查询** - 输入股票名称或代码即可分析
- 🤖 **AI 驱动** - 使用 DeepSeek 深度思考模式
- 📊 **完整分析** - 涵盖估值、财务、竞争格局等多维度
- 📱 **响应式设计** - 完美适配手机和PC端
- ⚡ **快速响应** - Cloudflare Workers 全球加速

## 技术栈

- **前端**: Vue 3 + Vite + TailwindCSS
- **后端**: Cloudflare Workers
- **AI**: DeepSeek API (深度思考模式)
- **部署**: Cloudflare Pages + Workers

## 使用方法

1. 访问在线地址
2. 输入股票名称或代码（如：东鹏特饮、605499、腾讯等）
3. 点击分析按钮
4. 查看完整的 AI 分析报告

## 文件结构

```
websites/
└── stock-ai-analyzer/
    ├── README.md              # 本文档
    ├── package.json           # 前端依赖配置
    ├── vite.config.js         # Vite 配置
    ├── wrangler.toml          # Cloudflare 配置
    ├── index.html             # HTML 入口
    ├── src/                   # 前端源码
    │   ├── main.js            # Vue 入口
    │   ├── App.vue            # 根组件
    │   ├── components/
    │   │   ├── StockInput.vue     # 股票输入组件
    │   │   ├── ResultDisplay.vue  # 结果展示组件
    │   │   └── LoadingSpinner.vue # 加载动画
    │   └── style.css          # 全局样式
    ├── functions/             # 后端 API
    │   └── api/
    │       └── analyze.js     # AI 分析 API
    └── public/                # 静态资源
```

## 提示词框架

详见 `src/prompt_framework.md`

## 环境配置

需要配置以下环境变量：

| 变量名 | 说明 | 必需 |
|--------|------|------|
| DEEPSEEK_API_KEY | DeepSeek API Key | 是 |
| DEEPSEEK_MODEL | 模型名称 (默认: deepseek-reasoner) | 否 |

## 部署

### 前端部署 (Cloudflare Pages)

```bash
npm run build
npx wrangler pages deploy dist
```

### 后端部署 (Cloudflare Workers)

```bash
npx wrangler deploy
```

## API 接口

### POST /api/analyze

请求体:
```json
{
  "stock": "股票名称或代码"
}
```

响应:
```json
{
  "success": true,
  "data": {
    "stock": "东鹏特饮",
    "analysis": "完整分析报告..."
  }
}
```

## 更新日志

### v1.0.0 (2026-02-01)
- 初始版本
- 基础股票分析功能
- 响应式 UI
- Cloudflare Workers 后端

## 注意事项

- API Key 保存在 Cloudflare Workers  Secrets 中
- 前端不直接暴露 API Key
- 建议使用 DeepSeek 的深度思考模式 (deepseek-reasoner)
