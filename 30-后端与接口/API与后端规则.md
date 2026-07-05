# API 与后端规则

## 后端职责

后端需要明确表达：

1. 输入
2. 输出
3. 错误
4. 状态变化
5. 副作用

## 接口格式

默认成功格式：

```json
{
  "success": true,
  "data": {}
}
```

默认失败格式：

```json
{
  "success": false,
  "error": {
    "code": "ERROR_CODE",
    "message": "Human readable error"
  }
}
```

## 错误处理规则

1. 用户页面看到的是简短人话
2. 原始异常写日志
3. 区分：
   - 参数错误
   - 权限错误
   - 外部 API 失败
   - 网络超时
   - 数据库不可用

## 后端实现原则

1. 不把一个 route 写成一切都在里面
2. service 负责业务逻辑
3. route 负责协议和状态码
4. validator 负责输入约束
