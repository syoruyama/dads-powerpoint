# デジタル庁デザインシステム PowerPoint スキル (`dads-powerpoint`)

[デジタル庁デザインシステム（DADS）](https://design.digital.go.jp/) の配色・書体・余白・アクセシビリティを応用して、編集可能な PowerPoint（`.pptx`）を作るための Agent Skill です。

元ネタ: [IT navi さんの公開スキル](https://x.com/itnavi2022/status/2097272006450553038)（ChatGPT / Codex 向け zip）。Claude Code と Codex の両方で使えるよう、このリポジトリにまとめています。

> DADS は Web 向けのプラットフォーム型デザインシステムであり、公式の PowerPoint テンプレートではありません。青の採用や 16:9 などは本スキルの既定値です。

## 構成

```
skills/dads-powerpoint/
├── SKILL.md                 # スキル本体（name / description + 手順）
├── agents/openai.yaml       # Codex / ChatGPT 用の表示・呼び出し設定
├── assets/                  # トークン JSON・アイコン
├── references/              # DADS 抜粋・スライドスタイル・実装メモ
└── scripts/dads-theme.mjs   # Artifact Tool 向けヘルパー
```

## Claude Code への入れ方

個人スキル（全プロジェクトで利用）:

```bash
git clone https://github.com/syoruyama/dads-powerpoint.git
mkdir -p ~/.claude/skills
cp -R dads-powerpoint/skills/dads-powerpoint ~/.claude/skills/
```

プロジェクト専用にする場合は、リポジトリ直下へ:

```bash
mkdir -p .claude/skills
cp -R path/to/dads-powerpoint/skills/dads-powerpoint .claude/skills/
```

起動し直したあと、`/dads-powerpoint` で呼べます。関連する依頼なら自動でも使われます。

## Codex への入れ方

個人スキル:

```bash
git clone https://github.com/syoruyama/dads-powerpoint.git
mkdir -p ~/.agents/skills
cp -R dads-powerpoint/skills/dads-powerpoint ~/.agents/skills/
```

リポジトリ内で使う場合:

```bash
mkdir -p .agents/skills
cp -R path/to/dads-powerpoint/skills/dads-powerpoint .agents/skills/
```

`$skill-installer` から GitHub パスを指定して入れることもできます。認識されないときは Codex を再起動してください。明示呼び出しは `$dads-powerpoint` です。

## ChatGPT への入れ方

1. このリポジトリの `skills/dads-powerpoint` を zip にする（フォルダごと）
2. ChatGPT の Skills からアップロード

または元の配布 zip をそのまま使っても構いません。

## 使い方の例

- 「デジタル庁のデザインシステムでパワポを作って」
- 「DADS ベースで社内説明スライドにして」
- `$dads-powerpoint` / `/dads-powerpoint` のあとに原稿や構成案を渡す

## 出典・ライセンス

- デザイン方針の根拠: デジタル庁デザインシステム（同梱 `references/dads/`）
- デザイントークン関連: `skills/dads-powerpoint/references/design-tokens-LICENSE.txt` を参照
- スライド応用スキルの元公開: [IT navi @itnavi2022](https://x.com/itnavi2022/status/2097272006450553038)

ロゴや「公式認定」の表示は付けません。最終成果物には「デザイン：デジタル庁デザインシステムの資料をもとに、スライド用に編集・加工」と公式サイトへのリンクを残してください。
