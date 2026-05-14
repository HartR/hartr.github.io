---
layout: post
title: "Automating Debian Server Recovery"
---
To expand a disk on a live Debian system, I usually use:

```bash
sudo lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv
sudo resize2fs /dev/ubuntu-vg/ubuntu-lv