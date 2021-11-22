### Download package
```bash
rsync -r -t -v --progress -u --partial -s rsync://<ServerIP>/snaps/logos9_0.1_amd64.snap .
```
or use grsync with source as: "rsync://<ServerIP>/snaps/logos9_0.1_amd64.snap"
and your preferred destination.

### Install package
```bash
sudo snap install --devmode --dangerous ./logos9_0.1_amd64.snap
```

### Run app (installs Logos and dependencies on 1st run [1.4 to 1.6 GB])
```bash
logos9
# OR
WINEDEBUG=1 SOMMELIER_DEBUG=1 logos9 # if you really want to see what's going on
```
or find it in your apps menu.

### Dependencies
#### snap packages [1072 MB]:
- logos9 [<1 MB]
  - snapd [34 MB]
  - core18 [58 MB]
  - gnome-3-28-1804 [172 MB]
    - gtk-common-themes [68 MB]
  - wine-platform-6-staging [376 MB]
  - wine-platform-runtime [363 MB]
#### wine installs [130 MB]
- corefonts (11 total) [4 MB]
- dotnet48 [120 MB] (dotNetFx40 [48 MB]+ dotNetFx48 [69 MB])
#### Logos installer [217 MB or 450 MB]
- Logos-x64.msi [217 MB or 450 MB]
  - Should be 217 MB, but nethogs reports ~450 MB.
- Snap installer will use ~/Downloads/Logos-x64.msi if it exists, otherwise it
  will download this one: https://downloads.logoscdn.com/LBS9/Installer/9.9.0.0011/Logos-x64.msi

### Debugging
Get full debugging info with these ENV variables:
```bash
WINEDEBUG=1 SOMMELIER_DEBUG=1 logos9 # if you really want to see what's going on
```
However, the sommelier script sets certain environment variables at runtime, so
it may not work to override them like this:
```bash
WINEDLLOVERRIDES= logos9
```
Another route is to skip the sommelier script and use the logos9.wine subcommand
directly:
```bash
cd ~/snap/logos9/common/.wine/drive_c/users/<user>/AppData/Local/Logos
WINEDLLOVERRIDES= logos9.wine Logos.exe
```

### logos9 snap subcommands
```bash
logos9.wine
logos9.winecfg
logos9.winetricks # CLI only. It fails if no args passed because of mis-linked yad executable
```
