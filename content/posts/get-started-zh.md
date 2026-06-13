---
title: "快速開始：用十分鐘設定你的部落格"
description: "設定你的 Buroguru 教學"
thumbnail: "/images/posts/e24c53c0-ea28-4522-a95e-6a420b0b6f4f.png"
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


	![image.png](/images/posts/3df0679e-6251-4015-a694-5cd0ccb58e1e.png)

2. 開啟權限

	點進剛新增的 Integration，在 **Content Capabilities** 區塊中，至少開啟 **Read content** 權限。


	![image.png](/images/posts/7cb9801f-a02d-4785-85d5-2d527824808d.png)

3. 複製 Notion token

	建立後你會看到 **Internal Integration Token**，請複製這個 Token，稍後會使用。


	![image.png](/images/posts/a84a2dfe-6335-49c3-aa09-60cf1685be50.png)

4. 加入資料庫連線

	回到你剛剛建立的 Notion 資料庫（需為 full page），點右上角三點 → 選擇 **Connections**，並選擇剛剛建立的 Integration。


	![image.png](/images/posts/c8df0eb2-60f4-457c-97a4-b8d4b36d2369.png)


	![image.png](/images/posts/f2a4854e-524c-4e43-918c-ee8ff235d4bb.png)

5. 複製資料庫 ID

	點選右上角的 **Share** → **Copy Link**，你會獲得一個類似這樣的連結：


	[`https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa62487XXXXXX?v=...`](https://www.notion.so/212d51c8314480ca8d4ffa624873e734)


	![image.png](/images/posts/0ae17a83-03cc-4373-9c48-01d30dcb6df7.png)


	`Database ID` 就是 `?` 前的那段 ID，例如上方範例為 `212d51c8314480ca8d4ffa62487XXXXXX`，請記下來，等等會用到。


## Step 3：建立 Repository 並設定 Secrets


當 Notion 整合完成後，你可以 fork Buroguru 專案並開始部署。

1. Fork 專案

	前往 [https://github.com/WuSandWitch/Buroguru](https://github.com/WuSandWitch/Buroguru) 並點選 **Fork**


	替你的 repo 命名，例如 `WuSandWitch-Blog` 。


	![image.png](/images/posts/68f09e2c-f8a9-4d1d-adcf-c905994f1147.png)

2. 設定 GitHub Secrets / Notion Token

	Fork 完成後，前往 **Settings → Secrets and variables → Actions**，然後點選 **New repository secret**


	![image.png](/images/posts/9ae4d659-6b89-47cb-a206-c0090517ef30.png)


	![image.png](/images/posts/0dac5e19-a666-4786-ae58-ec9dc7429bb8.png)


	新增一個名稱為 `NOTION_TOKEN` 的 Secret，值為剛剛複製的 Notion Integration Token。


	![image.png](/images/posts/716a887a-88c6-4eb7-b2d7-67d9c78a9b1b.png)


	再新增一個 Secret 名稱為 `NOTION_DATABASE_ID`，值為你剛剛記下的資料庫 ID。


	![image.png](/images/posts/36cac380-b75a-4b84-b685-69c59f9b83bc.png)


## Step 4：部署到 Vercel


現在你已經設定好 GitHub repo 和環境變數，接下來我們要將專案部署到 [Vercel](https://vercel.com/)！


登入後，點選 **+ Add New Project**，然後選擇你 fork 的 repo（例如 `WuSandWitch-Blog`）


![image.png](/images/posts/e48dd9d5-7295-46a8-b355-9c3984f4a1be.png)


![image.png](/images/posts/d13e581f-78b8-4961-a33f-76f763356f44.png)


按下 **Deploy** 即可部署，幾秒鐘後你的部落格就會正式上線！


![image.png](/images/posts/42b6c9e9-eb89-462b-97a2-d2fe52b7f097.png)


## 下一步：個人化你的部落格


你可以在 config 檔案裡面設定你的部落格，[教學看這ㄦ](https://buroguru.zudo.cc/posts/config-guide-zh)


## ⏱ 自動更新機制


部署完成後，Buroguru 會透過 GitHub Actions **每 12 小時自動同步 Notion 資料並重新部署**，你不需要額外操作。


如果需要立即更新，也可以到 GitHub 專案的 **Actions** 分頁手動觸發 workflow。


## 🗣 有問題嗎？


如果你在部署過程中遇到任何問題，歡迎透過[這裡](https://wusandwitch.zudo.cc/)提供的聯絡方式私訊我！


如果你覺得這個專案對你有幫助，請幫我在 GitHub 上按個 ⭐️，我會非常感謝！

