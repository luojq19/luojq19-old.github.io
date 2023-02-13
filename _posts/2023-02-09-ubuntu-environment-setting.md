---
layout: post
title:  "Ubuntu Python Environment Setup"
date:   2023-02-09 23:50:00 +0800
---

### oh-my-zsh
#### Installation
```
sh -c "$(wget -O- https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
#### Themes
Modify `~/.zshrc`:  
`ZSH_THEME="agnoster"`

#### Hide user name and machine name in the prompt
Add the following line to `~/.zshrc`:
```
prompt_context() {}
```

#### Plugins
First download zsh-autosuggestions:
```
git clone https://github.com/zsh-users/zsh-autosuggestions ${ZSH_CUSTOM:-~/.oh-my-zsh/custom}/plugins/zsh-autosuggestions
```
Then modify `~/.zshrc`:  
```
plugins=(
    git
    last-working-dir
    z 
    extract
    zsh-syntax-highlighting
    zsh-autosuggestions
)
source $ZSH/plugins/extract/extract.plugin.zsh
source $ZSH/plugins/z/z.plugin.zsh
source $ZSH_CUSTOM/plugins/zsh-syntax-highlighting/zsh-syntax-highlighting.zsh
source $ZSH_CUSTOM/plugins/zsh-autosuggestions/zsh-autosuggestions.zsh
```

Run `source ~/.zshrc` to activate the changes.

### Anaconda
#### Installation
Go to https://repo.anaconda.com/archive/ to find the newest version on your machine, e.g.
```
wget https://repo.anaconda.com/archive/Anaconda3-2022.10-Linux-x86_64.sh
```
Then run the installation script accordingly.

If the conda environment is not automatically activated, run `source ~/.zshrc`.

To create a new virtual environment, run
```
conda create -n env_name python=3.8
```

#### Useful packages
**mamba:**  faster environment solving

**torch, torchvision:** refer to pytorch.org to install

**gpustat, nvtop:** convenient GPU status visualization


