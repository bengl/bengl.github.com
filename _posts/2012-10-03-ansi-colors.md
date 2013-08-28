---
layout: oldpost
title: ANSI Colors 
---

I *love* ANSI escape sequences. You can use them to add color to your terminal apps, which I think is all kinds of awesome. I like to throw them anywhere and everywhere, since they're so simple and easily add a bit of readability to output or even input.

For example, many people's first experience with ANSI colors is by using Vim. Vim has great support for syntax highlighting in many languages and is extensible to just about any language with syntax files. You can enable syntax highlighting in Vim by typing <code>:set color</code> in normal mode. You can also change the color scheme in Vim.

Another common first encounter with ANSI colors is in git. If you haven't done this already, do <code>git config --global --add color.ui true</code>. This will enable color in all your git commands, which makes it a lot mroe readable.

The way these terminal apps implement these colors is actually rather simple. ANSI escape codes for colors look something like  <code>\033[Xm</code>, where X is the specific [color code](http://en.wikipedia.org/wiki/ANSI_escape_code#Colors) you want to use, and <code>\033</code> is the escape character. You can enter the excape character in Vim while in insert mode by pressing Ctrl-v, and then hitting the Esc key. It ends up looking like <code>^[</code> in Vim.

If you're creating terminal apps in Node.js, then I have to recommend Nathan Rajlich's [ansi.js](https://github.com/TooTallNate/ansi.js). It generates ANSI color escape codes for you using basic color names and RGB sequences, so you never have to worry about weird things like entering the escape character manually.

A while back, I wanted to learn a bit more about ANSI colors, so I created two barely useful tools that were fun to make, and do interesting things with ANSI color codes.

The first is [hashcolors](https://github.com/bengl/node-hashcolors). This adds a few terminal apps to your PATH that give visual representations of various hash functions applied to files or strings. I used ansi.js, which made it very easy to build. When applied to the tarball of the version of Node.js I built this with, it looks something like this:

![hashcolors](https://a248.e.akamai.net/camo.github.com/bf61bdd325051a1bab136c75ead19fbec5a0e92d/687474703a2f2f692e696d6775722e636f6d2f4b69354e762e706e67)

The second is [md5flag](https://github.com/bengl/md5flag). This adds a similar command, but instead of just outputting the colors representing a hash, it generates a "free speech flag" rendition. This is just a fun little toy.

More recently, I built a [QR code generator](http://qransi.com) that emits QR codes into the terminal using ANSI color codes. It's built as a web service, so you can use curl, [like this](http://codestre.am/8658aac87fd1c619960c730a2). I've also [rebuilt](https://github.com/bengl/qransi) it, in an attempt to re-learn C:

![qransi in C](https://a248.e.akamai.net/camo.github.com/3674bd03f1cad745ab02c125e7fc0891b859f0b2/687474703a2f2f692e696d6775722e636f6d2f6f48325a4a2e706e67)

You could use this to make iOS or Android apps that tie in to terminal apps. Perhaps server status monitor apps?

And now, for some extra fun, try <code>curl bryanenglish.com</code>. :)
