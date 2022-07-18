First, install hugo:

`brew install hugo`

Then create a repository:

```
mkdir rtrigg.github.io
cd rtrigg.github.io
git init
git remote add origin git@github.com:rtrigg/rtrigg.github.io.git
```

Add a github action to publish the work:

```
mkdir -p .github/workflows/
vim .github/workflows/gh-pages.yml
git add .github/workflows/gh-pages.yml
git commit -m "Add github action to build site"
git push --set-upstream origin main
```


Create a config.yaml (or toml or json, see
https://gohugo.io/getting-started/configuration/) containing the following:
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

Oh but I forgot to make a new hugo site:
```
hugo new site . --force
```
which prints out:

Just a few more steps and you're ready to go:

1. Download a theme into the same-named folder.
   Choose a theme from https://themes.gohugo.io/ or
   create your own with the "hugo new theme <THEMENAME>" command.
2. Perhaps you want to add some content. You can add single files
   with "hugo new <SECTIONNAME>/<FILENAME>.<FORMAT>".
3. Start the built-in live server via "hugo server".


```

Oh, but that makes a new config.toml, when I was using a config.yaml...

```
> cat config.toml 
baseURL = 'http://example.org/'
languageCode = 'en-us'
title = 'My New Hugo Site'
```

Maybe I can set similar variables things from config.toml in my config.yaml things will work.

```
> cat config.yaml 
Params:
  baseURL: https://rtrigg.github.io
  languageCode: 'en-us'
  title: 'My Tech Blog'
> rm config.toml
```

I scroll up, didn't I need a theme? Hmm, this one seems okay... I can always change it later

cd themes
git submodule add https://github.com/azmelanar/hugo-theme-pixyll


