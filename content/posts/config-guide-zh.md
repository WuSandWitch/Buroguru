---
title: "Buroguru 配置指南：自定義你的部落格"
description: "完整的 Buroguru 配置教學，讓你輕鬆自定義部落格的外觀、功能和內容設定。"
thumbnail: "/images/posts/9cd0cb7b-cede-4fea-ada6-4db0b57ecaae.png"
date: "2025-06-26"
tags: ["tutorial"]
---

# Buroguru 配置指南：自定義你的博客


Buroguru 提供了一個簡單的個人化功能，讓你可以輕鬆自定義部落格的各種部分。所有配置都集中在 `buroguru-config.ts` 文件中，讓部署變得簡單直覺。


## 配置文件結構


配置文件分為以下幾個主要部分：

- **網站設定** (Site Settings)
- **作者資訊** (Author Settings)
- **外觀設定** (Appearance)
- **博客功能** (Blog Settings)
- **首頁設定** (Homepage)
- **頁腳設定** (Footer)

## 網站基本設定


```typescript
site: {
  name: "你的部落格名稱",
  description: "部落格描述",
  url: "<https://yourblog.com>"
}
```


這些設定會影響：

- 瀏覽器標題和 SEO
- 導航欄中的網站名稱
- 社交媒體分享時的資訊

## 作者資訊配置


```typescript
author: {
  name: "你的名字",
  bio: "個人簡介",
  avatar: "/images/avatar.png",
  email: "your@email.com",
  social: {
    github: "<https://github.com/username>",
    twitter: "<https://twitter.com/username>",
    linkedin: "<https://linkedin.com/in/username>",
    notion: "<https://notion.so/username>",
    website: "<https://yourwebsite.com>"
  }
}
```


作者資訊會顯示在：

- 文章詳情頁
- 個人資料卡片
- 頁腳區域

## 外觀自定義


### 字體設定


```typescript
appearance: {
  fontFamily: 'serif', // 'serif' | 'sans' | 'mono'
  customFont: 'Inter', // Google Fonts 字體名稱（可選）
}
```

- `fontFamily`: 選擇基本字體類型
- `customFont`: 使用 Google Fonts 自定義字體

### 顏色主題


```typescript
appearance: {
  primaryColor: '222.2 84% 4.9%', // HSL 格式
  secondaryColor: '210 40% 96%',  // HSL 格式
}
```


顏色值使用 HSL 格式（色相 飽和度 明度），會自動適配深色和淺色模式。


### 標誌設定


```typescript
appearance: {
  logo: '/images/logo.png'
}
```


如果設定了 logo，會在導航欄和首頁中優先使用，否則使用作者頭像。


## 博客功能設定


```typescript
blog: {
  postsPerPage: 10,     // 每頁顯示文章數量
  showExcerpt: true,    // 是否在列表中顯示摘要
  showTags: true,       // 是否顯示標籤
  defaultThumbnail: "/images/default.png" // 預設縮圖（可選）
}

```


這些設定控制：

- 文章列表的顯示方式
- 分頁行為
- 標籤和摘要的顯示

## 首頁自定義


### Hero 設定


```typescript
homepage: {
  hero: {
    title: "博客標題",
    description: "博客描述文字",
    primaryButton: {
      text: "開始閱讀",
      href: "/posts/get-started"
    },
    secondaryButton: {
      text: "了解更多",
      href: "/about"
    }
  }
}

```


### 最新文章區塊


```typescript
homepage: {
  recentPosts: {
    title: "最新文章",
    viewAllText: "查看所有文章",
    count: 3  // 顯示最新文章數量
  }
}
```


## 頁腳設定


```typescript
footer: {
  text: "© 2025 你的名字",
  showBuiltWith: true,  // 是否顯示 "Built with Buroguru"
  links: [
    { name: "隱私政策", href: "/privacy" },
    { name: "聯絡我們", href: "/contact" }
  ]
}

```


## 完整配置範例


```typescript
const config: BuroguruConfig = {
  site: {
    name: "我的技術部落格",
    description: "分享程式設計和技術心得",
    url: "<https://myblog.com>"
  },

  author: {
    name: "張小明",
    bio: "全端工程師，熱愛分享技術知識",
    avatar: "/images/avatar.jpg",
    email: "contact@myblog.com",
    social: {
      github: "<https://github.com/username>",
      twitter: "<https://twitter.com/username>"
    }
  },

  appearance: {
    fontFamily: 'sans',
    customFont: 'Noto Sans TC',
    primaryColor: '200 100% 50%',
    logo: '/images/logo.png'
  },

  blog: {
    postsPerPage: 8,
    showExcerpt: true,
    showTags: true
  },

  navigation: {
    links: [
      { name: "首頁", href: "/" },
      { name: "技術文章", href: "/posts" },
      { name: "關於我", href: "/about" }
    ]
  },

  homepage: {
    hero: {
      title: "歡迎來到我的技術部落格",
      description: "在這裡分享程式設計經驗和技術見解",
      primaryButton: {
        text: "開始閱讀",
        href: "/posts"
      },
      secondaryButton: {
        text: "關於我",
        href: "/about"
      }
    },
    recentPosts: {
      title: "最新文章",
      viewAllText: "查看全部",
      count: 4
    }
  },

  footer: {
    text: "張小明的技術部落格",
    showBuiltWith: true
  }
}

```

