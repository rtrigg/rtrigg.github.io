---
title: "Setting up Hugo Blog on GitHub"
date: 2022-07-17T21:48:45-04:00
draft: false
---

I wanted to create a tech blog, where I could make posts, and I figured why not
on GitHub? After searching around, I decided on using Hugo for it, and started
with [this guide](https://gohugo.io/hosting-and-deployment/hosting-on-github),
and stumbled around on the internet to figure out the rest. This is less of a
"howto" and more of a window into a "howdid;" there's a ton of links at the end
where you can find well-organized instructions.

First, install Hugo

`brew install hugo # or apt, yum, from source, etc`

Then create a repository:

```
mkdir rtrigg.github.io # idk you gotta name it this way for pages
cd rtrigg.github.io
git init
# go create a repo on github, come back and:
git remote add origin git@github.com:rtrigg/rtrigg.github.io.git
```

[Add a GitHub Action to publish the work](https://gohugo.io/hosting-and-deployment/hosting-on-github):

```
mkdir -p .github/workflows/
vim .github/workflows/gh-pages.yml
git add .github/workflows/gh-pages.yml
git commit -m "Add github action to build site"
git push --set-upstream origin main
```

Create a config.yaml ([or toml or json](https://gohugo.io/getting-started/configuration/)) containing the following:

```
Params:
  baseURL: https://rtrigg.github.io
```

Add some content:
```
echo "# start of rtrigg.github.io" >> README.md
git add README.md
git add config.yaml
git commit -m "Add README and config.yaml"
git push
```

Oh but I [forgot to make a new hugo site](https://github.com/gohugoio/hugo/issues/4825):
```
hugo new site . --force
```

which prints out:

> Just a few more steps and you're ready to go:
>
>1. Download a theme into the same-named folder.
>   Choose a theme from https://themes.gohugo.io/ or
>   create your own with the "hugo new theme <THEMENAME>" command.
>2. Perhaps you want to add some content. You can add single files
>   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
>3. Start the built-in live server via "hugo server".

Oh, but that makes a new config.toml, when I was using a config.yaml...

```
cat config.toml
baseURL = 'http://example.org/'
languageCode = 'en-us'
title = 'My New Hugo Site'
```

Maybe I can set similar variables to use my config.yaml instead?

```
cat config.yaml
Params:
  baseURL: https://rtrigg.github.io
  languageCode: 'en-us'
  title: 'My Tech Blog'

rm config.toml
```

I scroll up in the terminal, didn't I need a theme? Hmm, this one seems okay...
I can always change it later. I hope!

```
cd themes
git submodule add https://github.com/azmelanar/hugo-theme-pixyll
git add *
git commit -m "Create hugo site, add theme, update howto"
```

Alright, now to add a post... Good thing I've been working on one the whole
time. I wonder how newlines are going to be handled. I've been wrapping at 80
characters, I'm doing all of this in vim.

```
hugo new posts/my-first-post.md
cat content/posts/my-first-post.md
---
title: "My First Post"
date: 2022-07-17T21:48:45-04:00
draft: true
---
```

Sorta boring, gotta add the content I was already writing into it! After that I
can add it and...

```
git commit -m "Move howto to fist blog post"
```

In theory the github action should build the hugo page from the content in my
main branch, and put that generated html, css, etc into the gh-pages branch,
where it will get published, and I'll have a blog on github now!

In practice, it looks like the generic github page:
![Where is Hugo?!](posts/static/nohugo.png)

Oh wait, github is using my `main` branch instead of the `gh-pages` branch
which was automagically created through the github action.

![I'd prefer IaC for this, but oh well...](posts/static/default_branch.png)

So now it will work, right? Nope! I still have `draft: true` up top. Well, if
this is the big moment of truth (or rather, the big moment of `draft: false`),
I should probably clean this post up a bit before I go live. I feel pretty good
about this, it was an hour and a half from inspiration to final post, and I may
have even learned a few things along the way.

**EDIT:** Well my theme isn't showing up! I had to add it to my config:
```
cat config.yaml 
Params:
  baseURL: https://rtrigg.github.io
  languageCode: 'en-us'
  title: 'My Tech Blog'
  themesDir: 'themes'
  theme: 'hugo-theme-pixyll'
```

Later: I ran into a lot of other troubles, and decided to switch to a newer
theme. The Pixyll theme I had picked, except for the README, hadn't been
updated in years. Searching for "hugo theme 2022" was the way to go, leading me
to a [new theme](https://github.com/adityatelange/hugo-PaperMod).


In no particular order, the websites I poked around at while trying to figure
this out and troubleshoot:

- <https://github.com/gohugoio/hugo>
- <https://gohugo.io/hosting-and-deployment/hosting-on-github>
- <https://github.com/marketplace/actions/hugo-setup>
- <https://github.com/gohugoio/hugo/issues/4825>
- <https://www.freecodecamp.org/news/your-first-hugo-blog-a-practical-guide/>
- <https://github.com/gohugoio/hugo/issues/2864>
- <https://themes.gohugo.io>
- <https://themes.gohugo.io/themes/hugo-theme-pixyll/>
- <https://www.andrewhoog.com/post/git-submodule-for-hugo-themes/>
- <https://tutorialedge.net/golang/hugo/hugo-adding-images-to-posts/>
- <https://docs.github.com/en/enterprise-cloud@latest/repositories/configuring-branches-and-merges-in-your-repository/managing-branches-in-your-repository/changing-the-default-branch>
- <https://gohugo.io/getting-started/usage/>
- <https://www.markdownguide.org/cheat-sheet>
- <https://gohugobrasil.netlify.app/themes/installing-and-using-themes/>
- <https://github.com/adityatelange/hugo-PaperMod>
- <https://github.com/adityatelange/hugo-PaperMod/wiki/>
- <https://docs.github.com/en/pages/getting-started-with-github-pages/configuring-a-publishing-source-for-your-github-pages-site>


Thanks for reading!
