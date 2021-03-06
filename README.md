# CSScomb plugin for Vim

## About
Plugin based on CSScomb algorithm.

The algorithm of CSScomb simulates web-technologists actions upon working with CSS-code to the limit. Usually to re-order code you move lines over each other considering comments in the code, multilines records of property values, hacks and everything that could be found in the real file. CSScomb reproduces these actions for you. This means that the parser "thinks" as a person editing the text, not as a blind robot parsing CSS.

For more info, online demo and tests see [csscomb.com](http://csscomb.com/)


## The Requirements

CSScomb is written in pure JavaScript. Install with:

```BASH
npm install -g csscomb
```

## Installation

### With Pathogen

```
cd ~/.vim/bundle
git clone https://github.com/miripiruni/CSScomb-for-Vim.git
```

### With Vundle
Add this to .vimrc:
```
Bundle 'git://github.com/miripiruni/CSScomb-for-Vim.git'
```

### With NeoBundle
Add this to .vimrc:
```
NeoBundle 'faceleg/vim-csscomb', {
        \ 'build': {
        \     'unix': 'npm install -g csscomb',
        \     'mac': 'npm install -g csscomb'
        \ }}
```

### Manual without plugins manager
```
git clone https://github.com/miripiruni/CSScomb-for-Vim.git csscomb
cp -r csscomb/plugin/* ~/.vim/plugin/
```

## Usage
Vim command:
```
:CSScomb
```

## Suggested Configuration

```VIML
"mnemonic: 'beatify css'
autocmd FileType css noremap <buffer> <leader>bc :CSScomb<CR>
" Automatically comb your CSS on save
autocmd BufWritePre,FileWritePre *.css,*.scss,*.sass silent! :CSScomb<CR>
```
