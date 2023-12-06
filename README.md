<div align="center"><p>
    <a href="https://github.com/ariefra/nvim-env/releases/latest">
      <img alt="Latest release" src="https://img.shields.io/github/v/release/ariefra/nvim-env?style=for-the-badge&logo=starship&color=C9CBFF&logoColor=D9E0EE&labelColor=302D41&include_prerelease&sort=semver" />
    </a>
    <a href="https://github.com/ariefra/nvim-env/pulse">
      <img alt="Last commit" src="https://img.shields.io/github/last-commit/ariefra/nvim-env?style=for-the-badge&logo=starship&color=8bd5ca&logoColor=D9E0EE&labelColor=302D41"/>
    </a>
    <a href="https://github.com/ariefra/nvim-env/blob/main/LICENSE">
      <img alt="License" src="https://img.shields.io/github/license/ariefra/nvim-env?style=for-the-badge&logo=starship&color=ee999f&logoColor=D9E0EE&labelColor=302D41" />
    </a>
    <a href="https://github.com/ariefra/nvim-env/stargazers">
      <img alt="Stars" src="https://img.shields.io/github/stars/ariefra/nvim-env?style=for-the-badge&logo=starship&color=c69ff5&logoColor=D9E0EE&labelColor=302D41" />
    </a>
    <a href="https://github.com/ariefra/nvim-env/issues">
      <img alt="Issues" src="https://img.shields.io/github/issues/ariefra/nvim-env?style=for-the-badge&logo=bilibili&color=F5E0DC&logoColor=D9E0EE&labelColor=302D41" />
    </a>
    <a href="https://github.com/ariefra/nvim-env">
      <img alt="Repo Size" src="https://img.shields.io/github/repo-size/ariefra/nvim-env?color=%23DDB6F2&label=SIZE&logo=codesandbox&style=for-the-badge&logoColor=D9E0EE&labelColor=302D41" />
    </a>
    <a href="https://twitter.com/intent/follow?screen_name=folke">
      <img alt="follow on Twitter" src="https://img.shields.io/twitter/follow/folke?style=for-the-badge&logo=twitter&color=8aadf3&logoColor=D9E0EE&labelColor=302D41" />
    </a>
</div>

nvim-env is a user script to make it easy to install and use multiple config for your Neovim.

## ✨ Features

- 🔥 add new config from git
- 🚀 custom name

## ⚡️ Requirements

- Neovim >= **0.9.4** (tested)
- Git >= **2.19.0** (for partial clones support)
- Bash

## 🚀 Installation

<details><summary>Using Git</summary>


```sh
git clone https://github.com/ariefra/nvim-env
cd nvim-env
./nvim-env --help
```

</details>


## 🚀 Usage

<details><summary>add new environment</summary>


nvim-env --add [env] [git-url]

  Examples:
  ```sh
  nvim-env --add nv       https://github.com/appelgriebsch/Nv
  nvim-env --add mnabila  https://github.com/mnabila/nvimrc
  nvim-env --add znvim    https://github.com/Zeddnyx/Znvim
  nvim-env --add lunarvim https://github.com/LunarVim/LunarVim
  nvim-env --add astrovim https://github.com/AstroNvim/AstroNvim
  nvim-env --add fitrh    https://github.com/fitrh/init.nvim
  nvim-env --add doomnvim https://github.com/doom-neovim/doom-nvim
  nvim-env --add adics    https://github.com/AdiCahyaSaputra/my-neovim-setup
  ```

</details>


<details><summary>run nvim environment</summary>


nvim-env --run [env] [other_nvim_args]

  Examples:
  ```sh
  nvim-env --run nv
  nvim-env --run mnabila & nvim-env --run znvim
  ```

</details>

<details><summary>list available nvim environment</summary>


nvim-env --ls

  Examples:
  ```sh
  nvim-env --ls
  ```

</details>

<details><summary>delete nvim environment</summary>


nvim-env --rm [env]

  Examples:
  ```sh
  nvim-env --rm astrovim
  ```

</details>

## ⚙️ Configuration

<details><summary>Use user's home for common nvim environment</summary>


NVIM_USE_USERHOME=(true | false) nvim-env [parameters]

  this prefix if set to true (default) will cause nvim-env to use your user home 
  for data,state & cache using XDG_DATA_HOME, XDG_STATE_HOME, XDG_CACHE_HOME
  this will save space on your disk, and faster downloads for common plugins.

  Caveat is that you need to use **UPDATE** only instead of sync (i.e. in lazy.nvim)
  to avoid deleting plugins needed by other, although they will be redownloaded
  if lazy.nvim updated in the other environment.

  Examples: Nvchad requires indent-blankline.nvim version 2.20.7 instead of current, thus need isolated storage 
  ```sh
  NVIM_USE_USERHOME=false nvim-env --add nvchad https://github.com/NvChad/NvChad
  NVIM_USE_USERHOME=false nvim-env --run nvchad
  ```

</details>

