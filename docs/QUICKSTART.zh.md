# Seedance 2.0 Skill OS 快速入门

> 版本 6.6.0 · 从安装到写出第一个「有导演意图」的提示词，约 5 分钟。
> 完整文档见 [README](../README.md) 与 [中文指南](README.zh.md)。

## 这是什么

Seedance 2.0 Skill OS 是一个 agent skill，它像导演一样调度 Seedance 2.0，而不是堆砌形容词。核心只有一条：**导演这个模型，别去抠画面细节。** 你描述场景在「做什么」，技能把这份意图编译成可直接使用的提示词。

## 1. 安装（约 5 分钟）

把本仓库作为**一个**名为 `seedance-20` 的根技能安装；它的子技能和参考会按相对路径自动加载。

**Codex（有一键安装脚本）：**

```bash
python scripts/install_codex_skill.py --force
```

脚本会把仓库复制到 `~/.codex/skills/seedance-20`（或 `$CODEX_HOME/skills/seedance-20`）。重启 Codex，然后调用 `$seedance-20`。

**从 GitHub 安装（若你的客户端支持按仓库地址安装）：**

```text
https://github.com/Emily2040/seedance-2.0
```

**手动复制（其它客户端）：** 把整个文件夹复制到你客户端的技能目录，保持名字 `seedance-20`。常见目标路径（请在你自己的客户端里核实，这不是通用保证）见 [README 安装表](../README.md#install)：例如 Claude Code `.claude/skills/`、Cursor `.cursor/skills/`、GitHub Copilot `.github/skills/`、Windsurf `.windsurf/skills/`。

> 安全第一：只把它安装到你信任的 agent 客户端。在陌生或第三方 agent 里使用前，请先读 [SECURITY.md](../SECURITY.md)。

## 2. 按场景选技能

| 你手上有… | 先加载 |
|---|---|
| 一个模糊的想法 | `seedance-interview` |
| 一个清晰的场景 | `seedance-prompt` |
| 多段连续剧情 | `seedance-sequence` |
| 已接受、要接着拍的片段 | `seedance-continuation` |
| 效果差或被拦截的结果 | `seedance-troubleshoot` |
| 涉及角色、品牌、明星或真人 | `seedance-copyright` |

## 3. 动笔前先「导演」——四个问题

1. **这场戏在做什么？** 一个转折、一次揭示、一种情绪，还是一次展示？
2. **镜头怎么说这件事？** 远景表现孤立、特写看脸、推镜带出顿悟。
3. **光在做什么？** 时间、软硬、冷暖——都为这个意图服务。
4. **声音在做什么？** 近乎无声、一处环境细节，或一句台词。

## 4. 一个例子

**堆砌（弱）：**

```
史诗级电影感镜头，一个女人在读信，很有情绪，光很美，4K
```

**导演（强）：**

```
中近景，平视；她放下信，双手静止，一个缓慢推镜到来；柔和的窗光让她的脸保持平实；近乎无声，只有一声椅子摩擦。
```

## 5. 两条省素材的规则

- **参考标签原样保留**——`[Image1]`、`[Video1]`、`[Audio1]`、`@图1`、`@视频1`。绝不翻译或改写它们。
- **别想一次生成整段故事。** 先生成 Clip 01，观察它「实际」怎么结束，再用真实结尾写 Clip 02（`seedance-continuation`）。

## 6. 安全

- **内容安全：** 如果想法涉及受保护角色、明星、品牌、logo、歌曲，或真人的脸/声音，不要换个语言把它藏起来——用 `seedance-copyright` 改写成原创、已授权或后期替代的方案。
- **agent 安全：** 本包**不发起任何网络请求，也不含遥测**；脚本是确定性的、离线运行。绝不要把 API 密钥、账号 cookie 或私有素材粘贴进你不信任的 agent。详见 [SECURITY.md](../SECURITY.md)。

## 7. 深入了解

- `references/directing-engine.md` — 读懂场景，选定唯一意图（35 个完整类型示例）。
- `references/capability-map.md` — 顺着模型强项、绕开已知限制来设计。
- `references/api-workflow.md` — API、提供商、价格、模型 ID（均标注来源日期）。
- `references/examples-by-mode.md` — T2V、I2V、V2V、R2V、FLF2V、编辑、延长的示例。

---

其它语言：[English](QUICKSTART.md) · [日本語](QUICKSTART.ja.md) · [한국어](QUICKSTART.ko.md) · [Español](QUICKSTART.es.md) · [Русский](QUICKSTART.ru.md)
