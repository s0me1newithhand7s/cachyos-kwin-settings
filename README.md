# cachyos-compositor-settings

General settings for Wayland compositors.

Dependencies:

```Sh
adw-gtk-theme
kitty
qt6ct
xdg-desktop-portal
bibata-cursor-theme
uwsm
thunar
noto-fonts
noto-fonts-emoji
gnome-keyring
xdg-desktop-portal-gtk
xdg-terminal-exec
kanshi
```

## Reposotiry tree

### Path [`.config/autostart/`](./etc/skel/.config/autostart/)

| config | purpose |
| - | - |
| [kanshi.desktop](./etc/skel/.config/autostart/kanshi.desktop) | UWSM managed XDG Autostart for Kanshi daemon |
| [noctalia.desktop](./etc/skel/.config/autostart/noctalia.desktop) | UWSM managed XDG Autostart for Noctalia Shell |
| - | - |

1. `kanshi` is universal Wayland monitors and profiles managing daemon.
2. `nocatalia` is Wayland widgets framework. Same as `kanshi`.

You can write your own `.desktop` file with lesser amount of lines, this files are references for "best case scenario".

You can make their `systemd` service override in `.config/systemd/user/app-<name>@autostart.service.d/slice.conf`. We do not provide overrides for sake of compatability.

### Paths [`.config/gtk-3.0/`](./etc/skel/.config/gtk-3.0/) and [`.config/gtk-4.0/`](./etc/skel/.config/gtk-4.0/)

Both setting.ini are looks of `GTK` apps, hence versioned 3.0 and 4.0.

### Path  [`.config/kanshi/`](./etc/skel/.config/kanshi/)

Kanshi is a Wayland Displays and Profiles Manager. [This](./etc/skel/.config/kanshi/config) conifg file contains default profile and catch-all preset for prefered display settings.

### Path [`.config/kitty/`](./etc/skel/.config/kitty)

Kitty is GPU based feature-rich terminal emulator. [`Config`](./etc/skel/.config/kitty/kitty.conf) contains few config lines since `kitty` does not require much of configuration.

### Path [`.config/uwsm/env.d/`]

UWSM also manages proper `environment` exporting. [`Env`](./etc/skel/.config/uwsm/env.d/env/) makes it easier to deattach all the environments from compositors and also follows logic of basic `env` files.

### Path [`.config/xdg-desktop-portal/`](./etc/skel/.config/xdg-desktop-portal/)

XDG Desktop Portal directive. Contains [`portals.conf`](./etc/skel/.config/xdg-desktop-portal/portals.conf) with default `gtk` portal as fallback and no `impl`. With installed compositors you gonna have `<compositor>-portals.conf` for per-compositor settings.

### Path [`.config/xdg-terminals.list`](./etc/skel/.config/xdg-terminals.list)

XDG Terminal Exec directive. UWSM uses it for `uwsm-app -T` and `Terminal=true` in `.desktop` entries. You can list / remove your prefered terminal ot use, `list` scans for desktop entry of listed terminal before starting one.

### Path [`.config/mimeapps.list`](./etc/skel/.config/mimeapps.list)

MIME apps is XDG Specification on default apps per MIME type. Currently listed only `Thunar` as File Manager. you can use `xdg-open` for both querying and opening with listed MIME apps.

<br/>

Thank you for choosing CachyOS!

