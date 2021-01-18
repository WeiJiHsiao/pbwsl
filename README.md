Using `pbcopy` and `pbpaste` commands in
WSL (Windows Subsystem for Linux). 

# Installation 
Clone this project with `git clone`.

Modify your `.bashrc` file by adding
```bash
alias pbcopy="/path/to/pbwsl/pbcopy"
alias pbpaste="/path/to/pbwsl/pbpaste"
```

# Usage
`pbcopy` takes standard input and places it in the clipboard buffer, while `pbpaste` takes data from the clipboard buffer and writes it to the standard output.
```bash
cat far.txt | pbcopy
pbpaste > boo.txt
```

# Using in Vim

To use system clipboard as yank register in `vim`/`neovim`, modify your `.vimrc` or `init.vim` file by adding 
```bash
let g:clipboard = {
	\ 'name': 'pbwsl',
	\ 'copy': {
	\    '+': ['/path/to/pbwsl/pbcopy'],
	\    '*': ['/path/to/pbwsl/pbcopy'],
	\ },
	\ 'paste': {
	\    '+': ['/path/to/pbwsl/pbpaste'],
	\    '*': ['/path/to/pbwsl/pbpaste'],
	\ },
	\ 'cache_enable': 1,
	\}
```
