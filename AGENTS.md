# Project instructions

## Project goal

维护 GitHub 仓库 `Ailuren-scriptwriter-3act-15beats`，以及其中可直接放入 Codex skills 目录的中文剧本创作 skill：把主题、人物、情节碎片或画面灵感发展成三幕式、Save the Cat 15 Beats 与场景级大纲。

## Directory conventions

- `SKILL.md`：skill 的触发规则、创作流程与输出边界。
- `references/`：创作时读取的节拍定义与输出模板。
- `assets/readme/`：只存 README 展示所需的静态视觉资产。
- 根目录中文 `.md` 与 `.png`：真实示例剧本及其结构/分镜输出。

## Naming

- GitHub 仓库名称使用 `Ailuren-scriptwriter-3act-15beats`。
- skill 名称使用 `Ailuren-scriptwriter-3act-15beats`。
- README 资产使用小写英文短横线命名；示例内容保留中文文件名，避免改变创作素材的原始语义。

## Validation

- 运行 `python3 /Users/ailuren/.codex/skills/beautify-github-readme/scripts/audit_readme.py README.md`。
- 检查 `git diff --check`。
- 变更 README 视觉资产时，在约 900px 与 360px 宽度检查渲染结果。

## Cleanup

- 不删除用户提供的示例剧本或图片。
- 不提交密钥、token、临时预览文件或系统生成的 `.DS_Store`。
