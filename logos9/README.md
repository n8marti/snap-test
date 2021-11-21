### Download package
```bash
rsync -r -t -v --progress -u --partial -s rsync://<ServerIP>/snaps/logos9_0.1_amd64.snap .
```
or use grsync with source as:
rsync://<ServerIP>/snaps/logos9_0.1_amd64.snap
and your preferred destination.

### Install package
```bash
sudo snap install --devmode --dangerous ./logos9_0.1_amd64.snap
```

### Run app (installs Logos and dependencies on 1st run [1.4 to 1.6 GB])
```bash
logos9
```
or find it in your apps menu.

#### snap packages [1072 MB]:
- logos9 [<1 MB]
  - snapd [34 MB]
  - core18 [58 MB]
  - gnome-3-28-1804 [172 MB]
    - gtk-common-themes [68 MB]
  - wine-platform-6-staging [376 MB]
  - wine-platform-runtime [363 MB]
#### wine installs [130 MB]
- corefonts [10 MB]
- dotnet48 (dotNetFx40 + dotNetFx48) [120 MB]
#### Logos installer [217 MB or 450 MB]
- Logos-x64.msi [217 MB or 450 MB]
  - Should be 217 MB, but nethogs reports ~450 MB.
- Snap installer will use ~/Downloads/Logos-x64.msi if it exists, otherwise it
  will download this one: https://downloads.logoscdn.com/LBS9/Installer/9.9.0.0011/Logos-x64.msi
