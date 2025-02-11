# Utils

#### [console.log](https://developer.mozilla.org/en-US/docs/Web/API/console/log_static) with colors
```sh
console.log('\x1b[41m\x1b[37m RED BACKGROUND \x1b[0m'); 
console.log('\x1b[44m\x1b[37m BLUE BACKGROUND \x1b[0m');
```

#### MacOS profile

`~/.zprofile`

## GIT

Si haces un pull o quieres eliminar un commit ` git reset --hard HEAD~1` remueve un commit del stack

# Amplify
To mock a function use `amplify mock function <functionName>`

# Git Hooks
1.- Set [Global hooks](https://stackoverflow.com/a/37293198) (Hooks that'll work on any repo, **this will overwrite local hooks**)

## Pre-commit example
```
#!/bin/sh
#
# An example hook script to verify what is about to be committed.
# Called by "git commit" with no arguments.  The hook should
# exit with non-zero status after issuing an appropriate message if
# it wants to stop the commit.
#
# To enable this hook, rename this file to "pre-commit".

yellow='\033[0;33m'
reset='\033[0m'
red='\033[0;31m'
blue='\033[0;34m'

echo "${yellow}Did you check grammar?${reset}"

# Allows us to read user input below, assigns stdin to keyboard
exec < /dev/tty

while true; do
  read -p "[Y/n] " yn
  if [ "$yn" = "" ]; then
    yn='Y'
  fi
  case $yn in
      [Yy] ) echo "${blue}cool${reset}"; exit 0;;
      [Nn] ) echo "${red}Review before continuing${reset}"; exit 1;;
      * ) echo "Please answer y or n for yes or no.";;
  esac
done
```
MIT

**Free Software, Hell Yeah!**
