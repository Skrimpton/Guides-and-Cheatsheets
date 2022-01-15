# Simple terminal and script tips'n'tricks
## Tested on Manjaro KDE using konsole 21.12.0 and zsh 5.8 (x86_64-pc-linux-gnu)

### You can write this:
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
   
<sup> <b> *and even like this:* </b> </sup>

```bash
[ -d "$PWD" ] && 
{
echo "ofc"
} || {
echo "lol wut"
}
```
*(but you shouldn't)*



### You can add newlines in your command prompt using ALT+ENTER or ALTGR+ENTER <br> *sometimes — depending on which emulator and/or shell you're using*

So you can write that long-ass oneliner like you would in a script — with visible newlines — like God intended

![Screenshot_14-01-2022_124330](https://user-images.githubusercontent.com/64572787/149510315-f038a511-1a0d-49da-af81-52c9a0ee6de3.png)

### Kill all background-jobs - bash aliases

*- For suspended jobs*
```bash
alias kill-all-suspended='thejobs=$(jobs -ps | wc -l);[ "$thejobs" != 0 ] && while [ "$thejobs" != 0 ];do for i in "$thejobs"; do [ "$thejobs" != 0 ] && kill %$i; done; thejobs=$(jobs -ps | wc -l); done || echo "No suspended jobs"'
```

*- For all jobs opened using the '&'-sign:*
```bash
alias kill-all-jobs='thejobs=$(jobs | wc -l);[ "$thejobs" != 0 ] && while [ "$thejobs" != 0 ];do for i in "$thejobs"; do [ "$thejobs" != 0 ] && kill %$i; done; thejobs=$(jobs | wc -l); done || echo "No jobs"'
```
