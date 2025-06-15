# Minecraft FreeDesktop Integration
This repository has a `.desktop` file and an icon for Minecraft Launcher, allowing it to be integrated into Linux desktop environments. These files are taken from official Debian release.

## Edit the `.desktop` file
Before installing, edit `minecraft-launcher.desktop` to update the `Exec=` path:
```bash
vim minecraft-launcher.desktop
```
Modify this line:
```ini
Exec=/path/to/minecraft-launcher
```
## User-specific installation
```bash
mkdir -p ~/.local/share/applications/ 
mv minecraft-launcher.desktop ~/.local/share/applications/

mkdir -p ~/.local/share/icons/hicolor/symbolic/apps/
mv minecraft-launcher.svg ~/.local/share/icons/hicolor/symbolic/apps/

chmod +x ~/.local/share/applications/minecraft-launcher.desktop
update-desktop-database ~/.local/share/applications/
```
## System-wide installation
```bash
sudo mkdir -p /usr/share/applications/
sudo mv minecraft-launcher.desktop /usr/share/applications/

sudo mkdir -p /usr/share/icons/hicolor/symbolic/apps/
sudo mv minecraft-launcher.svg /usr/share/icons/hicolor/symbolic/apps/

sudo chmod +x /usr/share/applications/minecraft-launcher.desktop

sudo update-desktop-database
```
If Minecraft Launcher doesn't appear try restarting your session:
```bash
xdg-desktop-menu forceupdate
```
