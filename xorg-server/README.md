README for xorg-server

---

UPGRADE
=======

On major ABI changes (e.g., 1.16.0 -> 1.17.0) you must rebuild input
and video packages.  Failure to do so may leave you without mouse,
keyboard, or 3D acceleration:

```sh
# as root
pkgman update -fr $(pkgman list --regex \
                    --filter='^xorg-xf86-(input|video)|^mesa')
```

NVIDIA Users
------------

If you use NVIDIA, also run:

```sh
# as root
gl-select use xorg && gl-select use nvidia
```

Safe Reboot (SysRq)
-------------------

If you forget to rebuild and lose input, and your kernel has SysRq
enabled, you can reboot safely by holding Alt + SysRq and typing:

```
reisub
```

---

End of file.
