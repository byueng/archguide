# Arch install guide of all
Without arch wiki, just this file.

## archlinux system install
- **disk configuration**: 1G-EFI, 400G-/home, test-/root(/)
- **extra package**: neovim, fish

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
- **vimium**: Vimium provides keyboard shortcuts for navigation and control in the spirit of Vim.
- **Gnome Shell integration**: For Arch Linux, Debian, Fedora, Gentoo and Ubuntu you can install package named "gnome-browser-connector".

## fonts in terminal
`sudo pacman -S ttf-fira-code`

## terminal alacritty configuration
[config url](https://alacritty.org/config-alacritty.html)
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


## vscodium setting
vscodium use the same setting logic as vscode,[vscode setting url](https://code.visualstudio.com/docs/getstarted/settings#_settingsjson)

```json
{
    
    "editor.fontSize": 14.5,
    "editor.fontFamily": "Fira Code",
    "workbench.colorTheme": "Dracula Theme",
    "background.enabled": true,
    "background.fullscreen": {
        "images": ["https://yys.res.netease.com/pc/zt/20230421141009/data/picture/20200609/3/2/1920x1080.jpg"], // urls of your images
        "opacity": 0.95, // 0.85 ~ 0.95 recommended
        "size": "cover", 
        "position": "center",
    }
    // variable background need extension background
}

```

### extensions(something like python isn't be needed)
- **Dracula Theme Official**: color theme
- **Markdown Preview Github Styling**: preview md file in vscode
- **background**: display background in vscode

## Gnome extension(OS beauty)
Using extensions application and install `gnome-browser-connector`

extensions list:
- **AppIndicator and KStatusNotifierItem Support**: Adds AppIndicator, KStatusNotifierItem and legacy Tray icons support to the Shell
- **Dash to Dock**: 在外观栏中将透明度调整为50%
- **Coverflow Alt-Tab**
- **Blur my Shell **
- **Search Light**: This is a Gnome Shell extension that takes the apps search widget out of Overview
- **Hide the dock in overview**: hide the overview list when *cmd*



## bluetooth service
When I want to connect my bluetooth, I can't turn on the switch that it will turn back to off if I turn on it.

<video src="https://itsfoss.com/content/media/2023/11/cant-enable-bluetooth-arch-linux.webm" poster="https://img.spacergif.org/v1/1920x1080/0a/spacer.png" width="1920" height="1080" loop="" autoplay="" muted="" playsinline="" preload="metadata" style="background: transparent url('https://itsfoss.com/content/media/2023/11/cant-enable-bluetooth-arch-linux_thumb.jpg') 50% 50% / cover no-repeat;"></video>

>tips: markdown supports HTML language, in many place can find the same display using HTML as markdown. And some special things such as video which only can writed by HTML


## Tools 
- **[catppuccin](https://github.com/catppuccin)**: contains all themes which I want, good tools! 