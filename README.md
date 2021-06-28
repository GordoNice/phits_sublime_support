# Syntax highlighting and execute of PHITS input files support for Sublime Text

This repo consists of files which are dedicated to provide syntax highlighting for
[PHITS](https://phits.jaea.go.jp/) input files in [Sublime Text editor](https://www.sublimetext.com/).
Additionally, it provides support for build option.

![](https://github.com/GordoNice/phits_sublime_support/blob/master/Screenshot.png "Screenshot with syntax highlighting")

Contents:

```
.
├── linux
│   ├── phig3d.sublime-build      # file for build option (geometry view of currently open input file)
│   └── phits.sublime-build       # file for build option (launch calculations of currently open input file)
└── win                           # same files as in "linux" folder, but dedicated to windows
    ├── phig3d.sublime-build
    └── phits.sublime-build
├── phits-comments.tmPreferences  # file which provides comment out option
├── phits.sublime-syntax          # file with syntax highlighting
├── README.md
```

Steps to make everything work:

1. Download all the files from repo as a zip or git clone.
2. Place 4 files (`phits.sublime-syntax`,
`phits-comments.tmPreferences` + 2 files from `win` or `linux` directory) in
sublime config directory. This path is by default: `~/.config/sublime-text-3/Packages/User`
for linux users and `C:\Users\{username}\AppData\Roaming\Sublime Text 3\Packages\User`
for windows (please change `{username}` part accordingly).

3.  - For Windows users, when PHITS is installed in `C:/phits` (which is default) no
need to change anything, because the default path is already set in files under
`win` directory. Though, if PHITS was installed in arbitrary directory, then paths
in files under `win` directory should be changed accordingly.
    - For linux users: one need to change paths (look for `{path_to_phits}`) in both `phits.sublime-build` and
`phig3d.sublime-build` files accordingly, these paths are the place with PHITS files.

After these simple steps, input files will be highlighted, and the ability to
execute PHITS input files right from the sublime will be provided.

## Some additional notes

**If one cannot see syntax highlighting:** please check if it was chosen in the
right bottom corner of sublime, for the PHITS input files it should be `PHITS input`

**Comment out option:** one can even comment out (and uncomment back) lines using
`ctrl+/` shortcut (default).

**Color scheme:** highlighting colors were developed for Monokai color scheme
(`Preferences -> Color Scheme...`). Other color schemes might look not that good.

Make sure that in `Tools → Build System` there is a `phits` option set for PHITS
run and `phig3d` option if one want to show geometry using phig3d.

`ctrl+B` is a default shortcut for build option (surely, may be different,
please look at the `Tools -> build` to make it sure). So, `ctrl+B` will launch
current PHITS input right from the sublime!

Made by Ivan Gordeev \<GN\>, 2021 for [PHITS community](https://meteor.nucl.kyushu-u.ac.jp/phitsforum/), enjoy! :blush:
