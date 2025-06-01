# install
## reference
[building-a-blog-from-scratch](https://www.philoli.com/building-a-blog-from-scratch/)

[official_tutorial](https://hexo.io/zh-cn/docs/github-pages#%E4%B8%80%E9%94%AE%E9%83%A8%E7%BD%B2)

## install nodejs
```bash
conda create -n blog python=3.10 -y
conda activate blog
conda install nodejs -y
```

## install hexo and run
```bash
npm install hexo-cli -g
hexo init blog
cd blog
npm install
hexo server
```

## install themes
```bash
git clone https://github.com/next-theme/hexo-theme-next themes/next
```

## install plugins
```bash
npm install --save hexo-deployer-git hexo-generator-feed hexo-filter-mathjax hexo-word-counter hexo-generator-searchdb hexo-generator-sitemap
```

## run local demo
```bash
hexo server
```

## add new post
```bash
hexo new [post_name]
```

and edit ```_post/[post_name].md```

# deploy
## create git repo
create repo named ```your_name.github.io```

## init repo
- Init local folder of git repo
```bash
git init
```

- Modify ```package.json```, add command to update git submodule
```json
"scripts": {
    "update-theme": "git submodule update --remote"
  },
```
- Modify ```.github/workflows/pages.yml``` to update git submodule when building and copy config.
```bash
npm run update-theme && cp _next_config.yml themes/next/_config.yml && npm run build
```

- Add theme repo to themes folder
```bash
git submodule add https://github.com/next-theme/hexo-theme-next themes/next
```

- **Must** create at least 1 post to let the site have ```index.html```
```bash
hexo new first_post
```

- Add other files to git.

- Push.

- Git repo -> settings -> pages -> set from actions.

# clone the repo and update new posts on a diffrent machine
## clone repo
```bash
git clone --recursive https://github.com/CurssedCoffin/CurssedCoffin.github.io
```

## install node env
```bash
npm install
```

## add new post
```bash
hexo new post_name
```

## preview at local machine
```bash
hexo server
```

## push
push new files to git repo.