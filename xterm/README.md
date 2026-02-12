README for xterm

---

NOTES
=====

Opening Terminal Links with the Keyboard
----------------------------------------

**Requires:**

- `p5-regexp-common`
- `pick`
- `xdg-utils`

Create a script named `urlpick.sh` in your `$PATH`:

```sh
#!/bin/sh
perl -MRegexp::Common -lne 'print $1 if /$RE{URI}{-keep}/' |
    pick | xargs xdg-open
```

Add to your `.Xresources`:

```
XTerm*printerCommand: xterm -T urlpick.sh -e sh -c 'urlpick.sh <&3' 3<&0
*VT100*Translations: #override\n\
    Ctrl Alt <Key>F: print-everything(noAttrs)
```

Reload configuration:

```sh
xrdb -load ~/.Xresources
```

Open a new terminal and test with **Ctrl+Alt+F**.

---

End of file.
