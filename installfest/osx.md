# Mac OSX - 1

For the first portion of the class, we'll be working exclusively inside of the browser. We'll be installing the following tools.

* Slack
* Homebrew
* Git

If you already have some tools and software installed that are similar to below, it will be more conveient for you to switch over than it will be for you to try to go ahead with your current versions.

## Hidden Files

With a finder window open, set your finder to display hidden unix files by default:

```text
cmd + shift + .
```

## Slack

We will be using slack to communicate throughout the course. You should've received an invite to our channels via e-mail. You can login via the web browser, but downloading / installing the app is highly recommended.

[Download Slack](https://slack.com/downloads)

## Homebrew

Homebrew is a package manager that we will use to install various command line tools in our class.

Open up terminal, and paste the following command to install Homebrew. You might be prompted to install XCode Command Line Tools during the install process.

```text
ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)"
```

You may be prompted to installed XCode command line tools. When prompted, click and install through that, and you're homebrew installation will continue.

After the installation process, run the command `brew doctor`. If any warnings or errors are displayed, we will need to resolve them before proceeding with the rest of the install fest.

## Xcode

Speaking of Xcode, install Xcode through the App Store. [Link here](https://itunes.apple.com/us/app/xcode/id497799835?mt=12)

## GIT

Before we do this process, please make sure you have signed up for an account on [Github](http://www.github.com). We will be installing a version of GIT from home brew and also configuring it.

To install GIT

```text
brew install git
```

#### Configuring GIT

Using your email credentials for GIT, run these commands with your user and email configured.

```text
git config --global user.name "YOUR-USERNAME"
git config --global user.email "YOUR-EMAIL-ADDRESS"
git config --global push.default simple
git config --global credential.helper osxkeychain
```

## Sublime

We'll be running **Sublime**, as our text editor of choice.

Download and install the latest version [https://www.sublimetext.com/](https://www.sublimetext.com/)

### Run sublime from your command line

#### Setting up the bash shell for sublime \(and other stuff\)

> do you have any other shell configuration files in your home directory? `ls -la ~` If you have something named `.zshrc`, `.bashrc`, `.bash_profile` Take the contents out of this file and put it in the new one we are creating. Then delete the old file.

Find the location of your copy of sublime from the terminal:

```text
ls -la /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl
```

Should run without errors.

If not, make sure to change this location reference in the code below, or move your copy of sublime to the correct location.

#### File Setup

Create a new shell config file.

```text
touch ~/.profile
```

Then open this new file in a text editor such as TextEdit

```text
open ~/.profile
```

Put this code inside:

```text
export PS1="\[\033[36m\]\u\[\033[m\]@\[\033[32m\]\h:\[\033[33;1m\]\w\[\033[m\]\$ "
export CLICOLOR=1
export LSCOLORS=ExFxBxDxCxegedabagacad
alias sublime="/Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl"
export VISUAL=sublime
export EDITOR="$VISUAL"

function subledit() {
  sublime ~/.profile
}

function profilerefresh() {
  echo "Refreshing your configuration."
  source ~/.profile
}
```
Save the file, then close the text editor.

Run this on your terminal:

```text
echo '[[ -s ~/.profile ]] && source ~/.profile' >> ~/.zprofile
```

**Testing** Open a _NEW_ Terminal window and run:

```text
sublime ~/Documents
```

**to open the entire current directory**

```text
sublime .
```

### Install the sublime `packagecontrol` library

Package Control allows you to add new functionality to sublime.

[https://packagecontrol.io/installation](https://packagecontrol.io/installation)

### Use the class `Preferences.sublime-settings` file:

[https://raw.githubusercontent.com/wdi-sg/gitbook-2018/master/Preferences.sublime-settings](https://raw.githubusercontent.com/wdi-sg/gitbook-2018/master/Preferences.sublime-settings#)

Open sublime and use the menu bar to go to: Sublime Text -&gt; Preferences -&gt; Settings

On the right window \(Preferences.sublime-settings\), earse the current contents of the file and paste in the entire contents of the file from the link above.

#### Using Package Control

[https://packagecontrol.io/docs/usage](https://packagecontrol.io/docs/usage)

> Package Control is driven by the Command Palette. To open the palette, press `ctrl+shift+p` \(Win, Linux\) or `cmd+shift+p` \(OS X\). All Package Control commands begin with Package Control:, so start by typing Package.

### Set Sublime to use `editorconfig` files

* `cmd+shift+p` type in `Package Control: Install Package` \(auto-complete will help you\) and press return
* type in `editorconfig` to install the package

### Get the `.editorconfig` file:

[https://raw.githubusercontent.com/wdi-sg/gitbook-2018/master/.editorconfig](https://raw.githubusercontent.com/wdi-sg/gitbook-2018/master/.editorconfig)

Create a file named `.editorconfig` exactly, and save it in your home directory:

```text
cd ~
touch .editorconfig
sublime .editorconfig
```

Paste the contents from the above link into the file.

### Get the `.gitignore file`

[https://raw.githubusercontent.com/wdi-sg/gitbook-2018/master/.gitignore](https://raw.githubusercontent.com/wdi-sg/gitbook-2018/master/.gitignore)

Create a file named `.gitignore` exactly, and save it in your home directory.

```text
cd ~
touch .gitignore
sublime .gitignore
```

Paste the contents from the above link into the file.

### Set Sublime to run as your git commit message editor

#### BEFORE YOU RUN THIS, MAKE SURE THE PATH / LOCATION OF YOUR SUBLIME APP IS CORRECT

```text
ls -la /Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl
```

Should run without errors.

Then:

```text
git config --global core.editor "/Applications/Sublime\ Text.app/Contents/SharedSupport/bin/subl -w"
```

## Optional: install some other sublime packages:

* ColorPicker \(pick colors by typing `COMMAND + SHIFT + c`, handy for CSS\)
* Color Highlighter \(visually displays colors for hex/rgb values\)
* GitGutter \(shows git additions/deletions\)
* BracketHighlighter \(highlight brackets and tabs\)

## Floobits

Install the floobits sublime extension:

* `cmd+shift+p` type in `Package Control: Install Package` \(auto-complete will help you\) and press return
* type in `floobits` to install the package
* click to automatically create an account
* `cmd+shift+p` type in `Package Control: Install Package` \(auto-complete will help you\) and press return
* type in `floobits complete sign up` this will take you to the floobits website and prompt you to sign up.

