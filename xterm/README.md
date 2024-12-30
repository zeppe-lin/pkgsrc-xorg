README xterm

---


NOTES
=====

Opening terminal links with the keyboard
----------------------------------------

*Requires*:
 - p5-regexp-common
 - pick
 - xdg-utils

Create the following script, named e.g. `urlpick.sh` and place it to your
`$PATH`:

```sh
#!/bin/sh
perl -MRegexp::Common -lne 'print $1 if /$RE{URI}{-keep}/;' |
    pick | xargs xdg-open
```

Next, add to your `.Xresources` the following lines:

```
XTerm*printerCommand: xterm -T urlpick.sh -e sh -c 'urlpick.sh <&3' 3<&0

*VT100*Translations: #override\n\
  Ctrl Alt <Key>F: print-everything(noAttrs)
```

Reload:
```sh
xrdb -load ~/.Xresources
```

Start new terminal and test new feature through `CTRL+ALT+F` shortcut.


---

End of file.
