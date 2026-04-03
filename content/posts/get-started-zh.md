---
title: "快速開始：用十分鐘設定你的部落格"
description: "設定你的 Buroguru 教學"
thumbnail: "/images/posts/c0bf0cde-96e1-4f88-8d93-ff8c4a8eee31.png"
date: "2025-06-22"
tags: ["tutorial"]
---

### [English Version](https://buroguru.zudo.cc/posts/get-started-en)


# 如果你還不認識 Buroguru…


請先參考這篇介紹：[什麼是 Buroguru？](https://buroguru.zudo.cc/posts/intro)


這是一份教你如何使用 Buroguru 快速部署自己 Notion 部落格的教學。


## Step 1：建立資料庫


在部署 Buroguru 之前，你需要準備一個 Notion 資料庫作為部落格的內容來源。你可以[複製這個模板](https://www.notion.so/21ad51c831448068b621f3b5def5dd2d)，或依照下列欄位自行建立：


| 欄位名稱          | 類型            | 說明                                                          |
| ------------- | ------------- | ----------------------------------------------------------- |
| `Title`       | Title         | 文章標題                                                        |
| `id`          | Text          | 文章的 ID，也是文章的網址尾段（slug），例如 `buruguru.zudo.cc/get-started-zh` |
| `Published`   | Checkbox      | 是否發佈                                                        |
| `Tags`        | Multi-select  | 分類標籤                                                        |
| `Date`        | Date          | 發佈時間                                                        |
| `Description` | Text          | 預覽時顯示的摘要                                                    |
| `Thumbnail`   | Files & media | 縮圖圖片                                                        |


## Step 2：設定 Notion Integration


為了讓 Buroguru 存取你的 Notion 資料庫，我們需要建立一個 Notion Integration 並取得金鑰。

1. 建立新的 Integration

	前往 [Notion Integration 頁面](https://www.notion.so/profile/integrations)，點選「Add Integration」，選擇資料庫所在的 workspace，並輸入名稱，例如 `blog`，logo 可略。


	![image.png](/images/posts/ef681d62-a865-4e81-a36e-d619d0e4130b.png)

2. 開啟權限

	點進剛新增的 Integration，在 **Content Capabilities** 區塊中，至少開啟 **Read content** 權限。


	![image.png](/images/posts/f82768e3-f5ed-49d0-b573-b49e08aab73f.png)

3. 複製 Notion token

	建立後你會看到 **Internal Integration Token**，請複製這個 Token，稍後會使用。


	![image.png](/images/posts/b8b956f6-78c4-4761-b5a9-aadc1912ae75.png)

4. 加入資料庫連線

	回到你剛剛建立的 Notion 資料庫（需為 full page），點右上角三點 → 選擇 **Connections**，並選擇剛剛建立的 Integration。


	![image.png](/images/posts/e077c95b-590d-4b38-953a-73eb46c3a331.png)


	![image.png](/images/posts/47555ee3-f9a9-43d7-aed7-3f4bf0c68031.png)

5. 複製資料庫 ID

	點選右上角的 **Share** → **Copy Link**，你會獲得一個類似這樣的連結：


	[`https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa62487XXXXXX?v=...`](https://www.notion.so/212d51c8314480ca8d4ffa624873e734)


	![image.png](/images/posts/ac0648e4-55fe-4784-a13d-a9d1ebc0be41.png)


	`Database ID` 就是 `?` 前的那段 ID，例如上方範例為 `212d51c8314480ca8d4ffa62487XXXXXX`，請記下來，等等會用到。


## Step 3：建立 Repository 並設定 Secrets


當 Notion 整合完成後，你可以 fork Buroguru 專案並開始部署。

1. Fork 專案

	前往 [https://github.com/WuSandWitch/Buroguru](https://github.com/WuSandWitch/Buroguru) 並點選 **Fork**


	替你的 repo 命名，例如 `WuSandWitch-Blog` 。


	![image.png](/images/posts/483fe13a-c431-45a2-8ad9-a7a71ca5bc67.png)

2. 設定 GitHub Secrets / Notion Token

	Fork 完成後，前往 **Settings → Secrets and variables → Actions**，然後點選 **New repository secret**


	![image.png](/images/posts/4fa4e826-9df8-4303-8d6e-88dba21098a0.png)


	![image.png](/images/posts/a5e4f057-a08f-4061-9e9c-8960b5a924a4.png)


	新增一個名稱為 `NOTION_TOKEN` 的 Secret，值為剛剛複製的 Notion Integration Token。


	![image.png](/images/posts/3d071269-730e-4187-9bfb-9b44aac2e485.png)


	再新增一個 Secret 名稱為 `NOTION_DATABASE_ID`，值為你剛剛記下的資料庫 ID。


	![image.png](/images/posts/f7d5a976-d257-4938-b2f0-d3c4b4437382.png)


## Step 4：部署到 Vercel


現在你已經設定好 GitHub repo 和環境變數，接下來我們要將專案部署到 [Vercel](https://vercel.com/)！


登入後，點選 **+ Add New Project**，然後選擇你 fork 的 repo（例如 `WuSandWitch-Blog`）


![image.png](/images/posts/513563de-d4cf-425b-a87c-6489c344218f.png)


![image.png](/images/posts/70eac66d-79eb-4d39-9e0d-8ca43d351ab7.png)


按下 **Deploy** 即可部署，幾秒鐘後你的部落格就會正式上線！


![image.png](/images/posts/534fcd51-b2e1-4a07-a73c-e71deea25c65.png)


## 下一步：個人化你的部落格


你可以在 config 檔案裡面設定你的部落格，[教學看這ㄦ](https://buroguru.zudo.cc/posts/config-guide-zh)


## ⏱ 自動更新機制


部署完成後，Buroguru 會透過 GitHub Actions **每 12 小時自動同步 Notion 資料並重新部署**，你不需要額外操作。


如果需要立即更新，也可以到 GitHub 專案的 **Actions** 分頁手動觸發 workflow。


## 🗣 有問題嗎？


如果你在部署過程中遇到任何問題，歡迎透過[這裡](https://wusandwitch.zudo.cc/)提供的聯絡方式私訊我！


如果你覺得這個專案對你有幫助，請幫我在 GitHub 上按個 ⭐️，我會非常感謝！

