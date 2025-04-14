# 🛠️ Development Environment Setup Guide (macOS)
This guide documents how I set up a development environment on a Mac. It includes tools, productivity utilities, programming environments, and visual enhancements to streamline your workflow.

## 📑 Table of Contents

- [Homebrew](#homebrew)
- [Tab Management](#tab-management)
- [Switching Between Running Applications](#switching-between-running-applications)
- [Hidden Bar](#hidden-bar)
- [Computer Stats](#computer-stats)
- [Itscal](#itscal)
- [Pomodoro](#pomodoro)
- [Node](#node)
- [Web Browsers](#web-browsers)
- [iTerm2](#iterm2)
- [VS Code](#vs-code)

---
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

## Time Out
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


## WEb browser
1. Brave
2. Google chrome
3. Firfox developer edition
   - `brew search firefox` to see options then you can do `brew install`
  
### settings
- Open previously open tabs before closing
- Alwasys ask where to save files
- disable all most of the default settings you might not need, e.g., recommened stories
- New tab is a blanck page
- can set up your default search engine
- May disable search engine suggestions so that you only see things you already visisted
- May disabkle shortcuts to certain search engines that you don't use. e.g., !g <search key words> to search on google engine via brave
- For security, you can tuurn off "ask to save password" if you want as well as tuen off "remember search and form history"
### Extenstions
- Tablis. by tabliss.io for displaying nice greeting when you open a tab
- OneTab. In one click, it can take all the open tabs and throws them in one tab. Then you could also share the list of those tabs as a unique url
- Dark reader. for automatic dark theme
- uBlock Origin. for ad blocling
- Privacy Badger. Blocks tracking scripts
- Decentraleyes. Cached libtaries that are loaded from CDNs

# iterm2
- set up oh-my-zsh.
    - zsh is the actual shell that we are using normally on mac as default. you can do `echo $SHELL`
    - If you want to use bash, you may use oh-my-bash
    - go to to ohmyzsh.sh, click install and run the install commad in your terminal
    - this already improves the degault iterm with some colors, etc.
    - this by default enables using the up arrow to search through previous commands
- the `.zshrc` file
    - this is where the zsh configurations are. this file is usually in the home directory, you can do `nano ~/.zshrc` to view it.
- in setting, choose the minimal theme
- Go to keys, key mappings and choose Keymappings, then at the bottom, choose "Natrual text editing" and also remove the existing keymaps.
    - by default, if I have a command in the terminal using a shortcut `option+arrow keys` would move over words and these do not work by default
- Under settings genralcheck, reuse previous session's directory. So if I open up another tab, I want it to use the previous directory as the previous tab
- download and installanonymous pro font
- configuring Oh-my zsh. see my `.zshrc` file:
    - CASE_SENSITIVE="true". If it auto completinng
    - ENABLE_CORRECTION="true". If I make a mistake
    - plugins=(git). It shows me what brank I am on in a given repo, it also gives you some aliases
    - set up my default editor to "nano" or "nvim"
    - Yo
- Aliases: `alias < below>`
    - l="ls" # List files  in current directory
    - ll="ls -al" # List all files in current directory in long list format
    - o="open ." # Open the current directory in finder
    - gaa="git add ."
    - gcm="git commit -m"
    - gpsh="git push"
    - gss="git status -s"

  ## Git SSH key
  - can go to Github>authenticstion>connect with SSH>Generte new SSH key
  - this allows us to clone and push to repos that we have access to
  - ssh-keygen -t ed25519 -C "youremailongithub@example.com". Sacve it to the default location
  - Enter pass phrase
  - Add SSH key to the ssh-agent
      - eval "$(ssh-agent -s)"
      - Setup automatically loading keys to the ssh-agent store like MacOS keychain
          - `open ~/.ssh/config` or  `touch ~/.ssh/config`
          - `nano ~/.ssh/config`. ctrl y, ctrl x
        ```sh
        Host github.com
          AddKeysToAgent yes
          UseKeychain yes
          IdentityFile ~/.ssh/id_ed25519
        ```
      - pbcopy < ~/.ssh/id_ed25519.pub # copies the contents of id_ed25519.pub to my clipboard
      - Go to your github settings ans add that key
          - under settings, SSH and GPG keys,
          - add new ssh key
          - give it a name like the computer it  belongs to
          - cmd + v to pase the copied key

  - git clone `dotfiles` to the home folder of my local machine. use the ssh tab suggested command
  - cd to that folder
  - run `./config.sh` to run script to update your .szhrc and other config # check ourt w3jc's git hub

## vscode
Settings
- Font: Anonymous pro
- Theme
- Extenstions
    - copy a list of extensions-names
    - put them in a txt file `vs-estensions.txt`
    - run `cat vs-extensions.txt | xargs -L1 code --install-extension`
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
- See my `settings.json`.
- Copy that file and do `>Open user Settings(JSON)`. it will open the `settings.json` where you paste and save.
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
