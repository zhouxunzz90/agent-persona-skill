#  agent-persona-skill

这是一个skills 仓库，用于存放可复用的技能包与相关配置。

**Skills**
1. `agent-persona-creation`：根据中文“人格设定模版”和“三层认知架构”生成或完善 AI 角色设定文档。路径：`skills/agent-persona-creation`

**使用方式**
1. 进入 `skills/agent-persona-creation` 阅读 `SKILL.md`
2. 按 `SKILL.md` 指引加载 `references/` 中的规则与模板
3. 按需调用 skill，生成或完善角色设定文档

**目录结构**
```text
skills/
  agent-persona-creation/
    SKILL.md
    agents/
      openai.yaml
    references/
      persona_logic.md
      persona_template.md
```
