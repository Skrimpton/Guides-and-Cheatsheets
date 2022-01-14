# Simple terminal and script tips tricks
## Tested on Manjaro KDE using konsole 21.12.0 and zsh 5.8 (x86_64-pc-linux-gnu)

### You can write this:
```bash
if [ -d "$PWD" ];then;echo "Yeah it is";else;echo "Hmmm... It should be";fi
```
<b>*and this*</b>
   
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

### You can add newlines in your command prompt using ALT+ENTER or ALTGR+ENTER <br> *sometimes — depending on which emulator and/or shell you're using*

So you can write that long-ass oneliner like you would in a script — with visible newlines — like God intended


![](https://user-images.githubusercontent.com/64572787/149509707-7d7a4977-0390-4cd1-b094-6180358c9e36.png)

