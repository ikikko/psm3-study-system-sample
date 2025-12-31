# PSM III学習システム

このシステムは、Scrum.orgのProfessional Scrum Master III (PSM III)試験対策のための学習ツールです。Cursor Agentとファイルベースでやり取りしながら、エッセイ形式の問題に取り組み、詳細なフィードバックを受け取ることができます。

## システムの使い方

### 1. 問題を出題してもらう

#### 方法1: チャットで依頼

```
「問題を出して」
```

または

```
「問題番号XXXを出して」
```

#### 方法2: Cursorコマンドを使用

Cursorのコマンドパレット（`Cmd+Shift+P` / `Ctrl+Shift+P`）から`create-question`コマンドを実行します。

- 引数を指定しない場合: 1問がランダムに選択されます
- 引数を指定する場合: 指定した数だけ問題がランダムに選択されます（例: `create-question 2`で2問）

Agentが`questions/`ディレクトリから問題を選択し、新しいセッションディレクトリ（`sessions/YYYY-MM-DD_HH-MM/`）を作成します。詳細な手順は`templates/question_template.md`を参照してください。

### 2. 問題に回答する

セッションディレクトリ内の`answer.md`ファイルに回答を記入してください。

### 3. 添削を依頼する

```
「添削して」
```

Agentが回答を読み取り、評価観点に基づいて詳細なフィードバックを`feedback.md`に出力します。

## ファイル構造

```
psm3/
├── README.md                    # このファイル
├── questions/                   # 問題データベース
│   ├── question_010.md         # 問題1
│   ├── question_011.md         # 問題2
│   └── ...
├── sessions/                    # 学習セッション
│   └── YYYY-MM-DD_HH-MM/       # セッションごとのディレクトリ
│       ├── question.md         # 出題された問題
│       ├── answer.md           # ユーザーの回答
│       └── feedback.md         # 添削結果
├── templates/                   # テンプレート
│   ├── question_template.md    # 問題作成用テンプレート
│   └── feedback_template.md    # 添削結果テンプレート
└── .cursor/                     # Cursor設定
    └── commands/               # Cursorコマンド
        └── create-question.md  # 問題出題コマンド
```

## 評価基準

本システムは[Scrum.org公式FAQ](https://www.scrum.org/support/enhanced-level-iii-assessment-scoring-and-feedback)に基づいた採点基準を使用しています。

### 評価方法

各問題は以下の4段階で評価されます：

- **Exceeded Expectations（期待を上回る）**: スクラムの概念と原則を深く理解し、実践的に適用できている
- **Met Expectations（期待を満たす）**: スクラムの基本概念を理解し、適切に適用できている
- **Did Not Meet Expectations（期待を下回る）**: スクラムの基本概念の理解が不足している
- **Not Attempted（未回答）**: 問題に回答していない

### 評価観点

各問題は以下の観点で評価されます：

1. **スクラムガイドの理解**: 公式ドキュメントの内容に基づいているか
2. **実践的な適用**: 具体的な状況での適用方法を示しているか
3. **専門領域の分析**: 問題固有の専門知識の分析
4. **学習目標達成**: 問題の学習目標に対する回答の完全性と明確性

### 重要な評価要素

- スクラムガイドとの整合性
- 正しいスクラム用語の使用
- 質問への直接的な回答
- スクラムの価値観や三本柱との関連
- 明確性と具体性

詳細な採点基準は`templates/feedback_template.md`を参照してください。
