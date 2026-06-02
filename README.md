# 石垣島リマインダー（Discord自動通知）

GitHub Actions のサーバーから毎日 Discord にトレーニングのリマインダーを送る仕組み。
**パソコン（Mac）がオフでも動きます。**

## 中身
- `.github/workflows/reminder.yml` … 毎日 朝8時ごろ / 夜21時ごろ（日本時間）に Discord へ投稿
- Discord の Webhook URL は GitHub の「Secrets」に `DISCORD_WEBHOOK_URL` という名前で保存（コードには書かない）

## 手動テスト
GitHubの「Actions」タブ →「Ishigaki Reminder」→「Run workflow」で今すぐ1通送れる。

## 時間・文面を変えたいとき
`reminder.yml` の cron（UTC基準。8:00 JST=`0 23`、21:00 JST=`0 12`）やメッセージを編集。

## 旅行(6/13)後に止めたいとき
- Actionsタブ →「Ishigaki Reminder」→ 右上「…」→「Disable workflow」で停止。
- または Claude に「リマインダー止めて」と頼む。
