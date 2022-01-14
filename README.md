# Simple terminal and script tips tricks
### You can write:
```bash
if [ -d "$PWD" ];then;echo "Yeah it is";else;echo "Hmmm... It should be";fi
```

#### or

```bash
if [ -d "$PWD" ];then
   echo "Yeah it is"
else
   echo "Hmmm... It should be"
fi
```

### Like this:

```bash
[ -d "$PWD" ] && echo "ofc" || echo "lol wut"

```

#### even like this:

```bash
[ -d "$PWD" ] && {
echo "ofc"
} || {
echo "lol wut"
}
```

### *Some terminal emulator let you add newlines using ALT+ENTER or ALTGR+ENTER <br> So you can write that long-ass oneliner like you would in a script — with visible newlines — <br> Like God intended*



![](https://imma.gr/110386xb8eef.jpg)

