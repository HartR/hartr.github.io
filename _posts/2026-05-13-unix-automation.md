---
layout: post
title: "A Small Recovery Playbook for Debian and Ubuntu Servers"
description: "A practical checklist for expanding disks, checking filesystems, and leaving notes your future self can trust."
date: 2026-05-13
categories: [Infrastructure]
tags: [linux, automation, recovery]
reading_time: "4 min read"
---

Good recovery notes are short, boring, and easy to run under pressure. When a server runs out of disk, the goal is not to remember every flag by heart; the goal is to have a safe sequence that makes the current state visible before changing it.

## First, identify what you have

Start with read-only commands. Confirm the block devices, mounted filesystems, and volume groups before touching anything.

```bash
lsblk -f
df -hT
sudo vgs
sudo lvs
```

I like to paste those outputs into the incident notes before making changes. It creates a simple before-and-after record and makes rollback conversations much easier.

## Expand the logical volume

On a typical Ubuntu install using LVM, the sequence often looks like this:

```bash
sudo lvextend -l +100%FREE /dev/ubuntu-vg/ubuntu-lv
sudo resize2fs /dev/ubuntu-vg/ubuntu-lv
```

That said, device names are not universal. Treat the paths above as an example and verify the actual logical volume name with `sudo lvs` first.

## Verify the result

After resizing, check the filesystem and capture the final state.

```bash
df -hT
sudo lvs
```

A useful playbook ends with evidence. If the disk is healthy again, write down the final size, the command sequence, and any unusual output.

## What I want in every recovery note

- The exact host and environment
- The symptom that triggered the work
- The read-only inspection commands
- The mutation commands
- The final verification output
- Anything I would change next time

That structure turns a one-off fix into operational knowledge. Future you gets a checklist instead of a memory test.
