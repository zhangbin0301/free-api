# Free API - 免费 OpenAI & Anthropic 兼容 API

[中文](README.md) | [English](README_EN.md)

这是一个免费提供的、兼容 OpenAI API 和 Anthropic Messages API 格式的大模型接口服务。

## 快速入口

| 项目 | 链接 |
|------|------|
| 在线体验 | [在线体验](https://chat.good.hidns.vip) |
| 使用教程 | [视频教程（B 站）](https://www.bilibili.com/video/BV1XHw2zrEzY) |


## 接口信息

| 配置项 | 值 |
|--------|-----|
| API 地址 | `https://openai.good.hidns.vip/v1` |
| API Key | `https://github.com/smanx/free-api` |

> 该 Key 为公开共享用途，请勿用于生产环境中的强依赖场景。


## 支持的模型（[模型状态页面](https://status.good.hidns.vip)）

| 模型名 | 模型ID示例 | 说明 |
|------|---------|------|
| GPT | gpt-5.4 | 对话、识图、工具，推荐使用 |
| Grok | grok-4.1-fast | 生图首选，对话内容限制较少 |
| Claude | claude-sonnet-4.6 | 新增，测试 |
| Qwen | qwen3.5-flash | 通义千问 |
| GLM | z-ai/glm5 | 智谱 GLM |
| Kimi | moonshotai/kimi-k2.5 | Kimi |
| MiniMax | minimaxai/minimax-m2.5 | MiniMax |
| DeepSeek | deepseek-ai/deepseek-v3.2 | DeepSeek |

> 模型变更：`gpt-5.4` 和 `gpt-5.3-codex` 已重新上线，可直接使用。

> 注意：该服务的 `Grok` `Claude` 和 `Qwen` 不支持工具调用，强行调用时返回结果可能异常。

## 支持的端点

- `/v1/models` - 模型列表
- `/v1/chat/completions` - 对话补全
- `/v1/images/generations` - 图片生成
- `/v1/messages` - Anthropic Messages API（兼容 Claude SDK）

## 最小可用示例

将以下命令直接复制到终端即可测试：

```bash
curl https://openai.good.hidns.vip/v1/chat/completions \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer sk-B882bCwUweSeMRscoNwxZw4vxpjXmvWTLBxO5aXC7WAYhfwa" \
  -d '{
    "model": "gpt-5.2",
    "messages": [
      {
        "role": "user",
        "content": "你好，请简单介绍一下你自己"
      }
    ]
  }'
```

### 图片生成（/v1/images/generations）

> 当前图片生成需要指定模型：`grok-imagine-1.0`

当前仅支持 `response_format: "b64_json"`（返回 base64）。

`size` 可选值：
- `1024x1024`
- `1024x1792`
- `1792x1024`
- `1280x720`
- `720x1280`

#### 返回 base64（最小可用）

```bash
curl https://openai.good.hidns.vip/v1/images/generations \
  -H "Content-Type: application/json" \
  -H "Authorization: Bearer sk-B882bCwUweSeMRscoNwxZw4vxpjXmvWTLBxO5aXC7WAYhfwa" \
  -d '{
    "model": "grok-imagine-1.0",
    "prompt": "生成一张极简风格的火箭扁平图标，白色背景",
    "n": 1,
    "size": "1024x1024",
    "response_format": "b64_json"
  }'
```

## 交流社区

- Telegram 群组：[https://t.me/+qQEwPrh9bJZlZjJl](https://t.me/+qQEwPrh9bJZlZjJl)
- QQ 群：1094693043

## 注意事项

- 本服务免费提供给个人使用，请合理使用。
- 限流规则：同一 IP 10 秒内最多可调用 5 次，超过后将触发 10 秒限流；该规则后续可能调整。
- 请勿提交敏感信息、隐私数据或重要业务内容。
- 项目承诺不收集任何信息；如仍有顾虑，可以选择不使用。
- 后续如有变动，将在本项目中更新说明。
