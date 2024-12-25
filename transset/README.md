README transset

---


REQUIREMENTS
============

First of all, for transparency to work in X you have to have X-server with
XComposite extension working.  `transset` is not a program that creates
transparency, it's a program that sets properties for windowses.  These
properties must then be supported by the underlaying X-server.

Use `picom` as composite manager, for example.


CONFIGURATION
=============

You can use keyboard or mouse shortcuts to set transparency value to the
focused windows.

Keyboard Bindings
-----------------

See dwm's `config.def.h` for example.

Mouse Bindings
--------------

The **scrollwheel method** can be realized via `xbindkeys`.  Bind pressing control
+ scrolling up to `transset -p --inc 0.1` and pressing control + scrolling
down to `transset --min 0.1 -p --dec 0.2`.  The `--min` flag makes sure you'll
not be able to make windowses invisible.

**~/.xbindkeysrc**:

```
"transset --min 0.1 -p --dec 0.2"
control + b:4
"transset -p --inc 0.1"
control + b:5
```


---

End of file.
