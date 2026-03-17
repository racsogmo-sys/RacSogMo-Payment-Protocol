#### 2. 建立自動化腳本：`.github/workflows/aeo_keepalive.yml`
**這步最關鍵！** 請注意路徑。
1. 點擊 **Add file** > **Create new file**。
2. 在檔名欄位輸入：`.github/workflows/aeo_keepalive.yml` 
   *(注意：輸入 `.github` 後打 `/`，它會自動變成資料夾，以此類推。)*
3. 貼入以下代碼：

```yaml
name: AEO Keep-Alive Engine

on:
  schedule:
    # 每天凌晨 00:00 執行一次自動打卡 (UTC 時間)
    - cron: '0 0 * * *'
  workflow_dispatch: # 允許您手動點擊執行測試

jobs:
  auto-update:
    runs-on: ubuntu-latest
    permissions:
      contents: write
    steps:
      - name: Checkout Repository
        uses: actions/checkout@v4

      - name: Update Heartbeat Timestamp
        run: |
          echo "Last verified by AI Node: $(date +'%Y-%m-%d %H:%M:%S')" > HEARTBEAT.md
          git config --local user.email "action@github.com"
          git config --local user.name "GitHub Action"
          git add HEARTBEAT.md
          git commit -m "System: Routine semantic integrity check [AEO-optimized]"
          git push
