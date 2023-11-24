## Knowing your shell


A **shell** is a type of computer program called a command-line interpreter that lets Linux and Unix users control their operating systems with command-line interfaces. Shells allow users to communicate efficiently and directly with their operating systems. [know more](https://en.wikipedia.org/wiki/Shell_(computing))


### Why Zsh ?
**Zsh** is also an environment that can be used as a command-line interpreter for shell scripting or as an interactive login shell. **Zsh** is built on top of bash thus it has additional features. Zsh is the default shell for macOS and Kali Linux. Well what is the difference between **bash** and **zsh** ? why should i care ?  

- Wildcard substitutions allow systems to process more than one command at a time or to find snippets of phrases from text files which bash can't.
- Customizing, themeing, plugin support & other makes it more reason to switch.

### Changing bash to Zsh

Install the package :

`Debian`
```
sudo apt install zsh
```
`Arch`
```
sudo pacman -S zsh

```
`Changing shell to Zsh`
```
chsh -s /bin/zsh
```

`Revert (want to go back ?)`

```
chsh -s /bin/bash
```

## Customizing .zshrc

```
autoload -U compinit
zstyle ':completion:*' menu select
zmodload zsh/complist`
setopt extendedglob`
_comp_options+=(globdots)
```
Enables autocompletion for zsh & other (optional)


### Installation of oh-my-zsh

```
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```


### [Theme](https://github.com/ohmyzsh/ohmyzsh/wiki/Themes)

add line in .zhrc

```
ZSH_THEME="fino"
```

### History

add lines in .zhrc (optional)

```
HISTSIZE=10000
SAVEHIST=10000
setopt appendhistory
setopt INC_APPEND_HISTORY
setopt SHARE_HISTORY
```



### Auto-suggestions

```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions

```

### Zsh-syntax-highlighting

```
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

```

add this line in .zhrc for plugins.

```
plugins=(git zsh-autosuggestions zsh-syntax-highlighting)

```

you can view all the plugins of [oh-my-zsh](https://github.com/ohmyzsh/ohmyzsh)
```
cd ~/.oh-my-zsh/plugins
```


[want to learn vim ?](https://thevaluable.dev/vim-advanced)


