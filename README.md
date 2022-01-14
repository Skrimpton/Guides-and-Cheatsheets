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

### *Sometimes (depending on which emulator and/or shell you're using) you can add newlines in your command prompt using ALT+ENTER or ALTGR+ENTER*

So you can write that long-ass oneliner like you would in a script — with visible newlines — like God intended


![](https://imma.gr/110386xb8eef.jpg)

