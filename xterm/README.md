README xterm

---


NOTES
=====

Opening terminal links with the keyboard
----------------------------------------

**Requires**:
  * `p5-regexp-common`
  * `pick`
  * `xdg-utils`

Create a script named `urlpick.sh` and place it in your `$PATH`:

```sh
#!/bin/sh
perl -MRegexp::Common -lne 'print $1 if /$RE{URI}{-keep}/' |
    pick | xargs xdg-open
```

Add this to your `.Xresources`:

```
XTerm*printerCommand: xterm -T urlpick.sh -e sh -c 'urlpick.sh <&3' 3<&0
*VT100*Translations: #override\n\
    Ctrl Alt <Key>F: print-everything(noAttrs)
```

Reload:

```sh
xrdb -load ~/.Xresources
```

Start a new terminal and test with Ctrl+Alt+f.


---

End of file.
