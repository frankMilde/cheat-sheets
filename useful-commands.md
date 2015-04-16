Useful Linux Commands
=====================

Todo
----
- When the list grows maybe sort after topics?

#### Replace content across files
`ack -l "search" | xargs sed -i 's/search/replace/g'`

### Generate diffs
- Single files
```
diff -u orig.c new.c > changes.diff`
```
- Multiple files
Create two folders `old/` and `new/` which can contain multiple files and
even subdirs. That way you can patch multiple applications.
```
diff -rupN old/ new/ > changes.diff
```

### Patches
- Using `patch`
```
patch [-p1] < changes.diff
```
      ^^^^^

The `-p1` flag might be necessary to ignore the toplevel path when patching
whole dirs with subdirs.
- Using `git`
```
git apply changes.diff
```
### Transfer file attributes from file a -> b
```
touch -r a b
```

### Show fonts installed on system
```
fc-list
```
### Update system fonts
```
fc-cache -fv
```

### Install AUR packages
D/l tar ball to `~/local/src/`. Extract. Change to dir. Run
```
makepkg -s
sudo pacman -U <package-name>
```

