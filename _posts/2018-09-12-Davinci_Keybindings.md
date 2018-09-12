---
title: Insanely Useful DaVinci Resolve Shortcuts
author: Jannik C. Altgen
date: 4.6.2016
layout: post
permalink: /insanely-useful-davinci-resolve-shortcuts/
image: /img/10_cover.jpg
---

Many a productivty article cites the use of keybindings as a major factor that increases productivity and, in my experience, this is true 100%. DaVinci Resolve is no exception to this rule: there are so many functions to control that finding the corresponding menu item from the dropdown menus just becomes tedious. Obviously, when you are grading in a comfy grading suite with a badass color grading panel, a lot of these keybindings will be conveniently mapped to a godzillion buttons so you don't need to learn the combos. But that isn't my reality right now and actually, when you are grading rushes on set as a DIT or so, you don't have space for a panel, so keybindings are your way to go, too. Here we go, my X most used keybindings in DaVinci Resolve. *Note: These are Windows keybindings. For Mac, for the most part, the Control key is substituted with the Mac Key.*

## Managing Nodes

### Deactivate the Current Node - Ctrl + D

When building looks, I frequently want to know whether the node I am working on right now improves the grade. I might be trying how strongly to desaturate the shadows. Click *Ctrl + D* and you instantly disable the current node and see what the clip would look like without the changes made in said node. Magic.

### Deactivate All Nodes - Alt + D

The same as Ctrl + D, yet it deactivates the *entire grade*. Every node selected in the layer of the clip (pre-group, clip, post-clip or timeline layer) will be deactivated. This is great for trying on, if you will, the entire grade at once. Does it look seemless? Are you happy with your work? This is a way to check.

### Append a Serial Node - Alt + S

When building looks, it is insanely usefull to quickly append another node to the node-graph. *Alt + S* does exactly that: it adds an ordinary corrector node *after* the node you are currently working on.

### Prepend a Serial Node - Shif + S

The same as appending a node, just that *Shift + S* adds the new corrector node before the current node. If you notice you really want to make a complex selection and route the keying into your current node or maybe you want to correct the white balance before going into your current node. Building sensible node graphs can seem daunting and to truly leverage the power of node-based compositing you need some practice. I started improving my node-trees by looking at other people's graphs and slowly understanding them. Then I vowed to use every single type of node on my next project and went through with it.

## Controlling Views

### Cleaning the UI - Alt + F

The default DaVinci Resolve color tab is rather cluttered. Timelines, clip lists, node graph and much more keep your eyes searching for what you really want to see - the image. *Alt + F* gets rid of a lot of this clutter and lets you see the image in a larger window.

### Going Full Screen - Ctrl + F

Finished with your changes? Try it in fullscreen. I realize this makes sense only for people without multiple displays. If you have a dedicated monitor that always displays fullscreen, this is redundant.

### Fullscreen Plus Goodies - Shift + F

In the previous full-screen mode, you cannot edit Power Windows. It can be really useful to do this, though. *Shift + F* provides the view you want, an almost-fullscreen view of the image with the option to change windows.

### Fitting After Zooming - Shift + Z

You might have zoomed around the image using the mouse wheel to change fine details of a selection or check noise reduction. Afterwards, *Shift + Z* brings the clip back to fit the window.

## A lot of time goes into ...

### Masking - Shift + H

When masking, that is, sub-selecting parts of the image, DaVinci gives you heaps of options to see what you are selecting. *Shift + H* shows you the area you have selected by blacking / graying out the non-selected areas of the image. This gives you a great way of checking your selection.

## Dealing With Playback

### Skipping between clips - Arrow Keys Up / Down

By using the *up and down arrow keys*, you skip between clips in the timeline horizontally, meaning to the next / previous clips. This is insanely useful to quickly check if a grade matches the neighbouring clips.

### Loop Playback - X

You *always* have to watch your grade in playback. *Always.* The easiest way to do this is to *loop playback* to just one clip.

### Skipping to beginning/end of clip - Period, Comma

Within a clip, you can skip to the beginning of this clip using the *period* button. Skip to the clip's end using the comma.

## Keyframes

## Adding Keyframes - X

Long shots with lots of movement often need excessive keyframing to change various values across time. Easily adding keyframes with a keystroke makes this process a lot less painful.
