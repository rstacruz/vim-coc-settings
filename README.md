# Rico's Neovim + Coc settings

:wave: Hey there, here's my setup on how I use coc.nvim to make my Vim work like an IDE.

I've been VSCode, Atom, Sublime, and other modern editors. They are fantastic! I love how I get automatic type hints, amazing auto-complete, inline documentation, and many things that Vim users may consider to be frivolous luxuries.

They're no Vim, though. VSCode's Vim emulation can be a bit slow (try doing `9j` on vscode-vim, and try it on Vim itself). They also take a lot of memory, which can be too much for 4GB/8GB laptops.

Since [coc.nvim](https://github.com/neoclide/coc.nvim/) came around, there's no need to compromise anymore. You can get IDE-like features in Vim, and here's how I did it!

## Install Vim (and friends)

You need `neovim` (or `vim` 8.1+), `nodejs` and `yarn`. Coc's internals runs on Node.js.

| Platform             | Command                               |
| -------------------- | ------------------------------------- |
| macOS (via Homebrew) | `brew install nodejs neovim yarn`     |
| Arch Linux           | `sudo pacman -Syu nodejs neovim yarn` |

I suggest using [vim-plug](https://github.com/junegunn/vim-plug) to manage your dependencies.

## Copy from the files here

The files in this repo are things you can merge into your Vim/Neovim configuration.

| File                                                          | Desrcpition                         |
| ------------------------------------------------------------- | ----------------------------------- |
| ~/.config/nvim/[init.vim](./init.vim)                         | List of plugins to load             |
| ~/.config/nvim/[coc-settings.json](./coc-settings.json)       | Settings for coc-nvim               |
| ~/.config/nvim/[after/plugin/coc.vim](./after/plugin/coc.vim) | Key bindings and other Coc settings |

If you're using Vim instead of Neovim, take what's in `init.vim` and place it in `~/.vimrc`, and the config folder is `~/.vim` instead of `~/.config/nvim`.

## Also see

Many of the configuration are lifted from almost-verbatim from Coc documentation. I highly recommend checking those out too.

- https://github.com/neoclide/coc.nvim/#example-vim-configuration

## Key bindings

See [after/plugin/coc.vim](.after/plugin/coc.vim) for a full list of key bindings. Below are some of the features that I find to be most useful:

<table>

<tr>
<td>Key</td>
<td>Description</td>
</tr>

<tr>
<td>
<kbd>g</kbd><kbd>h</kbd> &mdash; <strong>Show hint/documentation</strong><br>
Shows a hint for whatever's on the cursor. This means type definitions, JSDoc comments, and documentation (when available). Similar to VSCode's mouse over functionality.
</td>
<td>
<img src='./screenshots/coc_show_docs.gif'>
</td>
</tr>

<tr>
<td>
<kbd>space</kbd> <kbd>c</kbd> <kbd>r</kbd> &mdash; <strong>Rename symbol</strong><br>
Rename whatever is on the cursor. Similar to VSCode's Rename Symbol command (F2).
</td>
<td>
<img src='./screenshots/coc_rename.gif'>
</td>
</tr>

<tr>
<td>
<kbd>ctrl</kbd>-<kbd>n</kbd> &mdash; <strong>Code completion</strong><br>
Code completion just happens. <code>ctrl-n</code> and <code>ctrl-p</code> are default Vim key bindings for browsing through code completions.
</td>
<td>
<img src='./screenshots/coc_completion.gif'>
</td>
</tr>

<tr>
<td>
<kbd>space</kbd>-<kbd>c</kbd><kbd>c</kbd>-<kbd>prettier</kbd> &mdash; <strong>Prettier</strong><br>
Prettier formatting happens on every save, automatically! You can also trigger it manually via invoking Coc commands via <code>space-c-c</code>.
</td>
<td>
<img src='./screenshots/coc_prettier.gif'>
</td>
</tr>

<tr>
<td>
<kbd>space</kbd> <kbd>c</kbd> <kbd>c</kbd> &mdash; <strong>Show available commands</strong><br>
Fix tslint problems automatically, run Prettier manually, auto-fix eslint, and more.
</td>
<td>
-
</td>
</tr>

<tr>
<td>
<kbd>space</kbd> <kbd>c</kbd> <kbd>x</kbd> &mdash; <strong>Enable/disable e<u>x</u>tensions</strong><br>
If you don't need tsserver in your current project, you can temporarily disable them.
</td>
<td>
-
</td>
</tr>

<tr>
<td>
<kbd>space</kbd> <kbd>c</kbd> <kbd>l</kbd> &mdash; <strong><u>L</u>ist errors</strong><br>
When you find errors, use this to shown them all
</td>
<td>
-
</td>
</tr>

</table>

## References

- These were extracted from [rstacruz/vimfiles](https://github.com/rstacruz/vimfiles/).
- These work great with [rstacruz/vim-for-scratch](https://github.com/rstacruz/vim-from-scratch).
