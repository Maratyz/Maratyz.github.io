---
title: The First Take
date: 2021-11-25 22:44:25
tags: 
- tech
- blog
- troubleshoot
---

* [The First Take Youtube channel](https://www.youtube.com/channel/UC9zY_E8mcAo_Oq772LEZq8Q/featured)
## Blog setup 
* Wanna try the combination of [HackMD.io](http://hackmd.io/) with Github page according to https://medium.com/starbugs/%E7%94%A8-hackmd-%E8%88%87-github-action-%E6%89%93%E9%80%A0%E4%BD%A0%E7%9A%84%E9%9D%9C%E6%85%8B%E7%B6%B2%E7%AB%99-%E7%B7%9A%E4%B8%8A%E6%96%87%E7%AB%A0%E7%B7%A8%E8%BC%AF%E5%B9%B3%E5%8F%B0-1d9b1a663e18
* Hexo and Github Action are therefore used as the current blog hosting solution
### Hexo config for Github Action
* `package.json` follow
* `_config.yml`: follow https://hexo.io/docs/one-command-deployment#Git
### Repo name
* The Github page has to be at root and thus the repo name needs to be the format `username.github.io`
* The paths in the generated `index.html` assume style files including css,font,jss,images directories relative to root
* Other repo name will create an additional path, resulting in that style files cannot be corrected referenced
### Git, Github Action, Theme, and Static Page Generation
* The first setup creates an empty `index.html` and thus blank page
* It was found that `themes/minima` was committied as a github submodule
* The hexo github action yrpang/github-actions-hexo@v1.3 does not pull git submodule during generating static pages
* To customise the theme, it was decided to drop the git submodule and commit the content to the main repo
* One **Deploy Key** can only be associated with one github repository

