# liuyucheng-codex-skills

这是一个个人长期复用的 Codex 规则与工程 skills 仓库。

目标：

1. 让不同项目共享稳定的工程原则
2. 减少每个项目都重新写长总则
3. 提供高频工程问题的可复用模板
4. 支持换电脑后快速恢复工作环境

## 仓库内容

- `00-核心总则/`
  所有项目通用的最小规则
- `10-项目模板/`
  新项目短版 `AGENTS.md` 模板
- `20-界面规则/`
  页面结构、结果区、边界控制
- `30-后端与接口/`
  API 和后端 contract 规则
- `40-数据库/`
  schema、迁移、字段与关系
- `50-验证与交付/`
  build、上线前一致性、交付标准
- `60-依赖与选型/`
  build-vs-buy、禁止手搓清单
- `70-skills设计/`
  skill 设计规则与工程类 skill 模板
- `80-runbooks/`
  常见工程流程的运行手册

## 如何在项目中使用

1. 新项目只保留一个短版 `AGENTS.md`
2. 项目 `AGENTS.md` 里引用本仓库，而不是复制一整套长规则
3. 按需读取专项文档，不要默认把所有文档都塞进常驻上下文

详细见：

- `README-怎么使用这套规则库.md`
- `README-什么时候必须问用户.md`
- `README-换电脑迁移.md`

## 推荐工作流

1. 先判断任务类型
2. 再读取对应文档
3. 先输出计划
4. 再编码
5. 最后验证

## 适合沉淀成 skill 的场景

- bug-fix
- external-api-debug
- delivery-readiness
- feature-build
- code-review
- refactor

这些模板在 `70-skills设计/` 下。
