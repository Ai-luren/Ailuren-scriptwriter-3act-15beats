<p align="center">
  <img src="./assets/readme/hero.svg" width="100%" alt="中文剧本创作：三幕式与 15 Beats，把主题、人物和情节碎片发展成可执行的故事结构">
</p>

# 中文剧本创作：三幕式 + 15 Beats

一个给中文创作者使用的 Codex Skill。你只需要提供主题、人物、情节碎片、画面灵感或结局设想，它会把素材发展成一套可以继续写剧本、拆分镜、做 AI 视频的故事结构。

仓库与调用名：`Ailuren-scriptwriter-3act-15beats`

> 默认方法：三幕式（建立 → 对抗 → 解决） + Save the Cat 15 Beats + 场景级剧情大纲

## 真实输出： 《雨夜救猫》

只展示一个完整案例，方便从文本一路看到结构和视觉结果。

### 文本

完整故事文本：[`examples/雨夜救猫.md`](./examples/雨夜救猫.md)

> 一个习惯独来独往、怕麻烦的外卖骑手，在暴雨夜听见旧楼天台传来小猫的求救声。为了救下一只被困在水塔边缘的橘猫，他不得不走进停电的旧楼、接受陌生人的帮助，并在一次看似微小的救援中重新学会相信人与人之间的连接。

**核心主题：** 愿意伸手帮助别人，也是在重新接住自己。

### 三幕式结构图

<p align="center">
  <img src="./assets/examples/雨夜救猫-三幕式-结构.png" width="100%" alt="雨夜救猫的三幕式结构图：建立、对抗、解决">
</p>

### 15 Beats 分镜图

<p align="center">
  <img src="./assets/examples/雨夜救猫-15beats-分镜.png" width="100%" alt="雨夜救猫的 15 Beats 分镜图，从开场画面推进到救出小猫的结尾">
</p>

## 它解决什么问题

很多故事不是没有画面，而是缺少一条能持续推进的因果线。这个 skill 会先找到故事发动机，再把素材放进结构里：

```text
主角 + 外在目标 + 内在需求 + 阻碍 + 风险
                              ↓
             三幕式骨架 + 15 个剧情功能
                              ↓
                  可执行的场景级剧情大纲
```

它尤其适合：

- AI 剧情短片与分镜前期开发
- 30 秒至 15 分钟的广告、TVC 与品牌故事
- 只有主题、人物或几个画面时的故事起稿
- 已有剧情但中段松散、转折不足、结尾无力的结构重写

## 核心方法

### 三幕式：控制故事的方向

| 幕 | 任务 | 关键检查 |
| --- | --- | --- |
| 第一幕｜建立 | 建立人物、世界、欲望与缺陷，完成催化事件 | 主角为什么现在必须行动？ |
| 第二幕｜对抗 | 展开行动、关系线与核心卖点，持续升级压力 | 中点是否改变了游戏规则？ |
| 第三幕｜解决 | 从失败或主题线获得新认识，用行动完成高潮 | 结尾是否证明人物已经改变？ |

### 15 Beats：控制转折，不制造 15 个镜头

15 Beats 是剧情功能，不要求 15 个独立场景。短片可以压缩和合并，但必须保留关键的因果关系：

```text
01 开场画面 → 02 主题呈现 → 03 铺垫 → 04 催化事件 → 05 迟疑挣扎
06 进入第二幕 → 07 B 故事 → 08 核心展开 → 09 中点 → 10 危机逼近
11 一切尽失 → 12 灵魂黑夜 → 13 进入第三幕 → 14 终局 → 15 结尾画面
```

完整节拍定义在 [`references/beat-sheet.md`](./references/beat-sheet.md)，默认交付格式在 [`references/output-template.md`](./references/output-template.md)。

## 使用方式

把仓库中的 `SKILL.md` 与 `references/` 一起复制到 Codex 的 skills 目录，并在对话中调用：

```text
$Ailuren-scriptwriter-3act-15beats

我想做一支 60 秒 AI 剧情广告：
- 主题：真正的轻，不只是重量更轻
- 主角：一个在城市中移动办公的年轻创意人
- 产品：轻薄笔记本
- 必须出现：通勤、会议、夜晚收尾

请按三幕式 + 15 Beats，输出故事核心、人物弧光、节拍表和场景级剧情大纲。
```

如果你只有一个模糊想法，也可以直接说：

```text
我想写一个雨夜救猫的短片，主角是怕麻烦的外卖骑手，结尾希望有温暖的反转。
```

信息不完整时，skill 会保留已有设定，只补充让因果成立所必需的内容，并把关键补充列为“创作假设”。

## 不会用？照着这 4 步开始

### 第 1 步：Codex 一键安装（推荐）

在新的 Codex 对话中，复制下面整段并发送。`skill-installer` 会从公开 GitHub 仓库读取根目录的 `SKILL.md` 和 `references/`：

```text
$skill-installer

请从这个公开 GitHub 仓库安装 Codex skill：
https://github.com/Ai-luren/Ailuren-scriptwriter-3act-15beats

请安装仓库根目录的 skill，安装名使用：Ailuren-scriptwriter-3act-15beats
安装完成后告诉我安装路径。
```

安装完成后，在新的 Codex 对话中输入 `$Ailuren-scriptwriter-3act-15beats` 即可调用。

### 手动安装（备用）

把仓库里的 `SKILL.md` 和 `references/` 文件夹复制到 Codex 的 skills 目录：

```bash
mkdir -p ~/.codex/skills/Ailuren-scriptwriter-3act-15beats/references
cp SKILL.md ~/.codex/skills/Ailuren-scriptwriter-3act-15beats/
cp references/*.md ~/.codex/skills/Ailuren-scriptwriter-3act-15beats/references/
```

### 第 2 步：不会写提示词，就先填 4 个空

直接复制下面这段，把括号里的内容换成你的想法：

```text
$Ailuren-scriptwriter-3act-15beats

帮我把这个想法发展成一个故事：
- 主角：（谁）
- 他/她想要：（外在目标）
- 最大阻碍：（什么在阻止他/她）
- 我想表达：（主题或情绪）

请输出：一句话故事、人物弧光、三幕式结构、15 Beats 节拍表和场景级剧情大纲。
如果信息不足，请做最少必要补充，并列出创作假设。
```

### 第 3 步：只有一个画面也可以

例如你只想到“雨夜、一个外卖骑手、一只被困的猫”，可以这样说：

```text
$Ailuren-scriptwriter-3act-15beats

我只有一个画面：雨夜里，一个外卖骑手听见旧楼楼顶有猫叫。
请帮我补成一个 3 分钟的温暖短片，主角一开始怕麻烦、拒绝和人连接，
结尾希望他在邻居帮助下救出小猫，也重新相信人与人之间的善意。
```

### 第 4 步：结果不满意，就指定一处修改

不需要重新描述整个故事，直接指出要改哪里：

```text
保留人物和结局，但把中点改得更有冲击力；
让一切尽失比中点更严重；
再输出修改后的 15 Beats 和受影响的场景大纲。
```

建议第一次先看“故事核心”和“人物弧光”，确认主角真正想要什么，再继续修改节拍和场景。不要一开始就要求完整对白，否则结构还没稳定就会过早进入写作细节。

更完整的操作说明见 [`docs/getting-started.md`](./docs/getting-started.md)。

## 完整案例

| 示例 | 适合观察的部分 | 文件 |
| --- | --- | --- |
| 《雨夜救猫》 | 小人物弧光、B 故事、15 Beats 到分镜 | [`examples/雨夜救猫.md`](./examples/雨夜救猫.md) |

图片统一放在 [`assets/examples/`](./assets/examples/)；README 只展示这个案例，避免多个案例抢夺阅读焦点。

## 创作边界

- 15 Beats 是检查故事功能的工具，不是公式化的 15 镜头清单。
- 不会为了套结构推翻用户最重要的创意。
- 高潮应由主角做出关键选择，不能靠突然出现的新能力或新人物解决。
- AI 视频适配会优先控制角色、场景、道具和动作的连续性；除非用户要求，不自动生成图像或视频提示词。

## 文件结构

```text
.
├── SKILL.md                         # skill 主规则
├── references/
│   ├── beat-sheet.md                # 15 Beats 定义与时长压缩
│   └── output-template.md           # 默认交付模板
├── assets/readme/hero.svg           # README 首屏视觉
├── assets/examples/                 # 案例结构图与分镜图
└── examples/                        # 所有案例文本
```

## License

本项目由 @Ai路人 创建与维护。

## 验证

README 的图片、SVG 和替代文本可用以下命令检查：

```bash
python3 /Users/ailuren/.codex/skills/beautify-github-readme/scripts/audit_readme.py README.md
git diff --check
```

本 README 的视觉素材使用现有案例，不依赖远程图片、外部字体或动态徽章。
