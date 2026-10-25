# dmenu-patched

dmenu (the suckless dynamic menu for X) built from the 5.4 release tarball with
the [xresources patch][1] applied, which adds runtime configuration via X
Resources (`dmenu.font`, `dmenu.foreground`, `dmenu.background`, etc.).

Declares `provides=('dmenu')` and `conflicts=('dmenu')`, so it replaces the
repository `dmenu` package.

## Manual install

```sh
makepkg -si
```

This builds the package and installs it. Because it conflicts with the repo
`dmenu`, pacman will prompt to remove that package first; accept it.

To build the package without installing:

```sh
makepkg -f
```

The resulting `dmenu-patched-*.pkg.tar.zst` can then be installed with
`sudo pacman -U <file>`.

[1]: https://tools.suckless.org/dmenu/patches/xresources/
