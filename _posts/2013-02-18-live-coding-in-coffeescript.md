---
layout: post
title: Live Coding in CoffeeScript 
---

![Twinkle Twinkle in Beats.IO](/images/twinkle.png)

I've been working on a project of mine for the past few days that I had previously neglected. It's called [Beats.IO](http://beats.io), and it's a fun little tool for making music by writing code.

### Backstory

A whole bunch of years ago, I read an article called [Hacking Perl in Nightclubs](http://www.perl.com/pub/2004/08/31/livecode.html). I thought it was the coolest thing ever. It introduced me to something called live-coding, and in particular live-coding music. For the uninitiated, this is the idea of performing musical compositions by writing code, on the fly. Music and code are both things I love, so seeing them come together sounds pretty awesome to me. I dabbled a bit in this scene way back then, but largely ignored it ever since.

Fast forward to last year. I was working with Ruby on Rails full-time, and just starting to learn [CoffeeScript](http://coffeescript.org/), because it seemed rather cool. At the same time, I was reading about exciting new browser features like [Web Audio API](https://dvcs.w3.org/hg/audio/raw-file/tip/webaudio/specification.html). It all sort of clicked together: why not make a live-coding environment for CoffeeScript, in the browser, so that live-coding performances can happen anywhere! CoffeeScript made for a great language to use here, since it's so much quicker to write it than JavaScript. The idea of Beats.IO was born.

Within a few hours of dreaming this up, I had found [Audiolet](https://github.com/oampo/Audiolet), an audio sythesis and manipulation library for JavaScript. All it took was a bit of JavaScript glue to tie this together with CoffeeScript and [Ajax.org's ACE](http://ace.ajax.org/) editor, and soon I was making tones and loops and everything! I added a few helper methods in there just to avoid typing too much (which is rather useful when demoing live!). Everything went great, but unfortunately, like many side projects, this one fell aside when work and other things piled on.

### Today

About a week ago, a friend asked me how Beats.IO was coming along. I was a bit embarassed that I hadn't really maintained it, but that drove me to have another crack at it this weekend. I've added a bunch of new helper methods and some new features. There are [docs](http://beats.io/docs.html), but here's a rundown of the new stuff.

##### 1. Saving
Now when you edit something in Beats.IO, your text gets encoded into the address bar, so you can bookmark it, share it, [whatever](http://bit.ly/151ZByC) you want. This comes with the bonus that refreshing no longer causes you to save your work, which can be useful when your sounds start getting a little hairy.
##### 2. bsimple
This provides a simple synth that just plays a single note. This is useful with sequencing commands.
##### 3. bkick
A kick drum. Very [simple](http://bit.ly/YubJUT), plays once. You should use it with bseq or bplay.
##### 4. bseq
This is just a shorter way of doing PSequence(), which is used to set up a schedule of notes to play in synths, etc.
##### 5. bplay
Plays a sequence on a node.
##### 6. bloop
Equivalent to bseq, except with no sequence and loops indefinitely. This is most useful [with bkick](http://bit.ly/12ZuSUq).

### Future
I want to keep building on this, adding new features and new helper methods, in order to make live-coding in the browser more awesome. I've been thinking of maybe adding [Processing.js](http://processingjs.org/) to get some visuals going, or maybe adding a visualization of Audiolet node graph. The most important things, I think, are to keep exposing more features of Audiolet as short helper methods and provide more built-in instruments for quick and easy live performances.

If you have any ideas, or would like to help out, please let me know! Beats.IO is on [Github](https://github.com/bengl/beatsio), and I welcome any and all pull requests.
