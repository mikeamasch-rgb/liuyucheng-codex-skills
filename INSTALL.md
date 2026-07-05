# 安装与迁移

## 一、在新电脑上使用

### 1. 克隆仓库

```bash
git clone <your-repo-url>
```

### 2. 放置位置建议

建议放在桌面，目录名保持：

```txt
Desktop/liuyucheng-codex-skills
```

如果你更喜欢别的位置也可以，但项目里的 `AGENTS.md` 路径引用要同步调整。

### 3. 项目接入方式

在新项目里创建一个短版 `AGENTS.md`，只写：

- 项目目标
- 主流程
- 最小常驻规则
- 路由到本仓库

参考：

- `10-项目模板/短版AGENTS模板.md`

### 4. 可选：同步到 Codex 本地目录

如果后续你把某些模板做成真正的本地 skills，可放到：

```txt
%USERPROFILE%\\.codex\\skills
```

## 二、迁移时别忘的东西

除了这个仓库，你还应检查：

1. `C:\\Users\\admin\\.codex\\AGENTS.md`
2. `C:\\Users\\admin\\.codex\\skills`
3. `.env` / API keys
4. Docker / PostgreSQL
5. 代理客户端配置

## 三、迁移后最先做什么

1. 确认 `git` 和 `gh` 可用
2. 确认项目短版 `AGENTS.md` 路径有效
3. 运行一次项目 `build`
4. 验证数据库、代理、外部 API 是否可用
