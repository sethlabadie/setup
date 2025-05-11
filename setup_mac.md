# Mac Setup

## What we'll cover
We are going to install everything that you will need to setup your Mac. Please do this in order!

1. [Prerequisites](#prerequisites)
2. [Modify Function Key Use](#modify-function-key-use)
3. [GIT](#git)
4. [Brew Package Manager](#brew-package-manager)
5. [Zsh](#zsh)
6. [Install Other Packages](#install-other-packages)
7. [uv Tool](#uv-tool)
8. [Direnv](#direnv)
9. [Terminal Emulator](#terminal-emulator)
10. [Terminal Enhancement](#terminal-enhancement)
11. [Text Editor / IDE](#text-editor--ide)
12. [Artificial Intelligence](#artificial-intelligence)
13. [Browser](#browser)
14. [Install Google Chrome for Linux](#install-google-chrome-for-linux)
15. [Node Version Manager](#node-version-manager)


## Prerequisites

- Make sure you have an Apple ID
- Ensure that you're running the most recent operating system. You can check your version by going to "System Preferences" and clicking on "Software Update"
- Optionally, download XCode from the Mac App Store. This IDE is primarily for Mac development in Swift, but can be used with other languages, although not ideally.

Install XCode Command Line Tools. Run the following command in the terminal. `xcode-select --install`

This installs the Command Line Tools package via the Terminal application. This is to ensure you have it installed correctly and in the correct path. XCode Command Line Tools in needed for Homebrew installation.

## Modify Function Key Use

Go to System Settings/Keyboard/Keyboard Shortcuts/Function Keys, ensure that the toggle "Use F1, F2, etc. keys as standard function keys" is toggled.


## GIT

- Use your Linux package manager to install Git, e.g. `sudo dnf install git -y` for Fedora.

- Next, we'll configure Git so that we can download/upload to Github easily. You'll want to get your gitconfig setup to recognize your github credentials:

1. Set up your command line Git [username](https://docs.github.com/en/get-started/getting-started-with-git/setting-your-username-in-git#setting-your-git-username-for-every-repository-on-your-computer)
2. Set up your command line Git user [email](https://docs.github.com/en/account-and-profile/setting-up-and-managing-your-github-user-account/managing-email-preferences/setting-your-commit-email-address#setting-your-email-address-for-every-repository-on-your-computer)
3. Cache your Github [password](https://help.github.com/articles/caching-your-github-password-in-git/) so that you don't have to type it in every single time you push to Github.

Finally, ensure that VSCode is your global text editor for all things Git:

```sh
git config --global core.editor "code -n -w"
```

Confirm `gitconfig` is set up, both for your username/email and gitignore by running `git config --global -l`
You should see that your username, email, gitignore, and editor are all listed.


## Brew Package Manager

[Brew](https://brew.sh) is a package manager for Linux and MacOS. It works similar to apt or dnf. I use it to download most software, both command-line and gui apps. The benefit is that you can regularly use ```brew update && brew upgrade && brew cleanup``` to update all apps you downloaded with brew.


## Zsh

- zsh is a modern shell that is backwards-compatible with bash and provides many additional features.
- Install `zsh` using Brew, e.g. `brew install zsh`.
- You may need to modify your `/etc/shells` list to include the path to zsh. You can find the path to zsh by running `which zsh`. Then run `sudo echo $(which zsh) >> /etc/shells`.
- Finally, set zsh as your default shell using `chsh -s $(which zsh)`.


## Install Other Packages

- You can use Brew to install packages.
- `WGET` is a command-line utility for downloading files from the web.
- `Tree` is a command-line utility for visualizing directory structures.
- `Neofetch` is a command-line utility for displaying system information.
- `LSD` is a command-line utility for visualizing directory contents.
- `Zoxide` is a command-line utility for quickly navigating to directories.
- `Ripgrep` is a command-line utility for searching text in files.
- `uv` is an extremely fast Python package and project manager, written in Rust.
- `fzf` is a command-line fuzzy finder.
- `direnv` is a command-line utility for managing environment variables.  Version 2.36 has added functionality to automatically load and unload environment variables when you enter and leave a directory. This is useful for managing environment variables for different projects.


## uv Tool

- uv is a tool for installing Python versions and Python packages and managing Python dependencies, projects, and virtual environments.
- Install a recent version of Python using uv: `uv python install 3.12`.
- Using uv tool, install cookiecutter: `uv tool install cookiecutter`.
- Using uv tool, install pre-commit: `uv tool install pre-commit`.
- Using uv tool, install ruff: `uv tool install ruff`.


## Direnv

I like [direnv](https://direnv.net), also [here](https://github.com/direnv/direnv), to load and unload environment variables depending on the current directory. Before each prompt, direnv checks for the existence of a .envrc file in the current and parent directories. If the file exists, it is loaded into a sub-shell and all exported variables are then captured by direnv and then made available to the current shell. It supports hooks for all the common shells like bash, zsh, tcsh and fish. This allows for project-specific environment variables. Install with brew.


## Terminal Emulator

- MacOS comes with a very basic terminal emulator pre-installed. Instead, we will install [Ghostty](https://ghostty.org/), the best terminal emulator available. Use the following command: `brew install --cask ghostty`

- Customize your Ghostty configuration by following the documentation for the configuration options [here](https://ghostty.org/docs/config).


## Terminal Enhancement

- Install the [Monaspace font](https://github.com/githubnext/monaspace). Monaspace is a great texture-healing font which includes Nerd Fonts, Powerline symbols, and ligatures.
- If desired, install some [Nerd Fonts](https://www.nerdfonts.com/).
- Install [Oh My Zsh](https://ohmyz.sh/#install).
- Install [Powerlevel10k](https://github.com/romkatv/powerlevel10k#oh-my-zsh).
- Install [zsh-autosuggestions](https://github.com/zsh-users/zsh-autosuggestions#oh-my-zsh).
- Install [zsh-syntax-highlighting](https://github.com/zsh-users/zsh-syntax-highlighting#oh-my-zsh).
- Install [Amazon Q](https://github.com/awslabs/amazon-q)(<https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing.html>)and [Amazon Q Developer CLI](<https://docs.aws.amazon.com/amazonq/latest/qdeveloper-ug/command-line-installing-ssh-setup-autocomplete.html>).


## Text Editor / IDE

For a Text Editor / IDE, I primarily use [VS Code](https://code.visualstudio.com) and its forks (currently trying out [Cursor](https://www.cursor.com) and [Windsurf](https://windsurf.com)). VS Code is open source (although owned by Microsoft), is customizable, and has plenty of extensions. It is also the most popular text editor and you will probably see most people using it. Cursor and Windsurf are forks with built-in AI agents. One benefit of VS Code is synchronization of settings and extensions. On my work computer, I log in to my account on VS Code, and everything is set up the way I want.

For VS Code, complete the `Launching from Command Line` instructions [here](https://code.visualstudio.com/docs/setup/mac#_launching-from-the-command-line). This is a command that allows you to open a file or directory in your VSCode text editor from the command line by running `code SOME_FILENAME`

Another great option is [JetBrains PyCharm](https://www.jetbrains.com/pycharm/), a full-featured IDE, which I install using the [Toolbox App](https://www.jetbrains.com/toolbox-app/). Finally, I also install [JupyterLab](https://jupyter.org), which is a web-based notebook environment for interactive computing. Install with Brew. I would also like to try [NeoVim](https://neovim.io), but currently have little experience.


## Artificial Intelligence

VS Code has GitHub Copilot built-in, while Cursor and Windsurf have their own built-in AI tools which query multiple agents. For terminal autocompletions and suggestions, I use [Amazon Q](https://aws.amazon.com/codewhisperer/resources/#Getting_started/), [here](https://docs.aws.amazon.com/codewhisperer/latest/userguide/whisper-setup-ide-devs.html), [here](https://docs.aws.amazon.com/codewhisperer/latest/userguide/whisper-setup-ide-devs.html), or [here](https://docs.aws.amazon.com/codewhisperer/latest/userguide/what-is-cwspr.html). Sourcery is a nice option which is focused more on testing and documentation, so it is complementary to the general AI agents. Amazon Q is tricky to set up, as you need to activate some settings in AWS Toolkit and create a AWS Builder ID (Developer account, different from an AWS account).


## Browser

For a browser, I use [Vivaldi](https://vivaldi.com). Vivaldi is a Chromium-based browser that offers better security and lots of features. I add several extensions: Save to Pocket for reading articles; daily.dev and hackertab.dev to keep track of developer news; octotree, to see github files in a tree format; OctoLinker; github-vscode-icons; GitHub File Icons; Dark Reader; Session Buddy; SocialFocus; WakaTime; and Wappalyzer. I use daily.dev as my homepage.

In Vivaldi, I use the following workspaces: 'Personal', 'Work', 'Data Science', and 'Education & Training'. In the Personal workspace, I will pin tabs for [GMail](mail.google.com), [Google Calendars](calendar.google.com), my bank, etc. In Work, I pin work email, my timesheet, etc. I stack tabs for various projects or threads.

Another great browser option is the [Brave Browser](https://brave.com), another Chromium-based browser that offers excellent security, plus access to TOR websites.


## Install Google Chrome for Linux

- For web development, I recommend using Google Chrome. It is the most popular browser and has the best developer tools.


## Node Version Manager

Node does not come built in to Mac, so we need to install it. First, we'll install `npm`, the 'Node package manager'.  

```sh
$ brew install npm
```

Since you might need different versions of Node for different projects, we won't be installing node directly with `npm`. Instead, we'll first install `n` (very descriptive name), which we can use to install a specific version of Node. We'll install `n` globally by using the `-g` flag, because `n` is used at the command-line for different node projects, not for individual projects. You might need administrator privileges to install node modules globally, so we put `sudo` ( (S)uper (U)ser (DO) ) at the start of the command to run it as an administrator. When you run commands with `sudo`, you'll be asked to type your user account password at the commandline. You won't see your password (or even `****`) as you type it, so make sure you type it carefully. 

```sh
$ sudo npm install -g n 
```


Download the latest stable (production-ready, non-experimental) version of node.

```sh
$ sudo n stable
```
