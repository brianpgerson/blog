---
title: "Your own Hugo blog in 20 minutes"
date: 2020-06-05
images:
tags: 
  - code
---

## Do you have twenty minutes?

Alright, good. If you don't, this is going to be a challenge, but you're welcome to give it a try anyways.

Things you need to be familiar with:

1. The command line
2. Git
3. Some kind of useful text editor that isn't Notepad or Microsoft Word 2007

Got it? Cool.

First step: install Hugo. If you're on an apple machine, it is simply:

```
brew install hugo
```

This will take some of your twenty minutes. Once it is done, create a directory for your blog. I chose :

```
mkdir ~/code/blog
```

Great! Hugo is probably almost done. When it is, you'll make sure you're in your blog directory, then:

```
hugo new site YOUR_BLOG_NAME
```

Dope! You have a scaffolding now under `blog/YOUR_BLOG_NAME`. Now you just need a theme. Don't spend too much time on this; we only had twenty minutes, remember? 

Browse https://themes.gohugo.io/ and when you find something you like, I recommend downloading the zip file so you can keep everything under one git file. Download the theme and unzip into `~/code/blog/YOUR_BLOG_NAME/themes/`. If you used the [Hermit theme](https://github.com/Track3/hermit), you would have `~/code/blog/YOUR_BLOG_NAME/themes/hermit` as your directory structure. Delete the zip file. What are we at, 8 minutes?

Okay, so if you look in `/themes/hermit/exampleSite/`, you'll see a bunch of stuff that looks kinda like your `~/code/blog/YOUR_BLOG_NAME` directory. This is not a coincidence! Every theme has a demo site that shows off how it displays a bunch of different stuff: posts, about-me pages, images, fancy markdown, etc. You want to get a shell going for YOUR site, so here's what you're going to do.

```
cp /YOUR_BLOG_NAME/themes/hermit/exampleSite/content/posts /YOUR_BLOG_NAME/content/posts
// if there's a "pages" section in the example site
cp /YOUR_BLOG_NAME/themes/hermit/exampleSite/content/pages /YOUR_BLOG_NAME/content/pages
rm /YOUR_BLOG_NAME/config.toml
cp/YOUR_BLOG_NAME/themes/hermit/exampleSite/config.toml /YOUR_BLOG_NAME/config.toml
```

More about that last command in a moment. For now, try running `hugo serve`. If you get errors, make sure you only have the one config.toml and that the github page for your theme doesn't have any esoteric requirements. Ideally, though, it'll *just work*, and you can visit the URL in the stoud (usually [localhost:1313](http://localhost:1313/)) to see your site.

Doesn't look like *your* sight, though, does it? That's fine, we have like 4 more minutes, so go ahead and open up that `config.toml`. This is, shockingly, where a bunch of your configurations live. Right now, things like `author` and `site name` etc are all set to whatever the author of your theme wanted on the demo site. 

Go ahead and edit those to reflect your own blog. You'll probably come back later and spend plenty of more time on this, but for now, maybe just get the author name to be your name.

Ok, almost done here. The rest is going to be about hosting, so if you already have a plan for that, then GET OUT OF HERE, THE REST OF US HAVE WORK TO DO!

### Hosting

I used Netlify, so that's what you will use too, if you're using this guide.

First, though, we need a repo. From `~/code/blog/YOUR_BLOG_NAME`, let's go ahead and run `git init`. Make your repo, push it up to github (or bitbucket or whatever other freaky thing you use), and head to https://www.netlify.com/.

Hurry and click `Sign up in seconds!` cause we have no time to spare!

You'll select `New site from Git` as your option, then authorize Netlify to access the new repo you just created and pushed to. Netlify should recognize that it's a Hugo site, so you can just leave the default build options it gives you.

Go ahead and click Deploy, because we're running out of time!

You should see a nice error-free build, but if you don't, one thing worth trying is copying the `netlify.toml` file from your theme's /exampleSite directory into your blog's root dir. You can also make sure that the theme you chose isn't hella old and incapable of running with current versions of Hugo. Otherwise, you're probably outta luck and going to take more than twenty minutes to figure this out.

<breathes> Okay, I think we're done. Upon successful building, Netlify will give you a random link to your blog. Check it out - it should look identical to your `hugo serve` local version. 

If you make changes locally and push them up? That's right: Netlify will kick off a *fresh build* just for you and your new commits. It literally takes a few seconds for new content to show up.

Lastly, if you would like to get a custom domain, Netlify *does* make it very easy to do so. I picked my domain, bought it for 10 bucks, and set up HTTPS within an extra couple minutes. 

Not bad for a day's work!