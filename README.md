# ctags-nightly-build

build [Universal Ctags](https://github.com/universal-ctags/ctags) every night via GitHub Actions.

## Notes

This repository only provides prebuilt binaries for `macOS`, `Linux`, `FreeBSD`, `OpenBSD`, `NetBSD`. If you need prebuilt binaries for `Windows`, please go to [ctags-win32](https://github.com/universal-ctags/ctags-win32)

This repository only for building purpose. If you encounter any problems with these prebuilt binaries, please file an issue on [Universal Ctags issue tracker](https://github.com/universal-ctags/ctags/issues)

If you are extreamly concerned about performance, building it on you local machine from [source](https://github.com/universal-ctags/ctags) is a better choice as long as you know [Autotools](https://www.gnu.org/software/automake/manual/html_node/Autotools-Introduction.html) well.

## Dependency Graph

![dependencies](uctags-dependencies.svg)

## for `Linux`, `FreeBSD`, `OpenBSD`, `NetBSD`

All dependent libraries including libc are statically-linked into the executable.

Archive file structure:

```text
uctags-2023.02.02-linux-x86_64
├── bin
│   ├── ctags
│   ├── optscript
│   └── readtags
└── .ppkg
    ├── config.log
    ├── COPYING
    ├── dependencies.box
    ├── dependencies.dot
    ├── MANIFEST.txt
    ├── README.md
    └── RECEIPT.yml
```

These archive files are created by [ppkg](https://github.com/leleliu008/ppkg), some extra files are shipped with the archive, which all are located in a hidden directory named `.ppkg`.

## for `macOS`

All dependent libraries except `/usr/lib/libSystem.B.dylib` are statically-linked into the executable.

Archive file structure:

```text
uctags-2023.02.02-MacOSX11.0-arm64
├── bin
│   ├── ctags
│   ├── optscript
│   └── readtags
└── .xcpkg
    ├── config.log
    ├── COPYING
    ├── dependencies.box
    ├── dependencies.dot
    ├── MANIFEST.txt
    ├── README.md
    └── RECEIPT.yml
```

These archive files are created by [xcpkg](https://github.com/leleliu008/xcpkg), some extra files are shipped with the archive, which all are located in a hidden directory named `.xcpkg`.
