README fontconfig

---


POST-INSTALL
============

After upgrading `fontconfig`, always build font information cache files by the
following command (or just enable post-install scripts):

```sh
fc-cache --force --system-only
```

Also, always run `rejmerge` and upgrade `/etc/fonts/fonts.conf` and
`/etc/fonts/fonts.dtd`.

`/etc/fonts/conf.avail` ships with configuration snippets that can be symlinked
from `/etc/fonts/conf.d` to enable them.  It's recommended to use these
snippets instead of duplicating XML code in your `/etc/fonts/local.conf`.

For more information on `conf.avail/conf.d`, please see:
https://gitlab.freedesktop.org/fontconfig/fontconfig/-/raw/main/conf.d/README.in

For more information on `fontconfig`, please see:
https://www.freedesktop.org/software/fontconfig/fontconfig-user.html


---

End of file.
