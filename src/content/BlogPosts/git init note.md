---
title: "git notes"
date: "2025-08-25"
tags: ["notes", "astro"]
excerpt: "有關git 的學習筆記"
---

# Using git command to create new project and push it

Change to project  folder 

```bash
cd wk/; git init
```

setting remote.

```bash
git remote add origin https://github.com/user/project.git
```

Add someting

```bash
git add something
```

commit them what's your add items.

```bash
git commit -m "Message for this time commit"
```

Push your project to github/gitlab server.

```bash
git push -u origin master
```