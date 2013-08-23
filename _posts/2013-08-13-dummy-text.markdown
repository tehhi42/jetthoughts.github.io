---
layout: post
title:  "Dummy text!"
date:   2013-08-13 11:43:33
categories: hello welcome new
---

# Build With Predefined HTML Classes

There are two ways to build ``flex-video`` containers in Foundation 4: with our predefined HTML classes or with our mixins. Building flex-video containers using our classes is simple, you'll just need to create a ``<div class="flex-video">`` and apply the classes you want to style it appropriately.

The available class options:

widescreen: Will give the player a widescreen aspect ratio.
vimeo: This will ensure that we don't add extra padding since Vimeo has controls within the player, itself.

```html
<div class="flex-video">
  <iframe width="420" height="315" src="http://www.youtube.com/embed/0_EW8aNgKlA" frameborder="0" allowfullscreen></iframe>
</div>
```
For these styles to come across, make sure you have the default Foundation CSS package or that you've selected flex-video from a custom package. These should be linked up following our default HTML page structure.