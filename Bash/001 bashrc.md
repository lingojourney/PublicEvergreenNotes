The `.bashrc` file is a script that runs every time you open a new terminal session. It’s a great place to add aliases, functions, and other configurations to streamline your workflow. Here are some productivity examples:

**Aliases:**

```bash
# Shortcuts for navigation
alias ..='cd ..'
alias ...='cd ../../../'
alias ....='cd ../../../../'
alias ~='cd ~'

# Git commands
alias gs='git status'
alias ga='git add'
alias gc='git commit'
alias gp='git push'

# System updates for Debian/Ubuntu
alias update='sudo apt-get update && sudo apt-get upgrade'
```

**Functions:**

```bash
# Create a new directory and enter it
mkcd() {
  mkdir -p "$1" && cd "$1"
}

# Extract various archive file types
extract() {
  if [ -f "$1" ]; then
    case "$1" in
      *.tar.bz2)   tar xjf "$1"     ;;
      *.tar.gz)    tar xzf "$1"     ;;
      *.bz2)       bunzip2 "$1"     ;;
      *.rar)       unrar e "$1"     ;;
      *.gz)        gunzip "$1"      ;;
      *.tar)       tar xf "$1"      ;;
      *.tbz2)      tar xjf "$1"     ;;
      *.tgz)       tar xzf "$1"     ;;
      *.zip)       unzip "$1"       ;;
      *.Z)         uncompress "$1"  ;;
      *.7z)        7z x "$1"        ;;
      *)           echo "don't know how to extract '$1'..." ;;
    esac
  else
    echo "'$1' is not a valid file"
  fi
}
```

**Prompt Customization:**

```bash
# Customize the Bash prompt
export PS1="\[\033[01;32m\]\u@\h\[\033[00m\]:\[\033[01;34m\]\w\[\033[00m\]\$ "
```

These are just a few examples of how you can customize your `.bashrc` for better productivity. [Remember to reload your `.bashrc` with `source ~/.bashrc` or simply open a new terminal window to apply the changes](https://www.freecodecamp.org/news/bashrc-customization-guide/)[1](https://www.freecodecamp.org/news/bashrc-customization-guide/)[2](https://adamtheautomator.com/bashrc/)[3](https://medium.com/@tzhenghao/a-guide-to-building-a-great-bashrc-23c52e466b1c)[4](https://itnext.io/easy-bash-scripting-tips-to-increase-productivity-7227f6d12756)[5](https://dev.to/donasmi43473554/a-full-guide-to-linux-bashrc-and-how-to-use-it-ji9).