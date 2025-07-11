# 🛠️ Development Environment Setup Guide (macOS)
This guide documents how I set up a MacOS machine for development. It includes tools, productivity utilities, programming environments, and visual enhancements to streamline your workflow.

## 📑 Table of Contents
- [Cloning this repo](#cloning-this-repository)
- [Homebrew](#homebrew)
- [Tab Management](#tab-management)
- [Switching Between Running Applications](#switching-between-running-applications)
- [Hidden Bar](#hidden-bar)
- [Computer Stats](#computer-stats-at-a-glance)
- [Itscal](#itscal)
- [Pomodoro](#pomodoro)
- [Node](#node-js)
- [Web Browsers](#web-browsers)
- [iTerm2](#iTerm-2-and-shell-customization)
- [Python](#python-setup)
- [VS Code](#vs-code)
- [Other tools I have installed](#other-tools-i-have-installed)
- [References and Tutorials](#references-and-tutorials)

---
## Cloning this repository

To clone this repository to my local machine and run the `config.sh` script:
```sh
git clone git@github.com:alakin4/dev-env-setup.git
cd ~/dev-env-setup
sh ./config.sh
```

> Note
> If you are working with a new machine, you might get and xcode-select error that no developer tools were found. Then, you would be prompted to download and install them.
> Also, remember to set up your git to be able to do the clone. The github documentation is pretty comprehensive for this.

## Homebrew

[Homebrew](https://brew.sh/) is a package manager for macOS (or Linux) that makes it easy to install and manage software tools and applications. It’s often called “the missing package manager for macOS.”

### 🔧 Installation

To install Homebrew:

1. Open your terminal.
2. Run the following command:
   ```zsh
   /bin/bash -c "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/HEAD/install.sh)"
3. You may be prompted to enter your system password for sudo/administrative access to be able to modify system files.
4. To verify the installation, run:
   ```zsh
   brew
  You should see a list of available commands if it was installed correctly.

> Note: 
> Homebrew uses formulae for CLI tools and casks for desktop applications.

### Installing Multiple Applications with Brew
You can automate the installation of multiple applications by listing them in a text file and running a single command.

1. GUI/Desktop Applications. These are the base apps that I typiclaly use on every machine:
  - `discord`
  - `spotify`
  - `figma`
  - `vlc`: For watching videos
  - `keka`: replacement for archive tools. Its handy with zip files and rar files Archive tool, etc
  - `kap`: Screen recording tool
  - `keycastr`: Shows key presses on screen (useful for demos)
  - `iterm2`: Better terminal that the default mac terminal emulator
  - `visual-studio-code`: My favourite code editor

To install all apps (brew casks) included in `apps.txt` at once, run:
```zsh
   xargs brew install < apps.txt
```
2. CLI Tools. These are the base formula that I typically have installed:
  - `ffmpeg`: Video conversion and trimming
  - `imagemagick`: Image format conversion from the command line
  - `wget`: File retrieval over HTTP/FTP
  - `telnet`: Network utility
  - `tldr`: Simplified man pages with usage examples of many different cli tools
To install all cli apps (brew formula) included in `cli-apps.txt` at once, run:
```zsh
xargs brew install < cli-apps.txt
```

## Tab Management
For managing and snapping windows into place using keyboard shortcuts, install [Rectangle](https://rectangleapp.com/).

### Installation

Download it from the website or run:
```shell
brew install --cask rectangle
```
Once installed, you’ll see the Rectangle icon in your macOS menu bar.
### Example Shortcuts
   - `⌘ + ⌥ + ←/→/↑/↓` — move window to half/quarter of screen
   - `⌃ + ⌘ + ←`— snap to top-left corner (You can customize shortcuts in the Rectangle preferences)

## Switching Between Running Applications
I use [Alt Tab](https://alt-tab-macos.netlify.app/) to get a full window preview (similar to Windows' Alt+Tab)
### Installation
```shell
brew install --cask alt-tab
```
After installation, you can:
   - use `Tab + ← / →` to preview open windows in a grid-like display.
   - Customize shortcut keys and layout in AltTab’s settings via the menu bar icon.

## Hidden Bar
[Hidden Bar](https://formulae.brew.sh/cask/hiddenbar) helps declutter your Mac’s menu bar by hiding icons you don’t need to see all the time.
### Installation 
```shell
brew install --cask hiddenbar
```
Once installed, you can hide menu bar items by dragging them to the left of the divider icon.

## Computer Stats at a Glance
Use [Stats](https://mac-stats.com/) to view key metrics like CPU usage, memory, network activity, and more directly from your menu bar.

Example features include:
- See network traffic, RAM, CPU, and disk usage
- Add multiple time zones to your menu bar
  >  Tip:
  >  To disable system clocks and just show Stats’ timezones, open System Settings, search for "Clocks", and turn off the default menu bar clock.

## Itsycal
[Itsycal](https://www.mowglii.com/itsycal/) is a lightweight menu bar calendar that integrates with your system calendar.
### Installation
```shell
brew install --cask itsycal
```
Click the icon in the menu bar to view your upcoming events and navigate dates quickly.

## Pomodoro
[Time Out](https://www.dejal.com/timeout/) reminds you to take regular breaks to reduce screen fatigue and boost productivity.
### Installation
```shell
brew install --cask time-out
```
You can customize break durations, intervals, and notifications in the app settings.

## Node.js
[Node.js](https://nodejs.org/) is a runtime environment that allows you to run JavaScript outside the browser—commonly used for backend development. I use **NVM (Node Version Manager)** to install and manage different versions of Node.js.

### Installing Node.js via NVM
1. Go to the [NVM GitHub repository](https://github.com/nvm-sh/nvm) and follow the installation instructions:
   ```shell
   curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.2/install.sh | bash
   ```
2. The script automatically adds NVM setup code to your `~/.zshrc` (or `~/.bashrc` if using bash).
3. Reload your terminal or run:
   ```shell
   source ~/.zshrc
   ```
4. For example, I can install the latest Node.js version (e.g., version 20.x):
    ```shell
    nvm install 20
    ```
5. Confirm the installation:
    ```shell
   node -v
    ```
### Installing Global CLI Tools
I use these global tools from NPM that can be used across projects:

   ```shell
   npm i -g lite-server http-server license gitconfig
   ```
Running the above command installs these:
- `lite-server`: Lightweight development server with live reload
- `http-server`: Quickly serves static files from a folder
- `license`: Auto-generates open-source license files
- `gitconfig`: Generates `.gitconfig` files based on the type of project. I prefer to do this when startign the project.

 > Installing these globally (`-g`) allows you to use them from any terminal session, regardless of your current project directory.


## Web Browsers
For development and personal browsing, I have these browsers installed:
1. **Brave**. A privacy-focused browser with built-in ad and tracker blocking. Search the internet for this but you can also install it using brew.
2. **Google Chrome**. Widely supported browser with extensive DevTools. [Search the internet](https://www.google.com/chrome/dr/download/) to get the installation.
3. **Firefox Developer Edition**. Firefox version optimized for developers with debugging features and CSS grid visualization.
   > To find available Firefox versions:
   > ```shell
   > brew search firefox
   > ```
   > Then install the version you prefer, e.g.,:
   > ```shell
   > brew install --cask firefox-developer-edition
   > ```
   
### Suggested Settings (Applies to almost all browsers)
These settings can improve both productivity and privacy:
   - Reopen previously open tabs on launch
   - Always ask where to save files
   - Set new tab page to blank
   - Customize your default search engine. I tend to set this to brave.
   - Optionally disable shortcuts to specific search engines (e.g., !g for Google in Brave)
   - For security, you can tuurn off "Ask to save passwords" and "Remember search and form history”

### Browser Extensions (Optional)
These are the extensions that I have heard about from other people, e.g., [CJ from Coding Garden](https://coding.garden/):
- [Tablis](https://tabliss.io/). Beautiful new tab page with customizable greetings and background images
- OneTab. Collapse all your open tabs into a single list. Share the tab list via a unique URL.
- uBlock Origin. Powerful and efficient ad blocker. You might need to manually turn this off for some sites.
- Privacy Badger. Automatically blocks invisible trackers and scripts.

## iTerm2 and Shell Customization
[iTerm2](https://iterm2.com/) is a powerful alternative to the default macOS Terminal. Pairing it with `zsh` and `oh-my-zsh` improves appearance and command-line experience significantly.

### Setting up Oh My Zsh
macOS now uses `zsh` as the default shell. You can confirm this by running:
```shell
echo $SHELL
```
To enhance zsh, install [Oh My Zsh](https://ohmyz.sh/):
> If you want to use bash, you may use [oh-my-bash](https://github.com/ohmybash/oh-my-bash)
```shell
sh -c "$(curl -fsSL https://raw.githubusercontent.com/ohmyzsh/ohmyzsh/master/tools/install.sh)"
```
> Successfully running the above command already improves the degault iterm with some colors, etc. By default enables using the up arrow to search through previous commands

### iTerm2 Preferences from the GUI
I have some prefecrence that I normally do from the GUI
   - Theme: Select the minimal theme under Appearance for cleaner visuals.
   - Natural Text Editing: Go to Preferences → Keys → Key Bindings, click "Presets..." at the bottom → choose Natural Text Editing. Also remove existing default mappings to avoid conflicts.
     > By default, if I have a command in the terminal using a shortcut `option+arrow keys` would move over words and these do not work by default so turning on Natural Text Editing helps with that
   - Directory Reuse: Under General → Working Directory, select "Reuse previous session's directory"
   - Font: Install and apply [Anonymous Pro](https://fonts.google.com/specimen/Anonymous+Pro) (or any other preferred developer-friendly font). You can actually set this in the `.zshrc` file

### The `.zshrc` file
The .zshrc file holds your shell configuration. You can view or edit it with:
```shell 
    nano ~/.zshrc
```
If it does not exist, you will have to create it at the root by doing
```shell 
    touch ~/.zshrc
```
Copy and paste contents of the `.zshrc` in this repository file into the `.zshrc` on the machine. Remomber to do `source ~/.zshrc` to have the settings loaded.

### Setting up Git with SSH
Connecting to GitHub via SSH allows you to securely push/pull code. follow these steps:
1.  Generate an SSH Key. This allows us to clone and push to repos that we have access to.
   - Go to Github>authenticstion>connect with SSH>Generte new SSH key
   - Go to your terminal and do:
     ```sh
     ssh-keygen -t ed25519 -C "youremailongithub@example.com"
     ```
     Save to the default location and Add a secure passphrase when prompted
2. Start and Configure ssh-agent. Setup automatically loading keys to the ssh-agent store like MacOS keychain
   ```sh
   eval "$(ssh-agent -s)"
   touch ~/.ssh/config
   nano ~/.ssh/config
   ```
   Paste the following configuration:
   ```sh
   Host github.com
    AddKeysToAgent yes
    UseKeychain yes
    IdentityFile ~/.ssh/id_ed25519
   ```
3. Add SSH Key to GitHub
   Copies the contents of `id_ed25519.pub` to the clipboard
   ```sh
   pbcopy < ~/.ssh/id_ed25519.pub
   ```
  Then:
     - Go to GitHub → Settings → SSH and GPG keys
     - Click "New SSH Key"
     - Name it (e.g., MacBook Pro), paste with ⌘ + V, and save

## Python setup
This section outlines how to configure your Python environment for development, including dependency management, formatting, and tools.

### Installation
I also install Python on macOS is via Homebrew:
   ```sh
   brew install python
   ```
This will install the latest stable version of Python along with pip (Python's package manager).
To confirm installation:
   ```sh
   python3 --version
   pip3 --version
   ```
You can also download Python directly from the [official website](https://www.python.org/).

### 📦 Dependency Management

I use a combination of tools to manage dependencies across projects:
   1. [Poetry](https://python-poetry.org/). Poetry handles dependency resolution and virtual environments for each project.
   2. [uv](https://docs.astral.sh/uv/guides/install-python/): A faster drop-in replacement for pip, pip-tools, and virtualenv (used under the hood by Ruff, too)

      ```shell
      brew install poetry
      brew install uv
      ```
   3. [pip](https://packaging.python.org/en/latest/): Python’s built-in package installer.

   > See these helpful articles: [Article 1](https://cloudnativeengineer.substack.com/p/uv-python-package-manager) and [Article 2](https://www.loopwerk.io/articles/2024/python-poetry-vs-uv/)
   
### Autoformatter. 
I use [Ruff](https://docs.astral.sh/ruff/formatter/) for linting and auto-formatting. It’s fast, modern, and supports most of what you’d get from Flake8, isort, and Black in one tool.
   
## VS Code
VS code is my favourite code editor. Having it set up right solves several issues, such as recognizing imports, and using the correct python version.

### Installation
You can install VS code using brew (see [Homebrew section](#homebrew)) or by visiting the [website](https://code.visualstudio.com/)

### Extensions
Here is a base set of recommended python expentions I use for my projects:
```json
{
  "recommendations": [
    "ms-python.python",
    "ms-python.debugpy",
    "ms-python.vscode-pylance",
    // Python autoformatter
    "charliermarsh.ruff",
    "ms-toolsai.jupyter",
    "GitHub.copilot",
    "tamasfe.even-better-toml",
    // Allows you abut more flexibility in how you define your comments !,?, TODO
    "aaron-bond.better-comments",
    // Can help you view your workflows
    "github.vscode-github-actions",
    // For making diagrams
    "bierner.markdown-mermaid",
    // Can help you view the contents of the database
    "alexcvzz.vscode-sqlite",
    // Allows tyou to open any oflder or repository inside a docker container
    "ms-vscode-remote.remote-containers"
  ]
}
```

I also have other extensions, mostly for webdev

```json
{
  "recommendations": [
    "formulahendry.auto-rename-tag",             // Auto rename paired HTML/XML tags
    "naumovs.color-highlight",                   // Highlight CSS colors
    "dbaeumer.vscode-eslint",                    // ESLint integration
    "esbenp.prettier-vscode",                    // Prettier formatter
    "csstools.postcss",                          // PostCSS Intellisense
    "yoavbls.pretty-ts-errors",                  // Pretty TypeScript Errors
    "bradlc.vscode-tailwindcss",                 // Tailwind CSS Intellisense
    "dsznajder.es7-react-js-snippets",           // React snippets
    "andys8.react-css-modules",                  // CSS Modules support
    "styled-components.vscode-styled-components",// Styled components highlighting
    "svelte.svelte-vscode",                      // Svelte syntax and support
  ]
}
```

Other geneneral extensions

```json
{
  "recommendations": [
    "quicktype.quicktype",                       // Paste JSON as Code
    "mikestead.dotenv",                          // .env syntax highlighting
    "vscode-icons-team.vscode-icons",            // File icons
    "streetsidesoftware.code-spell-checker",     // Spell checker
    "postman.postman-for-vscode",                // For API testing
    "rangav.vscode-thunder-client",              // Thunder Client for API requests
    "bierner.markdown-mermaid",                  // Mermaid preview for Markdown
    "kisstkondoros.vscode-gutter-preview"        // Show gutter previews for images
  ]
}
```

To install multiple extensions in one go via the command line, you can
    - download the `vs-python-extensions.txt`, `vs-json-extensions.txt`, and `vs-general-extensions.txt` files
    - run 
       ```shell
       cat vs-python-extensions.txt | xargs -L1 code --install-extension
       cat vs-json-extensions.txt | xargs -L1 code --install-extension
       cat vs-general-extensions.txt | xargs -L1 code --install-extension
       ```
    
### VS Code Settings
VS Code has 3 levels of settings:

- Folder setting. These are typically project specific and are shared with other developers. They are normmaly stored under `<project-name>.vscode/settings.json`. My typical project specific settings look are as follows
  ```json
  {
  // Editor settings
  "editor.defaultFormatter": "charliermarsh.ruff",
  //Python settings
  "python.analysis.autoSearchPaths": true,
  "python.analysis.diagnosticSeverityOverrides": {
    "reportMissingImports": "none"
  },
  "python.analysis.autoImportCompletions": true,
  "python.analysis.extraPaths": ["${workspaceFolder}/src"],
  "python.envFile": "${workspaceFolder}/.env",
  "python.terminal.activateEnvironment": true,
  // Test settings
  "python.testing.pytestEnabled": true,
  "python.testing.unittestEnabled": false,
  "python.testing.cwd": "${workspaceFolder}/tests",
  "python.testing.autoTestDiscoverOnSaveEnabled": true,
  "rewrap.autoWrap.enabled": true,
  "rewrap.reformat": true,
  "rewrap.wrappingColumn": 88
   }
  ```
  > One missing setting to add could be `"python.defaultInterpreterPath": ${workspaceFolder}/.venv/bin/python`
  > These are stored in `.vscode/settings.json`. The extenstions are found in  `.vscode/extensions.json`

- Workspace settings. These are bassically referring to the VS code window or workspace. I do not use these that much but an example json you can have is the following
  ```json
  {
  "": [
     {
     "name": "my_project",
     "path": "my_project",
     }
  ],
  "settings": {
     "workbench.colorCustomizations": {
        "titleBar.activeBackground": #FFC0CB
        },
     }
  }
  ```
  > Here, I set the `titleBar` of the workspace with the pink color.

- User Settings. I use these to modify how I like my VS code to look, independept of specific projects
  ```json
  {
  "files.exclude": {
    ".git": true,
    "**/.git": true,
    "**/.svn": true,
    "**/.hg": true,
    "**/CVS": true,
    "**/.DS_Store": true,
    "**/Thumbs.db": true
  },
  "extensions.autoUpdate": "onlyEnabledExtensions",
  // Git settings
  "git.autofetch": true,
  "git.confirmSync": false,
  "git.enableSmartCommit": true,
  "git.showActionButton": {
    "commit": false,
    "publish": false,
    "sync": false
  },
  // Github Copilot settings
  "github.copilot.enable": {
    "*": true,
    "plaintext": false,
    "scminput": false,
    "yaml": false
  },
  // Explorer settings [how you naviate files]
  "explorer.excludeGitIgnore": true,
  "explorer.autoReveal": true,
  "explorer.confirmDelete": false,
  "explorer.confirmDragAndDrop": false,
  // Workbench settings
  "workbench.colorTheme": "Default Dark+",
  "workbench.colorCustomizations": { "titleBar.activeBackground": "#10794f" },
  "workbench.editor.enablePreview": false,
  "workbench.editor.tabSizing": "shrink",
  "workbench.editor.showTabs": "none", // Pressing `ctrl + tab` shows you the open files and you and navigate the one you like
  "workbench.settings.editor": "json",
  "workbench.layoutControl.enabled": false,
  "workbench.sideBar.location": "right",
  // Editor settings
  "ruff.importStrategy": "useBundled",
  "editor.formatOnPaste": true,
  "editor.formatOnSave": true,
  "editor.formatOnSaveMode": "file",
  "editor.codeActionsOnSave": {
    "source.organizeImports": "always",
    "source.fixAll": "always"
  },
  "editor.tabCompletion": "on",
  "window.zoomLevel": 1,
  "editor.minimap.maxColumn": 80,
  "editor.snippetSuggestions": "top",
  "editor.minimap.enabled": "false",
  "editor.linkedEditing": "true",
  "html.format.wrapLineLength": 80,
  "python.analysis.autoImportCompletions": true,
  "settingsSync.ignoredSettings": [],
  "editor.rulers": [
    { "column": 80, "color": "#5e7233", "lineStyle": "dotted" },
    { "column": 88, "color": "#3d0e7f" }
  ],
  // Python settings
  "[python]": {
    "editor.defaultFormatter": "charliermarsh.ruff"
  },
  // Javascript settings
  "[javascript]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[jsonc]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "[typescriptreact]": {
    "editor.defaultFormatter": "vscode.typescript-language-features"
  },
  "rewrap.autoWrap.enabled": true,
  "rewrap.reformat": true,
  "rewrap.wrappingColumn": 88,
  "javascript.updateImportsOnFileMove.enabled": "always",
  "[javascriptreact]": {
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  "C_Cpp.default.compilerPath": "",
  "editor.largeFileOptimizations": false,
  "diffEditor.maxComputationTime": 0,
  "[markdown]": {
       "editor.defaultFormatter": "yzhang.markdown-all-in-one"
     }
  }
  ```

> Workspace settings override User settings and Folder settings override workspace settings
> I normally login-in with my Github accounts and have my user settings synced accross my devices. 
----
### 💡 Pro VS Code Tips


#### Keyboard Shortcuts Cheat Sheet

| Action                                     | Shortcut                          | Notes                                                  |
|-------------------------------------------|-----------------------------------|--------------------------------------------------------|
| Open file by name                         | `⌘ + P`                           | Quick navigation to files                              |
| Jump to previous cursor location          | `Ctrl + -`                        | Useful for retracing edits                             |
| Symbol search                             | `#<symbol>` in search             | Fuzzy search for variables/functions                   |
| Cmd-click on function/var                 | `⌘ + click`                       | Jump to definition                                     |
| Select entire line                        | `⌘ + L`                           | Tap multiple times to expand selection                 |
| Jump to start/end of line                 | `⌘ + Shift + ←/→`                 | Press twice for wrapped lines                          |
| Expand selection by scope                 | `⌘ + Shift + P > Expand Selection`| View all scope options                                 |
| Move line up/down                         | `⌥ + ↑/↓`                         | Shift entire line                                      |
| Duplicate line                            | `⇧ + ⌥ + ↑/↓` or `⌘ + ⇧ + D`      | Clone current line                                     |
| Select all matching selections            | `⌘ + ⇧ + L`                       | Multi-cursor editing across similar lines              |
| Open command palette                      | `⌘ + ⇧ + P`                       | Run any command                                        |
| Open Extensions tab                       | `⌘ + ⇧ + X`                       | Manage your extensions                                 |
| Open Version Control (Git) tab            | `⌘ + ⇧ + G`                       | Built-in Git UI                                        |
| Toggle sidebar                            | `⌘ + ⌥ + B`                       | Show/hide file explorer and panels                     |
| Rename variable                           | `F2`                              | Changes all occurrences of a variable                  |
| Search in editor                          | `> New Search Editor`             | View search results in a file-like view                |

Key: ⌘ -> command, ⌥ -> option
---

#### Features & Best Practices

- **Sticky Headers**: Keeps function or class name pinned at the top when scrolling deep code blocks.
- **Timeline View**: Recover unsaved or overwritten files, even outside of Git commits.
- **File Navigation**: You don’t have to click through files—navigate by recent edits or symbol search instead.
---

### other useful extensions but I dont usethem often

| Extension                     | Purpose                                                                 |
|------------------------------|-------------------------------------------------------------------------|
| GitHub Pull Requests         | Manage PRs without leaving VS Code                                     |
| Auto Rename Tag              | Automatically rename paired HTML/XML tags                              |
| File Utils                   | Quick file rename, delete, move, etc.                                  |
| Sort JSON Objects            | Keep JSON tidy and organized                                           |
| SQLite Viewer                | Lightweight embedded SQLite browser                                    |
| Apc Customize UI++           | Hide interface elements, customize layout via settings.json            |


> Finally:
> - Try `MD IO`, `Operator Mono`, or any coding-friendly monospaced font
> - Set up different profiles for different projects (e.g., Python, JavaScript, writing)
> - To identify slow extensions: search online for *"VS Code extension profiling tools"*


## Other tools I have installed
Here are a few additional tools that I frequently use for development and infrastructure management:

### Neovim

[Neovim](https://neovim.io/) is a modern, extensible terminal-based text editor. It’s a faster, more powerful alternative to Vim with Lua support for plugin development.

Install via Homebrew:

```bash
brew install neovim
```

If `nvim` is added as an alias to `.zshrc`, You can launch it with:
```bash
nvim
```

### Colima
[Colima](https://github.com/abiosoft/colima) (short for Container on Lima) is a fast and lightweight container runtime for macOS, designed as an alternative to Docker Desktop.
   
   ```bash
   brew install colima
   ```
   
Then you can start it with:
   ```bash
   colima start
   ```

Colima can be used with Docker CLI out of the box:
   ```bash
   docker ps
   ```
> In case docker is not installed with colima, you may need to independently do `brew install docker`

### AWS CLI
The AWS Command Line Interface (CLI) is a tool to manage AWS services from the terminal.

Install via Homebrew:
   ```bash
   brew install awscli
   ```
After installing, configure it with your credentials:
   ```bash
   aws configure
   ```
You’ll be prompted to enter your AWS Access Key ID, Secret Access Key, Region, and output format.

### Rust
[Rust](https://www.rust-lang.org/) is a systems programming language known for speed, safety, and great tooling.

Install via the official installer:
```sh
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
```
After installation:
```sh
source $HOME/.cargo/env
```
Verify Rust and its package manager cargo:
```sh
rustc --version
cargo --version
```

> 🔧 Use cargo install <tool> to install CLI tools written in Rust (e.g., cargo install exa, cargo install ripgrep).

## 📚 References and Tutorials

These resources were incredibly helpful in guiding my setup process:

- [YouTube: Mac Developer Environment Setup (Coding Garden)](https://www.youtube.com/watch?v=GK7zLYAXdDs)
- [GitHub: mac-setup Configuration Files](https://github.com/CodingGarden/mac-setup)
- [GitHub: VS Code Settings by Coding Garden](https://github.com/CodingGarden/vscode-settings)
- [YouTube: Ultimate VS Code Setup (ArjanCodes)](https://www.youtube.com/watch?v=PwGKhvqJCQM)
