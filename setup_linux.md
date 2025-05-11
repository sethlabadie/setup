# Linux Setup

## What We'll Cover

We are going to install everything that you will need. Please do this in order!
** Instructions are for Fedora, but should be similar for other distributions. When installing packages in Ubuntu, use `apt-get` instead of `dnf`. **


## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Terminal](#terminal)
3. [Updating and Upgrading](#updating-and-upgrading)
4. [Zsh](#zsh)
5. [Git](#git)
6. [Brew](#brew)
7. [Install Other Linux Packages](#install-other-linux-packages)
8. [uv Tool](#uv-tool)
9. [Terminal Enhancement](#terminal-enhancement)
10. [Visual Studio Code](#vs-code)
11. [Install Google Chrome for Linux](#install-google-chrome-for-linux)
12. [NPM and NodeJS](#npm-and-nodejs)


## Prerequisites

- Update and upgrade your package manager by running `sudo dnf update`, and upgrade your packages by running `sudo dnf upgrade` in the terminal.

- Ensure that you're running the most recent operating system.
- If you want to check the version of Fedora you are running, you can use the command `cat /etc/os-release`, `cat /etc/fedora-release`, or `hostnamectl`.
- To check if you are running the latest version of Fedora, you can use the command `dnf check-update` or `cat /etc/os-release` to see if there are any available updates for your system.
- To perform a full system upgrade, use the `dnf system-upgrade command`. First, download the updates with `sudo dnf system-upgrade download --releasever=<version>` where <version> is the Fedora version you want to upgrade to. Then, reboot into the upgrade environment with `sudo dnf system-upgrade reboot`.
- After the upgrade, it is advisable to remove retired packages by running `sudo dnf install remove-retired-packages` if you are upgrading across one release, or `sudo dnf install remove-retired-packages --old-release=<old release version>` if you are upgrading across two releases.


## Updating and Upgrading

The `update` command in dnf will resynchronize your package index with their sources. This goes out to each software's source to check what updates are available. The update require's elevated permissions. Therefore you'll need to run the command using `sudo` (super user do). The command will require your user password. It's the same password you used to login to your system.

```sh
sudo dnf update -y
```

Now that dnf has an updated list of current software, you'll want to upgrade anything that requires upgrading

```sh
sudo dnf upgrade -y
```

## Terminal

- Linux distributions come with a terminal emulator pre-installed, usually xterm or gnome-terminal. Instead, we will install [Ghostty](https://ghostty.org/), the best terminal emulator available. For Fedora, you can install it using the following commands:

```sh
sudo dnf install dnf-plugins-core
sudo dnf copr enable pgdev/ghostty
sudo dnf install ghostty
```

Other distributions will have different installation methods. Follow [these instructions](https://ghostty.org/download) to install Ghostty on your system.

- Customize your Ghostty configuration by following the documentation for the configuration options [here](https://ghostty.org/docs/config).

## Zsh

- zsh is a modern shell that is backwards-compatible with bash and provides many additional features.
- Install `zsh` using your Linux package manager, e.g. `sudo dnf install zsh -y` for Fedora.
- You may need to modify your `/etc/shells` list to include the path to zsh. You can find the path to zsh by running `which zsh`. Then run `sudo echo $(which zsh) >> /etc/shells`.
- Finally, set zsh as your default shell using `chsh -s $(which zsh)`.


## GIT

- Use your Linux package manager to install Git, e.g. `sudo dnf install git -y` for Fedora.

- Next, we'll configure Git so that we can download/upload to Github easily. You'll want to get your gitconfig setup to recognize your github credentials:

1. Set up your command line Git [username](https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git#setting-your-git-username-for-every-repository-on-your-computer)
2. Set up your command line Git user [email](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-user-account/managing-email-preferences/setting-your-commit-email-address#setting-your-email-address-for-every-repository-on-your-computer)
3. Cache your Github [password](https://help.github.com/articles/caching-your-github-password-in-git/) so that you don't have to type it in every single time you push to Github.

Confirm `gitconfig` is set up, both for your username/email and gitignore by running `git config --global -l`
You should see that your username, email, gitignore, and editor are all listed.


## Brew Package Manager

- Homebrew is a package manager for Linux and macOS. It is not available on Windows, but you can use it in WSL.
- Brew generally has a faster release schedule than Fedora's dnf, and packages are installed in the home folder, so you do not need to use sudo to install anything.
- Brew requires Git to be installed first.
Install [Brew](https://brew.sh) as instructed in the link (paste the curl link into your terminal).
- Create a `~/.zshrc` file and add the following to it:
`eval "$(/home/linuxbrew/.linuxbrew/bin/brew shellenv)"`
- Run `source ~/.zshrc` to apply the changes.
- Brew recommends to install `gcc`. Use your Linux package manager to install gcc, e.g. `sudo dnf install gcc -y` for Fedora.
Brew also recommends to install the `Development Tools` package. Use your Linux package manager to install `Development Tools`, e.g. `sudo dnf group install development-tools` for Fedora.
- Now you can use the `brew install ...` command to install packages instead of using your distribution's package manager.


## Install Other Linux Packages

- You can use either your Linux package manager or Brew to install packages. I recommend using Brew.
- `WGET` is a command-line utility for downloading files from the web.
- `Tree` is a command-line utility for visualizing directory structures.
- `Neofetch` is a command-line utility for displaying system information.
- `LSD` is a command-line utility for visualizing directory contents.
- `Zoxide` is a command-line utility for quickly navigating to directories.
- `Ripgrep` is a command-line utility for searching text in files.
- `uv` is an extremely fast Python package and project manager, written in Rust.
- `fzf` is a command-line fuzzy finder.
- `direnv` is a command-line utility for managing environment variables. As of March 2025, the rpm version of direnv is older than the version available from Brew. You can use the Brew version instead. Version 2.36 has added functionality to automatically load and unload environment variables when you enter and leave a directory. This is useful for managing environment variables for different projects.


## uv Tool

- uv is a tool for installing Python versions and Python packages and managing Python dependencies, projects, and virtual environments.
- Install a recent version of Python using uv: `uv python install 3.12`.
- Using uv tool, install cookiecutter: `uv tool install cookiecutter`.
- Using uv tool, install pre-commit: `uv tool install pre-commit`.
- Using uv tool, install ruff: `uv tool install ruff`.


## Direnv

I like [direnv](https://direnv.net), also [here](https://github.com/direnv/direnv), to load and unload environment variables depending on the current directory. Before each prompt, direnv checks for the existence of a .envrc file in the current and parent directories. If the file exists, it is loaded into a sub-shell and all exported variables are then captured by direnv and then made available to the current shell. It supports hooks for all the common shells like bash, zsh, tcsh and fish. This allows for project-specific environment variables. Install with brew.

## Terminal Enhancement

- Install the [Monaspace font](https://github.com/githubnext/monaspace). Monaspace is a great texture-healing font which includes Nerd Fonts, Powerline symbols, and ligatures.
- If desired, install some [Nerd Fonts](https://www.nerdfonts.com/).
- Install [Oh My Zsh](https://ohmyz.sh/#install).
- Install [Powerlevel10k](https://github.com/romkatv/powerlevel10k#oh-my-zsh).
- Install [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions#oh-my-zsh).
- Install [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting#oh-my-zsh).
- Install [Amazon Q](https://github.com/awslabs/amazon-q)(<https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html>)and [Amazon Q Developer CLI](<https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing-ssh-setup-autocomplete.html>).


## VS Code

- Download [Visual Studio Code](https://code.visualstudio.com/download) and click on the `.rpm` installer (or `.deb` for Ubuntu).
- During install, VSCode will add itself to your system's PATH environmental variable. This will allow you to open VSCode from the terminal by simply typing `code`. You can also open files in VSCode from the terminal by typing `code SOME_FILENAME`.
- Various forks of VS Code exist; you can try [Cursor](https://www.cursor.com) or [Windsurf](https://windsurf.com). Both have AI agents built-in.
- In settings, set 'Monaspace Neon' as the first font, and enable ligatures.

## Artificial Intelligence

VS Code has GitHub Copilot built-in, while Cursor and Windsurf have their own built-in AI tools which query multiple agents. For terminal autocompletions and suggestions, I use [Amazon Q](https://aws.amazon.com/codewhisperer/resources/#Getting_started/), [here](https://docs.aws.amazon.com/codewhisperer/latest/userguide/whisper-setup-ide-devs.html), [here](https://docs.aws.amazon.com/codewhisperer/latest/userguide/whisper-setup-ide-devs.html), or [here](https://docs.aws.amazon.com/codewhisperer/latest/userguide/what-is-cwspr.html). Sourcery is a nice option which is focused more on testing and documentation, so it is complementary to the general AI agents. Amazon Q is tricky to set up, as you need to activate some settings in AWS Toolkit and create a AWS Builder ID (Developer account, different from an AWS account).

### Browser

For a browser, I use [Vivaldi](https://vivaldi.com). Vivaldi is a Chromium-based browser that offers better security and lots of features. I add several extensions: Save to Pocket for reading articles; daily.dev and hackertab.dev to keep track of developer news; octotree, to see github files in a tree format; OctoLinker; github-vscode-icons; GitHub File Icons; Dark Reader; Session Buddy; SocialFocus; WakaTime; and Wappalyzer. I use daily.dev as my homepage.

In Vivaldi, I use the following workspaces: 'Personal', 'Work', 'Data Science', and 'Education & Training'. In the Personal workspace, I will pin tabs for [GMail](mail.google.com), [Google Calendars](calendar.google.com), my bank, etc. In Work, I pin work email, my timesheet, etc. I stack tabs for various projects or threads.

Another great browser option is the [Brave Browser](https://brave.com), another Chromium-based browser that offers excellent security, plus access to TOR websites.


## Install Google Chrome for Linux
- For web development, I recommend using Google Chrome. It is the most popular browser and has the best developer tools.
- Ubuntu - Use apt to download it: `sudo apt install google-chrome-stable -y` (you may need to add the repository first)
- Fedora - Use dnf to download it: `sudo dnf install google-chrome-stable -y` (you may need to add the repository first)


## NPM and NodeJS
In this section, we'll use dnf to install npm, a package manage for node.
We'll then use npm to install n, which manages different versions nodejs.
Lastly, we'll use n to install the latest stable version of nodejs.
```sh
sudo dnf install npm
sudo npm install -g n
sudo n stable
```
