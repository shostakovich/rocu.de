---
layout: post
status: publish
published: true
title: Resize panes in VIM with your arrow-keys
---
It's worth to write about your learning's. Even if they seem small.

Recently [I turned of my arrow keys in VIM](http://www.rocu.de/how-to-not-use-the-arrow-keys-any-more-in-vim/) and blogged about it.

After reading my article [Philipp Fehre](http://sideshowcoder.com/) suggested, that I could take this a step further and use the arrow keys for resizing panes.

So I went ahead and copied the following 5 lines from his [.vimrc](https://github.com/sideshowcoder/dotvim/blob/master/home/.vimrc):

    " Make arrowkey do something usefull, resize the viewports accordingly
    nnoremap <Left> :vertical resize +5<CR>
    nnoremap <Right> :vertical resize -5<CR>
    nnoremap <Up> :resize +5<CR>
    nnoremap <Down> :resize -5<CR>

Phil was right! This is a great way of resizing panes.
