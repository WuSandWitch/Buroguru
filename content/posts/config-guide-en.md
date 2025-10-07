---
title: "Buroguru Configuration Guide: Customize Your Blog"
description: "Complete guide to Buroguru configuration, learn how to easily customize your blog's appearance, features, and content settings."
thumbnail: "/images/posts/4fbe1bdd-a408-4f9d-b473-18142e73eb4a.png"
date: "2025-06-26"
tags: ["tutorial"]
---

![image.png](/images/posts/5715d3c8-61b8-46b5-8b1c-3a4ee4f7b271.png)


# Buroguru Configuration Guide: Customize Your Blog


Buroguru provides a powerful and flexible configuration system that allows you to easily customize every aspect of your blog. All configurations are centralized in the `buroguru-config.ts` file, making management simple and intuitive.


## Configuration File Structure


The configuration file is divided into several main sections:

- **Site Settings**
- **Author Settings**
- **Appearance**
- **Blog Settings**
- **Homepage**
- **Footer**

## Basic Site Settings


```typescript
site: {
  name: "Your Blog Name",
  description: "Blog description",
  url: "<https://yourblog.com>"
}
```


These settings affect:

- Browser title and SEO
- Site name in navigation bar
- Information when sharing on social media

## Author Information Configuration


```typescript
author: {
  name: "Your Name",
  bio: "Personal bio",
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


Author information is displayed in:

- Article detail pages
- Profile card
- Footer area

## Appearance Customization


### Font Settings


```typescript
appearance: {
  fontFamily: 'serif', // 'serif' | 'sans' | 'mono'
  customFont: 'Inter', // Google Fonts name (optional)
}
```

- `fontFamily`: Choose basic font type
- `customFont`: Use Google Fonts custom font

### Color Theme


```typescript
appearance: {
  primaryColor: '222.2 84% 4.9%', // HSL format
  secondaryColor: '210 40% 96%',  // HSL format
}
```


Color values use HSL format (hue saturation lightness), automatically adapting to dark and light modes.


### Logo Settings


```typescript
appearance: {
  logo: '/images/logo.png'
}
```


If a logo is set, it will be used preferentially in the navigation bar and homepage, otherwise the author avatar will be used.


## Blog Feature Settings


```typescript
blog: {
  postsPerPage: 10,     // Number of posts per page
  showExcerpt: true,    // Whether to show excerpts in lists
  showTags: true,       // Whether to show tags
  defaultThumbnail: "/images/default.png" // Default thumbnail (optional)
}
```


These settings control:

- How article lists are displayed
- Pagination behavior
- Display of tags and excerpts

## Homepage Customization


### Hero Section Settings


```typescript
homepage: {
  hero: {
    title: "Blog Title",
    description: "Blog description text",
    primaryButton: {
      text: "Get Started",
      href: "/posts/get-started"
    },
    secondaryButton: {
      text: "Learn More",
      href: "/about"
    }
  }
}
```


### Recent Posts Section


```typescript
homepage: {
  recentPosts: {
    title: "Recent Posts",
    viewAllText: "View all posts",
    count: 3  // Number of recent posts to display
  }
}
```


## Footer Settings


```typescript
footer: {
  text: "© 2024 Your Name",
  showBuiltWith: true,  // Whether to show "Built with Buroguru"
  links: [
    { name: "Privacy Policy", href: "/privacy" },
    { name: "Contact Us", href: "/contact" }
  ]
}
```


## Complete Configuration Example


```typescript
const config: BuroguruConfig = {
  site: {
    name: "My Tech Blog",
    description: "Sharing programming and technology insights",
    url: "<https://myblog.com>"
  },

  author: {
    name: "John Doe",
    bio: "Full-stack developer passionate about sharing technical knowledge",
    avatar: "/images/avatar.jpg",
    email: "contact@myblog.com",
    social: {
      github: "<https://github.com/username>",
      twitter: "<https://twitter.com/username>"
    }
  },

  appearance: {
    fontFamily: 'sans',
    customFont: 'Inter',
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
      { name: "Home", href: "/" },
      { name: "Tech Articles", href: "/posts" },
      { name: "About Me", href: "/about" }
    ]
  },

  homepage: {
    hero: {
      title: "Welcome to My Tech Blog",
      description: "Sharing programming experiences and technical insights",
      primaryButton: {
        text: "Start Reading",
        href: "/posts"
      },
      secondaryButton: {
        text: "About Me",
        href: "/about"
      }
    },
    recentPosts: {
      title: "Latest Posts",
      viewAllText: "View All",
      count: 4
    }
  },

  footer: {
    text: "John Doe's Tech Blog",
    showBuiltWith: true
  }
}
```


## Configuration Reference


### Site Settings

- `name`: Site name (string)
- `description`: Site description for SEO (string)
- `url`: Site URL (string)
- `favicon`: Custom favicon path (optional string)

### Author Settings

- `name`: Author name (string)
- `bio`: Author biography (string)
- `avatar`: Author avatar image path (string)
- `email`: Contact email (optional string)
- `social`: Social media links (object)
	- `github`: GitHub profile URL
	- `twitter`: Twitter profile URL
	- `linkedin`: LinkedIn profile URL
	- `notion`: Notion profile URL
	- `website`: Personal website URL

### Appearance Settings

- `fontFamily`: Base font family ('serif' | 'sans' | 'mono')
- `customFont`: Google Fonts name (optional string)
- `primaryColor`: Primary color in HSL format (string)
- `secondaryColor`: Secondary color in HSL format (optional string)
- `logo`: Logo image path (optional string)

### Blog Settings

- `postsPerPage`: Number of posts per page (number)
- `showExcerpt`: Whether to show post excerpts (boolean)
- `showTags`: Whether to show post tags (boolean)
- `defaultThumbnail`: Default post thumbnail (optional string)

### Navigation Settings

- `links`: Array of navigation links
	- `name`: Link display name (string)
	- `href`: Link URL (string)
	- `external`: Whether it's an external link (optional boolean)

### Homepage Settings

- `hero`: Hero section configuration
	- `title`: Main headline (string)
	- `description`: Description text (string)
	- `primaryButton`: Primary CTA button
	- `secondaryButton`: Secondary CTA button
- `recentPosts`: Recent posts section
	- `title`: Section title (string)
	- `viewAllText`: "View all" link text (string)
	- `count`: Number of posts to show (number)

### Footer Settings

- `text`: Footer text (optional string)
- `showBuiltWith`: Show "Built with Buroguru" link (boolean)
- `links`: Additional footer links (optional array)
