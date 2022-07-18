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

Add some content:

```
echo "# start of wqrtrigg.github.io" >> README.md
git add README.md
git commit -m "Add README"
git push
```
