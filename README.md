# Free API - 免费 OpenAI 兼容 API

这是一个免费的兼容 OpenAI API 格式的大模型接口服务。

## 使用教程

- [视频教程（B 站）](https://www.bilibili.com/video/BV1XHw2zrEzY)

## 接口信息

| 配置项 | 值 |
|--------|-----|
| API 地址 | `https://openai.good.hidns.vip/v1` |
| API Key | `sk-B882bCwUweSeMRscoNwxZw4vxpjXmvWTLBxO5aXC7WAYhfwa` |


## 支持的模型

| 模型 | 说明 | 访问速度 |
|------|------|----------|
| gpt | 对话、识图、工具，推荐使用 | 正常 |
| grok | 生图首选，对话内容无限制 | 正常 |
| qwen3.5 | 通义千问 | 不稳 |
| glm5 | 智谱 GLM | 很慢 |
| k2.5 | Kimi | 很慢 |
| minimax-m2.5 | MiniMax | 很慢 |

> 注意：该服务的 `grok` 和 `qwen` 不支持工具调用，在调用工具时会胡言乱语。

## 支持的端点

- `/v1/chat/completions` - 对话补全
- `/v1/models` - 模型列表

## 注意事项

- 本服务为免费提供给个人，请合理使用
- 模型变更：`gpt-5.4` 和 `gpt-5.3-codex` 已下线；为避免正在使用的人出问题，本服务目前使用 `gpt-5.2` 和 `gpt-5.2-codex` 作为替代（如你正在使用5.4或5.3，请及时调整切换到5.2）
- 后续有什么变动会在该项目更新
