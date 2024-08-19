# Arch install guide of all
Without arch wiki, just this file.

## archlinux system install
- disk configuration: 1G-EFI, 400G-/home, test-/root(/)
- extra package: neovim, fish

## user using sudo without passwd
- add `Defaults:(user_name) !authenticate` in `/etc/sudoers`, must use `sudo` open file

## set default shell
- use fish as default shell
- find fish file path, `chsh -l`
- `chsh -s (fish.path)`

## set archlinuxcn
- `sudo nvim /etc/pacman.config`, in last row add
```
[archlinuxcn]
Server = https://mirrors.tuna.tsinghua.edu.cn/archlinuxcn/$arch
```
- `sudo pacman -Syu`
Then download $linuxqq^AUR$, chromium, clash-verge which allow get information on Internet.

## Chinese fonts
Default linux can't display Chinese, need install extra package including Chinese.
- package: adobe-source-han-sans-cn-fonts

---------
The following contents are in no particular order

## chromium extensions
- vimium: Vimium provides keyboard shortcuts for navigation and control in the spirit of Vim.
- Gnome Shell integration: For Arch Linux, Debian, Fedora, Gentoo and Ubuntu you can install package named "gnome-browser-connector".

## fonts in terminal
- `sudo pacman -S ttf-fira-code`

## terminal alacritty configuration
(config url)[https://alacritty.org/config-alacritty.html]
```toml
[shell]
program = "/usr/bin/fish"

[window]
dimensions = {columns = 169, lines = 60}
opacity = 0.7
startup_mode = "Windowed"

[font]
normal = { family = "Fira Code", style = "normal"}
size = 14.5

[colors.primary]

background = "#282a36"
foreground = "#f8f8f2"
bright_foreground = "#ffffff"

[colors.cursor]

text = "#282a36"
cursor = "#f8f8f2"

[colors.vi_mode_cursor]

text = "CellBackground"
cursor = "CellForeground"

[colors.selection]

text = "CellForeground"
background = "#44475a"

[colors.normal]

black = "#21222c"
red = "#ff5555"
green = "#50fa7b"
yellow = "#f1fa8c"
blue = "#bd93f9"
magenta = "#ff79c6"
cyan = "#8be9fd"
white = "#f8f8f2"

[colors.bright]

black = "#6272a4"
red = "#ff6e6e"
green = "#69ff94"
yellow = "#ffffa5"
blue = "#d6acff"
magenta = "#ff92df"
cyan = "#a4ffff"
white = "#ffffff"

[colors.search.matches]

foreground = "#44475a"
background = "#50fa7b"

[colors.search.focused_match]

foreground = "#44475a"
background = "#ffb86c"

[colors.footer_bar]

background = "#282a36"
foreground = "#f8f8f2"

[colors.hints.start]

foreground = "#282a36"
background = "#f1fa8c"

[colors.hints.end]

foreground = "#f1fa8c"
background = "#282a36"
```

