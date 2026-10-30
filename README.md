<div align="center">

# Discord AutoTranslate

**Discord 多语言消息自动翻译模块 | Multilingual Discord message translation**

基于 [LibXposed API 102](https://github.com/libxposed/api)。

[源码与构建 Source](https://github.com/wxmyyds/DiscordAutoTranslate) · [Releases](https://github.com/Xposed-Modules-Repo/io.github.wxmyyds.discordautotranslate/releases)

[简体中文](#简体中文) | [English](#english)

</div>

---

## 简体中文

Discord AutoTranslate 是一个 LSPosed 模块，可将 Discord 消息翻译为设置的目标语言。

### 功能

- 自动翻译多语言消息，并按原位置替换正文
- 保留 Markdown 标题、列表、提及、表情和代码等结构
- 行内图标显示翻译状态，可切换原文与译文；失败时可重试
- 支持回复引用、编辑后重译、富 Embed 和投票卡片
- 支持 OpenAI-Compatible、OpenAI Responses、Anthropic Messages 协议；部分协议可使用流式响应
- 提供设置页、配置检查、测试连接和测试翻译

### 系统要求

- Android 8.0 或更新版本（API 26+）
- 支持 LibXposed API 102 的 LSPosed
- Discord 340.13 Stable（`versionCode` 340013）；其他版本不保证兼容

### 安装与配置

1. 从本仓库 [Releases](https://github.com/Xposed-Modules-Repo/io.github.wxmyyds.discordautotranslate/releases) 下载并安装 APK。
2. 打开模块设置，填写 API URL、密钥和模型并保存。可以在启用 LSPosed 模块前完成配置。
3. 在 LSPosed 中启用 **Discord AutoTranslate**，并将 `com.discord` 加入作用域。
4. 强制停止并重启 Discord。

模块启用前保存的配置会在 LSPosed service 可用后自动同步。设置页可使用「测试连接」和「测试翻译」检查配置。

### 隐私

消息正文会发送到你配置的翻译服务；消息正文与译文不会写入模块日志。API 密钥保存在本机私有配置中，并同步至 LSPosed remote preferences。

### 免责声明

本项目与 Discord Inc. 无关联。Discord 为 Discord Inc. 的商标。使用本模块可能违反 Discord 服务条款，请自行评估风险。

---

## English

Discord AutoTranslate is an LSPosed module that translates Discord messages into your selected target language.

### Features

- Automatically translate multilingual messages and replace their text in place
- Preserve Markdown structures such as headings, lists, mentions, emoji, and code
- Inline status icon with original/translation toggle and retry on failure
- Translate reply previews, edited messages, rich embeds, and poll cards
- Supports OpenAI-Compatible, OpenAI Responses, and Anthropic Messages APIs; streaming is available for supported protocols
- Includes a settings screen, configuration checks, connection testing, and translation testing

### Requirements

- Android 8.0 or later (API 26+)
- LSPosed with LibXposed API 102 support
- Discord 340.13 Stable (`versionCode` 340013); other versions are not guaranteed to work

### Installation and Setup

1. Download and install the APK from this repository's [Releases](https://github.com/Xposed-Modules-Repo/io.github.wxmyyds.discordautotranslate/releases).
2. Open the module settings, enter your API URL, key, and model, then save. You can do this before enabling the LSPosed module.
3. Enable **Discord AutoTranslate** in LSPosed and add `com.discord` to its scope.
4. Force-stop and restart Discord.

Settings saved before activation are synchronized automatically when the LSPosed service becomes available. Use **Test Connection** and **Test Translation** in the settings screen to verify your configuration.

### Privacy

Message content is sent to your configured translation service. Message content and translations are not written to the module logs. The API key is stored in the app's private storage and synchronized to LSPosed remote preferences.

### Disclaimer

This project is not affiliated with Discord Inc. Discord is a trademark of Discord Inc. Use of this module may violate Discord's Terms of Service; use it at your own discretion.
