# gh-receipt

🧾 GitHub の活動レシート - あなたの頑張りを美しく表示

## 特徴

- 📊 公開/プライベートリポジトリの活動を分けて集計
- 📈 週間アクティビティをビジュアルグラフで表示
- 🔐 プライバシーに配慮（リポジトリ名は非表示）
- ✨ SNSでシェアしやすいクリーンなデザイン

## 必要なもの

- [GitHub CLI (gh)](https://cli.github.com/) がインストールされていること
- `gh auth login` で認証済みであること
- `jq` コマンド（ほとんどのシステムにプリインストール済み）

## インストール

### npx で実行（インストール不要）
```bash
npx gh-receipt
npx gh-receipt nano72mkn
```

### グローバルインストール
```bash
npm install -g gh-receipt
```

### 手動インストール
```bash
# リポジトリをクローン
git clone https://github.com/nano72mkn/gh-receipt.git
cd gh-receipt
chmod +x gh-receipt

# PATH に追加
cp gh-receipt ~/.local/bin/
```

## 使い方

```bash
# 自分の活動レシートを出力
gh-receipt

# 特定のユーザーのレシートを出力
gh-receipt nano72mkn

# 過去7日間のレシート
gh-receipt nano72mkn 7
```

## 認証について

gh CLI の認証を使用するため、追加の設定は不要です。プライベートリポジトリも自動的に含まれます。

認証状態の確認：
```bash
gh auth status
```

## 出力例

```
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
       🧾 GitHub Activity Receipt
              Last 30 days
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━

📈 Activity Summary

  Total Contributions
  584 activities

  Breakdown
  ├─ Commits (Public):     3
  ├─ Commits (Private):    581
  ├─ Pull Requests:        0
  ├─ Code Reviews:         0
  └─ Issues:               0

📅 Weekly Activity

  Sun ▓▓▓▓▓▓▓▓▓▓▓▓▓▓ 43
  Mon ▓▓▓▓▓▓▓▓▓▓ 31
  Tue ▓▓▓ 9

🔥 Amazing work! Keep it up!
━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━━
```
📊 nano72mkn の活動レポート
期間: 過去 30 日間 (2024-05-11 〜 今日)
──────────────────────────────────────────────────

✨ 合計コミット数: 156

📅 期間別サマリー:
  今日: 12 コミット
  今週: 45 コミット
  今月: 98 コミット

🔥 アクティブなリポジトリ:
  1. my-awesome-project          ████████████████████ 40
  2. learning-rust               ████████████         24
  3. dotfiles                    ████████             16
  4. blog                        ████                 8
  5. experiments                 ██                   4

📈 日別アクティビティ:
  06/04 (火)   ████████             8
  06/05 (水)   ████████████         12
  06/06 (木)   ██████               6
  06/07 (金)   ████████████████     16
  06/08 (土)   ██                   2
  06/09 (日)   █████                5
  06/10 (月)   ████████████         12

──────────────────────────────────────────────────
アクティブな日数: 25日 / 平均: 6コミット/日
```