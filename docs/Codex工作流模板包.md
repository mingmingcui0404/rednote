# Codex 工作流模板包

适用对象：内容创作者、独立开发者、运营团队、知识产品团队，以及想把重复工作沉淀成 AI 工作流的人。

使用方式：

1. 先选择一个与你当前项目最接近的 `AGENTS.md` 模板。
2. 再选择一个对应任务的 Skill 模板。
3. 用高阶提示词启动 Codex 执行具体任务。
4. 按检查清单确认风险动作、发布内容和交付质量。

---

## 一、5 个 AGENTS.md 模板

### 模板 1：通用项目协作版

```md
# AGENTS.md

## 项目概览

这是一个用于 [项目用途] 的项目。请先阅读相关文件，再进行修改。

## 工作原则

- 优先沿用现有代码结构、命名方式和文件组织。
- 不做与当前任务无关的重构。
- 修改前先理解上下文，避免只改表面问题。
- 如果发现用户未提及但会影响任务完成的问题，可以一并指出。

## 常用命令

- 安装依赖：`[填写命令]`
- 本地运行：`[填写命令]`
- 语法检查：`[填写命令]`
- 测试：`[填写命令]`
- 构建：`[填写命令]`

## 编辑规则

- 优先小范围修改。
- 不删除用户已有内容，除非任务明确要求。
- 新增文件要命名清晰，避免临时文件污染项目。
- 重要变更后说明修改位置和验证结果。

## 验证要求

完成修改后，至少运行最轻量的可用检查命令。
如果无法运行检查，需要说明原因。

## 高风险动作

以下动作必须先获得用户确认：

- 删除文件
- 发布内容
- 提交表单
- 推送代码
- 修改线上配置
```

### 模板 2：前端网页项目版

```md
# AGENTS.md

## 项目类型

这是一个前端网页项目。请优先关注用户体验、响应式布局、可访问性和视觉一致性。

## 设计原则

- 第一屏应直接呈现核心功能，不做无意义的营销页。
- UI 保持清晰、稳定、可扫描。
- 文字不能溢出、遮挡或在移动端重叠。
- 组件状态要完整：默认、hover、禁用、空状态、加载状态。

## 技术约定

- HTML 结构保持语义化。
- CSS 优先复用现有变量和类名。
- JavaScript 保持简单可读，避免无必要框架。
- 图标、按钮、表单控件使用统一风格。

## 常用命令

- 语法检查：`node --check app.js`
- 本地预览：直接打开 `index.html` 或使用项目已有 dev server。

## 修改要求

- 修改前先阅读 `index.html`、`styles.css`、`app.js`。
- 如果新增内容涉及页面默认数据，要同步更新本地存储 key，避免旧缓存遮挡新内容。
- 重要前端修改后，尽量用浏览器打开页面验证。

## 输出说明

完成后说明：

- 修改了哪些文件
- 新增了哪些功能或内容
- 是否完成语法检查或浏览器验证
```

### 模板 3：内容运营项目版

```md
# AGENTS.md

## 项目定位

这是一个内容运营项目，重点是选题、文案、排版、发布和复盘。

## 内容风格

- 语言自然，适合小红书/公众号/短视频平台阅读。
- 标题要有吸引力，但避免夸大承诺。
- 正文要有真实场景、具体方法和可执行建议。
- 标签要相关，不堆砌无关热词。

## 工作流程

1. 明确目标用户。
2. 提炼痛点或需求。
3. 生成标题、开头、正文、标签。
4. 给出封面建议和配图建议。
5. 补充发布前检查清单。
6. 如需发布，先准备草稿，最终发布前必须确认。

## 合规边界

- 不自动点赞、收藏、评论或制造虚假互动。
- 不生成虚假经历、虚假数据、虚假背书。
- 涉及医疗、金融、法律等内容时必须提示风险。
- 发布前需人工确认平台规则和事实准确性。

## 输出格式

每篇内容至少包含：

- 标题
- 开头钩子
- 正文
- 标签
- 封面建议
- 评论区互动建议
```

### 模板 4：自动化脚本项目版

```md
# AGENTS.md

## 项目类型

这是一个自动化脚本项目。目标是把重复流程变成稳定、可复用、可验证的脚本。

## 编写原则

- 优先使用标准库和项目已有工具。
- 参数、路径、权限边界要清楚。
- 默认不执行破坏性操作。
- 对外部系统的写入、提交、发布必须确认。

## 脚本要求

- 支持清晰的输入参数。
- 输出可读日志。
- 对失败情况给出明确错误信息。
- 避免把密钥、cookie、token 写入日志或文件。

## 验证要求

- 能 dry-run 的脚本优先支持 dry-run。
- 修改后至少跑一次最小样例。
- 如果依赖网络、账号或外部权限，需要说明前置条件。

## 禁止事项

- 不读取或导出用户 cookie。
- 不绕过验证码、风控或平台限制。
- 不批量刷互动。
- 不静默删除重要文件。
```

### 模板 5：知识产品项目版

```md
# AGENTS.md

## 项目定位

这是一个知识产品项目，目标是把经验、流程和模板整理成可销售的交付物。

## 内容原则

- 先解决一个明确问题，再扩展成体系。
- 每个模块都要有模板、案例或检查清单。
- 避免空泛概念，优先给可复制的步骤。
- 输出内容要适合后续转成 PDF、课程讲义或社群资料。

## 交付结构

推荐使用：

1. 使用说明
2. 核心方法
3. 模板
4. 示例
5. 常见问题
6. 检查清单

## 编辑规则

- 文档标题清晰。
- 层级不要过深。
- 保留可直接复制的代码块或模板块。
- 每个模板前说明适用场景。

## 输出要求

完成后说明：

- 文档保存位置
- 包含哪些模块
- 后续可如何包装成产品
```

---

## 二、5 个 Skill 模板

### Skill 模板 1：小红书文章生成与发布准备

```md
---
name: xhs-content-publisher
description: Generate Xiaohongshu-style posts from a topic or direction, format them for publishing, prepare cover ideas and hashtags, update a local publishing workspace when available, and use Chrome only to prepare a logged-in publishing draft. Use when the user asks to create, format, stage, or prepare Xiaohongshu content.
---

# Xiaohongshu Content Publisher

## Workflow

1. Understand the user's direction, product, audience, and desired tone.
2. Generate a Xiaohongshu-ready post:
   - Title
   - Hook
   - Body
   - Hashtags
   - Cover idea
   - Comment interaction plan
3. If a local publishing workspace exists, add the post as the first draft.
4. If Chrome publishing is requested, open the logged-in Xiaohongshu creator page.
5. Upload only user-provided or approved images.
6. Fill the draft fields.
7. Stop before final publishing unless the user explicitly confirms.

## Writing Rules

- Keep paragraphs short.
- Avoid exaggerated claims.
- Prefer concrete scenes and personal observations.
- Tags must be relevant.

## Safety

- Do not like, collect, comment, follow, or simulate user engagement.
- Do not publish without confirmation.
- Do not inspect cookies or tokens.
```

### Skill 模板 2：Codex 项目改造助手

```md
---
name: codex-project-refactor
description: Help Codex inspect a local project, identify the smallest safe implementation path, edit files, run checks, and summarize changes. Use when the user asks to modify, debug, refactor, or improve a local code project.
---

# Codex Project Refactor

## Workflow

1. Inspect project structure with fast file search.
2. Read the smallest relevant set of files.
3. Identify existing patterns before editing.
4. Make scoped changes.
5. Run available checks.
6. Summarize what changed and what could not be verified.

## Rules

- Do not rewrite unrelated files.
- Do not remove user changes.
- Prefer existing helpers and conventions.
- Add comments only when they clarify non-obvious logic.

## Verification

Use the lightest meaningful check:

- Syntax check
- Unit test
- Build
- Browser verification
```

### Skill 模板 3：知识产品打包助手

```md
---
name: knowledge-product-packager
description: Turn a rough topic, workflow, or expertise area into a structured knowledge product with modules, templates, examples, exercises, and checklists. Use when the user asks to create a course outline, template pack, paid guide, workshop, or training material.
---

# Knowledge Product Packager

## Workflow

1. Define the target user and paid promise.
2. Split the product into modules.
3. For each module, create:
   - Concept
   - Use case
   - Template
   - Example
   - Exercise
   - Checklist
4. Add packaging suggestions:
   - PDF
   - Notion
   - Video course
   - Live training
   - Consulting offer

## Output Rules

- Make content actionable.
- Avoid vague motivational text.
- Include reusable templates.
- Use clear headings and copy-ready blocks.
```

### Skill 模板 4：浏览器发布审核助手

```md
---
name: browser-publish-reviewer
description: Review content before publishing through Browser or Chrome, check title/body/tags/assets/compliance, prepare the draft, and require user confirmation before external publication. Use when publishing to a website, CMS, social platform, or creator backend.
---

# Browser Publish Reviewer

## Workflow

1. Review the content for clarity, compliance, and formatting.
2. Confirm required assets exist.
3. Open the publishing page only when necessary.
4. Fill form fields carefully.
5. Check preview and visibility settings.
6. Ask for confirmation before final publish.

## Checklist

- Title is accurate.
- Body has no obvious factual issue.
- Tags are relevant.
- Cover image is uploaded.
- Visibility is correct.
- No private information is included.

## Boundaries

- Do not bypass CAPTCHA.
- Do not submit payment or sensitive forms.
- Do not publish without explicit confirmation.
```

### Skill 模板 5：多 Agent 协作编排

```md
---
name: multi-agent-workflow-orchestrator
description: Decompose a complex task into specialist agent roles, assign research/execution/review responsibilities, merge outputs, and produce a final decision or deliverable. Use when a task needs research, planning, implementation, review, or multiple independent perspectives.
---

# Multi-Agent Workflow Orchestrator

## Workflow

1. Define the final deliverable.
2. Split the work into roles:
   - Research agent
   - Builder agent
   - Reviewer agent
   - Editor agent
3. Give each role a narrow task and clear output format.
4. Keep context separated where useful.
5. Merge findings.
6. Resolve conflicts.
7. Produce the final answer or artifact.

## Role Templates

### Research Agent
Find facts, examples, and constraints.

### Builder Agent
Create the draft, code, workflow, or asset.

### Reviewer Agent
Identify risks, missing pieces, and weak assumptions.

### Editor Agent
Polish structure, clarity, and user-facing language.

## Rules

- Do not create agents without a clear reason.
- Keep one final owner for decisions.
- Review outputs critically before merging.
```

---

## 三、20 条 Codex 高阶提示词

1. 先阅读相关文件，理解现有结构和命名方式，再给出最小修改方案并执行。

2. 请不要直接重构整个项目，只围绕我提出的问题做最小必要改动。

3. 修改前先列出你会查看哪些文件，以及为什么这些文件相关。

4. 如果发现我的需求里有风险或歧义，请先说明你的假设，然后继续用最稳妥的方案执行。

5. 请把这个重复流程整理成一个可复用的 Skill，包括触发条件、步骤、安全边界和验证方法。

6. 帮我为这个项目写一版 AGENTS.md，让 Codex 以后能自动理解项目结构、运行命令和编辑规则。

7. 请把这个任务拆成：信息收集、实现、验证、交付总结四个阶段完成。

8. 你可以主动运行必要的检查命令，但涉及删除、发布、提交、推送的动作必须先问我。

9. 请先判断这件事适合写进提示词、AGENTS.md、Skill、插件还是自动化任务，并说明理由。

10. 请为这个功能补一个最小可验证版本，不要一次性做复杂系统。

11. 请从用户体验角度检查这个页面，重点看移动端、文字溢出、按钮状态和空状态。

12. 请用 code review 的方式审查这段改动，优先指出 bug、风险和缺少的测试。

13. 请把这个内容改成小红书风格：标题有钩子，正文短段落，结尾有互动引导，但不要夸大。

14. 请把这个知识点拆成系列化内容，每篇都要有标题、用户痛点、正文结构和引流点。

15. 请把这套经验打包成一个可售卖模板包，包含模板、案例、练习和检查清单。

16. 请设计一个多 Agent 协作方案：一个负责研究，一个负责执行，一个负责审核，最后由你合并。

17. 请在实现后告诉我：改了什么、为什么这样改、如何验证、还有什么残余风险。

18. 请把所有外部平台操作停在最终确认前，不要替我点击发布、提交或付款。

19. 请检查当前工作区是否有现成工具或依赖，优先使用已有能力，不要重复造轮子。

20. 请把这个任务沉淀成标准工作流，输出流程图式步骤、输入要求、输出格式和检查点。

---

## 四、小红书运营工作流案例

### 案例名称

用 Codex 搭建“小红书内容生成与发布准备工作流”

### 适用场景

适合个人 IP、知识博主、AI 工具博主、运营团队，用来把选题、写作、排版、封面、发布和复盘串成固定流程。

### 工作流总览

```text
选题方向
  ↓
目标用户分析
  ↓
生成标题/正文/标签
  ↓
生成封面建议或封面图
  ↓
写入发布工作台
  ↓
人工检查
  ↓
Chrome 打开发布后台
  ↓
填入草稿
  ↓
最终确认后发布
  ↓
记录评论和数据
  ↓
生成下一篇选题
```

### Step 1：输入选题方向

示例输入：

```text
帮我写一篇关于 Codex 高阶使用方法的小红书文章，面向想提升效率的内容创作者和独立开发者。
```

需要补充的信息：

- 目标用户是谁
- 文章想解决什么问题
- 风格是干货、故事、观点还是教程
- 是否需要发布到小红书

### Step 2：生成小红书文章

输出结构：

```md
标题：
Codex 高阶用法：别把它只当成会写代码的聊天框

开头：
真正好用的 Codex，不是你每次都把需求讲一遍，而是让它逐渐拥有你的工作方法。

正文：
1. 把项目规则写进 AGENTS.md
2. 把重复流程沉淀成 Skill
3. 工具要分清楚
4. 让它先读再改
5. 危险动作设确认点

标签：
#Codex #AI工具 #效率工具 #工作流 #自动化
```

### Step 3：生成封面建议

封面文案：

```text
Codex 高阶用法
别把它只当成聊天框
```

视觉建议：

- 竖版 3:4
- 背景简洁
- 标题大字
- 辅助关键词：AGENTS.md / Skill / MCP / Chrome

### Step 4：写入发布工作台

数据字段：

```js
{
  title: "Codex 高阶用法：别把它只当成会写代码的聊天框",
  hook: "真正好用的 Codex，不是你每次都把需求讲一遍，而是让它逐渐拥有你的工作方法。",
  body: ["正文段落 1", "正文段落 2", "正文段落 3"],
  tags: ["Codex", "AI工具", "效率工具", "工作流", "自动化"],
  status: "已排期",
  publishDate: "2026-06-24",
  assets: ["封面图路径"],
  engagementTasks: ["回复评论区问题", "整理下一篇选题"]
}
```

### Step 5：发布前人工审核

检查重点：

- 标题是否夸大
- 正文是否超过平台字数限制
- 标签是否相关
- 封面是否清晰
- 是否涉及无法证实的功能承诺
- 是否需要补充免责声明

### Step 6：Chrome 发布准备

Codex 可以做：

- 打开已登录的小红书发布后台
- 上传用户提供的封面图
- 填写标题和正文
- 检查预览
- 停在发布前等待确认

Codex 不应该做：

- 自动点赞
- 自动收藏
- 自动评论
- 未确认直接发布
- 绕过验证码或风控

### Step 7：发布后复盘

记录指标：

- 曝光
- 点击
- 点赞
- 收藏
- 评论
- 关注转化
- 评论区高频问题

复盘模板：

```md
发布时间：
标题：
选题类型：
封面风格：
点赞：
收藏：
评论：
最有价值评论：
下一篇延展选题：
```

---

## 五、发布前检查清单

### 内容检查

- [ ] 标题准确，没有夸大承诺。
- [ ] 开头 3 秒内能说明用户为什么要看。
- [ ] 正文有具体场景，不只是空泛观点。
- [ ] 每段适合手机阅读，没有过长段落。
- [ ] 结尾有自然互动引导。

### 合规检查

- [ ] 没有虚假经历、虚假数据、虚假背书。
- [ ] 没有医疗、金融、法律等高风险绝对建议。
- [ ] 没有侵犯他人版权的图片、截图或文案。
- [ ] 没有诱导刷赞、刷收藏、刷评论。
- [ ] 没有泄露账号、客户、项目或个人隐私。

### 平台检查

- [ ] 字数在平台限制内。
- [ ] 标签与内容相关。
- [ ] 封面图清晰，手机端可读。
- [ ] 可见性设置正确。
- [ ] 如需定时发布，时间已确认。

### Codex 操作检查

- [ ] Codex 已完成草稿准备。
- [ ] 发布页面内容已人工预览。
- [ ] 最终发布动作已由用户明确确认。
- [ ] 没有自动点赞、收藏或评论。
- [ ] 发布后记录数据并保存复盘。

---

## 六、模板包售卖页文案参考

### 产品名

《Codex 工作流模板包：把重复工作变成 AI 执行系统》

### 一句话卖点

不是再给你 100 条提示词，而是帮你搭一套能长期复用的 Codex 工作流。

### 适合谁

- 想用 Codex 提升效率的人
- 内容创作者
- 独立开发者
- 小团队负责人
- 想把经验产品化的知识博主

### 你会得到

- 5 个 AGENTS.md 模板
- 5 个 Skill 模板
- 20 条高阶提示词
- 1 套小红书运营工作流案例
- 1 份发布前检查清单

### 不适合谁

- 只想要一键暴富方法的人
- 不愿意整理自己工作流程的人
- 想用 AI 批量刷互动或绕过平台规则的人

### 交付形式

- Markdown 文档
- 可转 PDF
- 可复制模板
- 可二次改造成 Notion 模板或课程讲义
