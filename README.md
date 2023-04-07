# UBUNTU SETUP WALKTHROUGH

## 1. Install curl and vim

```bash
sudo apt-get install curl vim
```

## 2. Install zsh

```bash
sudo apt-get install zsh
```

## 3. Install git

```bash
sudo apt-get install git
```

## 4. Install oh-my-zsh

```bash
sh -c "$(curl -fsSL https://raw.githubusercontent.com/robbyrussell/oh-my-zsh/master/tools/install.sh)"
```

## 5. Change zsh config file

```bash
vim ~/.zshrc
```

## to

```bash
export ZSH="$HOME/.oh-my-zsh"
ZSH_THEME="pygmalion"

plugins=(
  git
  zsh-autosuggestions
  zsh-syntax-highlighting
)

source $ZSH/oh-my-zsh.sh
```

## 6. Install plugins

```bash
git clone https://github.com/zsh-users/zsh-syntax-highlighting.git ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-syntax-highlighting

git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```

## 7. Set zsh as default shell

```bas
chsh -s $(which zsh)
```

## 8. Install nvm and node

```bash
curl -o- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | zsh

source ~/.zshrc

nvm install node
```

## 9. Get [JetBrains Mono](https://www.jetbrains.com/lp/mono/) font and set it in terminal

## 10. Install vscode

```bash
sudo snap install --classic code
```

## 11. Login to vscode and wait for extensions to install

## 12. Setup git ssh key and add to [github](https://github.com/settings/keys)

```bash
ssh-keygen -t rsa -b 4096 -C "
```

## 13. Setup git config

```bash
git config --global user.name "[PUT USERNAME HERE]"
git config --global user.email "[PUT EMAIL HERE]"
```

## 14. Install docker

```bash
sudo apt-get install docker.io
```

## 15. Install docker-compose

```bash
sudo apt-get install docker-compose
```

## 17. Install [docker-desktop](https://docs.docker.com/desktop/install/ubuntu/)

## 18. Install chrome browser

```bash
 wget https://dl.google.com/linux/direct/google-chrome-stable_current_amd64.deb

 sudo dpkg -i google-chrome-stable_current_amd64.deb
```

## 19. Install discord, spotify

```bash
sudo snap install discord
sudo snap install spotify
```
