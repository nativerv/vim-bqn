# BQN support for Vim

Fork of [BQN](https://github.com/mlochbaum/BQN) repo containing only vim plugin so you can easily use it with plugin managers.

### Cross-editor support

[bqnlsp](https://git.sr.ht/~detegr/bqnlsp) implements [Language Server Protocol](https://en.wikipedia.org/wiki/Language_Server_Protocol) support for BQN, which allows code evaluation with error reporting. After building, see instructions for [VSCode](https://git.sr.ht/~detegr/bqnlsp/tree/master/item/editors/vscode/README.md), [Neovim](https://git.sr.ht/~detegr/bqnlsp/tree/master/item/editors/neovim/nvim-lspconfig/README.md), or [Helix](https://github.com/helix-editor/helix/wiki/How-to-install-the-default-language-servers#bqn).

[tree-sitter-bqn](https://github.com/shnarazk/tree-sitter-bqn) implements [tree-sitter](https://tree-sitter.github.io/tree-sitter/) support, and includes instructions for [Helix](https://github.com/shnarazk/tree-sitter-bqn). Many other editors such as Neovim and emacs allow for tree-sitter integration.

### Vim

Copy or symlink all files into the corresponding directories in `~/.vim`. Add the following two lines to `~/.vim/filetype.vim`:

      au! BufRead,BufNewFile *.bqn setf bqn
      au! BufRead,BufNewFile * if getline(1) =~ '^#!.*bqn$' | setf bqn | endif

Include `syntax on` in your .vimrc for syntax highlighting and `filetype plugin on` for keyboard input. View docs from vim with `:help bqn`.

To use vim-plug to install BQN support for vim, add this to your plugin section of your `.vimrc`:

      Plug 'mlochbaum/BQN', {'rtp': 'editors/vim'}

Then run `:PlugInstall`.

#### Neovim interactivity

See [nvim-bqn](https://git.sr.ht/~detegr/nvim-bqn) for an additional plugin that provides bindings to run BQN code as you're editing it.
