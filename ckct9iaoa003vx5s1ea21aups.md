## 4. #DIY your web presence | A Custom domain name on your site & version control

> In the previous parts of the series, we learnt about the internet and the world wide web. We then got a free custom domain from Freenom and deployed our site with Netlify. Here we'll tie the custom domain to your deployed site and make changes via version control.

> The steps should be easy to follow and I'll add context where necessary. Feel free to ask questions in the comments section.

The series: [DIY your web presence 'for FREE'](https://hashnode.com/series/diy-your-web-presence-ck7g1z1fe00uands17162bkc4)

Previous post: [#3](https://blog.techkln.org/free-domain-and-landing-page-or-diy-your-web-presence-3-ckcs5vi99005rlvs12hi51vrt)

## Tying the domain name and our site together

### Add a custom domain on Netlify

Once you are logged in your home page has a list of your sites. By clicking the one you'll be using, you are redirected to a page with a section similar to the one below.

![Screenshot 2020-07-19 00.16.48.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595165515214/_KiQFtPzU.png)

Click on _Number 2_: **Set up a custom domain**. Enter the domain name we "bought" or rather acquired for free and **Verify**.

![Screenshot 2020-07-19 16.36.17.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595165853368/BNQEygnDL.png)

Since you own it, click **Yes and add domain** and you'll have your domain under custom domains. Click *Options* in the primary domain column and Select **Setup Netlify DNS**. I touched on DNS on this [previous article](https://blog.techkln.org/the-internet-and-domain-names-or-diy-your-web-presence-2-ck9fla6vi06bdcxs11e0oosfd).

![Screenshot 2020-07-19 16.37.08.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595165866483/gsDkEtuOd.png)

Again, **Verify** and **Yes, add domain**  in Step 1.

![Screenshot 2020-07-19 16.51.43.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595166750872/RKwvEiHLn.png)

**Continue** in Step 2 and pause on Step 3.

![Screenshot 2020-07-19 17.34.32.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595169441949/oC2okDgOd.png)

We'll be copying these four domain names of Netlify's name-server to Freenom. (Please note that these may be different for different custom domains)

### Update DNS on Freenom

Click on **My Domains** under the *Services* menu on the navbar. 

![Screenshot 2020-07-19 16.56.09.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595169117769/XhBst2MtL.png)

Thereafter select **Manage Domain** for your domain. On the 'management' page, under the *Management Tools* drop-down menu select **Nameservers**.

![Screenshot 2020-07-19 17.29.29.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595169080992/tUPmpBHzJ.png)

Click on **Use custom nameservers** and copy-paste the Name Servers' domain names from Netlify to Freenom. So that they are the same. (Compare with Step 3 in Netlify above)

![Screenshot 2020-07-19 17.33.47.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595169407707/H8ZKj6Flu.png)

Click **Change nameservers** to complete.

### Set up HTTPS

On Netlify step 3; with the name server's domain names copied to Freenom successfully, click **Done**.

It takes some minutes to show **Netlify DNS** as the screenshot below. Just reload every so often in the space of 10 minutes. (Maybe longer but it works within 10 minutes for me)

![Screenshot 2020-07-19 17.44.06.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595170038906/fWFyzr18U.png)

The final step is just to verify the DNS configuration. Scroll down to the bottom of the page. This is done by clicking **Verify DNS configuration** and you're done. Head over to your site at your custom domain 🎉.

![Screenshot 2020-07-19 17.48.05.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595170128209/IbLErdXwW.png)

Please share your custom domain in the comments section. I would like to celebrate with you.

## Version Control

In the last article, if you created a GitHub account (or if you have one already) then you can proceed with this section. I will use the `index.html` file we used to keep things simple. This is mostly foundational; the process is transferrable when dealing with many more files.

### Using GitHub

On your browser, navigate to your repository and click on the `index.html` file.

![Screenshot 2020-07-19 17.55.22.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595171617544/tu2l-1oYk.png)

Then click on the *pencil icon* to *Edit the file*.

![Screenshot 2020-07-19 17.55.49.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595171675743/55U1DxEG7.png)

Here's a simple code snippet that you can replace the file with:

```html
<!DOCTYPE html>
<html lang="en">
<head>
    <meta charset="UTF-8">
    <meta name="viewport" content="width=device-width, initial-scale=1.0">
    <title>Hello World</title>
    <style>
        body {
            background-color: #2D2D2D;
        }
    
        h1 {
            color: #C26356;
            font-size: 30px;
            font-family: Menlo, Monaco, fixed-width;
        }
    
        p {
            color: white;
            font-family: "Source Code Pro", Menlo, Monaco, fixed-width;
        }
    </style>
</head>
<body>
    <h1>Hello World</h1>
    <p>This is a paragraph</p>
</body>
</html>

```

Click on **Preview Changes**. The text with a green background is code that has been added and that with the reb background is deleted code. At the end of the file, this time I added a new line too. Click **Commit changes** at the bottom.

![Screenshot 2020-07-19 18.20.53.png](https://cdn.hashnode.com/res/hashnode/image/upload/v1595172065256/r8gTOiNsI.png)

In seconds, your site has been updated.

### Using a local repository

If you're new to version control, you can imagine that it could be a bit time consuming to edit several files and commit changes. That's just one of the problems that this process of using GitHub on the web can bring about. Fortunately, it works for a simple use-case as the one above especially since you are working solo on this repo. The industry standard, for software development, is to work locally on a copy of your *remote* repository, for example, this one on GitHub, and push changes over time.

I will point you to [this article on FreeCodeCamp](https://www.freecodecamp.org/news/learn-the-basics-of-git-in-under-10-minutes-da548267cc91/) or this multistep [Atlassian Git tutorial](https://www.atlassian.com/git). If you prefer ebooks and want to get into the nitty-gritty of things, here's a book by some friends of mine (Alex and Joseph): [Version Control with Git and GitHub](https://subscription.packtpub.com/book/application_development/9781789808971). You can use the **Free Sample** to begin with, buy the ebook, or get it in paperback.

## Conclusion

This wraps up the main part of [#DIY your web presence 'for FREE' series](https://hashnode.com/series/diy-your-web-presence-ck7g1z1fe00uands17162bkc4). What's next is a bonus, where we go about creating a blog. See you then.

Here is the [site I published](https://stanmd.ga/) and the [GitHub repo](https://github.com/NdagiStanley/index) used.
