# Design

In a form of Q&A I'll try to explain design behind `compositor-settings` template repository

---

**Q**: Why are we using root config file as includes list?

**A**: When user opts for changing settings instead of 1 mono file with all settings mangled up they could open related docs page and work on settings they need to change. That's also helps with readability of whole project.

---

**Q**: Why are we pointing on files in [`README.md`](./README.md)?

**A**: When user opens repository with prefered compositor they would instantly dive into needed file, part of config.

---

**Q**: Why are we deattaching Bar/Widgets/Shells from compositors?

**A**: Instead of treating every `cachyos-compositor` repo and package as self-contained DE we are creating more flexible framework to users. They could easily opt for "dotfiles from CachyOS" with packages like `cachyos-noctalia-settings`, `cachyos-dms-settings` or `cachyos-compositor-tinted` if they are going to make thier own DE. It's a fair middle ground between ready-to-use dotfiles and compositor-only settings.

---

**Q**: Why there is `xdg-desktop-portal` config?

**A**: Sicne XDG portals differ from compositor to compositor, and Desktop Portal supports `<desktop>-portal.conf` instead of shipping monofile with all settings in it we are shipping general `xdg-desktop-portal-gtk` for compositors as ultimate fallback in `cachyos-compositor-template` and per-compositor settings per package / config. That also helps users in future to customize XDG Desktop Portals directives easily, without breaking something important in main file. Thus, it also helps maintainers update related directives without breaking main one.

## Configuring

Short guide for future maintainers in initialization of more compositors.

1. Let UWSM handle things.

UWSM have environment, uses XDG Autostart and provides much better SystemD integration with slices. With XDG Terminal Exec you don't have to specify which terminal to use - `uwsm-app -T` utilizes it.

2. Documentation.

We cannot be ultimate wiki for everything all at once. Instead we could let maintainers and creators of such compositors lead users through configuration if they opt for customization. Use comments with docs links.

3. Outputs (monitors) are not compositor job.

In `cachyos-compositor-template` we have Kanshi - it's a wonderful daemon that makes output configuration much easier and compositor-agnostic.

4. Theming is not our scope.

Theming is not univerasal. We are providing our option, or following defaults from maintainers. There is no universal solution in animations, rounding, etc. Colors are handled externally - Noctalia, DMS, Tinted or user.

## Design:

Repository `README.md` must follow certain design, described at [`TEMPLATE.md`](./TEMPLATE.md).

Repository tree must follow next logic:

```Sh
README.md
LISENCE
/etc/
-> skel/
--> .config/
---> <compositor>/
-----> config                           # imports
-----> config/                          # cfg directory
------> animations,layout,inputs,misc   # actual configurations
-----> xdg-desktop-portal/
------> <compositor>-portals.conf        # compositor's portal settings
```

Repository cannot contain anything beyond listed.

## Edge-cases

`Jay` is only example here:

1. `Jay`'s config is monolith file.
2. `Jay`'s `xdg-desktop-portal` is another edge case and does not follow logic of `wlroots` nor `smithay` compositors.

all other edge-cases could be listed here.
