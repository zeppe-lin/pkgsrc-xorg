README transset

---


REQUIREMENTS
============

Transparency in X requires an X server with the XComposite extension.
`transset` itself does not create transparency -- it simply sets
window properties that must be supported by the X server.

The following composite managers are available:

* `picom`
* `xorg-xcompmgr`


CONFIGURATION
=============

You can adjust window transparency using keyboard or mouse shortcuts.

Keyboard Bindings
-----------------

See dwm's `config.def.h` for example.

Mouse Bindings
--------------

The **scrollwheel method** can be realized via `xbindkeys`.  Bind
pressing control + scrolling up to `transset -p --inc 0.1` and
pressing control + scrolling down to `transset --min 0.1 -p --dec 0.2`.
The `--min` flag makes sure you'll not be able to make windowses
invisible.

```sh
# ~/.xbindkeysrc
"transset --min 0.1 -p --dec 0.2"
control + b:4

"transset -p --inc 0.1"
control + b:5
```


---

End of file.
