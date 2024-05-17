# UBUNTU SETUP WALKTHROUGH

## 1. Install homebrew

```bash
/bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
```

## 2. Install neovim

```bash
brew install neovim
```

## 3. Install zsh

```bash
sudo apt install zsh
```

## 4. Set zsh as default shell

```bash
chsh -s $(which zsh)
```

## 5. Install git

```bash
sudo apt install git
```

## 6. Install fzf and zoxide

```bash
brew install fzf zoxide
```

## 7. Change zsh config file

```bash
nvim ~/.zshrc
```

## to

```bash
# Enable Powerlevel10k instant prompt. Should stay close to the top of ~/.zshrc.
# Initialization code that may require console input (password prompts, [y/n]
# confirmations, etc.) must go above this block; everything else may go below.
if [[ -r "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh" ]]; then
  source "${XDG_CACHE_HOME:-$HOME/.cache}/p10k-instant-prompt-${(%):-%n}.zsh"
fi

# Set the directory we want to store zinit and plugins
ZINIT_HOME="${XDG_DATA_HOME:-${HOME}/.local/share}/zinit/zinit.git"

# Download Zinit, if it's not there yet
if [ ! -d "$ZINIT_HOME" ]; then
   mkdir -p "$(dirname $ZINIT_HOME)"
   git clone https://github.com/zdharma-continuum/zinit.git "$ZINIT_HOME"
fi

# Source/Load zinit
source "${ZINIT_HOME}/zinit.zsh"

# Add in Powerlevel10k
zinit ice depth=1; zinit light romkatv/powerlevel10k

# Add in zsh plugins
zinit light zsh-users/zsh-syntax-highlighting
zinit light zsh-users/zsh-completions
zinit light zsh-users/zsh-autosuggestions
zinit light Aloxaf/fzf-tab

# Add in snippets
zinit snippet OMZP::git
zinit snippet OMZP::sudo
zinit snippet OMZP::command-not-found

# Load completions
autoload -Uz compinit && compinit

zinit cdreplay -q

# To customize prompt, run `p10k configure` or edit ~/.p10k.zsh.
[[ ! -f ~/.p10k.zsh ]] || source ~/.p10k.zsh

# Keybindings
bindkey -e
bindkey '^p' history-search-backward
bindkey '^n' history-search-forward
bindkey '^[w' kill-region

# History
HISTSIZE=5000
HISTFILE=~/.zsh_history
SAVEHIST=$HISTSIZE
HISTDUP=erase
setopt appendhistory
setopt sharehistory
setopt hist_ignore_space
setopt hist_ignore_all_dups
setopt hist_save_no_dups
setopt hist_ignore_dups
setopt hist_find_no_dups

# Completion styling
zstyle ':completion:*' matcher-list 'm:{a-z}={A-Za-z}'
zstyle ':completion:*' list-colors "${(s.:.)LS_COLORS}"
zstyle ':completion:*' menu no
zstyle ':fzf-tab:complete:cd:*' fzf-preview 'ls --color $realpath'
zstyle ':fzf-tab:complete:__zoxide_z:*' fzf-preview 'ls --color $realpath'

# Aliases
alias ls='ls --color'
alias vim='nvim'
alias c='clear'

[ -f ~/.fzf.zsh ] && source ~/.fzf.zsh
export PATH="/home/soruse/.local/bin:$PATH"

# Shell integrations
eval "$(fzf --zsh)"
eval "$(zoxide init --cmd cd zsh)"
eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"

export NVM_DIR="$HOME/.nvm"
[ -s "$NVM_DIR/nvm.sh" ] && \. "$NVM_DIR/nvm.sh"  # This loads nvm
[ -s "$NVM_DIR/bash_completion" ] && \. "$NVM_DIR/bash_completion"  # This loads nvm bash_completion

# bun completions
[ -s "/home/soruse/.bun/_bun" ] && source "/home/soruse/.bun/_bun"

# bun
export BUN_INSTALL="$HOME/.bun"
export PATH="$BUN_INSTALL/bin:$PATH"
```

## 8. Install nerdfont and set it as default terminal font

```bash
https://github.com/ryanoasis/nerd-fonts/releases/download/v3.2.1/JetBrainsMono.zip
```

## 9. Open new terminal instance and walk through the Powerlevel10k setup

## 10. Install nvm+node, pnpm and bun

```bash
# nvm and node
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | zsh
source ~/.zshrc
nvm install 20

# pnpm
npm i -g pnpm

# bun
curl -fsSL https://bun.sh/install | bash
```

## 11. Install vscode

```bash
sudo snap install --classic code
```

## 12. Login to vscode and wait for extensions to install

## 13. Setup git ssh key and add to [github](https://github.com/settings/keys)

```bash
ssh-keygen -t rsa -b 4096 -C "
```

## 14. Setup git config

```bash
git config --global user.name "[PUT USERNAME HERE]"
git config --global user.email "[PUT EMAIL HERE]"
```

## 15. Install docker

```bash
brew install docker
```

## 16. Install docker-compose

```bash
brew install docker-compose
```

## 17. Install [docker-desktop](https://docs.docker.com/desktop/install/ubuntu/)
