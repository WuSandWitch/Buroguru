---
title: "Get Started: Setup your blog in 10 minutes "
description: "Tutorial of setting up your own Buroguru."
thumbnail: "/images/posts/aef5a942-c187-4cd4-ac57-2c8da898b8c6.png"
date: "2025-06-22"
tags: ["tutorial"]
---

### [中文版本](https://buroguru.zudo.cc/posts/get-started-zh)


# If…


you don’t know what is Buroguru, please check here.


This is the quick tutorial that teach how to deploy your own Notion blog using Buroguru.


## Step 1: Setting up database


Before deploying Buroguru, you'll need to prepare a Notion database to serve as your blog’s content source. You can either clone the [template](/21ad51c831448068b621f3b5def5dd2d) or create your own with following fields.


| Field Name    | Type          | Description                                                                                 |
| ------------- | ------------- | ------------------------------------------------------------------------------------------- |
| `Title`       | Title         | The title of the post.                                                                      |
| `id`          | Text          | The id of the post, also the url-slug of the blog. (e.g. `buruguru.zudo.cc/get-started-en`. |
| `Published`   | Checkbox      | Whether to publish.                                                                         |
| `Tags`        | Multi-select  | Category tags                                                                               |
| `Date`        | Date          | Just date that indicate the time your wrote the post.                                       |
| `Description` | Text          | Brief summary of the posts shown in preview.                                                |
| `Thumbnail`   | Files & media | Thumbnail image.                                                                            |


## Step 2: Setting up Notion Integration


To allow Buroguru to access your Notion database, you need to create a Notion Integration and get the access token.

1. Create new integration

	Go to [Notion Integration](https://www.notion.so/profile/integrations) and click ‘Add Integration’, select the workspace where your database is located, and give your integration a name like ‘blog’, the logo is not required.


	![image.png](/images/posts/91abec79-39d5-4401-880a-538073a2eddf.png)

2. Update the capabilities

	Click the new added integration, In the **Content Capabilities** section, at least toggle **Read content.**


	![image.png](/images/posts/19d09d18-1199-4856-a863-212a98141880.png)

3. Copy Notion token

	After creating it, you’ll see a field labeled **`Internal Integration Token`**. Copy this token, we’ll use it later.


	![image.png](/images/posts/c47dc97b-950b-4ef4-a21d-26dddf13f5d8.png)

4. Add connection

	Go back to the Notion database you create earlier in “full page”, click the three dots in the top right, then on the bottom, click **Connections** and select the integration just added.


	![image.png](/images/posts/226a47ce-fdc5-4251-aa00-e17746674e7d.png)


	![image.png](/images/posts/af15d7ad-ace8-4488-94a2-409964e662f2.png)

5. Copy database id

	Click **Share** button on the top right, and click **Copy Link,** and you’ll get a link like [`https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa62487XXXXXX?v=212d51c8314480a89fea000cXXXXXX&source=copy_link`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f) .


	![image.png](/images/posts/a15ca285-7f82-434d-8650-cfc1296092ed.png)


	And the `Database ID` will be the first id (the one before `?`), the one in the example will be  [`212d51c8314480ca8d4ffa62487XXXXXX`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f)```, and keep it, we'll also use it later.


## Step 3: Setting up repository and token


Once the Notion integration is ready, you can fork the Buroguru repository to your GitHub account and deploy your blog to Vercel in just a few clicks.

1. Fork the repository

	Go to [https://github.com/WuSandWitch/Buroguru](https://github.com/WuSandWitch/Buroguru) and click **Fork.**


	![image.png](/images/posts/b76fe014-1aea-4779-9074-d341624c68d8.png)


	Give the repository you like, like `WuSandWitch-Blog`

2. Configure Github Secrets /  Notion token

	After clone, go to **Setting**, and then **Secrets and variables**, go to **Action,** and add the “Repository Secrets”, by clicking **New repository secret.**


	![image.png](/images/posts/b0bd7d69-ca80-4a6c-8e45-8ac4fc884b83.png)


	![image.png](/images/posts/c74d0fae-b831-4139-92df-150a7b39d0d3.png)


	Now add two secret, one is `NOTION_TOKEN`, which is the Notion Integration token we just keep.


	![image.png](/images/posts/585aae8f-a2ce-4fd5-a433-7d433e6f10fb.png)


	And another one is `NOTION_DATABASE_ID` which is the blog database id we just keep.


	![image.png](/images/posts/a5e41727-dd6c-4ee8-8d84-1c05839bce5b.png)


## Step 4: Deploy to Vercel


With your GitHub repository ready and secrets configured, it’s time to deploy your blog to [Vercel](https://vercel.com/) and go live with your Notion-powered blog!


After logging in, click **+ Add New Project**, then select your forked repo (e.g., `WuSandWitch-Blog`).


![image.png](/images/posts/224323cc-f9df-4b0d-90e5-db9fca2cdd07.png)


![image.png](/images/posts/e6c54243-7d0c-470c-a4a0-2e1c8bd73c68.png)


And with that, your blog should be welly deploy after you hit **Deploy. Congrats.**


![image.png](/images/posts/7e605ad5-6aaf-4db5-8243-351d01797fcc.png)


# Next Step


You can personalize your blog in config file, check [here](https://buroguru.zudo.cc/posts/config-guide-en).


# About Auto Updates


Once your blog is deployed, Buroguru will automatically sync content from your Notion database **every 12 hours** via GitHub Actions. The new posts will be published and redeployed without any manual steps.


If needed, you can also go to the **Actions tab in GitHub** and manually trigger the update workflow.


# So…


You can DM me if you encounter some trouble during deploy your blog. You can reach me from any contact information I’ve provided in [here](https://wusandwitch.zudo.cc/).


And please give me a little star on Github if you like it, I’ll be appreciated.

