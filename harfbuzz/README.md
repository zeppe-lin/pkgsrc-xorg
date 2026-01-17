README harfbuzz

---


POST-INSTALL
============

After `harfbuzz` is installed, rebuild and reinstall `freetype`:

```sh
# as root
pkgman update -fr --deps --depsort freetype
```


---

End of file.
