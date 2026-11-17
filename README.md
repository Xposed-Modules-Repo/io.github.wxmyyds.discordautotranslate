<div align="center">

# Discord AutoTranslate

**LSPosed module for translating Discord messages**

[Latest module APK](https://github.com/Xposed-Modules-Repo/io.github.wxmyyds.discordautotranslate/releases/latest) · [Source code](https://github.com/wxmyyds/DiscordAutoTranslate) · [中文](#简体中文) | [English](#english)

</div>

---

## 简体中文

这是一个面向 Discord Android 的 LSPosed 模块。它通过你配置的翻译服务翻译消息，并尽量保留 Discord 原有的富文本结构。

### 下载

| 项目 | 下载 |
|---|---|
| 模块 APK | [本仓库最新 Release](https://github.com/Xposed-Modules-Repo/io.github.wxmyyds.discordautotranslate/releases/latest) |
| Discord 340.13 Stable（versionCode 340013）| [下载 Discord APK](https://1drv.ms/u/c/8ccaf25c5b0de4fb/IQC_FsEpTW9pQYQTZZX4XrKJAUecfhaG98Q7V0cyTK1MIqg?e=QTqag5) |
| Discord 352.17 Stable（versionCode 352017）| [下载 Discord APK](https://1drv.ms/u/c/8ccaf25c5b0de4fb/IQCbMILHoJWrQYp5eeZrkUTAAT85sbCHsOEhamnOonbWzCg?e=qh9gUL) |

### 功能概览

- 翻译消息正文，并提供原文／译文切换；失败时可手动重试。
- 尽可能保留 Markdown、链接、表情、提及和代码等宿主结构；无法安全回填时保留原文。
- 支持回复预览、富 Embed 和投票内容翻译。
- 支持 OpenAI Compatible、OpenAI Responses、Anthropic Messages 协议，以及设置页中的配置检查和翻译测试。
- 支持服务器／频道翻译范围：频道规则优先于服务器，未命中时使用默认策略（默认翻译或默认不翻译）。
- 自动翻译、项目日志和流式请求使用开关，名称与说明随当前设置状态更新。

### 安装

1. 从本仓库的 [Releases](https://github.com/Xposed-Modules-Repo/io.github.wxmyyds.discordautotranslate/releases/latest) 下载并安装**模块 APK**。
2. 打开模块设置，配置翻译服务地址、密钥、模型和目标语言，然后保存。
3. 在 LSPosed 中启用模块，并将 `com.discord` 加入作用域。
4. 强烈建议先使用“配置检查”“测试连接”或“测试翻译”确认配置与请求正常。
5. 强制停止并重新启动 Discord。

要求 Android 8.0（API 26）或更新版本，以及支持 LibXposed API 102 的 LSPosed。模块设置可以在启用模块前填写；LSPosed 服务可用后会同步设置。

### 翻译范围

在设置页打开“翻译范围”，选择默认策略后分别添加服务器、频道规则。频道规则覆盖服务器规则，删除规则即恢复继承；私信按频道规则及默认策略判定。在 Discord 开发者模式中复制服务器或频道 ID 后手动添加，编辑后需保存、同步并重启 Discord。模块不采集最近目录或真实名称。

### 隐私与免责声明

消息的可翻译内容会发送到你配置的翻译服务。请确认该服务符合你的隐私要求；不要在不可信的翻译服务中使用敏感消息。启用项目日志后，非 2xx 上游 HTTP 错误原文会记入日志，可能包含敏感信息，分享前请检查。本模块不是 Discord 官方产品，与 Discord Inc. 无关联。Discord 为其商标；使用本模块或第三方客户端安装包可能违反 Discord 服务条款，请自行评估风险。

---

## English

Discord AutoTranslate is an LSPosed module for Discord on Android. It sends translatable message content to the translation service you configure and preserves Discord's rich-text structure where it can do so safely.

### Downloads

| Item | Download |
|---|---|
| Module APK | [Latest release in this repository](https://github.com/Xposed-Modules-Repo/io.github.wxmyyds.discordautotranslate/releases/latest) |
| Discord 340.13 Stable (`versionCode` 340013) | [Download Discord APK](https://1drv.ms/u/c/8ccaf25c5b0de4fb/IQC_FsEpTW9pQYQTZZX4XrKJAUecfhaG98Q7V0cyTK1MIqg?e=QTqag5) |
| Discord 352.17 Stable (`versionCode` 352017) | [Download Discord APK](https://1drv.ms/u/c/8ccaf25c5b0de4fb/IQCbMILHoJWrQYp5eeZrkUTAAT85sbCHsOEhamnOonbWzCg?e=qh9gUL) |

### Features

- Translate message bodies with an original/translation toggle and manual retry on failure.
- Preserve Markdown, links, emoji, mentions, and code where safe; keep the original text when a translation cannot be mapped safely.
- Translate reply previews, rich embeds, and poll content.
- Supports OpenAI Compatible, OpenAI Responses, and Anthropic Messages, with configuration and translation tests in the settings screen.
- Server and channel translation scope: channel rules override server rules, then the default policy (translate by default or do not translate by default).
- Auto-translation, project logs, and streaming requests use switches whose names and descriptions follow the current settings.

### Translation scope

Open **Translation scope** in settings, choose the default policy, then add server and channel rules. Channel rules override server rules, and deleting a rule restores inheritance; direct messages use channel rules and the default policy. Copy a server or channel ID in Discord's developer mode and add it manually, then save, sync, and restart Discord. The module does not collect a recent-location directory or real names.

### Installation

1. Download and install the **module APK** from this repository's [latest release](https://github.com/Xposed-Modules-Repo/io.github.wxmyyds.discordautotranslate/releases/latest).
2. Open module settings, configure your translation endpoint, API key, model, and target language, then save.
3. Enable the module in LSPosed and add `com.discord` to its scope.
4. Strongly consider using **Check settings**, **Test connection**, or **Test translation** first.
5. Force-stop and restart Discord.

Requires Android 8.0 (API 26) or later and LSPosed with LibXposed API 102 support. Settings may be entered before enabling the module and are synchronized when the LSPosed service becomes available.

### Privacy and disclaimer

Translatable message content is sent to the translation service you configure. Review that service's privacy practices and do not use an untrusted service for sensitive messages. When project logs are enabled, raw non-2xx upstream HTTP errors are logged and may contain sensitive information; check before sharing. This is an unofficial project and is not affiliated with Discord Inc. Discord is a trademark of Discord Inc. Use of this module or third-party client APKs may violate Discord's Terms of Service; use them at your own discretion.
