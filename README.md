# cachyos-kwin-settings

[**KWin**](https://github.com/KDE/kwin) is KDE Plasma's compositor.

Dependencies:

```Sh
kwin xdg-desktop-portal-kde libkscreen polkit-kde-agent qt6-tools
```

## Reposotiry tree

### Path [`.config/`](./etc/skel/.config/)

KWin settings are not read from it's own directory - they are pulled from `kwin`-* / `k`-* files in `~/.config` directory.

| config | purpose |
| ------ | ------- |
| [`kwinrc`](./etc/skel/.config/kwinrc) | kwin's basics; amount of desktops, compositing |
| [`kxkbrc`](./etc/skel/.config/kxkbrc) | KDE Plasma XKB Settings; layouts, variant, compose key|
| [`kwinrulesrc`](./etc/skel/.config/kwinrulesrc) | kwin's composing rules; window rules |
| [`kglobalshortcutsrc`](./etc/skel/.config/kglobalshortcutsrc) | KDE Plasma shortcuts; laucnher, session quit |
              
### Path [`.config/xdg-desktop-portal/`](./etc/skel/.config/xdg-desktop-portal/)

KWin being KDE Plasma compositor is only compatable with `xdg-desktop-portal-kde`, declared in [`kwin-portals.conf`](./etc/skel/.config/xdg-desktop-portal/kwin-portals.conf).

### Path [`.config/autostart/`](./etc/skel/.config/autostart/)

KDE Plasma provides it's own KDE Plasma Polkit Agent. Since we are using XDG Desktop Portal from KDE we must use [`kde-polkit-agent.desktop`](./etc/skel/.config/autostart/kde-polkit-agent.desktop).

### Path [`.config/uwsm/env.d/`](./etc/skel/.config/uwsm/env.d/)

KDE Plasma sets up ceratin variables, so we are in [`env-kwin`](./etc/skel/.config/uwsm/env.d/env-kwin).

### Path [`.local/share/applications/`](./etc/skel/.local/share/applications/)

KDE Plasma starts with `startplasma-wayland` which start essential to KDE daemons.

| path | purpose |
| - | - |
| [`laucnher.desktop`](./etc/skel/.local/share/applications/launcher.desktop) | your launcher; we ship configured with noctalia |
| [`uwsm-stop.desktop`](./etc/skel/.local/share/applications/uwsm-stop.desktop) | UWSM managed grace shutdown |

`kglobalshortcutsrc` runs desktop entries on keybinds. We are shipping bare minimum for usability.

### Path [`/usr/share/wayland-sessions/`](./usr/share/wayland-sessions/)

KWin is not `kwin` as binary, nor it's an actual compositor. We are shipping `kwin-wayland` managed by UWSM in [`kwin-uwsm.desktop`](./usr/share/wayland-sessions/kwin-uwsm.desktop).

<br/>

Thank you for choosing CachyOS!
