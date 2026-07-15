# 沉浸叙事引擎

一个 AI 驱动的成人互动叙事系统。你扮演主角，AI 负责构建世界、操控 NPC、推进剧情——每个 NPC 都有自己的性格、目标和底线，世界会随时间自行运转。

## 这是什么

简单说：你和 AI 一起编故事。但和普通角色扮演不一样的是——

- **NPC 有脑子**：每个角色有自己的性格、记忆、目标和底线。会拒绝、会犹豫、会主动出击，不是你的提线木偶。
- **世界在转**：你不在的时候，NPC 也会做自己的事。消息会传播，关系会变化，事情不会停在原地等你。
- **存档能续**：随时存档，换个对话窗口接着玩，状态不丢。
- **有边界有安全词**：你的硬边界不会被突破。任何时候喊停就停，不需要理由。

## 怎么用

实际 Skill 位于 `adult-tension-narrative/`。将这个目录安装到 Codex 的 skills 目录后，可以这样使用：

```
开局                    → 随机生成世界观、角色和故事开场
继续 / ...              → 剧情往前推一小步，停在你能接手的地方
快进到明天晚上           → 时间跳跃，世界自动算这期间发生了什么
存档                    → 输出可跨对话使用的 YAML 存档
载入存档                → 校验并载入 YAML，不重新生成开局
解除暂停                → 只解除安全暂停，不载入存档
本局不碰 XXX            → 添加你的硬边界，AI 不会碰
暂停 / 安全词            → 立即停止所有亲密内容，不问为什么
```

## 文件结构

| 文件 | 说明 |
|------|------|
| `adult-tension-narrative/SKILL.md` | 核心规则：开局流程、回合推进、NPC 决策、状态模型、输出规范 |
| `adult-tension-narrative/agents/openai.yaml` | Codex 界面配置 |
| `adult-tension-narrative/references/角色设计.md` | 角色创建流程：世界观→张力引擎→NPC 全维角色卡→配角建档 |
| `adult-tension-narrative/references/世界运转.md` | 时间系统、事件队列、离屏行动、关系网络传播、世界追算 |
| `adult-tension-narrative/references/状态总结.md` | v3 存档格式、校验、迁移和跨对话续玩 |
| `adult-tension-narrative/scripts/validate_state.py` | 基于 YAML 结构的状态校验脚本 |
| `adult-tension-narrative/tests/test_validate_state.py` | 存档校验器自动化测试 |

## 内容说明

本引擎仅处理**虚构的成年人**角色。内容可包含成熟氛围、情感张力和亲密互动。所有亲密互动必须建立在明确、持续且可撤回的同意之上。

## 许可

MIT
