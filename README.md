# IG_Crawler — Instagram 自動化資料爬取工具

本專案使用 Python + Selenium 自動化爬取 Instagram 貼文資訊與留言內容，並將資料整理為可供分析的 CSV 格式。
適合資料分析、研究專題、互動行為研究等用途。

## 功能特色

可自動登入 Instagram，若是初次使用，登入後將儲存登入階段於瀏覽器

自動滾動頁面載入更多內容

擷取貼文文字、按讚數、留言資料

下載 Reels / 影片（透過 yt-dlp）

自動清洗表情符號、整理格式

將結果匯出成 CSV

📦 套件需求（Requirements）

可使用 pip 一次安裝，請執行：

`pip install selenium pandas emoji yt-dlp`

## 執行過程

1. 執行主程式
python ig_crawler.py

2. 若初次使用則需於終端機輸入帳號密碼，登入過之後即會自動登入

3. 輸入欲爬取之帳號

程式將會自動載入頁面、滾動、擷取資料。

## 輸出資料

- 最終將輸出以下欄位的 CSV：

  - 帳號名稱

  - 發文時間

  - 按讚數

  - 檔案大小

  - 影片時長

  - 影片網址

- 以及另一個CSV專門存放留言資料

  - 影片ID

  - 留言內容

## 注意事項（Important Notes）

- 若登入需要雙重驗證，請手動輸入。

- 使用 yt-dlp 下載，因此請確保COOKIE檔案有正常產生。

- 因IG觀看留言數需HOVER產生，無法使用headless，因此選擇將視窗移出顯示範圍外，避免誤觸同時也提升美觀與方便性

## 使用到的主要套件

- Selenium

  負責控制瀏覽器、登入、滾動、抓元素。

- Pandas

  整理爬到的資料，輸出 CSV 格式。

- Emoji

  處理留言裡的 Emoji。

- yt-dlp

  下載 Instagram Reels。

## 未來可改進（TODO）

- 加入更多錯誤處理（Exception Handling）

- 改成 Async（提高爬取速度）
