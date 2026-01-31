README for fontconfig

---

POST-INSTALL
============

After upgrading `fontconfig`, rebuild font cache files (executed by
`post-install` scripts):

```sh
# as root
fc-cache --force --system-only
```

Always run `rejmerge` and update:

* `/etc/fonts/fonts.conf`
* `/etc/fonts/fonts.dtd`

Configuration snippets in `/etc/fonts/conf.avail` can be symlinked
from `/etc/fonts/conf.d` instead of duplicating XML code in
`/etc/fonts/local.conf`.

---

REFERENCES
==========

* `conf.avail/conf.d`:
https://gitlab.freedesktop.org/fontconfig/fontconfig/-/raw/main/conf.d/README.in

* `fontconfig`:
https://www.freedesktop.org/software/fontconfig/fontconfig-user.html

---

End of file.
