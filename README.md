# Bias Correction（认知偏误纠正系统）

> 不告诉你"你错了"——而是问"有没有可能……"。一个让 AI 自动检测并温和纠正 39 种认知偏误的 skill。

**版本**：v1.0.0 | **许可证**：MIT

## 这是什么

一个触发词驱动的认知偏误纠正 skill。当你的提问出现偏误信号（过度确定、直觉先行、从众、沉没成本……）或隐式推理结构（单向因果链、滑坡论证、幸存者案例……）时，AI 会自动介入，指出推理在哪里出了问题，并给出可执行的纠正动作。

**不是**：所有问题都强制过一遍偏误检查清单。
**而是**：平时正常回答，只在检测到偏误信号时才介入，且介入强度随问题深度自动调节。

## 核心能力

- **39 个认知偏误**：8 个必学 + 31 个进阶，覆盖信息处理/自我认知/社会群体/决策行为/概率预测五大类
- **双通道识别**：显性触发词（"我肯定""大家都这样""已经投了"）+ 8 类隐式推理结构（果→因单向链、极端类比、虚假均势……）
- **分级介入**：L0/L1 轻度点缀，L2-L3 才激活完整六步协议——不在小事上舞大刀
- **第一性原理前置**：纠偏之前先拆解底层事实，防止"纠偏本身变成另一种偏差"
- **默会知识激活**：尊重经验直觉，逻辑与直觉矛盾时明确标注取舍
- **对抗性审查**：输出前红队自己的结论——最强反对者/压力测试/代价不对称
- **决策追踪**：深度分析后生成决策日志，30 天后提醒复盘，用真实结果校准判断
- **文化适配**：参考父母/面子/集体优先等东方情境不误诊为偏差
- **元层防护**："我已经懂偏误所以免疫"本身就是偏差（道德许可），系统自带自检

## 与 thinking-models 的关系

| | bias-correction（本 skill） | [thinking-models](https://github.com/Mihooni/thinking-models) |
|---|---|---|
| 定位 | **哪里会出错**——防错护栏 | **怎么做更好**——分析工具箱 |
| 内容 | 39 偏误 + 纠正方法 | 66 思维模型 + 匹配表 |
| 触发 | 偏误信号驱动，非默认激活 | 所有提问自动分级介入 |

两者编号互通（如沉没成本 = BC#29 = TM#1）、协议兼容、可独立使用也可组合。**单装本 skill 时**，深度分析所需的思维模型由内置的"第一性原理 + 对抗审查 + 决策树"兜底；装了 thinking-models 则自动联动，识别到偏误后推荐对应模型深挖。

## 安装

### Claude Code（macOS/Linux）

```bash
# 1. 克隆仓库
git clone https://github.com/Mihooni/bias-correction.git ~/.cc-switch/skills/bias-correction

# 2. 创建 symlink 挂载
ln -s ~/.cc-switch/skills/bias-correction ~/.claude/skills/bias-correction

# 3. 重启 Claude Code
```

### Claude Code（Windows）

```powershell
git clone https://github.com/Mihooni/bias-correction.git %USERPROFILE%\.cc-switch\skills\bias-correction
cmd /c mklink /D %USERPROFILE%\.claude\skills\bias-correction %USERPROFILE%\.cc-switch\skills\bias-correction
```

### Cursor / Codex / Cline / Continue

```bash
# Cursor：将 AGENTS.md 复制为项目根目录的 .cursorrules
cp ~/.cc-switch/skills/bias-correction/AGENTS.md /path/to/your/project/.cursorrules

# Codex / Cline / Continue：复制为项目根目录的 AGENTS.md
cp ~/.cc-switch/skills/bias-correction/AGENTS.md /path/to/your/project/AGENTS.md
```

### 手动安装（不使用 git）

1. 下载本仓库 ZIP 并解压
2. 将 `bias-correction` 文件夹放到任意位置
3. 按上方命令创建 symlink

## 文件结构

```
bias-correction/
├── SKILL.md    ← 主文件：39偏误 + 六步协议 + 匹配表 + 决策树
├── AGENTS.md   ← 跨平台格式（Codex/Cline/Continue/Cursor）
├── README.md   ← 本文件
├── LICENSE
└── CHANGELOG.md
```

## 输出示例

### L0 简单问题（轻介入，不展示框架）

**问**："Python 最新版本是多少？"

**答**：Python 3.12.4。

> 注意一个常见误区：直接照搬官网首页版本号——某些发行版/框架有各自的支持矩阵。

### L2 深度问题（完整协议，输出偏差本质）

**问**："我在这个项目已经投了 20 万，虽然数据一直不好，但再坚持半年应该能行吧？"

**答**：

## 偏差本质
你的推理核心是 **沉没成本谬误（BC#29）+ 确认偏误（BC#1）**——用"已投入"支撑"继续投"，再用"应该能行"回避了反面证据的主动搜寻。

## 分析
关键检验不是"还能不能坚持"，而是**"今天是第一次接触，看到这个项目的现状，我还会投 20 万进去吗？"**——把过去的投入从决策里完全剥离后，剩下的才是真判断。隐式偏差：你说"应该能行"时依据的是希望而非数据，这是**动机性推理（BC#14）**——结论先于证据链。反直觉一点：此刻止损不是承认失败，而是把剩余资源从"补过去的洞"挪到"赌未来的赢"，两者期望值完全不同。

## 行动
1. **今日重判** — 假装第一次评估这个项目，只看现有数据决定投不投 — 今天
2. **设定验证点** — 写下"3 个月内出现什么信号就该撤"，白纸黑字 — 本周
3. **算机会成本** — 这半年时间和预算如果投到第二选择，期望回报是多少 — 1 周内

## 不纠的代价
最常见的结局不是"坚持成功了"，而是 6 个月后再投 20 万，用更大的沉没成本支撑更难回头的处境。

## 适用场景

### ✅ 适合触发
- 投资决策（加仓/止损/"已经投了"）
- 过度自信的断言（"我肯定""100% 确定""必然"）
- 从众判断（"大家都这样做""所有人都在买"）
- 直觉先行（"我感觉""说不清但就是觉得"）
- 复盘归因（"运气不好""环境不行""早就知道会这样"）
- 论证审查（发现自己在"两边都有道理"或滑坡推演）

### ❌ 不适合触发
- 纯事实查询（版本号/日期/定义）
- 代码报错/调试
- 创意娱乐（写故事/讲笑话）
- 无偏误信号的普通提问——按常规回答，不强制检查

## 方法论来源

- Daniel Kahneman《思考，快与慢》——系统1/系统2、锚定、损失厌恶、框架效应
- Max Bazerman & Don Moore《Judgment in Managerial Decision Making》——过度自信、谈判偏误
- Annie Duke《对赌》——决策与结果分离、事前验尸
- Robert Cialdini《影响力》——从众、权威、承诺一致
- 以及行为经济学、认知心理学的学术共识（标注 📊学术共识 的条目均有实证文献支持）

## 更新日志

参见 [CHANGELOG.md](CHANGELOG.md)

## License

MIT
