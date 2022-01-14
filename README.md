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

### *Some terminal emulators let you add newlines using ALT+ENTER or ALTGR+ENTER*

So you can write that long-ass oneliner like you would in a script <br> — with visible newlines — <br> Like God intended


![](https://imma.gr/110386xb8eef.jpg)

