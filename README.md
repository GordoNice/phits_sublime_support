# Syntax highlighting and execution of PHITS input files support for Sublime Text editor

This repo consists of files which are dedicated to provide syntax highlighting for
[PHITS](https://phits.jaea.go.jp/) input files in [Sublime Text editor](https://www.sublimetext.com/).
Additionally, it provides support for build option (execution of PHITS input files from sublime).

![](https://github.com/GordoNice/phits_sublime_support/blob/master/Screenshot.png "Screenshot with syntax highlighting")

Contents:

```
.
├── linux-macOS
│   ├── dchain.sublime-build  # file for build option of dchain)
│   ├── phig3d.sublime-build  # file for build option of phig 3d (geometry view of currently open input file)
│   └── phits.sublime-build   # file for build option (launch calculations of currently open input file)
└── win                       # same files as in "linux-nmacOS" folder, but dedicated to windows
    ├── phig3d.sublime-build
    └── phits.sublime-build
├── phits-comments.tmPreferences  # file which provides comment out option
├── phits.sublime-syntax          # file with syntax highlighting
├── README.md
```

Steps to make everything work:

1. Download all the files from the repo as a zip or via git:
   ```
   git clone https://github.com/GordoNice/phits_sublime_support.git
   ```
2. Place 5 (4 for windows) files (`phits.sublime-syntax`, `phits-comments.tmPreferences` + 3 (2 for windows)
   files from `linux`, `macOS` or `win` or  directory) in sublime config directory.
   This path is by default (for linux users):
   ```
   ~/.config/sublime-text-3/Packages/User
   ```
   or for macOS:
   ```
   /Users/{username}/Library/Application Support/Sublime Text 3/Packages/User
   ```
   and for windows users:
   ```
   C:\Users\{username}\AppData\Roaming\Sublime Text 3\Packages\User
   ```
   (please change `{username}` part accordingly).
3.  - For Windows users, when PHITS is installed in `C:/phits` (which is default)
      no need to change anything, because the default path is already set in files under
      `win` directory. Though, if PHITS was installed in arbitrary directory, then paths
      in files under `win` directory should be changed accordingly.
    - For linux and macOS users: one need to change paths (look for `{path_to_phits}`) in
      every `[name].sublime-build` file accordingly,
      these paths are the place with PHITS files.

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

Made by Ivan Gordeev, 2021 for [PHITS community](https://meteor.nucl.kyushu-u.ac.jp/phitsforum/), enjoy! :blush:
