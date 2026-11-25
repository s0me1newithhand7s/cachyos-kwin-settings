# cachyos-compositor-settings

<!-- List project name with short descripion here -->
<!-- [Name](link) desc. -->

Dependencies:

<!-- List compositor package name and related xdg-desktop-portal package here -->

```Sh
compositor xdg-desktop-portal-wlr
```

## Reposotiry tree

<!-- Should be [.config/compositor/](./etc/skel/.config/compositor/)  -->

### Path `.config/compositor/`:

in `config` you can find all `includes` from directory `config/`

<!-- Should be [.config/compositor/config/](./etc/skel/.config/compositor/config/)  -->

### Path `.config/compositor/config`

<!-- Should also point to and actual files via [`config`](./etc/skel/.config/compositor/config/configfile) -->

| config | purpose |
| ------ | ------- |
| `general`    | compositor's basics; mod key, xwayland         |
| `inputs`     | libinput settings; mouse, keyboard, cursor     |
| `keybinds`   | compositor's keybinds; customize to you liking |
| `workspaces` | general settings and workspaces rules;         |
| `misc`       | ungrouped settigs;                             |
              
<!-- Should be [.config/xdg-desktop/](./etc/skel/.config/compositor/config/)  -->

### Path `.config/xdg-desktop-portal/`

In `compositor-portals.conf` you can configure `xdg-desktop-portal` directives for `compositor`; Default portal already set

<br/>

Thank you for choosing CachyOS!
