# Smart Git Prompt

Git is undoubtedly amazing. But constantly switching branches can be confusing though as you have to run `git status` to see which branch you're currently on and you do the same to see if you have uncommited files.

The solution to this is to have your terminal display the current
branch with dirty state (* is displayed with the branch name if the branch is dirty)


## Overview

If you `cd` to a Git working directory, you will see the current Git branch
name displayed in your terminal prompt. When you're not in a Git working
directory, your prompt works like normal.

![Git Branch in Prompt](https://raw.github.com/bhanuchawla/smart-git-prompt/master/preview.png)


## Installation

Clone the project to a `.bash` folder in your home directory:

```bash
mkdir ~/.bash
cd ~/.bash
git clone git://github.com/bhanuchawla/smart-git-prompt.git
```

Edit your  `~/.profile` or `~/.bash_profile` and add the following to the top:

```bash
export SMARTGITPROMPT=~/.bash/smart-git-prompt
source $SMARTGITPROMPT/main.sh
export PS1="\u@\h \w \[$txtcyn\]\$git_branch\[$txtred\]\$git_dirty\[$txtrst\]\$ "
```

Optionally, if you want a nice pretty prompt when using `sudo -s`, also add
this line:

```bash
export SUDO_PS1="\[$bakred\]\u@\h\[$txtrst\] \w\$ "
```

The new prompt will take effect beginning in your next session. This usually
means logging out completely. To enable it in your current session, you can
simply run `source ~/.profile` or `source ~/.bash_profile` (whichever you
edited above) in your terminal.


## Configuring

If you followed the above installation instructions, you've added the default
prompt style already by defining the `PS1` variable. If you don't know how to
customize your prompt, I recommend you check [this][5] how-to.

[5]: http://www.cyberciti.biz/tips/howto-linux-unix-bash-shell-setup-prompt.html

Basically, to have the current Git branch shown, simply add `$git_branch` to
your `PS1` variable, and make sure the variable value is defined with double
quotes. A set of color variables have also been set for you to use. For a list
of available colors check `colors.sh`.


## Updating

Assuming you followed the default installation instructions and cloned this
repo to `~/.bash/smart-git-prompt`:

```bash
cd ~/.bash/smart-git-prompt
git pull
```


## License

```
        DO WHAT THE #### YOU WANT TO PUBLIC LICENSE
                    Version 2, December 2004

 Copyright (C) 2014 Bhanu Chawla

 Everyone is permitted to copy and distribute verbatim or modified
 copies of this license document, and changing it is allowed as long
 as the name is changed.

            DO WHAT THE #### YOU WANT TO PUBLIC LICENSE
   TERMS AND CONDITIONS FOR COPYING, DISTRIBUTION AND MODIFICATION

  0. You just DO WHAT THE #### YOU WANT TO.
```
