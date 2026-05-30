# 🌙 openai-gemini

将 Google Gemini API 转换为 OpenAI 兼容格式的代理服务，**支持多种部署平台**。

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/21967201/openai-gemini)
[![Deploy to Netlify](https://www.netlify.com/img/deploy/button.svg)](https://app.netlify.com/start/deploy?repository=https://github.com/21967201/openai-gemini)

## ✨ 特性

- 🌐 **多平台支持**: Vercel、Netlify、Cloudflare Workers、Deno、Bun、Node.js
- 🚀 **免费部署**: 利用各平台的免费额度
- 🔄 **OpenAI 兼容**: 可直接用于 Open WebUI、Chatbox 等客户端
- 📊 **流式输出**: 支持 \stream: true\
- 🔒 **安全**: API Key 通过环境变量管理

## 🚀 快速部署

### 方法 1: Vercel 一键部署

点击上方 "Deploy with Vercel" 按钮，按照提示操作。

\\\ash
# 或使用 CLI
vercel deploy

# 本地开发
vercel dev
\\\

### 方法 2: Netlify 一键部署

点击上方 "Deploy to Netlify" 按钮。

\\\ash
# 或使用 CLI
netlify deploy

# 本地开发
netlify dev
\\\

### 方法 3: Cloudflare Workers

\\\ash
npm install -g wrangler
wrangler secret put GEMINI_API_KEY
wrangler deploy
\\\

### 方法 4: 本地运行（Node/Deno/Bun）

\\\ash
# Node.js
npm install
node node.mjs

# Deno
deno run --allow-env --allow-net deno.mjs

# Bun
bun run bun.mjs
\\\

## 🔧 环境变量

| 变量 | 必填 | 说明 |
|------|------|------|
| \GEMINI_API_KEY\ | ✅ | Google Gemini API Key（从 [AI Studio](https://aistudio.google.com/app/apikey) 获取） |

## 📖 使用方法

### 在 Open WebUI 中使用

\\\ash
docker run -d -p 3000:8080 \\
  -e OPENAI_API_BASE_URL=https://你的域名.vercel.app/v1 \\
  -e OPENAI_API_KEY=任意值 \\
  --name open-webui \\
  ghcr.io/open-webui/open-webui:main
\\\

### API 调用示例

\\\ash
# 非流式请求
curl https://你的域名.vercel.app/v1/chat/completions \\
  -H "Content-Type: application/json" \\
  -d '{
    "model": "gemini-pro",
    "messages": [{"role": "user", "content": "Hello!"}],
    "stream": false
  }'

# 流式请求
curl https://你的域名.vercel.app/v1/chat/completions \\
  -H "Content-Type: application/json" \\
  -d '{
    "model": "gemini-pro",
    "messages": [{"role": "user", "content": "Hello!"}],
    "stream": true
  }'
\\\

## 📁 项目结构

\\\
├── api/                   # Vercel/Netlify 函数
├── src/                   # 源代码
├── public/                # 静态资源
├── node.mjs               # Node.js 入口
├── deno.mjs               # Deno 入口
├── bun.mjs                # Bun 入口
├── wrangler.toml          # Cloudflare 配置
├── vercel.json            # Vercel 配置
├── netlify.toml          # Netlify 配置
└── README.md
\\\

## 🌍 支持的平台

- ✅ **Vercel** (推荐)
- ✅ **Netlify**
- ✅ **Cloudflare Workers**
- ✅ **Deno Deploy**
- ✅ **Bun**
- ✅ **Node.js**

## 🤝 贡献

欢迎提交 Issue 和 Pull Request！

## 📝 许可证

详见 [LICENSE](LICENSE) 文件。

## 🙏 致谢

- [Google Gemini API](https://ai.google.dev/)
- [OpenAI API Reference](https://platform.openai.com/docs/api-reference)

---

**维护者**: [@21967201](https://github.com/21967201)  
**原始项目**: [PublicAffairs/openai-gemini](https://github.com/PublicAffairs/openai-gemini)

⭐ 如果这个项目对你有帮助，请给它一个 Star！