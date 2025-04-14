# 🛠️ Development Environment Setup Guide (macOS)
This guide documents how I set up a development environment on a Mac. It includes tools, productivity utilities, programming environments, and visual enhancements to streamline your workflow.

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
- [VS Code](#vs-code)

---
## Cloning this repository
To clone this repository to may local machine and run the `config.sh` script:
```sh
git clone git@github.com:alakin4/dev-env-setup.git ~/
cd ~/dev-env-setup
./config.sh
```

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
  you should see a list of available commands if it was installed correctly.

> Note: 
> Homebrew uses formulae for CLI tools and casks for desktop applications.
>
> Tip:
> You might need to run:
>  ```zsh
>    brew tap homebrew/cask-versions
>  ```
>  to get access to other casks  that are not listed by default.


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
  - `item2`: Better terminal that the default mac terminal emulator
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
After installation, you can use: `Tab + ← / →` to preview open windows in a grid-like display
Customize shortcut keys and layout in AltTab’s settings via the menu bar icon.

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
  >  Tip: To disable system clocks and just show Stats’ timezones, open System Settings, search for "Clocks", and turn off the default menu bar clock.

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
2. The script automatically adds NVM setup code to your ~/.zshrc (or ~/.bashrc if using bash).
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
For development and personal browsing, it's to have these browsers installed:
1. **Brave**. A privacy-focused browser with built-in ad and tracker blocking. Search the internet for this but you can also install it using brew.
2. **Google Chrome**. Widely supported browser with extensive DevTools. Search the internet to get the installation.
3. **Firefox Developer Edition**. Optimized for developers with debugging features and CSS grid visualization.
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

### iTerm2 Preferences from thr GUI
I have some prefecrence that I normally do from the GUI
   - Theme: Select the minimal theme under Appearance for cleaner visuals.
   - Natural Text Editing: Go to Preferences → Keys → Key Bindings, click "Presets..." at the bottom → choose Natural Text Editing. Also remove existing default mappings to avoid conflicts.
     > By default, if I have a command in the terminal using a shortcut `option+arrow keys` would move over words and these do not work by default so turning on Natural Text Editing helps with that
   - Directory Reuse: Under General → Working Directory, select "Reuse previous session's directory"
   - Font: Install and apply Anonymous Pro (or any other preferred developer-friendly font). You can actually set this in the `.zshrc` file

### The `.zshrc` file
The .zshrc file holds your shell configuration. You can view or edit it with:
```shell 
    nano ~/.zshrc
```
If it does not exist, you will have to create it ar the root by doing
```shell 
    touch ~/.zshrc
```
Copy and paste contents of the `.zshrc` in this repository file into the `.zshrc` on the machine.

### Setting Up Git with SSH
Connecting to GitHub via SSH allows you to securely push/pull code. follow these steps:
1.  Generate an SSH Key. This allows us to clone and push to repos that we have access to
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
   

## VSCode
VS code is my favourite code editor. Having it set up right solves several issues, such as recognizing imports, using the correct python version.

### Installation
You can install VS code using brew (see above) or by visiting the [website](https://code.visualstudio.com/)

### Extensions
1. General
     - `Even Better TOML`. TOML language support (syntax highlightling, folding, etc) to work with toml files, e.g., `pyproject.toml`
3. Autoformatter
     - `Ruff`. This is the extension for the python Ruff Linter. I have used `black` before but I recently switched to `Ruff`
4. Python specific
      - `Python` extension from Microsoft. 
      - `Python Debugger` from Microsoft
      - 
6. Javascript

Here is a base set of recommended python expentions I use for my projects:
```json
{
  "recommendations": [
    "ms-python.python",
    "ms-python.vscode-pylance",
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
    // For API testing
    "postman.postman-for-vscode",
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
    "quicktype.quicktype",                       // Paste JSON as Code
    "mikestead.dotenv",                          // .env syntax highlighting
    "formulahendry.auto-rename-tag",             // Auto rename paired HTML/XML tags
    "naumovs.color-highlight",                   // Highlight CSS colors
    "dbaeumer.vscode-eslint",                    // ESLint integration
    "esbenp.prettier-vscode",                    // Prettier formatter
    "vscode-icons-team.vscode-icons",            // File icons
    "streetsidesoftware.code-spell-checker",     // Spell checker
    "csstools.postcss",                          // PostCSS Intellisense
    "yoavbls.pretty-ts-errors",                  // Pretty TypeScript Errors
    "rangav.vscode-thunder-client",              // Thunder Client for API requests
    "bradlc.vscode-tailwindcss",                 // Tailwind CSS Intellisense
    "dsznajder.es7-react-js-snippets",           // React snippets
    "andys8.react-css-modules",                  // CSS Modules support
    "styled-components.vscode-styled-components",// Styled components highlighting
    "svelte.svelte-vscode",                      // Svelte syntax and support
    "bierner.markdown-mermaid",                  // Mermaid preview for Markdown
    "kisstkondoros.vscode-gutter-preview"        // Show gutter previews for images
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
    "csstools.postcss",                          // PostCSS Intellisense
    "yoavbls.pretty-ts-errors",                  // Pretty TypeScript Errors
    "rangav.vscode-thunder-client",              // Thunder Client for API requests
    "bradlc.vscode-tailwindcss",                 // Tailwind CSS Intellisense
    "dsznajder.es7-react-js-snippets",           // React snippets
    "andys8.react-css-modules",                  // CSS Modules support
    "styled-components.vscode-styled-components",// Styled components highlighting
    "svelte.svelte-vscode",                      // Svelte syntax and support
    "bierner.markdown-mermaid",                  // Mermaid preview for Markdown
    "kisstkondoros.vscode-gutter-preview"        // Show gutter previews for images
  ]
}
```

To install multiple extensions in one go via the command line, you can
    - download the `vs-estensions.txt` file
    - run `cat vs-extensions.txt | xargs -L1 code --install-extension`
    
### VS Code Settings
VS Code has 3 levels of settings:

- Folder setting. These are typically project specific and are shared with other developers. They are normmaly stored under `.vscode/settings.json`. My typical project specific settings look are as follows
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
- Workspace Settings. These are bassically referring to your VS code window or workspace. I do not use these that much but an example you can have is the following
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
  > Here I set the titleBar of the workspace with the pink color.
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

## Python setup
* For dependency management, I use the following
   - poetry. install using `brew install poetry`
   - uv. install using `brew install uv`
   - pip

> See these detailed articles: [Article 1](https://cloudnativeengineer.substack.com/p/uv-python-package-manager) and [Article 2](https://www.loopwerk.io/articles/2024/python-poetry-vs-uv/)

* Autoformatter. For Python, I mostly use [Ruff](https://docs.astral.sh/ruff/formatter/). For my pythoin projecgts, In normally have this as a dev dependency
Settings
* project specifi vscode settings. These are stored in `.vscode/settings.json`. The extenstions are found in  `.vscode/extensions.json`

### Creating a python project
mkdir my_project
cd my_project
uv init --no-workspace

- Font: Anonymous pro
- Theme
- Extenstions
    - FontSize ShortCuts: cmd + , cmd =, cmd -
    - vscode-icons
    - ESLint
    - Prettier. You can also haev prettierrc files in specific projects
    - Paste JSON a Code. >pase Json as code, give he paste a top level name and enter
    - Code spell checker. `cmd + .`
    - PostCSS Intellisense and highlighting
    - Pretty TypeScrip Errors
    - Thunder Client: make http requests inside  VSCode, instead of postman `cmd+shift+r` to open up thunder client
    - Tailwind CSS Intellisense
    - React: ES7 + React/Redux/React-Native snippets, CSS to JSS, CSS in JS, vscode-styled-components
    - Svelte for VS code
    - Markdown mermaid Preview
    
- Create a directory on my computer where I put all my code projects, I use `Projects`
- running `code .` or `code file_name` should be working for you.

- "workbench.editor.ShowTabs": "none". Pressing `ctrl + tab` shows you the open files and you and navigate the one you like
- "editor.snippetSuggestions": "top"
- "editor.minimap.enabled": "false"
- "editor.linkedEditing": "true"

### some pro tips
I normally run the regular version. Just so you know, there is an insiders version. I will also think about syncing.

- Folder based applications like svelte:
- can also think about turning tabs off and split screen.
- cmd + p to open up a file
- Pro Tips:
  - Instead of jumping through your application file by file, start thinking about jumping through your application  interms of where your edits are. `Ctrl + -`
  - In the vscode search bar, you could use ´#´ to do a symbol (variables, function or fuzzy search. e.g., #get_this
  - cmd + click then maybe ctrl + -
  - Being able to move select and expand your cursor:
      -  select by line: cmd + L. This can also be clicked several times
      -  Jump by begining and end of line: `cmd + shift + arrow`. If wrapped, you can tap arrow twice
      -  slect by scope. can do command pallete `>expand s` to see all the options
      -  move a line up and down: `option + up/down key`
      -  duplication of line: `shift+ option + up/down key`. Can also do `cmd + shift + d`
      -  Putting cursors on every singgle line: select all the lines, then  `cmd + shift+ l`
  - Side bars (memorise the shortcuts for the ones your use most)
      - files on the right for more space.
      - cmd + shift + p: to see the command pallete e.g., `> change case` after highlihtinhg a variable. `>unique` to see using count os items
      - cmd + shift + x: extensions
      - cmd + shift + g: version control. Think about using the version control gui if you wish
      - cmd + option + b: side bar
      - cmd + l after hihlihting a variable in java script. You mightneef to set this command up
  - vscode, it has your back. For example if you accidentally save over something, and close the tab and say you are in between git commits, the timelinewould help you to roll it back
  - vs code is an electron application
  - Extensions:
      - github pull request
      - extension to hide things?
      - can hide the mini-bar if you wish.
      - Better comments. In the User/settings.json, You can extend better comments `"better-comments.tags": [{"backgroundColor": "transparent"}, {"tag": "//", "underline": false}]` etc.
      - Auto rename Tag. chnages the starting and ending tag especially for html
      - File utils. `>delete`, `>remname`, `>move`, `>theme`
      - Sort json object
      - SQLite viewer. light weight gui in vscode
      - Code Spell checker. might constantly add new words to the dictionary
      - Apc customize UI++? hide things that you might not normally hide, instead of using a custom vscode injector using a websocket for realoding. This has hot reload. update the User/settings.json
      - NO NO: Import Cost. Show you the size of your imports. NO NO, it slows down your vs code
   
  - To to figure out if your extension is slowing down your vscode:
      - google proces time of an extention. probably there are tools
  - Theme? maybe the SyntaxFM, Cobalt2 Theme official, Level Up, SyntaxTasty
  - Font (monospace and coding fonts):  MD IO, Operator Mono
  - `>new search editor` something  to have your search in an actual edirot
  - Sticky headers. If you are inside of a function, it locks it at the top. can be handy for long classes and functions or nestes code (html, css) with deep indetentation
  - Activity bar, normally on the side
  - think about profiles.
      - say one for python, one javascript, work
   
  - Renaming variables. `F2` or right click chnage all occurances. Use `shift+enter` to preview
    
## Python:pip, uv, poetry, 

## neovim
## Keys and ssh
## colima
## awscli

Links for the tutorial I watched:
- https://www.youtube.com/watch?v=GK7zLYAXdDs
- https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqa2xreFBlclFFTGxrRzRMcTd2RjhiZ3prRXVEd3xBQ3Jtc0tuT1RXMkY4S21CZEM5WnFwTjRsTElwcnJlWGZpM2JMV29aRDAwb3lBaV93U2lMRlVvT2RuU2NmVF82eHdrdkQ4RmVlYVh0aHVRdzJ5cUZIUjg2N0dXZzZYRHh1ekZ5SVk4ZUZlWnFSblBpNTF4ZVFPVQ&q=https%3A%2F%2Fgithub.com%2FCodingGarden%2Fmac-setup&v=GK7zLYAXdDs
- https://www.youtube.com/redirect?event=video_description&redir_token=QUFFLUhqbVVmRml5TDZSSU55UE4wZXlvY1BDdXdIMjc4Z3xBQ3Jtc0trWnpIVnlXOWlOWUI3NmlsT0dBUF83YUxiOVR3VldubndWd211UnBmYTEtRklsYlQ1RzFiNDZWdzdWaTlibzA5Q085ZFQydUhwdGdHMHRRNVpmc0ZpczAzcXVXRTJWSEVVNEYwMkZVYUpEbnFHbFVXbw&q=https%3A%2F%2Fgithub.com%2FCodingGarden%2Fvscode-settings&v=GK7zLYAXdDs
