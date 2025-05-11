# Windows Setup

## What We'll Cover

We are going to install everything that you will need. Please do this in order!
** WSL Instructions are for Fedora, but should be similar for other distributions. When installing packages in Ubuntu, use `apt` instead of `dnf`. **

## Table of Contents

1. [Prerequisites](#prerequisites)
2. [Windows Terminal](#windows-terminal)
3. [WSL](#wsl)
4. [WSL GUI](#wsl-gui)
5. [Set up a real Linux GUI](#set-up-a-real-linux-gui)
6. [Update Package Manager](#update-package-manager)
7. [Zsh](#zsh)
8. [Git](#git)
9. [Brew Package Managr](#brew-package-manager)
10. [Install Other Linux Packages](#install-other-linux-packages)
11. [uv Tool](#uv-tool)
12. [Terminal Enhancement](#terminal-enhancement)
13. [Visual Studio Code](#vs-code)
14. [Install Google Chrome for Linux](#install-google-chrome-for-linux)
15. [NPM and NodeJS](#npm-and-nodejs)


## Prerequisites

- Ensure that you're running the most recent operating system (Windows 10 and 11 are both fine). You can update to the latest Windows version by selecting `Start > Settings > **Windows Update** > Check for updates.`

## Windows Terminal

- Download and install Windows Terminal from the Microsoft Store, or [this link](https://learn.microsoft.com/en-us/windows/terminal/install). You may already have it installed. This isn't necessary, but it is better than the default terminal installed in the past, and you will be using a Windows Terminal to manage your WSL environment.
- Open Windows Terminal and select `Settings`.
- Select `Profiles`.
- Select `Open JSON`.
- Add the following to the `profiles` section:

```json
{
    "name": "Windows Terminal",
    "commandline": "wt",
    "icon": "ms-appx:///Microsoft.WindowsTerminal_8wekyb3d8bbwe/Assets/terminal.png",
    "startingDirectory": "/home/<YOUR_USERNAME>"
}
```
- Install Ghostty from the Microsoft Store. Ghostty is a terminal emulator that allows you to run Linux commands in Windows. It is not necessary, but it is a nice addition to your setup.


## WSL

- Install [WSL](https://learn.microsoft.com/en-us/windows/wsl/install) as instructed in the link.
- WSL will install Ubuntu by default, but the previous link has instructions to install a different flavor of Linux instead. I use Fedora.
- Additional useful instructions are [here](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-ssh) and [here](https://learn.microsoft.com/en-us/windows/wsl/setup/environment).
- To access your WSL files in the File Explorer, navigate to `\\wsl.localhost\Fedora\home\<YOUR_USERNAME>`.

## WSL GUI

- Microsoft has the ability to run Linux GUI apps on Windows. Use the instructions for [WSL GUI apps](https://learn.microsoft.com/en-us/windows/wsl/tutorials/gui-apps). Without a real Linux GUI, you have to open the Linux App from the Linux terminal, such as by typing its name, such as `.google-chrome`.

## Set up a real Linux GUI

**untested**
<https://www.youtube.com/watch?v=7Sym3uL6YWo&t=1s>
Enable some features in Windows by clicking the Start button, typing "Turn Windows features on or off", and clicking the link. Enable "Virtual Machine Platform" and "Windows Subsystem for Linux". Restart your computer.

## Update Package Manager

- Use Microsoft Terminal to access your WSL environment. Select your Linux distribution from the dropdown menu.
- Update your Linux package manager, e.g. `sudo dnf update && sudo dnf upgrade -y` for Fedora.

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

- If you are using Windows, simply use `git config --global credential.helper "/mnt/c/Program\ Files/Git/mingw64/libexec/git-core/git-credential-manager-core.exe"` at the command line for this step.

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

- In Windows, download and install [Visual Studio Code](https://code.visualstudio.com/download). You will be running the Windows version of VS Code, but then running your WSL distro from within VS Code.
- During install, VS Code will add itself to your system's PATH envirnmental variable. This will allow you to open VS Code from the Windows terminal by simply typing `code`. You can also open files in VS Code from the Windows terminal by typing `code SOME_FILENAME`.
- Various forks of VS Code exist; you can try [Cursor](https://www.cursor.com) or [Windsurf](https://windsurf.com). Both have AI agents built-in.
- Install the [Remote Development Extension Pack](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack) extension for VS Code. This includes [Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.remote-wsl), which is required to use VS Code in your Linux environment on Windows.
- Open VS Code and select `Remote-WSL: New Window` from the command palette (Ctrl+Shift+P).
- In settings, set 'Monaspace Neon' as the first font, and enable ligatures.

- Other references: [here](https://code.visualstudio.com/docs/remote/wsl) and [here](https://code.visualstudio.com/docs/remote/wsl-tutorial).
[WSL Documentation](https://learn.microsoft.com/en-us/windows/wsl/),
[Set up a WSL development environment](https://learn.microsoft.com/en-us/windows/wsl/setup/environment)
[Developing in WSL](https://code.visualstudio.com/docs/remote/wsl)
[Linux Databases](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-database)
[Linux Docker](https://learn.microsoft.com/en-us/windows/wsl/tutorials/wsl-containers)
[Remote R Service on Linux](https://learn.microsoft.com/en-us/visualstudio/rtvs/setting-up-remote-r-service-on-linux)
[Remote Troubleshooting](https://code.visualstudio.com/docs/remote/troubleshooting)
[WSL Tutorial](https://code.visualstudio.com/docs/remote/wsl-tutorial)
[Remote - WSL](https://marketplace.visualstudio.com/items?itemName=ms-vscode-remote.vscode-remote-extensionpack)


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
