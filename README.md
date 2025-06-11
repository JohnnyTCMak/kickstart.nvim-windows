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


### Windows with Visual Studio Build

1. Install [neovim](https://neovim.io/) windows version
2. Download the latest version of [Microsoft Visual C++ Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170#latest-microsoft-visual-c-redistributable-version)
3. Install [Git](https://git-scm.com/downloads/win)
You may use neovim for the editor in git
4. Install a [nerd font](https://www.nerdfonts.com/)
5. Unzip the font and drag all the ttf files to Settings > Personalization > Fonts 
6. Make your terminal to use your font. 
    For Windows Terminal: Settings > Defaults (or your profile) > Appearance > Font face

7. Install telescope dependencies. [Microsoft C++ Build Tools](https://visualstudio.microsoft.com/visual-cpp-build-tools/), [fd](https://github.com/sharkdp/fd/releases), and [ripgrep](https://github.com/BurntSushi/ripgrep/releases) (Use msvc version).
8. Unzip and add everything to PATH (Including cmake that in the Microsoft C++ Build Tools).
9. Copy the init.lua to the ~\Appdata\Local\nvim
10. run `nvim`
11. Modify the line under "nvim-telescope/telescope-fzf-native.nvim" 
`build = "make"` to `build = "cmake -S. -Bbuild -DCMAKE_BUILD_TYPE=Release && cmake --build build --config Release && cmake --install build --prefix build"`
12. under fewlines modify the `return vim.fn.executable("make") == 1` to `return vim.fn.executable("cmake") == 1`. It's detects the cmake or you can delete the condition function
13. Done


