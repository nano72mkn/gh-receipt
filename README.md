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
# 自分の活動レシートを出力（過去30日間）
gh-receipt

# 特定のユーザーのレシートを出力
gh-receipt nano72mkn

# 期間オプション
gh-receipt -w              # 週間レポート（7日間）
gh-receipt --monthly       # 月間レポート（30日間）  
gh-receipt -y              # 年間レポート（365日間）
gh-receipt -d 90           # カスタム期間（90日間）

# 前期間との比較
gh-receipt -w --diff       # 今週 vs 先週
gh-receipt -m --diff       # 今月 vs 先月
gh-receipt -y --diff       # 今年 vs 昨年

# ユーザー指定と組み合わせ
gh-receipt nano72mkn -w    # nano72mkn の週間レポート
```

## 認証について

gh CLI の認証を使用するため、追加の設定は不要です。プライベートリポジトリも自動的に含まれます。

認証状態の確認：
```bash
gh auth status
```

## 出力例

```
================================================
                                                
            GITHUB ACTIVITY RECEIPT             
                                                
================================================
  2025/06/10 17:20:00                    
  USER: @nano72mkn                           
------------------------------------------------
                                                
  COMMITS (PUBLIC)                        3
  COMMITS (PRIVATE)                     581
                                  ------------- 
  TOTAL ACTIVITIES                      584
================================================
                                                
  DAILY BREAKDOWN (LAST 7 DAYS)                
  -----------------------------                
  06/04 水  [***                 ]   3
  06/05 木  [-                   ]   0
  06/06 金  [-                   ]   0
  06/07 土  [-                   ]   0
  06/08 日  [********************]  43
  06/09 月  [********************]  31
  06/10 火  [*********           ]   9
                                                
================================================
  NO: 3BCD58ACBCDA                             
                                                
  |||||| |||| | |||| ||| |||| ||||||| |||||||  
  3BCD58ACBCDA                                  
                                                
================================================
         Thank you for your commits!            
            Have a productive day!              
================================================

Powered by gh-receipt
```