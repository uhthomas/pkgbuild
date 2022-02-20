# pkgbuild

Packages for the [Arch User Repository](https://aur.archlinux.org/packages?K=uhthomas&SeB=m).

## Build

Use [paru](https://github.com/Morganamilo/paru).

```sh
❯ paru -Ui
```

## Test

Use [namcap](https://wiki.archlinux.org/title/Namcap).

```sh
❯ namcap -i PKGBUILD
```

## Contributing

Always update `.SRCINFO`.

```sh
❯ makepkg --printsrcinfo > .SRCINFO
```

Update checksums.

```sh
❯ makepkg -g -f -p PKGBUILD
```

Publish changes to the AUR, where `$pkgbase` is the name of the package.

```sh
❯ cd $pkgbase
❯ git init
❯ git remote add origin ssh://aur@aur.archlinux.org/$pkgbase
❯ git fetch origin
❯ git switch master
❯ git add -A
❯ git commit -m "..."
❯ git push
```
