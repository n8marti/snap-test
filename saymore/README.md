## SayMore via wine
- Makes use of wine-runtime snap and wine-platform-6-stable to minimize snap size and reduce maintenance burden.
- Downloads SayMoreInstaller.*.msi installer from SIL, unless already present in ~/Downloads.

### Dependencies
#### snap packages [953 MB]:
- saymore [<1 MB]
  - snapd [34 MB]
  - core18 [58 MB]
  - gnome-3-28-1804 [172 MB]
    - gtk-common-themes [68 MB]
  - wine-platform-6-stable [300ish MB]
  - wine-platform-runtime [363 MB]
#### wine installs [130 MB]
- corefonts (11 total) [4 MB]
- dotnet48 [120 MB] (dotNetFx40 [48 MB]+ dotNetFx48 [69 MB])
#### SayMore installer [36 MB]
- SayMoreInstaller.*.msi [36 MB]
- Snap installer will use ~/Downloads/SayMore.*.msi if it exists, otherwise it
  will download this one: https://software.sil.org/downloads/r/saymore/SayMoreInstaller.3.2.22.msi
