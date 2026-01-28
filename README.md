
# hyprwinwrap-toggle

A **maintained fork of `hyprwinwrap`** for Hyprland that lets you run a Wayland app as an animated wallpaper **and toggle its interactivity at runtime**.

Designed for setups like **idle / ambient wallpaper apps** that should normally behave like a background, but can temporarily receive input when needed.

---

## Features

* Run a windowed Wayland app as a wallpaper-like background surface
* Toggle input / interactivity at runtime via a Hyprland dispatcher
* Compatible with recent Hyprland releases
* Drag & drop, mouse and keyboard input supported when interactable

---

## Install

### Using `hyprpm`

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

For more details, see:

* [https://wiki.hyprland.org/Plugins/Using-Plugins/#installing--using-plugins](https://wiki.hyprland.org/Plugins/Using-Plugins/#installing--using-plugins)
* `hyprpm -h`

---

## Dispatch

```bash
hyprctl dispatch hyprwinwrap_toggle
```

This toggles input handling for all managed background windows.

---

## Configuration

Configuration follows the **original `hyprwinwrap` semantics**.

See upstream-style options here:

```
hyprwinwrap/README.md
```

Typical usage is matching a window by `class` or `title` and letting the plugin manage it as a background surface.

---

## Toggling interactivity

Example keybind:

```ini
bind = SUPER, L, exec, hyprctl dispatch hyprwinwrap_toggle
```

When disabled, the window behaves like a wallpaper.
When enabled, the window accepts mouse and keyboard input normally.

---

## Nix

Nix support is **not documented yet**.

If you are a Nix user and want to contribute:

* PRs are welcome
* Keep the scope focused (build + install only)

---

## Notes / Troubleshooting

* If tiled windows fail to render the wallpaper correctly:

  * Disable Hyprland blur “new optimizations”:

    ```ini
    decoration {
      blur {
        new_optimizations = false
      }
    }
    ```

* If Waybar or other layer-shell surfaces are covered:

  * Ensure the wallpaper window uses `layer = top`
  * Or hide Waybar on the monitor where the wallpaper app runs

---

## Scope & Support

This fork **intentionally limits its scope**:

* ✔ Input behavior and interactivity toggling
* ✔ Compatibility with newer Hyprland versions
* ✖ Rendering internals
* ✖ Visual effects or performance tuning

Issues related to **rendering behavior** should be reported upstream.

---

## Credits

* **hyprwinwrap** — original project and core logic
