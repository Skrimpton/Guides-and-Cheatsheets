# Simple terminal and script tips - for simple folks
#### Only tested on Manjaro KDE using konsole 21.12.0 and zsh 5.8 (x86_64-pc-linux-gnu)
##### And some of the [shortcuts](https://github.com/Skrimpton/Guides-and-Cheatsheets/blob/main/LINUX%20TERMINAL%20TIPS'N'TRICKS%20-%20WILL%20THEY%20WORK%20ON%20YOURS%3F%20(...%20for%20real:%20verify%20safety%20first,%20then%20try%20them%20-%20they%20should%20be%20safe%20little%20things,%20but%20better%20certain%20than%20sorry%20amirite%3F%20-%20...).md#shell-keybindings) don't work on that, so there is stuff in here that might not work for you

#
### Table of contents:
1. [Shorten "if ; then ; elif ; else ; fi "-blocks](https://github.com/Skrimpton/Guides-and-Cheatsheets/blob/main/LINUX%20TERMINAL%20TIPS'N'TRICKS%20-%20WILL%20THEY%20WORK%20ON%20YOURS%3F%20(...%20for%20real:%20verify%20safety%20first%2C%20then%20try%20them%20-%20they%20should%20be%20safe%20little%20things%2C%20but%20better%20certain%20than%20sorry%20amirite%3F%20-%20...).md#shorten-if--then--elif--else--fi--blocks)
2. [Listing enviornment variables](https://github.com/Skrimpton/Guides-and-Cheatsheets/blob/main/LINUX%20TERMINAL%20TIPS'N'TRICKS%20-%20WILL%20THEY%20WORK%20ON%20YOURS%3F%20(...%20for%20real:%20verify%20safety%20first%2C%20then%20try%20them%20-%20they%20should%20be%20safe%20little%20things%2C%20but%20better%20certain%20than%20sorry%20amirite%3F%20-%20...).md#listing-environment-variables)
3. [Newline(s)/empty lines in terminal (without executing a command)](https://github.com/Skrimpton/Guides-and-Cheatsheets/blob/main/LINUX%20TERMINAL%20TIPS'N'TRICKS%20-%20WILL%20THEY%20WORK%20ON%20YOURS%3F%20(...%20for%20real:%20verify%20safety%20first%2C%20then%20try%20them%20-%20they%20should%20be%20safe%20little%20things%2C%20but%20better%20certain%20than%20sorry%20amirite%3F%20-%20...).md#newlinesempty-lines-in-terminal)
4. [Kill *all* jobs](https://github.com/Skrimpton/Guides-and-Cheatsheets/blob/main/LINUX%20TERMINAL%20TIPS'N'TRICKS%20-%20WILL%20THEY%20WORK%20ON%20YOURS%3F%20(...%20for%20real:%20verify%20safety%20first%2C%20then%20try%20them%20-%20they%20should%20be%20safe%20little%20things%2C%20but%20better%20certain%20than%20sorry%20amirite%3F%20-%20...).md#kill-all-jobs-they-must-die)
5. [Shell Keybindings](https://github.com/Skrimpton/Guides-and-Cheatsheets/blob/main/LINUX%20TERMINAL%20TIPS'N'TRICKS%20-%20WILL%20THEY%20WORK%20ON%20YOURS%3F%20(...%20for%20real:%20verify%20safety%20first%2C%20then%20try%20them%20-%20they%20should%20be%20safe%20little%20things%2C%20but%20better%20certain%20than%20sorry%20amirite%3F%20-%20...).md#shell-keybindings)

#

[^1]:"$PWD" is a variable which holds the path of the folder where the terminal you are using is currently doing stuff from, or inside of  
—  
See what it is with:  
  echo "$PWD"  
—  
  If "$PWD" is:                    /home/Username/  
  Then the command:                mkdir lolfolder  
  ...will (attempt to) create:     /home/Username/lolfolder/</pre>  


## Shorten "if ; then ; elif ; else ; fi "-blocks
*The following examples check whether or not "$PWD" [^1] is a folder using:* ```[ -d /path/to/folder ]```
<br> *and then outputs a text — chosen by you — depending on whether or not it is, or isn't a folder<br> (hopefully it is)*


#### You can write these if-statements:

```
if [ -d "$PWD" ];then;echo "Yeah it is";else;echo "Hmmm... It should be";fi
```

```
if [ -d "$PWD" ]
then
   echo "Yeah it is"
else
   echo "Hmmm... It should be"
fi
```
#  
<b> Like this: </b>
   

```
[ -d "$PWD" ] && echo "ofc" || echo "lol wut"

```  
<sup> <b> *or like this:* </b> </sup>

```
[ -d "$PWD" ] && 
( echo "ofc" ) || 
( echo "lol wut" )
```

<b> <sup> *even like this* </b> </sup> 

   
```
[ -d "$PWD" ] &&
( 
  echo -e "\nofc"
  echo -e "it's only logical"
  echo -e "...get it? like spock"
  sleep .7 && echo -en "\n:"   
  sleep .5 && echo -en "'"
  sleep .4 && echo -e "D"    
   
) || (  

  echo "lol wut"

)
```
<sup> <b>note:</b> you can also use curlybrackets for the given examples, and they will return the desired values, but you shouldn't. see [refrences](https://github.com/Skrimpton/Guides-and-Cheatsheets/blob/main/LINUX%20TERMINAL%20TIPS'N'TRICKS%20-%20WILL%20THEY%20WORK%20ON%20YOURS%3F%20(...%20for%20real:%20verify%20safety%20first,%20then%20try%20them%20-%20they%20should%20be%20safe%20little%20things,%20but%20better%20certain%20than%20sorry%20amirite%3F%20-%20...).md#refrence-list-for-here-be-dragons-)

  
#### elif 
 
<sup> *Here we first check if PWD is a folder using an if-statement <br>
and then echoing something if the if-test returns true*</sup>

<sup>*The example exits in the elif-part, see the [linked](https://stackoverflow.com/a/53900466) stackoverflow response for more details* </sup>


```
( [ ! -d "$PWD" ] && echo -e "Not a folder..?" ) || ( [ -d "$PWD" ] && echo -e "Yeah it should be a folder" ) || echo -e ":O"   
```
 [Beejor](https://stackoverflow.com/a/53900466) 
  > *Also note that ( and [ are technically commands, so whitespace is required around them.*

 <sup>right way: <code>( [ -d /folder ] )</code></sup>

<sup>wrong way: <code>([-d /folder])</code></sup>

#

<sup> Speaking of $PWD... </sup>
## Listing environment variables:

<b> Bash </b>
```
bind -P
```
<b> Zsh </b>
```
env
```
<b> Both:
<br><sup>*will work in many shells*</sup> </b>
```
printenv
```
<b> One can also list predefined variables by just passing "set" without declaring any options<br><sup>*will work in many shells*</sup></b>
```
set   
```
<b><sup>*```set``` produces the most complete list of variables*</sup></b>
#

## Newline(s)/empty line(s) in Terminal

#### You can add new (empty) lines in your command prompt
  *So you can write that all-too-long-one-liner similiar to how you would in a script — with visible newlines! — like God intended*
  - powershell (windows 10): shift + enter
  - zsh: alt + enter / esc + enter
  - bash: ctrl + j *followed by* crtl + v
  
  [Stéphane Chazelas](https://unix.stackexchange.com/a/80820)
  > *Alternatively, instead of typing *Enter*, you can type Ctrl-V* (then) *Ctrl-J...*
  <br>*... To get the same behavior in bash, you can add to your ~/.inputrc:* <sup>
  <br>[disclaimer: only make changes like  this if you're sure there won't be dire sideffects]</sup>

```
  "\e\C-m": "\026\n"
```
  
#

## Kill all Jobs (they must die)
  *Functional (but bad and ugly) modified solution based on
  <br>good solution found in comment by user <b>jw013</b> to [this stackexchange question](https://unix.stackexchange.com/q/43527)*
![newline-example](https://user-images.githubusercontent.com/64572787/149652146-07720bae-bf23-4679-9f07-2d544403ce54.png) 

  
*- Kill all jobs*

```
alias kill-all-jobs='thejobs=$(jobs | wc -l);[ "$thejobs" != 0 ] && while [ "$thejobs" != 0 ];do for i in "$thejobs"; do [ "$thejobs" != 0 ] && kill %$i; done; thejobs=$(jobs | wc -l); done || echo "No jobs"'
```


*- Kill all <b>suspended</b> jobs*

```
alias kill-all-suspended='thejobs=$(jobs -ps | wc -l);[ "$thejobs" != 0 ] && while [ "$thejobs" != 0 ];do for i in "$thejobs"; do [ "$thejobs" != 0 ] && kill %$i; done; thejobs=$(jobs -ps | wc -l); done || echo "No suspended jobs"'
```

*- Readable version - for use in a script*
```
#!/bin/bash
  
####### SWITCHING WHICH OF THESE TWO LINES ARE COMMENTED OUT CHANGES IT FROM SUSPENDED JOBS TO ALL BACKGROUND JOBS
####### this is determined by the -ps option of the "jobs"-command 

#thejobs=$(jobs | wc -l) 
thejobs=$(jobs -ps | wc -l)
  
###################################################################  

[ "$thejobs" != 0 ] && while [ "$thejobs" != 0 ]
  do 
    for i in "$thejobs" 
      do 
        [ "$thejobs" != 0 ] && kill %$i
      done
    thejobs=$(jobs -ps | wc -l)
  done || echo "Nothing to kill"
```

#

## Shell Keybindings
##### *Copied from [2KAbhishek](https://gist.github.com/2KAbhishek/9c6d607e160b0439a186d4fbd1bd81df)

### Navigation 🚀

- Alt + f/b  - Move cursor to previous/next word <br>
- Ctrl + a/e - Move cursor to beginning/end of command <br>
- Ctrl + xx  - Toggle between the start of line and current cursor position <br>

  ---

### Editing ✏️

- Ctrl + x,e   - Open command in editor <br>
- Ctrl + k     - Cut till end <br>
- Ctrl + u     - Delete whole line (zsh)/ cut until beginning (bash) <br>
- Alt + w      - Delete until beginning (zsh) <br>
- Alt + l/u    - Lowercase/Uppercase word <br>
- Alt + c      - Capitalize Word <br>
- Ctrl + w     - Cut previous word <br>
- Alt + Del    - Delete previous word <br>
- Alt + d      - Delete next word <br>
- Alt +. or !$ - Previous commands last arguement <br>
- !*           - All arguments of previous command <br>
- Alt + t      - Swap current word with previous <br>
- Ctrl + t     - Swap the last two characters before the cursor (typo). <br>
- Esc + t      - Swap the last two words before the cursor <br>
- Ctrl + y     - Paste <br>
- Ctrl + _     - Undo <br>
- Alt + r      - Cancel the changes, revert <br>

  ---
### Process 📊

- Ctrl + l - Clear screen <br>
- Ctrl + c - Interrupt/Kill <br>
- Ctrl + d - Close Current Shell <br>
- Ctrl + z - Background/Foreground job <br>

  ---

### History ⏳

- Ctrl + r   - History search <br>
- Ctrl + s   - Go back to the next most recent command <br>
- ^abc­^­def   - Run previous command, replacing abc with def <br>

 ---

### Modes 🕹️

- Ctrl +x,v - vi mode (zsh) <br>
- set -o vi - Vi mode <br>

#

#### Refrence list, for here be dragons... [﹖](https://en.wikipedia.org/wiki/Here_be_dragons)

###### *[ZSH.sourceforge.io - Alternate forms for complex commands](https://zsh.sourceforge.io/Doc/Release/Shell-Grammar.html#Alternate-Forms-For-Complex-Commands)*

###### [man7.org - BASH manual on shellgrammar (compund commands are relevant)](https://man7.org/linux/man-pages/man1/bash.1.html#SHELL_GRAMMAR)

###### [linux.com - Curly brackets](https://www.linux.com/topic/desktop/all-about-curly-braces-bash/)

###### [Stackoverflow answer from "Beejor"](https://stackoverflow.com/a/53900466)

