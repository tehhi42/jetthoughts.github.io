---
layout: post
title: Convert authors names in Mercurial
author: Michael Nikitochkin
date: 2009-10-3
tags: mercurial,hg
category: tech
---

#### Problem:
Change name and email in mercurial repository.
    
#### Solution: 
Use the extension [ConvertExtension](http://mercurial.selenic.com/wiki/ConvertExtension). Install this extension and configure your __.hgrc__ to enable the extension by adding following lines:

```ruby
  [extensions]
  hgext.convert=
```

We create a file __authors__:

```ruby
  old_email@example.com=New Name <new_email@gmail.com>
```

Then run command to convert old project with old names and emails to new repo with new names:

```ruby
  hg convert project project_new -A authors
```
