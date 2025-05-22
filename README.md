# kickstart.nvim-windows

## Introduction

This is the guide for using windows in neovim kickstart.

You don't need choco or wsl.

Please refer to the [kickstart.nvim](https://github.com/nvim-lua/kickstart.nvim) for the official config

### Install Kickstart
```
git clone https://github.com/nvim-lua/kickstart.nvim.git "${env:LOCALAPPDATA}\nvim"
```
> [Backup](#FAQ) your previous configuration (if any exists)

Neovim's configurations are located under the following paths, depending on your OS:

| OS | PATH |
| :- | :--- |
| Windows (cmd)| `%localappdata%\nvim\` |
| Windows (powershell)| `$env:LOCALAPPDATA\nvim\` |


### Windows with MinGW

1. Install [neovim](https://neovim.io/) windows version
2. Download the latest version of [Microsoft Visual C++ Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-microsoft-visual-c-redistributable-version)
3. Install [Git](https://git-scm.com/downloads/win)
You may use neovim for the editor in git
4. Install a [nerd font](https://www.nerdfonts.com/)
5. Unzip the font and drag all the ttf files to Settings > Personalization > Fonts 
6. Make your terminal to use your font. 
    For Windows Terminal: Settings > Defaults (or your profile) > Appearance > Font face

7. Install telescope dependencies. [MinGW-W64](https://github.com/niXman/mingw-builds-binaries/releases), [fd](https://github.com/sharkdp/fd/releases), and [ripgrep](https://github.com/BurntSushi/ripgrep/releases) (Use msvc version).
8. Unzip and add to PATH. 
9. Go to your mingw64 bin and create the 'make' binary
    `cp mingw32-make make`
9. Copy the init.lua to the ~\Appdata\Local\nvim
10. run `nvim`
11. Done

### Windows with gcc/make using chocolatey
Alternatively, one can install gcc and make which don't require changing the config,
the easiest way is to use choco:

1. install [chocolatey](https://chocolatey.org/install)
either follow the instructions on the page or use winget,
run in cmd as **admin**:
```
winget install --accept-source-agreements chocolatey.chocolatey
```

2. install all requirements using choco, exit the previous cmd and
open a new one so that choco path is set, and run in cmd as **admin**:
```
choco install -y neovim git ripgrep wget fd unzip gzip mingw make
```
### WSL (Windows Subsystem for Linux)

```
wsl --install
wsl
sudo add-apt-repository ppa:neovim-ppa/unstable -y
sudo apt update
sudo apt install make gcc ripgrep unzip git xclip neovim
```



