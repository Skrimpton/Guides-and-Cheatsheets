# Simple terminal and script tips tricks
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
   
<sup> *and even like this:*

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


![](https://imma.gr/110386xb8eef.jpg)

