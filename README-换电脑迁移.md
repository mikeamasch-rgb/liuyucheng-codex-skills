# 换电脑迁移

这份文档用于说明：

1. 这套规则库换电脑后怎么恢复
2. 项目代码换电脑后怎么恢复
3. `.env` 和代理这些关键配置怎么重新落地

## 一、需要迁移的三层内容

### 1. 规则库仓库

克隆：

```bash
git clone https://github.com/mikeamasch-rgb/liuyucheng-codex-skills.git
```

建议放在：

```txt
Desktop/liuyucheng-codex-skills
```

### 2. 具体项目仓库

例如当前项目：

```bash
git clone https://github.com/mikeamasch-rgb/google-maps-leads.git
```

### 3. 本地 Codex 配置与 skills

如果你还需要同步本机级配置，检查：

- `C:\\Users\\<你>\\.codex\\AGENTS.md`
- `C:\\Users\\<你>\\.codex\\skills`

## 二、换电脑后项目怎么恢复

### 第一步：安装基础环境

至少确认有：

- Node / npm
- Git
- GitHub CLI（可选，但推荐）
- Docker（如果项目依赖容器）
- PostgreSQL（或项目要求的数据库）
- 代理客户端（如果需要访问 Google）

### 第二步：克隆项目

```bash
git clone https://github.com/mikeamasch-rgb/google-maps-leads.git
```

### 第三步：安装依赖

```bash
npm install
```

### 第四步：恢复 `.env`

先复制：

```bash
copy .env.example .env
```

然后填真实值。

至少确认这些变量：

- `DATABASE_URL`
- `GOOGLE_MAPS_API_KEY`
- `GOOGLE_PLACES_PROXY_URL`
- `ERP_BASE_URL`
- `ERP_TOKEN`

其中当前项目真正需要的是：

- `DATABASE_URL`
- `GOOGLE_MAPS_API_KEY`
- `GOOGLE_PLACES_PROXY_URL`

ERP 相关目前可为空。

## 三、代理配置怎么迁移

如果新电脑访问 Google 也需要代理：

1. 先确认代理客户端是否在运行
2. 再确认实际本地端口和协议
3. 不要默认旧电脑的端口一定一样

例如：

```env
GOOGLE_PLACES_PROXY_URL="http://127.0.0.1:10809"
```

或：

```env
GOOGLE_PLACES_PROXY_URL="socks://127.0.0.1:10808"
```

关键不是照抄，而是先核实哪一个端口在新电脑上真的可用。

## 四、换电脑后最容易出问题的点

1. 规则库路径变了，项目 `AGENTS.md` 路由失效
2. `.env` 没恢复完整
3. 数据库没启动
4. 本地代理端口和旧电脑不同
5. 浏览器能访问 Google，但 Node 进程不能
6. 只测了本地 build，没测真实外部 API

## 五、最小恢复验证

至少验证：

1. `npm run build`
2. 项目主页能打开
3. 数据库可连
4. 外部 API key 已生效
5. 如果依赖代理，服务端请求能真正出站
