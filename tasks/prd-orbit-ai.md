1. 引言 / Overview
在 orbit.ai 中为用户提供 零成本、多轮、沉浸式心理陪伴对话，替代传统静态日记，提升日活与留存。首期基于微信官方混元-pro 模型（1 亿 token/月免费），后续可无缝切换 Kimi/DeepSeek。
2. 目标（可衡量）
3 日内完成 MVP，支持文字+语音输入 → AI 回复 → 本地历史展示
7 日留存提升 ≥ 10%（We 分析「day7Retention」事件）
对话人均轮次 ≥ 3 轮/日（埋点事件 chat_round）
3. 用户故事（单会话可交付）
US-001：发送文字并收到 AI 回复
Description: 作为用户，我想输入文字并立即收到温柔回复，以便被倾听。
Acceptance Criteria:
[ ] 输入框 ≤200 字，点击「发送」调云函数 chatMulti
[ ] 返回内容 ≤75 字，显示在气泡卡片，加载动画 ≤1.5 s
[ ] 网络失败给出重试按钮，错误日志打印 Console
[ ] Typecheck 通过
[ ] UI 验证： 用 dev-browser 技能检查气泡样式与加载态
US-002：语音转文字输入
Description: 作为用户，我想用语音快速记录心情，以便解放双手。
Acceptance Criteria:
[ ] 长按语音按钮 ≤60 s，自动转文字（微信同声传写插件）
[ ] 转写成功率 ≥90%（普通话），失败可手动修改
[ ] 转写完成后自动触发 US-001 发送流程
[ ] Typecheck 通过
[ ] UI 验证： dev-browser 检查转写 loading & 结果气泡
US-003：本地历史会话列表
Description: 作为用户，我想查看今天所有对话，以便回顾情绪。
Acceptance Criteria:
[ ] 进入页面自动拉取当日 chat 集合（按 _openid + 日期）
[ ] 按时间倒序，单条显示用户气泡+AI 气泡+时间戳
[ ] 空状态提示「今天还没对话，说点什么吧」
[ ] Typecheck 通过
[ ] UI 验证： dev-browser 检查空状态与卡片间距
US-004：情绪 5 星标记（MVP 快捷版）
Description: 作为用户，我想给每次对话标情绪，以便以后看趋势。
Acceptance Criteria:
[ ] 发送后弹出 5 星评分（默认 3 星），可跳过
[ ] 评分随对话一起写入 chat 文档 mood: 1-5
[ ] 日后可一键关闭此弹窗（写入用户配置）
[ ] Typecheck 通过
[ ] UI 验证： dev-browser 检查星星点击态与跳过按钮
4. 功能性需求（编号 & 无歧义）
FR-1：云函数 chatMulti 支持 text+mood 参数，返回 {reply, ts}
FR-2：前端调用 wx.cloud.callFunction 名称固定为 chatMulti，超时 ≤5 s
FR-3：语音转写云函数 transcribeVoice 返回 {text, duration}，免费额度内使用
FR-4：数据库集合 chat 字段：_openid, text, reply, mood, ts, date
FR-5：历史列表自动滚动到底部（新消息可见）
FR-6：所有网络失败给出 Toast+重试按钮，不重试不埋点
5. 非目标（明确边界）
暂不支持多设备同步（仅当前微信账号）
暂不做后台推送/提醒
暂不做情绪折线、词云、报表（仅本地列表）
暂不做用户注册、登录、社交功能
6. 设计考虑（UI/UX）
reuse 现有气泡组件，用户右、AI 左，配色 #faf7f2 / #fff
输入栏固定底部，语音+文字双入口（同微信聊天）
加载用 skeleton 气泡，高度 40 rpx
空状态插画已存在 assets/empty-chat.svg
7. 技术考虑
混元-pro 免费额度 1 亿 token/月，模型切换只需改云函数 endpoint
语音转写走微信同声传写插件，0.5 元/分钟，前 2000 分钟/月免费
历史数据只存 90 天（云开发定时清理），减少存储费用
所有云函数统一 Nodejs 18，内存 256 M，超时 5 s
8. 成功指标
对话成功率 ≥ 98%（云函数错误率 <2%）
首句响应时间 ≤ 1.5 s（混元-pro 实测 0.8 s）
语音转写准确率 ≥ 90%（普通话）
7 日留存提升 ≥ 10%（We 分析事件 day7Retention）
9. 待澄清问题（可选）
是否需要在 MVP 内支持英文语音转写？
情绪折线视图是否放在第二迭代？
是否接入微信订阅消息提醒用户回来说话？
✅ Checklist
[x] 提出字母选项澄清问题
[x] 用户故事含验收标准 & dev-browser 验证
[x] 功能需求编号、无歧义
[x] 非目标明确
[x] 已保存至 tasks/prd-orbit-ai.md
下一步：按故事顺序实现 US-001 → US-004，每完成一个推送到 main 并截图验收。
