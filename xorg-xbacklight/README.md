README for xorg-xbacklight

---

TROUBLESHOOTING
===============

No outputs have backlight property
----------------------------------

If you encounter the error **"No outputs have backlight property"**,
`xrandr`/`xbacklight` may not be selecting the correct directory in
`/sys/class/backlight`.

Specify the directory by setting the Backlight option in the device
section of `/etc/X11/xorg.conf.d/20-video.conf`.

For example, if the directory name is `intel_backlight` and you are
using the Intel driver:

```xorg
Section "Device"
    Identifier  "Intel Graphics"
    Driver      "intel"
    Option      "Backlight"  "intel_backlight"
EndSection
```

---

End of file.
