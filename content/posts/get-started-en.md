---
title: "Get Started: Setup your blog in 10 minutes "
description: "Tutorial of setting up your own Buroguru."
thumbnail: "/images/posts/c06f1c70-721d-4c15-abe8-1a1ca306beb0.png"
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


	![image.png](/images/posts/e594d88e-ea52-4cc8-9eff-9b19a36c8349.png)

2. Update the capabilities

	Click the new added integration, In the **Content Capabilities** section, at least toggle **Read content.**


	![image.png](/images/posts/69c8ff3a-e7ad-49df-bc7b-bd341e9a2c29.png)

3. Copy Notion token

	After creating it, you’ll see a field labeled **`Internal Integration Token`**. Copy this token, we’ll use it later.


	![image.png](/images/posts/7bc223ca-0983-45ce-8c77-47669bf21de9.png)

4. Add connection

	Go back to the Notion database you create earlier in “full page”, click the three dots in the top right, then on the bottom, click **Connections** and select the integration just added.


	![image.png](/images/posts/f10e6aa6-04a1-48fb-8b2d-522a3e67a17f.png)


	![image.png](/images/posts/da27cfb3-8741-452d-b35d-0e1b425d097f.png)

5. Copy database id

	Click **Share** button on the top right, and click **Copy Link,** and you’ll get a link like [`https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa62487XXXXXX?v=212d51c8314480a89fea000cXXXXXX&source=copy_link`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f) .


	![image.png](/images/posts/6cd01733-d963-49bc-a597-ca71c2dd6b58.png)


	And the `Database ID` will be the first id (the one before `?`), the one in the example will be  [`212d51c8314480ca8d4ffa62487XXXXXX`](https://www.notion.so/wusandwitch-notes/212d51c8314480ca8d4ffa624873e734?v=212d51c8314480a89fea000c43f4e73f)```, and keep it, we'll also use it later.


## Step 3: Setting up repository and token


Once the Notion integration is ready, you can fork the Buroguru repository to your GitHub account and deploy your blog to Vercel in just a few clicks.

1. Fork the repository

	Go to [https://github.com/WuSandWitch/Buroguru](https://github.com/WuSandWitch/Buroguru) and click **Fork.**


	![image.png](/images/posts/d9705da5-2162-48bd-9373-fccd28216c40.png)


	Give the repository you like, like `WuSandWitch-Blog`

2. Configure Github Secrets /  Notion token

	After clone, go to **Setting**, and then **Secrets and variables**, go to **Action,** and add the “Repository Secrets”, by clicking **New repository secret.**


	![image.png](/images/posts/892b3d8d-4997-4200-b7e2-3b11ac919948.png)


	![image.png](/images/posts/a5b3f762-0a2f-4522-9ef7-e5d0e854b587.png)


	Now add two secret, one is `NOTION_TOKEN`, which is the Notion Integration token we just keep.


	![image.png](/images/posts/3a882ce7-2505-4a95-9cf2-cdf3811b3e51.png)


	And another one is `NOTION_DATABASE_ID` which is the blog database id we just keep.


	![image.png](/images/posts/30d7d4f9-4e7a-4c6e-980e-128d6804bbb9.png)


## Step 4: Deploy to Vercel


With your GitHub repository ready and secrets configured, it’s time to deploy your blog to [Vercel](https://vercel.com/) and go live with your Notion-powered blog!


After logging in, click **+ Add New Project**, then select your forked repo (e.g., `WuSandWitch-Blog`).


![image.png](/images/posts/df0e8015-f0ba-45b2-94b4-0b8b339ba3c0.png)


![image.png](/images/posts/fa32636c-0747-41cd-8c4d-cbcadad479aa.png)


And with that, your blog should be welly deploy after you hit **Deploy. Congrats.**


![image.png](/images/posts/9eaab143-65a6-4f08-88c7-849845f45f15.png)


# Next Step


You can personalize your blog in config file, check [here](https://buroguru.zudo.cc/posts/config-guide-en).


# About Auto Updates


Once your blog is deployed, Buroguru will automatically sync content from your Notion database **every 12 hours** via GitHub Actions. The new posts will be published and redeployed without any manual steps.


If needed, you can also go to the **Actions tab in GitHub** and manually trigger the update workflow.


# So…


You can DM me if you encounter some trouble during deploy your blog. You can reach me from any contact information I’ve provided in [here](https://wusandwitch.zudo.cc/).


And please give me a little star on Github if you like it, I’ll be appreciated.

