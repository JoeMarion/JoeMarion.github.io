---
layout: post
title:  "CSS Concepts"
date:   2015-09-23 20:37:53 +0800
author: Joe Marion
---

This week during DevBootcamp's Phase 0 we were introduced to CSS. I am writing this post to explain the differences between the CSS's display feature as it can be confusing.

The three that I am going to elaborate is Inline, Block, and Inline-block.

<!--more-->

### General rules for Inline elements:

* Can not have a height or width set.
* Allows other elements to sit to left and right.
* Respects left and right margins, but not top and bottom.

### General rules for Inline-Block elements:

* Allows other elements to sit to left and right.
* Repects top and bottom margins and padding.
* Repects height and width.

### General rules for Block elements:

* Respects all margins.
* Forces a line break after the block element.

#### Here is an image depicting the differences between the three:

![display]({{http://dustwell.com/div-span-inline-block.html}}/images/display.png)