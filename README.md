# Agent Skills 集合

- **GitHub：** [github.com/Go7hic/skills](https://github.com/Go7hic/skills)
- **说明：** 一组给 **Cursor / Codex / Claude Code** 等环境用的 **Agent Skills**（`SKILL.md` + 可选 `references/`）。每个子目录是一个独立技能，由编排器按 `description` 元数据匹配用户任务后加载。

## 目录结构

```
skills/
├── design-prompts-library/   # 总览：如何从 Design Prompts 系列里选风格
├── design-prompt-*/          # 各视觉/落地页风格（见下表）
└── favicon-so/               # favicon.so API 参考
```

## 通过 [skills.sh CLI](https://skills.sh/docs/cli) 安装本仓库

无需全局安装，在项目或任意目录执行：

```bash
npx skills add Go7hic/skills
```

对应源码仓库：[Go7hic/skills](https://github.com/Go7hic/skills)（`git@github.com:Go7hic/skills.git`）。

CLI 行为与更多参数见官方文档：[CLI Reference](https://skills.sh/docs/cli)。

**遥测：** 默认会上报匿名使用数据。关闭：

```bash
export DISABLE_TELEMETRY=1
```

## 安装方式（手动或其它工具）

- **Cursor**：将需要的技能文件夹复制或链接到 Cursor 配置的 skills 目录（例如用户级 `~/.cursor/skills/`），确保编排器能扫描到 `SKILL.md`。
- **Codex**：按官方说明安装到 `$CODEX_HOME/skills`（可用 [skill-installer](https://github.com/openai/codex) 等工具从路径或仓库拉取）。
- **Claude Code**：使用平台的 Skill 工具/配置，指向本仓库中对应子目录。

具体路径以你当前客户端文档为准。

## 技能一览

### Design Prompts 库

| 技能 ID | 用途简述 |
|--------|----------|
| `design-prompts-library` | 帮用户从 Design Prompts 系列里选风格、浏览美学方向 |
| `design-prompt-academia` | Academia 风格落地页/界面 |
| `design-prompt-art-deco` | Art Deco |
| `design-prompt-bauhaus` | Bauhaus |
| `design-prompt-bold-typography` | Bold Typography |
| `design-prompt-botanical` | Botanical / Organic Serif |
| `design-prompt-claymorphism` | Clay / Claymorphism |
| `design-prompt-cyberpunk` | Cyberpunk |
| `design-prompt-enterprise` | Corporate Trust |
| `design-prompt-flat-design` | Flat Design |
| `design-prompt-industrial` | Industrial |
| `design-prompt-kinetic` | Kinetic |
| `design-prompt-luxury` | Luxury |
| `design-prompt-material-design` | Material |
| `design-prompt-maximalism` | Maximalism |
| `design-prompt-minimal-dark` | Simple Dark |
| `design-prompt-modern-dark` | Modern Dark |
| `design-prompt-monochrome` | Monochrome |
| `design-prompt-neo-brutalism` | Neo-brutalism |
| `design-prompt-neumorphism` | Neumorphism |
| `design-prompt-newsprint` | Newsprint |
| `design-prompt-organic` | Organic / Natural |
| `design-prompt-playful-geometric` | Playful Geometric |
| `design-prompt-professional` | Business Style |
| `design-prompt-retro` | Retro |
| `design-prompt-saas` | Tech Style / SaaS |
| `design-prompt-sketch` | Hand-Drawn / Sketch |
| `design-prompt-swiss-minimalist` | Swiss |
| `design-prompt-terminal` | Terminal CLI |
| `design-prompt-vaporwave` | Vaporwave |
| `design-prompt-web3` | Crypto / Web3 |

实现细节、色板与约束以各技能目录下的 `SKILL.md` 及 `references/style.md`（若有）为准。

### 其他

| 技能 ID | 用途简述 |
|--------|----------|
| `favicon-so` | [favicon.so](https://favicon.so) 的抓取与转图标包 API 说明；对接路由、调试或扩 endpoint 时用 |

## 文件约定

- 每个技能根目录必有 **`SKILL.md`**，顶部 YAML frontmatter 含 `name`、`description`（有的含 `license` / `metadata`）。
- 可选 **`references/`**：长文规范、风格说明等，由 `SKILL.md` 引用。

## 许可

MIT

