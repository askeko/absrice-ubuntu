# Installation info

## nvim
!!!Install listed apt packages first
* git clone https://github.com/neovim/neovim
* cd neovim
* git checkout stable
* make CMAKE_BUILD_TYPE=RelWithDebInfo
* cd build && cpack -G DEB && sudo dpkg -i nvim-linux64.deb

## apt install
* zsh
* bat
* exa
* python3-pip
* texlive-full
* flatpak

### nvim dep
* gcc
* cmake
* git
* ninja-build
* gettext
* unzip
* curl
* xclip
* fzf
* ripgrep
* fd-find
* g++

#### manual install
LAZYGIT_VERSION=$(curl -s "https://api.github.com/repos/jesseduffield/lazygit/releases/latest" | grep -Po '"tag_name": "v\K[^"]*')
curl -Lo lazygit.tar.gz "https://github.com/jesseduffield/lazygit/releases/latest/download/lazygit_${LAZYGIT_VERSION}_Linux_x86_64.tar.gz"
tar xf lazygit.tar.gz lazygit
sudo install lazygit /usr/local/bin
rm lazygit.tar.gz
rm -rf lazygit

### bspwm dep
* libxcb-xinerama0-dev
* libxcb-icccm4-dev
* libxcb-randr0-dev
* libxcb-util0-dev
* libxcb-ewmh-dev
* libxcb-keysyms1-dev
* libxcb-shape0-dev
* feh
* dunst
* arandr
* onboard
* polybar
* maim
* xdotool

### slock dep
* libxrandr-dev

## git
### bspwm
* git clone https://github.com/baskerville/bspwm.git
* git clone https://github.com/baskerville/sxhkd.git
* cd bspwm && make && sudo make install
* cd ../sxhkd && make && sudo make install
* configs in .config/bspwm and .config/sxhkd
* remember to make executable: chmod u+x ~/.config/bspwm/bspwmrc

### slock
* git clone https://git.suckless.org/slock
* cd slock && sudo make clean install

## misc
### screentearing
* Fix screentearing see https://github.com/askeko/Arch-Linux-log_04/blob/main/post-installation.md#integrated-amd-gpu--screen-tearing-fix

### font
* https://github.com/ryanoasis/nerd-fonts/releases/download/v3.0.2/FiraCode.zip
* extract and cp to /usr/share/fonts
* fc-cache --force

### term
* curl -LO https://github.com/wez/wezterm/releases/download/20230712-072601-f4abf8fd/wezterm-20230712-072601-f4abf8fd.Ubuntu22.04.deb
* sudo apt install -y ./wezterm-20230712-072601-f4abf8fd.Ubuntu22.04.deb

### zsh
* chsh -s $(which zsh)
* mkdir .cache/zsh
* git clone https://github.com/zdharma-continuum/fast-syntax-highlighting ~/.local/bin/fast-syntax-highlighting/

### bat
Conflict with another package when installed through apt, add symlink
* ln -s /usr/bin/batcat ~/.local/bin/bat
Update cache
* bat cache --build

### Discord
* get deb and install: https://discord.com/download

### Spotify
* curl -sS https://download.spotify.com/debian/pubkey_7A3A762FAFD4A51F.gpg | sudo gpg --dearmor --yes -o /etc/apt/trusted.gpg.d/spotify.gpg
* echo "deb http://repository.spotify.com stable non-free" | sudo tee /etc/apt/sources.list.d/spotify.list
* sudo apt-get update && sudo apt-get install spotify-client

### rnote
* install flathub: https://flathub.org/setup/Ubuntu
* install rnote: https://flathub.org/apps/com.github.flxzt.rnote
* Add executable: sudo ln -s /var/lib/flatpak/exports/bin/com.github.flxzt.rnote /usr/bin/rnote

### Obsidian
Install deb: https://github.com/obsidianmd/obsidian-releases/releases/download/v1.3.7/obsidian_1.3.7_amd64.deb

### Caps to escape
Set the following in .profile: `setxkbmap -option caps:escape`

## Dev
### nvm
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.4/install.sh | bash >/dev/null 2>&1
source ~/.zprofile

#### node
nvm install node

### rustup / rust
curl --proto '=https' --tlsv1.2 -sSf https://sh.rustup.rs | sh
* !!! prompt enter "1"

### vscode
Download from https://code.visualstudio.com/docs/?dv=linux64_deb and install with apt
Add `"password-store":"gnome"` to Preferences: Configure Runtime Arguments using ctrl+shift+P

### Prompt
curl -sS https://starship.rs/install.sh | sh
* !!! prompt enter "y"

# todo
* keyboard
* multi monitor
