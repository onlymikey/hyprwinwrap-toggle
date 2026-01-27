# hyprwinwrap-toggle

A maintained fork of **hyprwinwrap** for Hyprland that lets you run a Wayland app as an animated wallpaper **and toggle its interactivity** on demand.

**Dispatch:**
```bash
hyprctl dispatch hyprwinwrap_toggle
```

> Use-case: a “lofi wallpaper app” that is usually non-interactive, but can be toggled to accept input when you want.

---

## Features

* Run a windowed Wayland app as a wallpaper-like background surface
* Toggle input/interactivity at runtime with a Hyprland dispatch
* Focused on staying usable with recent Hyprland versions

---

## Install

### Install with `hyprpm`

1. Update plugin headers:

```bash
hyprpm update
```

2. Add this repository:

```bash
hyprpm add https://github.com/onlymikey/hyprwinwrap-toggle
```

3. Enable the plugin:

```bash
hyprpm enable hyprwinwrap-toggle
```

See the Hyprland plugins wiki and `hyprpm -h` for more details:

* [https://wiki.hyprland.org/Plugins/Using-Plugins/#installing--using-plugins](https://wiki.hyprland.org/Plugins/Using-Plugins/#installing--using-plugins)

---

## Configuration

See the upstream-style configuration options here:

* `hyprwinwrap/README.md`

### Toggle interactivity

```bash
hyprctl dispatch hyprwinwrap_toggle
```

---

## Nix

Nix support is not currently documented. Contributions are welcome.

---

## Notes / Troubleshooting

* If tiled windows don’t render the wallpaper app correctly, try disabling Hyprland’s blur “new optimizations”:

  * Set `new_optimizations = false` in the blur section of `hyprland.conf`.
* If you use Waybar and it gets covered by the wallpaper app, set the wallpaper window layer to `top`.

---

## Credits

* Original project: **hyprwinwrap** (upstream authors and contributors)
* This fork focuses on maintenance and runtime interactivity toggling.
