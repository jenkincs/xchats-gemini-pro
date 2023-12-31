# ChatGPT using GeminiPro API

[English](README.md) | 中文

与 Gemini Pro 聊天的最简 WebUI。

体验网址： [XChats](https://xchats.top)

> [!WARNING]
> 本项目为开源项目，使用者必须在遵循 GOOGLE 的[使用条款](https://ai.google.dev/terms)以及**法律法规**的情况下使用，不得用于非法用途。
> 
> 根据[《生成式人工智能服务管理暂行办法》](http://www.cac.gov.cn/2023-07/13/c_1690898327029107.htm)的要求，请勿对中国地区公众提供一切未经备案的生成式人工智能服务。

[![image](https://github.com/babaohuang/GeminiProChat/assets/559171/d02fd440-401a-410d-a112-4b10935624c6)](https://xchats.top)

## 部署

### 使用 Vercel 部署（推荐）

[![Deploy with Vercel](https://vercel.com/button)](https://vercel.com/new/clone?repository-url=https://github.com/jenkincs/xchats-gemini-pro&env=GEMINI_API_KEY&envDescription=Google%20API%20Key%20for%20XchatsGeminiPro&envLink=https://makersuite.google.com/app/apikey&project-name=xchats-gemini-pro&repository-name=xchats-gemini-pro&demo-title=XChats%20Gemini%20Pro&demo-description=Minimal%20web%20UI%20for%20ChatGPT%20using%20Gemini%20Pro%20API.&demo-url=https%3A%2F%2Fxchats.top/&demo-image=https%3A%2F%2Fxchats.top%2Ficon.svg)

只需点击上面的按钮，并按照说明操作，即可部署自己的副本。

> [!NOTE]
> #### 关于 API 使用过程中 “User location is not supported for the API use” 的解决方案
> 如果你遇到了 **“User location is not supported for the API use”** 的问题，请按照以下步骤进行解决：
>
> 1. 前往 [**palm-netlify-proxy**](https://github.com/antergone/palm-netlify-proxy) 仓库并点击其中的 **“Deploy With Netlify**。
> 2. 部署完成后，你将收到 Netlify 分配的域名 （例如 `https://xxx.netlify.app`）。
> 3. 在你的 **XChats Gemini Pro** 项目中，设置名为 `API_BASE_URL` 的环境变量，其值为部署 palm-proxy 时获得的域名 (`https://xxx.netlify.app`)。
> 4. 重新部署你的 **XChats Gemini Pro** 项目来完成配置。这应该可以解决问题。
>
> 感谢 [**antergone**](https://github.com/antergone/palm-netlify-proxy) 提供解决方案。

## 环境变量

你可以通过环境变量来控制网站。

| 名称 | 说明 | 必填 |
| --- | --- | --- |
| `GEMINI_API_KEY` | 你的 Gemini API 密钥。可以从[此处](https://makersuite.google.com/app/apikey) 获取。| **✔** |
| `API_BASE_URL` | Gemini API 的自定义基本 URL。点击[此处](https://github.com/jenkincs/xchats-gemini-pro/README_cn.md#solution-for-user-location-is-not-supported-for-the-api-use)查看何时使用这个。| ❌ |
| `HEAD_SCRIPTS` | 在页面的“</head>”之前注入分析或其他脚本 | ❌ |
| `PUBLIC_SECRET_KEY` | 项目的密文字符串。用于为 API 调用生成签名 | ❌ |
| `SITE_PASSWORD` | 为网站设置密码，支持用逗号分隔的多个密码。如果不设置，网站将允许公开访问 | ❌ |

## 本地运行

### 前期环境
1. **Node**: 检查你的开发环境和部署环境是否都在使用 `Node v18` 或更高版本。你可以使用 [nvm](https://github.com/nvm-sh/nvm) 在本地管理多个 `node` 版本。

   ```bash
    node -v
   ```

2. **PNPM**: 我们建议使用 [pnpm](https://pnpm.io/) 来管理依赖关系。如果从未安装过 pnpm，可以使用以下命令进行安装：

   ```bash
    npm i -g pnpm
   ```

3. **GEMINI_API_KEY**: 在运行此应用程序之前，你需要从 Google 获取 API 密钥。你可以前往 [https://makersuite.google.com/app/apikey](https://makersuite.google.com/app/apikey)，申请 API 密钥。

### 部署

1. 安装依赖

   ```bash
    pnpm install
   ```

2. 复制 `.env.example` 文件并重命名为 `.env`，并在 `.env` 文件中添加 [`GEMINI_API_KEY`](https://makersuite.google.com/app/apikey)。

   ```bash
    GEMINI_API_KEY=AIzaSy...
   ```

3. 运行应用程序，项目会在 `http://localhost:3000/` 上运行。

   ```bash
    pnpm run dev
   ```

## 鸣谢

本项目受到以下开源项目的启发，并以其为基础：

- [ChatGPT-Demo](https://github.com/anse-app/chatgpt-demo) - 基础代码库和功能。
- [GeminiProChat](https://github.com/babaohuang/GeminiProChat) - Gemini Pro API 相关代码和功能.

