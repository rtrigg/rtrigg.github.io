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


