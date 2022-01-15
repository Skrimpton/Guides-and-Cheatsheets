# Simple terminal and script tips'n'tricks
#### Tested on Manjaro KDE using konsole 21.12.0 and zsh 5.8 (x86_64-pc-linux-gnu)
#

##### The following examples check if "$PWD" is a folder that exists <br> and then outputs a text chosen by you if it is or if it isn't (hopefully is)*
¹ "$PWD" is a command which prints the name of the current folder that the terminal you are using is doing stuff from or inside of*
   - if "$PWD" is /home/Username, then ```mkdir lolfolder``` will make /home/Username/lolfolder

#### You can write this:

```bash
if [ -d "$PWD" ];then;echo "Yeah it is";else;echo "Hmmm... It should be";fi
```
<b>*or this*</b>
   
```bash
if [ -d "$PWD" ];then
   echo "Yeah it is"
else
   echo "Hmmm... It should be"
fi
```
   
<b> Like this: </b>
   

```bash
[ -d "$PWD" ] && echo "ofc" || echo "lol wut"

```  
<sup> <b> *or like this:* </b> </sup>

```bash
[ -d "$PWD" ] && 
{ echo "ofc" } || 
{ echo "lol wut" }
```

<b> <sup> *even like this* </b> </sup> 

   
```bash
[ -d "$PWD" ] &&
{ 
  echo -e "\nofc"
  echo -e "it's only logical"
  echo -e "...get it? like spock"
  sleep .7 && echo -en "\n:"   
  sleep .5 && echo -en "'"
  sleep .4 && echo -e "D"    
   
} || {  

  echo "lol wut"

}
```

### [But here be dragons...:](https://en.wikipedia.org/wiki/Here_be_dragons)
#### *[ZSH.sourceforge.io - Alternate forms for complex commands](https://zsh.sourceforge.io/Doc/Release/Shell-Grammar.html#Alternate-Forms-For-Complex-Commands)*
##### [man7.org - BASH manual on shellgrammar (compund commands are relevant)](https://man7.org/linux/man-pages/man1/bash.1.html#SHELL_GRAMMAR)
##### [linux.com - Curly brackets](https://www.linux.com/topic/desktop/all-about-curly-braces-bash/)

#

#### You can add newlines in your command prompt using ALT+ENTER or ALTGR+ENTER <br> *sometimes — depending on which emulator and/or shell you're using*

So you can write that all-too-long one-liner visually similiar to a script — with visible newlines — like God intended


![](https://user-images.githubusercontent.com/64572787/149601795-1fa07384-d534-4b51-bbfe-16477d041fe4.png)


#### Kill all background-jobs - bash aliases
#

*- For all jobs*

```bash

alias kill-all-jobs='thejobs=$(jobs | wc -l);[ "$thejobs" != 0 ] && while [ "$thejobs" != 0 ];do for i in "$thejobs"; do [ "$thejobs" != 0 ] && kill %$i; done; thejobs=$(jobs | wc -l); done || echo "No jobs"'

```


*- For all suspended jobs*

```bash
alias kill-all-suspended='thejobs=$(jobs -ps | wc -l);[ "$thejobs" != 0 ] && while [ "$thejobs" != 0 ];do for i in "$thejobs"; do [ "$thejobs" != 0 ] && kill %$i; done; thejobs=$(jobs -ps | wc -l); done || echo "No suspended jobs"'
```


#



## Shell Keybindings
##### *(copy pasted from [2KAbhishek](https://gist.github.com/2KAbhishek/9c6d607e160b0439a186d4fbd1bd81df))*

### Navigation 🚀

Alt + f/b  - Move cursor to previous/next word <br>

Ctrl + a/e - Move cursor to beginning/end of command <br>

Ctrl + xx  - Toggle between the start of line and current cursor position <br>

---

### Editing ✏️

Ctrl + x,e   - Open command in editor <br>

Ctrl + k     - Cut till end <br>

Ctrl + u     - Delete whole line (zsh)/ cut until beginning (bash) <br>

Alt + w      - Delete until beginning (zsh) <br>

Alt + l/u    - Lowercase/Uppercase word <br>

Alt + c      - Capitalize Word <br>

Ctrl + w     - Cut previous word <br>

Alt + Del    - Delete previous word <br>

Alt + d      - Delete next word <br>

Alt +. or !$ - Previous commands last arguement <br>

!*           - All arguments of previous command <br>

Alt + t      - Swap current word with previous <br>

Ctrl + t     - Swap the last two characters before the cursor (typo). <br>

Esc + t      - Swap the last two words before the cursor <br>

Ctrl + y     - Paste <br>

Ctrl + _     - Undo <br>

Alt + r      - Cancel the changes, revert <br>

---

### Process 📊

Ctrl + l - Clear screen <br>

Ctrl + c - Interrupt/Kill <br>

Ctrl + d - Close Current Shell <br>

Ctrl + z - Background/Foreground job <br>

---

### History ⏳

Ctrl + r   - History search <br>

Ctrl + s   - Go back to the next most recent command <br>

^abc­^­def   - Run previous command, replacing abc with def <br>

---

### Modes 🕹️

Ctrl +x,v - vi mode (zsh) <br>

set -o vi - Vi mode <br>

