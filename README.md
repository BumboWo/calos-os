<p align="center">
<img width="697" height="564" alt="editme" src="https://github.com/user-attachments/assets/05789ba6-3832-400f-995e-082534f3ab7d" />  
</p>


# calOS Hyprland Starter
CalOS is a pre-configured, desktop-friendly, Arch+Hyprland starter setup that strives to be both feature-rich, yet minimalist; a blank template that the user can build on top of (and it also looks really cool). CalOS started as a fork of Omarchy when it first released, using the theme engine it shipped with alongside Walker's dmenu. Since then Omarchy has grown more and more bloated, while CalOS has done the opposite (less than 575 packages on a complete install)! **Note: This is only for experienced Arch Linux users. You must do all system maintenence on your own.** This OS is basically vanilla Arch Linux with Hyprland + themes. **calOS (and its installer) has been tested on both AMD (9070XT) and NVIDIA (3070) hardware. It should work on your system; if not, create an issue.**

CalOS is comprised of 3 main _parts_. The first is Arch Linux + Hyprland, with a hefty amount of intelligent, yet configurable, keybinds/defaults. Walker interacts with your system through launching applications and its extensive dmenu support. A customized Mechabar (waybar) helps monitor your system as well interact with your hyprland configuration. As aforementioned, this is primarily a desktop-friendly configuration. Features such as battery monitoring, lockscreens and power profiles (performance all the way) are not present by default. Feel free to add them if you want, it's your PC after all.

tl;dr its dotfiles baby
<p align="center">
<img width="3440" height="1440" alt="image" src="https://github.com/user-attachments/assets/90e38647-dd65-407b-90ee-3639d1078d50" />
</p>

### Who is calOS for?

CalOS is directed to primarily desktop users who have some familiarity with Arch Linux and wanted to try their hand at Hyprland. It ships with very gaming-friendly defaults (Steam especially) with a high amount of configurability. Productivity is not the main goal, functionality is. If you use your desktop PC as a glorified web browser, gaming machine or social outlet, calOS is for you. You can always add on whatever else you like, but at its base default configuration, calOS is simply a really nice Hyprland skin designed to be as bare as possible so you can add your own flair. **This is essentially a starter kit for your foray into Hyprland.**

## Overview

### System

* A custom hyprland.conf file with numerous keybinds and configurations.
  - Most keybinds should just *make sense*, such as Super + B launching your Browser. For a full list refer to the keybindings.conf file in ~/.config/hypr, or use `SUPER + K` to bring up a custom dmenu showcasing all keybindings currently active. Important bindings are:
  - Super + Escape to bring up your Walker dmenu for system features (toggle system settings, power menu, app launcher).
  - Super + Space shows your application launcher.
  - Super + Enter for your terminal (Alacritty).
  - Super + S for System Monitoring (btop++).
  - Super + N for Neovim.
  - Super + Y for Yazi (file manager).
  - Super + Q to close the active window.
* `SUPER + CTRL` brings up all of your system management keybinds. The binds below assume you are already holding down SUPER + CTRL.
```
 + L enables up your screensaver.
 + N will toggle hyprsunset (bluelight filter go to sleep).
 + W will toggle waybar on/off.
 + C shows your clipboard history (clipse).
 + B changes your backgroun.
 + S launches walker's dmenu, specifically for power options.
 + I shows internet settings (impala).
 + T is your theme menu. Refer to the style section below.
```
* `SUPER + SHIFT` are the browser-based keybinds. Refer to the keybindings.conf file in your ~/.config/hypr folder to easily change them. By default they open up popular webpages.
* Gaming friendly. Check out the `games.conf` file in your hyprland config folder to see all features. Notable features include a toggle for `game mode` that enables various features such as keybind disables (so you don't have to worry about launching unwanted keybinds while gaming) abd discord pass-through for push to talk globally. Defaults for launchers/steam are already included as well as a special workspace for games (`SUPER + G`).
* A highly configurable systemd service that launches on your **first terminal only** each login. Want to run certain startup scripts/display your cringe-inducing fastfetch configuration on the first terminal? Now you can! Once the first terminal launches a service begins that prevents it from launching again afterwards. 


### Style

<details>
<summary>Sexy Theme Switching Example</summary>

https://github.com/user-attachments/assets/07587456-a2ed-4ae3-8ec3-8985569445b8

</details>

Many, many, many (autistic) hours were spent tweaking each theme CalOS ships with to compliment the entire OS. Your waybar, audio visualizer, terminal and system monitoring tools will all change based on the theme you're feeling. This took so long you son of a bitch you better use this feature

<p align="center">
<img width="3440" height="1440" alt="image" src="https://github.com/user-attachments/assets/6b212088-7e7b-4a73-aea7-413f2f004816" />
<img width="3440" height="1440" alt="image" src="https://github.com/user-attachments/assets/c4a07c54-fd81-4713-b5a3-f6bbe4f7a10a" />
<img width="3440" height="1440" alt="image" src="https://github.com/user-attachments/assets/e0c7e999-cfa9-46d4-84dd-7ba250ae107f" />
</p>



This is a pretty decent spot to talk about how to interact with the operating system as a whole.
  - Workspace 1 is always active, even if it's blank (this allows you to scroll through it even if there are no windows currently active).
  - Workspace 2 deals with system interaction. Your btop++ lives here, as does an interactive terminal. CAVA (your audio visualizer) and cmus (tui-based music player) included.
  - Workspace 3 is your gaming stuff. Discord. Steam.
  - Workspace 4 and 5 are empty by default. Unlike workspace 1, these are de-activated until you switch to them.
  - User SUPER + 1, 2, 3, etc. to switch to a specific workspace. Hold SUPER + SHIFT + [NUMBER] to move the current active window to [NUMBER] workspace.

### Defaults

Trying to distance itself from various *opinionated* setups, calOS ships with as few defaults as possible. These include: Firefox (web browser), Alacritty (terminal), Steam (if chosen by the installer), Neovim (with customized lazygit) and Yazi (file manager).
* calOS utilizes sensible, lightweight defaults, with as little dependencies as possible. These include pqiv (image viewer, full yazi compatability), clipse (clipboard history), zoxide (`cd` upgrade), Pinta (simple image editor), cmus (terminal-based music player) and various TUI applications to manage system settings (bluetui/impala).
* **Open your system settings (SUPER + ESCAPE) and navigate to System -> Packages to see what is installed.** Remove whatever you dislike from there.

# Installation and Configuration

## How 2 Install

**You must have a fresh Arch install going into this.** Feel free to use any settings you want; from disk encryption to file system type. **Limine is heavily encouraged to be used as your bootloader as the installer enables extra features if it detects it.** Other bootloaders will function just fine, however. The only required settings are a **user with root** (which you should be using anyway, you dummy) and **pipewire to be installed**. 

```
sudo pacman -S git
```
Install git to clone the repository into the specified directory.

Create your directories:
```
mkdir -pv ~/.local/share
cd ~/.local/share
```

From there, clone this repository:

```
git clone https://github.com/criticalart/calos
```
Then `cd` into /calos/ and run `./install.sh.` Wow crazy. 

## Post Installation

* It is imperative that you familiarize yourself with your new system. One of the best ways is to look through the various configuration files.
* If you are a lazy sack of shit just read through the ~/.config/hypr configuration files as those are what you use to interact with your system.

## Why Paru?

* its better just try it don't be a bitch
