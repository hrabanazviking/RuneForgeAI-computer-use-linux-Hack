# Yrsa's mods — computer-use-linux

Personal improvements by Yrsa Freydisdottir, kept in this fork per Volmarr's
standing rule (mods to the desktop-agent tools live in the RuneForgeAI-*-Hack
forks, not only as local edits). Installed and verified live on purplelongship
(KDE Plasma 6 / Wayland) on 2026-11-19.

## Files

- `yrsa-desktop` — session wrapper. Non-interactive shells lack the KDE/Wayland
  session environment; this exports it (PATH, XDG_RUNTIME_DIR, DBus address,
  WAYLAND_DISPLAY, DISPLAY, XDG_CURRENT_DESKTOP, XDG_SESSION_TYPE) and dispatches:
  `yrsa-desktop cul <args>` (computer-use-linux), `yrsa-desktop aws <args>`,
  `yrsa-desktop kde <tool> [json]`, `yrsa-desktop doctor-all`.

## Install (on the machine)

```
install -m 755 yrsa-desktop ~/bin/yrsa-desktop
```

## Notes from the field

- Installed via npm into the user prefix: `npm install -g @agent-sh/computer-use-linux`.
- `computer-use-linux setup` enables AT-SPI (org.a11y.Status IsEnabled);
  already-running apps may need a restart before their tree appears.
- On KDE, its screenshot routes do NOT work (GNOME Shell absent, XDG portal
  demands a consent click, gnome-screenshot times out) — use kde-mcp's
  ScreenShot2 route for pictures of the live desktop.
- Pointer input works via /dev/uinput; keyboard input is portal-dependent and
  flaky by doctor — kde-mcp's keyboard tools are the reliable typing road.
