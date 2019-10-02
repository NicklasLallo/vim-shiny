# vim-shiny

## Fork
This fork allows shiny to take a custom function as an input to chain it together with other plugins.
More specifically it adds this new function:
```
function! shiny#custom(command, ...) abort range
  let s:count = a:lastline - a:firstline + 1
  exec 'normal "' . v:register . s:count . a:command
  let patterns = s:generate_patterns(s:count)
  call s:flash(patterns, s:vim_shiny_hi_paste)
endfunction
```
Which executes a command and then adds the shiny flash to it afterwards.

## Shiny
[![CircleCI](https://img.shields.io/circleci/project/github/MaxMEllon/vim-shiny/master.svg?style=flat-square&label=Circle%20CI)](https://circleci.com/gh/MaxMEllon/vim-shiny)
[![Support Vim 8.0.0039 or above](https://img.shields.io/badge/support-Vim%208.0.0039%20or%20above-yellowgreen.svg?style=flat-square)](github.com/vim/vim/releases/tag/v8.0.0039)
[![MIT License](https://img.shields.io/badge/license-MIT-blue.svg?style=flat-square)](LICENSE.txt)
[![Doc](https://img.shields.io/badge/doc%20-%3Ah%20vim--shiny-red.svg?style=flat-square)](./doc/vim-shiny.txt)

A plugin goal is effective highlight, like as [atom-vim-mode-plus](https://github.com/t9md/atom-vim-mode-plus).

- paste yank

![Demo movie](./.github/demo.gif)
> with vim-operator-flashy

- if enabled `termguicolors` or `gui_running`

![Demo movie](https://user-images.githubusercontent.com/9594376/32803036-8fbb49a2-c9c5-11e7-82e7-af5e79cbe925.gif)

- change window

![Demo movie](./.github/demo_win_change.gif)

## Inspired

- [vim-operator-flashy](https://github.com/haya14busa/vim-operator-flashy)
- [atom-vim-mode-plus](https://github.com/t9md/atom-vim-mode-plus)

Special Thanks!

## Usage

```vim
nmap p  <Plug>(shiny-p)
nmap P  <Plug>(shiny-P)
nmap gp <Plug>(shiny-gp)
nmap gP <Plug>(shiny-gP)
```

if you want to flash when change window

```vim
let g:vim_shiny_window_change = 1
```

LICENSE
---

MIT
