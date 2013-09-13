---
layout: post
title: Show log file from remote server
date: 26-12-2009
author: Michael Nikitochkin
tags: rails,capistrano,ruby
---

Create simple *capistrano* task for showing current log file from remote server so simple. Add next lines to *Capfile* or *config/deploy.rb* (if you are using rails)
 
```ruby
    desc
    task :show_log do
      run "tail -f #{current_path}/log/#{rails_env}.log"
    end
```

Run this task:

```bash
  # cap show_log
```

And you see log file in real time.

So it is universal method work for multistage capistrano extension too.

```bash
  # cap production show_log
```
