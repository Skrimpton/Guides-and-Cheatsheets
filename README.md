# Simple terminal tricks
### YOu can write:
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

### Like This:

```bash
[ -d "$PWD" ] && {echo "ofc"} || {echo "lol wut"}

```

#### or

```bash
[ -d "$PWD" ] && {
echo "ofc"
} || {
echo "lol wut"
}
```

*In KDE's konsole running zsh ALT+ENTER adds a newline in the command prompt <b> where this version is easier to type and read from history than long lines using ;*


