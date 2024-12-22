# shrc
RC files to set up a new computer

## Steps

### Install developer kit

### Install iTerm

### Set up a new github ssh key

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

Also install the fancy plugins: https://github.com/luan/nvim
You may need to install some dependencies, like `curl`, `fd`, `npm`, the [`pynvim`](https://github.com/neovim/pynvim) package, and `tmux`(?)

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

Also add this to your rc:
```sh
function clean-git-branches () {
	DEFAULT_BRANCH="${DEFAULT_BRANCH:-master}"
	git checkout $DEFAULT_BRANCH
	git fetch --prune
	git pull
	git branch -vv | grep --color=auto --exclude-dir={.bzr,CVS,.git,.hg,.svn} 'origin/.*: gone]' | awk '{print $1}' | xargs git branch -D
	git checkout -
}
```

### Install tmux

``` sh
brew install tmux
```

Then [install tpm](https://github.com/tmux-plugins/tpm?tab=readme-ov-file#installation):
```sh
git clone https://github.com/tmux-plugins/tpm ~/.tmux/plugins/tpm
```

Then Configure tmux with the .tmux.conf file in this repo.

`
