# yabai-config

yabai configuration for macOS, with a neutral base and stack, BSP and float profiles.

- Stack uses no gaps and 20px vertical / 40px horizontal padding. BSP uses 8px padding and gaps; float leaves windows to macOS.
- Ctrl-drag moves or resizes windows. Rules leave system apps, dialogs and selected utility windows floating.
- Runs with SIP enabled and no scripting addition. Shadow, opacity and animation settings are retained for reference; they need the scripting addition to take effect.

Requires yabai with Accessibility access. Back up your current config, then run from this repo:

```sh
mkdir -p ~/.config/yabai/profiles ~/.config/yabai/scripts
cp yabairc ~/.config/yabai/
cp profiles/*.sh ~/.config/yabai/profiles/
cp scripts/yabai-restart.sh ~/.config/yabai/scripts/
```

The base loads from `~/.config/yabai/yabairc` and leaves layout selection to a profile. With yabai running, apply one with `bash ~/.config/yabai/profiles/yabai-stack.sh` (or `yabai-bsp.sh` / `yabai-float.sh`). Display connection changes trigger a service restart. `scripts/yabai-restart.sh [stack|bsp|float]` restarts yabai and applies a profile; it defaults to stack.

Numbered backups are available as tags `v0.1.0`–`v0.3.0`; `v0.4.0` marks this configuration. Those older configs predate the current SIP-on setup.

MIT. See [LICENSE](LICENSE).
