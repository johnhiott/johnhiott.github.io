---
layout: post
title:  "iap, simple Atom package manager"
date:   2015-01-26 03:10:30
categories: development atom tools
---

# The need
I had a friend tell me he needed a package manager that would generate a file that he could check in to revision control that he could use to manage his Atom Plugins.  Shortly there after, iap was born.  Iap just wraps around Atom's existing package mananger, apm.  The only difference is iap maintains a text file that lists all of your plugins.  When you install a new package via iap, the text file is automatically updated.  When you install atom somewhere else, all you need is your file containing all of your installed plugins to quickly install them.

##Example Uses


- Populate package list with already installed packages

```bash
iap generate
```

- Install/Remove packages from the CLI

```bash
iap install {packagename}

```
- Install all saved packages

```bash
iap
```
- Remove installed package

```bash
iap remove {packagename}
```
