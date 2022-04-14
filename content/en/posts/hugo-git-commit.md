---
author: "Kevin Liu"
title: "How push your Hugo project on Github?"
date: 2022-04-13T20:08:06+09:00
description: "-"
draft: false
hideToc: false
enableToc: true
enableTocContent: false
author: Kevin Liu
authorEmoji: 👻
tags: 
- git
- hugo
- github
image: images/logo/git-icon-black.svg
---

### Deploy

going to your hugo project path and check the cmd below, you can preview your blog content before push it on the remote repository.

{{< highlight html >}}
hugo server --disableFastRender
{{< /highlight >}}

### Git

{{< highlight html >}}
git init
git add .
git commit -m "your comment messages"
git push -u origin main
{{< /highlight >}}


