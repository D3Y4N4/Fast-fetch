Code-Style Fastfetch Configuration

A minimal C/C++ pseudo-code configuration layout for Fastfetch.

Preview

01  system() { {#}
02    operatingSystem   = "Arch Linux"
03    kernelVersion     = "7.2.8-arch1-2"
04    systemUptime      = "8d, 2h, 25m"
05    currentTime       = "13:57:IST"
06    installedPackages = "844 (pacman)"
07  }
08  
09  hardware() { {#}
10    motherboard       = "LNVNB161216"
11    processor         = "AMD Athlon Silver 3050U"
12    graphics          = "Radeon Vega Series / Radeon Vega Mobile Series"
13    memory            = "4.97 GiB / 13.52 GiB"
14    storage           = "35.80 GiB / 232.69 GiB - ext4"
15  }
16  
17  // I Love all the colors mixed Together -BLACK


Configuration (~/.config/fastfetch/config.jsonc)

{
  "$schema": "https://github.com/fastfetch-cli/fastfetch/raw/dev/doc/json_schema.json",
  "logo": {
    "type": "kitty",
    "source": "~/.config/fastfetch/logo.png",
    "width": 25,
    "height": 12,
    "padding": {
      "right": 4
    }
  },
  "display": {
    "separator": " = ",
    "color": {
      "keys": "magenta",
      "output": "magenta"
    }
  },
  "modules": [
    {
      "type": "custom",
      "format": "{#magenta}01  system() { {#}{#}"
    },
    {
      "type": "os",
      "key": "02    operatingSystem  ",
      "keyColor": "magenta",
      "format": "\"{\u001b[35m}{pretty-name}{\u001b[0m}\""
    },
    {
      "type": "kernel",
      "key": "03    kernelVersion    ",
      "keyColor": "magenta",
      "format": "\"{\u001b[35m}{release}{\u001b[0m}\""
    },
    {
      "type": "uptime",
      "key": "04    systemUptime     ",
      "keyColor": "magenta",
      "format": "\"{\u001b[35m}{days}d, {hours}h, {minutes}m{\u001b[0m}\""
    },
    {
      "type": "datetime",
      "key": "05    currentTime      ",
      "keyColor": "magenta",
      "format": "\"{\u001b[35m}{hour}:{minute}:{time-zone-name}{\u001b[0m}\""
    },
    {
      "type": "packages",
      "key": "06    installedPackages",
      "keyColor": "magenta",
      "format": "\"{\u001b[35m}{all} (pacman){\u001b[0m}\""
    },
    {
      "type": "custom",
      "format": "{#magenta}07  }{#}"
    },
    {
      "type": "custom",
      "format": "{#magenta}08{#}"
    },
    {
      "type": "custom",
      "format": "{#magenta}09  hardware() { {#}{#}"
    },
    {
      "type": "board",
      "key": "10    motherboard      ",
      "keyColor": "magenta",
      "format": "\"{\u001b[35m}{name}{\u001b[0m}\""
    },
    {
      "type": "cpu",
      "key": "11    processor        ",
      "keyColor": "magenta",
      "format": "\"{\u001b[35m}{name}{\u001b[0m}\""
    },
    {
      "type": "gpu",
      "key": "12    graphics         ",
      "keyColor": "magenta",
      "format": "\"{\u001b[35m}{name}{\u001b[0m}\""
    },
    {
      "type": "memory",
      "key": "13    memory           ",
      "keyColor": "magenta",
      "format": "\"{\u001b[35m}{used} / {total}{\u001b[0m}\""
    },
    {
      "type": "disk",
      "key": "14    storage          ",
      "keyColor": "magenta",
      "format": "\"{\u001b[35m}{used} / {total} - {filesystem}{\u001b[0m}\""
    },
    {
      "type": "custom",
      "format": "{#magenta}15  }{#}"
    },
    {
      "type": "custom",
      "format": "{#magenta}16{#}"
    },
    {
      "type": "custom",
      "format": "{#30}17  // I Love all the colors mixed Together -BLACK{#}"
    }
  ]
}


Installation

Arch Linux

sudo pacman -S fastfetch


Ubuntu / Debian

For Ubuntu 24.04 LTS and newer:

sudo apt update
sudo apt install fastfetch


For older Ubuntu versions, use the official PPA:

sudo add-apt-repository ppa:zhangsongcui3371/fastfetch
sudo apt update
sudo apt install fastfetch


Fedora

sudo dnf install fastfetch


Void Linux

sudo xbps-install -S fastfetch


Alpine Linux

sudo apk add fastfetch


Gentoo

sudo emerge --ask app-misc/fastfetch


Setup Instructions

1. Create Directory & Configuration

Create the fastfetch configuration directory if it does not already exist:

mkdir -p ~/.config/fastfetch


Copy config.jsonc into your directory:

cp config.jsonc ~/.config/fastfetch/config.jsonc


2. Configure Image Logo

Place your desired image (e.g., logo.png) inside ~/.config/fastfetch/.

Ensure your terminal emulator supports image rendering (Kitty, WezTerm, Ghostty, Foot, etc.).

Update the logo block in ~/.config/fastfetch/config.jsonc to point to ~/.config/fastfetch/logo.png.

Usage

Run Fastfetch in your terminal:

fastfetch


To automatically run Fastfetch upon opening a terminal, add fastfetch to your shell profile (~/.bashrc, ~/.zshrc, or ~/.config/fish/config.fish).
