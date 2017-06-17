# Vim

## Help

|key|description|
|---|---|
|`:help key-notation`|find all key abbre meaning such as `<CR>`, `<C-r>` in `imap`.|
|`:imap`|display all insert mode key mappings|
|`:map`|display all key mappings, `n` for normal mode, `i` for insert mode|
|`:nmap`|display all normal mode key mappings|

## Shortcuts

### Normal Mode

|key|description|
|---|---|
|`ci"`, `ci'`, `ci(`, ...|replace string between `'`, `"`, `(` ...|

### Command Line Mode

|key|description|
|---|---|
|`:Gbrowse`|open current file in github, require `vim-fugitive`|
|`:command <alias> <origin command>`|align command|
|`:e %<.js`, `:e %:r.js`|open same file name with different extension|
|`:set paste`, `:set nopaste`|enable/disable paste as normal text editor|
|`:silent !open .`|open current folder in finder|

## Snippets

[UltiSnips](https://github.com/SirVer/ultisnips) is used for custom snippets.

|key|description|
|---|---|
|`:UltiSnipsEdit`|edit snippet of current file type|
