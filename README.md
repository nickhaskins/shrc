# shrc
RC files to set up a new computer

## Steps

### Install developer kit

### Install iTerm

### install home brew

### install oh my zsh

https://github.com/ohmyzsh/ohmyzsh

make sure the `git` and `fzf` plugins are installed:

```sh
# Which plugins would you like to load?
# Standard plugins can be found in $ZSH/plugins/
# Custom plugins may be added to $ZSH_CUSTOM/plugins/
# Example format: plugins=(rails git textmate ruby lighthouse)
# Add wisely, as too many plugins slow down shell startup.
plugins=(git fzf)
```

### install doomemacs

https://github.com/doomemacs/doomemacs


### Install neovim

`brew install neovim`

### Install git completion:

This doesn't seem to work anymore: https://github.com/git/git/blob/master/contrib/completion/git-completion.bash
The new version also doesn't work for some reason: https://github.com/git/git/blob/master/contrib/completion/git-completion.zsh
So try these one-time commands instead:

```sh
git config --global alias.co checkout
git config --global alias.st status
git config --global alias.lg "log --color --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

Also try these out:
```sh
git config --global user.name "Nick Haskins"
git config --global user.email "foo@bar.com"
```
