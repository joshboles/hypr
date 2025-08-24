# CLAUDE.md

This file provides guidance to Claude Code (claude.ai/code) when working with code in this repository.

## Configuration Architecture

This is a Hyprland window manager configuration repository that uses the Omarchy configuration system. The architecture follows a layered approach:

### Configuration Layers
1. **Omarchy defaults** - Base configurations from `~/.local/share/omarchy/default/hypr/` (do not edit directly)
2. **Current theme** - Theme-specific settings from `~/.config/omarchy/current/theme/`  
3. **User overrides** - Personal customizations in the individual `.conf` files in this repository

### File Structure and Purpose
- `hyprland.conf` - Main configuration file that sources all other configs in proper order
- `bindings.conf` - Comprehensive keybind definitions organized by modifier combinations (SUPER, SUPER+SHIFT, SUPER+ALT, SUPER+CTRL, SUPER+SHIFT+CTRL)
- `monitors.conf` - Display configuration including scaling, resolution, and positioning
- `input.conf` - Keyboard and touchpad settings  
- `windows.conf` - Sources app-specific window rules from `apps.conf`
- `apps.conf` - Sources individual app configurations from `apps/` directory
- `envs.conf` - Custom environment variables
- `autostart.conf` - Additional startup processes
- `hypridle.conf` - Idle management and screen locking configuration
- `hyprlock.conf` - Lock screen appearance and authentication settings
- `hyprbk` - Backup/alternative configuration file with different keybind layout

### Keybind Organization
The `bindings.conf` file uses a systematic approach:
- Keys are organized alphabetically within each modifier section
- All sections contain the same keys for consistency (active bindings and commented placeholders)
- Uses `bindd` for key bindings and `bindmd` for mouse bindings
- Placeholder entries are commented out and marked as `[AVAILABLE FOR BINDING]`

### Variable Definitions
Application shortcuts are defined as variables at the top of configuration files:
- `$browser` - Web browser command
- `$messenger` - Messaging application  
- `$notes` - Note-taking application
- `$terminal` - Terminal emulator
- `$webapp` - Web application launcher

## Configuration Management

### Reloading Configuration
- Most changes take effect immediately upon saving
- Environment variables and monitor settings require relaunching Hyprland (Super+Esc → Relaunch)
- Use `hyprctl reload` for configuration reload without restart

### Monitor Configuration
- Use `hyprctl monitors` to list current monitors and available resolutions
- Configure scaling for different display types in `monitors.conf`
- Examples provided for common setups (retina displays, 4K monitors, multi-monitor)

### Theme Integration
- Themes are managed through Omarchy and stored in `~/.config/omarchy/current/theme/`
- Background changes: Super+Ctrl+Space (next background), Super+Shift+Ctrl+Space (theme picker)
- Color variables from themes are available in lock screen and other configurations