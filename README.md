# NSFC Review — AI+自然科学交叉方向 青年基金函评自查

一个基于 [Claude Code](https://docs.anthropic.com/en/docs/claude-code) 的技能（Skill），帮助国家自然科学基金（NSFC）申请人在提交前，以严格函评专家的视角对申请书进行自查。

## 特性

- **五关递进审查**：科学问题 → 交叉融合 → 方法路线 → 验证方案 → 创新性与独立性，层层深入
- **文献对标驱动**：每关审查前主动联网检索文献，每关至少引用 3-5 篇，总计不少于 15 篇，绝不编造引用
- **六段式评审报告**：综合评价（A/B/C 评级）、主要缺陷、修改建议、三张图/三张表、风险评估、文献对标报告
- **全学科覆盖**：AI+物理、AI+化学、AI+生物、AI+地球科学、AI+材料、AI+能源、AI+环境等，自动识别学科方向

## 安装

将技能文件复制到你项目的 `.claude/skills/` 目录下：

```bash
# 方式一：直接克隆
git clone https://github.com/jinyh/nsfc-review.git
mkdir -p <你的项目>/.claude/skills/nsfc-review
cp -r nsfc-review/skills/nsfc-review/* <你的项目>/.claude/skills/nsfc-review/

# 方式二：作为 git submodule（方便后续更新）
cd <你的项目>
git submodule add https://github.com/jinyh/nsfc-review.git .claude/skills/nsfc-review
```

最终目录结构：

```
你的项目/
└── .claude/
    └── skills/
        └── nsfc-review/
            ├── SKILL.md
            └── references/
                └── review-prompt.md
```

## 使用

在项目目录下启动 Claude Code，然后提供你的申请书即可：

```
# 提供 PDF 文件
请帮我评审这份基金申请书：/path/to/申请书.pdf

# 或直接贴入文本
请模拟函评以下立项依据：
（粘贴申请书内容）
```

## 审查框架

| 关卡 | 审查焦点 | 文献对标重点 |
|------|----------|-------------|
| 第一关 | 科学问题是否"真问题" | 研究现状、open problems、已有解决方案 |
| 第二关 | 交叉融合是否"有内核" | 已有融合范式、领域知识嵌入方法 |
| 第三关 | 方法路线是否站得住 | 同类方法 benchmark、已知局限性 |
| 第四关 | 验证方案是否可信 | 同类研究验证标准、评价指标惯例 |
| 第五关 | 创新性与独立性 | 最相关文献逐篇对比 |

## 评级标准

- **A（优先资助）**：科学问题真实、交叉融合有内核、方法路线扎实、验证方案可信、创新性明确
- **B（可资助）**：整体合理但存在可修复的缺陷
- **C（不予资助）**：存在致命缺陷

## 前置要求

- [Claude Code](https://docs.anthropic.com/en/docs/claude-code) CLI 工具
- Claude Code 需要能够联网检索文献（用于文献对标）

## 许可证

MIT
