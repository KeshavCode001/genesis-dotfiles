# Genesis Dotfiles

A personalized Arch Linux Hyprland setup based on 43PR. It includes a wallpaper-driven theme, a choice of Waybar or the Pocket Dots notch, a Rofi launcher and wallpaper picker, and an animated in-session lock screen.

| Lock screen | Expanded dashboard |
| --- | --- |
| ![Lock screen with the blurred sample wallpaper](assets/screenshots/lock-screen.png) | ![Lock-screen dashboard with media controls and system readings](assets/screenshots/lock-dashboard.png) |

The lock-screen screenshots use a sample wallpaper and the configuration in this repository. [Original 43PR desktop preview](assets/desktop.png).

## Installation

This setup targets Arch-based systems with a Hyprland version that supports Lua configuration. Run the installer as your normal desktop user. It uses sudo for package operations and backs up existing files that it replaces.

### One-line install

```bash
git clone https://github.com/KeshavCode001/genesis-dotfiles.git "$HOME/genesis-dotfiles" && bash "$HOME/genesis-dotfiles/install.sh"
```

Run this on an Arch-based system with Git installed. The installer links files from `configs/` into `~/.config` and keeps backups under `~/.config-backups/`. Keep the checkout in place after installation. To inspect the setup first, download or clone the repository, review [packages.txt](packages.txt), then run [install.sh](install.sh) yourself.

Log out and back into Hyprland when the installer finishes. Press **Super + W** to choose a wallpaper, **Super + I** for Settings, and **Super + F10** to swap Waybar and the notch.

For a component-only installation, back up its existing folder and copy or link the matching files from [configs/](configs/). Use the [optional SDDM notes](sddm/README.md) to install the greeter separately.

## Config folders

| Path | Contents |
| --- | --- |
| [`configs/hypr/`](configs/hypr/) | Hyprland Lua, binds, rules and desktop scripts |
| [`configs/43pr/`](configs/43pr/) | Theme controller, preset palettes and application templates |
| [`configs/quickshell/`](configs/quickshell/) | Settings, notifications, power menu and other desktop components |
| [`configs/quickshell/pocketisland/`](configs/quickshell/pocketisland/) | Optional Pocket Dots notch and control center |
| [`configs/quickshell/nebulalock/`](configs/quickshell/nebulalock/) | In-session lock screen and unlock animation |
| [`configs/waybar/`](configs/waybar/) | Bar layout, modules, CSS and configuration generator |
| [`configs/rofi/`](configs/rofi/) | Launcher theme shared by the wallpaper picker |
| [`configs/matugen/`](configs/matugen/) | Wallpaper palette generation |
| [`configs/kitty/`](configs/kitty/) | Kitty terminal and theme integration |
| [`configs/.zshrc`](configs/.zshrc) | Zsh shell configuration |
| [`configs/starship.toml`](configs/starship.toml) | Starship prompt |
| [`configs/fontconfig/`](configs/fontconfig/) | Desktop font preferences |
| [`configs/systemd/user/`](configs/systemd/user/) | Optional desktop Pokémon services |
| [`extras/pokemon/`](extras/pokemon/) | Optional desktop Pokémon setup and tools |
| [`sddm/`](sddm/) | Optional wallpaper-sync and animation patch for the Astronaut greeter |

Terminal, shell, font and other application settings are grouped by application under [`configs/`](configs/).

## Keybinds

| Default | Action |
| --- | --- |
| Super + T / E / B | Terminal / file manager / browser |
| Super + D / V | Application launcher / clipboard |
| Super + Q | Close the focused window |
| Super + F / Space | Fullscreen / toggle floating |
| Super + 1–0 | Switch workspace |
| Super + Shift + 1–0 | Move window to workspace |
| Super + H/J/K/L | Focus window in a direction |
| Super + Shift + H/J/K/L | Move window in a direction |
| Super + Ctrl + H/J/K/L | Resize window |
| Super + left/right mouse drag | Move / resize window |
| Super + I / S / C | Settings / side panel / notes |
| Super + W | Wallpaper picker |
| Super + Shift + W | Hide or show the current bar |
| Super + F10 | Switch Waybar and Pocket Dots |
| Super + O / . | Opacity selector / toggle light and dark |
| Super + Shift + C | Color picker |
| Super + Tab / Grave | Session lock / power menu |
| Super + X / M | Cycle keyboard layout / toggle microphone mute |
| Super + R | Toggle recording |
| Delete / Shift + Delete | Full / area screenshot |
| Shift + F12 | Area OCR |
| Super + Shift + E | Exit Hyprland |

Edit supported shortcuts in **43PR Settings → Keybinds**. See [keybinds.lua](configs/hypr/keybinds.lua) for the full source. The session locker uses the `hyprlock` PAM service from the hyprlock package.

## Credits and licenses

Based on [43PR/dotfiles](https://github.com/43PR/dotfiles). The notch and optional Pokémon tools come from [Pocket Dots](https://github.com/diegoMalagrida/pocket-dots); the lock screen draws on [Nebula](https://github.com/LilaccFlowerr/Nebula). Waybar and Rofi styling draw on [binnewbs/arch-hyprland](https://github.com/binnewbs/arch-hyprland). The wallpaper picker builds on [hyprquickpaper](https://github.com/iamsurjog/hyprquickpaper). The optional greeter patch targets [SDDM Astronaut](https://github.com/Keyitdev/sddm-astronaut-theme).

See [LICENSE](LICENSE) and the component licenses in [Pocket Dots](configs/quickshell/pocketisland/LICENSE), [Nebula](configs/quickshell/nebulalock/LICENSE), and [Pokémon tools](extras/pokemon/LICENSE). Upstream artwork remains credited to its respective creators.

