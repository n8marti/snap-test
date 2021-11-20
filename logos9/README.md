## Installs needed on 1st run [1.4 to 1.6 GB]:
### snap packages [1072 MB]:
- logos9 [<1 MB]
  - snapd [34 MB]
  - core18 [58 MB]
  - gnome-3-28-1804 [172 MB]
    - gtk-common-themes [68 MB]
  - wine-platform-6-staging [376 MB]
  - wine-platform-runtime [363 MB]
### wine installs [130 MB]
- corefonts [10 MB]
- dotnet48 (dotNetFx40 + dotNetFx48) [120 MB]
### Logos installer [217 MB or 450 MB]
- Logos-x64.msi [217 MB or 450 MB]
  - Should be 217 MB, but nethogs reports ~450 MB.
- Snap installer will use ~/Downloads/Logos-x64.msi if it exists, otherwise it
  will download this one: https://downloads.logoscdn.com/LBS9/Installer/9.9.0.0011/Logos-x64.msi
