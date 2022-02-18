---
date: 2020-09-25T23:29
tags:
    - ue4
    - version control
    - git
    - perforce
---

# UE4 Version Control

I've personally found Perforce to be the better approach for version control. Git works really well with text files, but unfortunately due to UE4's almost completely binary nature, diffing and merges files is completely impossible, making resolving git conflicts nightmarish.

## Perforce

Good setup guide for DigitalOcean as a host:
<https://allarsblog.com/2014/09/25/setup-perforce-digital/>

Things to keep in mind:
- maximum of 5 users if you go over a maximum file size, which is really easy to go over in even just a blueprint-only project.

## Git

If git is your go-to, would highly recommend adding <htps://github.com/SRombauts/UE4GitPlugin>, since it support file locking via LFS.
Last time I tried locking was really slow, so make sure you've got the project on a fast SSD.