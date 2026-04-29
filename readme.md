# costory

Costory is a markdown-based AI story format specification designed for both human creators and AI systems. It shifts prompt writing from the traditional `{{char}}` / `{{user}}` dialogue perspective to a writer-centric perspective, where the author can define world settings, shape narrative style, and drive scene progression with structured plain text.

Costory 是一种基于 Markdown 的 AI 剧本格式规范，面向人类创作者与 AI 系统共同使用。它将传统的 `{{char}}` / `{{user}}` 对话提示视角，转变为“编剧视角”，让作者可以用结构化纯文本定义世界设定、控制叙事风格并推动场景发展。

Costory is built for readability first and machine parsing second. Writers can edit scripts as normal markdown documents, while programs can still parse stable fields through fixed heading rules, making scripts easier to maintain, share, and run across different tools.

Costory 的设计理念是“先可读，再可解析”。创作者可以像写普通 Markdown 一样编辑剧本，程序则通过固定标题规则稳定提取字段，使脚本更易维护、共享，并可在不同工具中运行。

## Online Demo

<https://costory.online>

## Parsing Rules

Only second-level headings (`##`) are recognized as key-value field boundaries in Costory 1.0. A heading can use either Chinese or English keyword variants, and the parser normalizes matched fields into English keys in the final structured object (such as JSON).

在 Costory 1.0 中，只有二级标题（`##`）会被识别为键值字段边界。标题可使用中文或英文关键字，解析器会将命中字段统一归一化为英文 key，最终输出为结构化对象（如 JSON）。

## Core Script Keys (1.0)

The core narrative keys are `_background_setting_`, `_writer_style_`, `_prologue_leadin_`, `_player_name_`, and `_player_desc_`, with corresponding Chinese forms `_背景设定_`, `_编剧风格_`, `_序幕引言_`, `_玩家名称_`, and `_玩家描述_`.

核心剧情字段包括 `_background_setting_`、`_writer_style_`、`_prologue_leadin_`、`_player_name_`、`_player_desc_`，对应中文形式分别为 `_背景设定_`、`_编剧风格_`、`_序幕引言_`、`_玩家名称_`、`_玩家描述_`。

## Story Metadata Keys (1.0)

Costory also supports story metadata keys: `_story_name_`, `_story_intro_`, `_story_tag_`, `_author_name_`, `_author_email_`, `_author_link_`, `_author_intro_`, `_keeper_name_`, `_keeper_email_`, `_keeper_intro_`, and `_keeper_link_`, each of which also has a Chinese heading variant.

Costory 同时支持故事元信息字段：`_story_name_`、`_story_intro_`、`_story_tag_`、`_author_name_`、`_author_email_`、`_author_link_`、`_author_intro_`、`_keeper_name_`、`_keeper_email_`、`_keeper_intro_`、`_keeper_link_`，每个字段都可使用对应中文标题。

## Minimal Example

```markdown
# costory 1.0 >>>
more: https://costory.online

## _background_setting_ >>>
A parallel fantasy world with inherited lore and characters.

## _writer_style_ >>>
Classical prose with suspense and layered plots.

## _prologue_leadin_ >>>
The story begins with an unexpected visitor.

## _player_name_ >>>
Wukong

## _player_desc_ >>>
```

```markdown
# costory 1.0 >>>
more: https://costory.online

## _背景设定_ >>>
一个平行幻想世界，沿用既有世界观与角色。

## _编剧风格_ >>>
古典文风，偏悬疑与层层推进。

## _序幕引言_ >>>
故事从一位意外来客登场开始。

## _玩家名称_ >>>
悟空

## _玩家描述_ >>>
```

Recommended file extensions are `.costory.md` or `.costory.txt` so tools can identify and load scripts consistently.

建议使用 `.costory.md` 或 `.costory.txt` 作为文件后缀，以便工具更稳定地识别和加载剧本。