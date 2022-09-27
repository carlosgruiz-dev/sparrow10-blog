---
title: "How to access WSL's files from Windows explorer"
date: 2022-09-27T16:26:36Z
draft: false
tags: ["linux", "wsl", "windows", "docker"]
---

I was looking for where Docker stores its volumes on a Windows machine. Looking at [this answer][1]
on Stack Overflow, I realized that if you type "`\\wsl$\`" in your Windows explorer, you can browse
all files inside your WSL instances.

How cool, huh?

![WSL instances on the Windows file explorer](/images/files-wsl-01.png)

Btw: Docker volumes are in:
- `\\wsl$\docker-desktop-data\data\docker\volumes` (Docker Engine v20.10.16)
- `\\wsl$\docker-desktop-data\version-pack-data\community\docker\volumes\` (Docker Engine v19.03)

See you next time.

[1]: https://stackoverflow.com/a/64418064
