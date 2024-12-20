# osu!Settings NightBot Commands Guide

A comprehensive guide for integrating osu!Settings with your Twitch chat through NightBot custom commands.

## 🚨 Essential Prerequisites

Before setting up these commands, ensure you have:

1. An active account on [osettings.flimixst.dev](https://osettings.flimixst.dev)
2. Completed settings profile on the website
3. Matching username between commands and your osu!Settings profile

> ⚠️ **Important**: Commands will return "Failed to get stats" if these prerequisites aren't met.

## 🎮 Command Configuration

### 🖊️ Tablet Settings

Beautiful formatted commands to display your tablet configuration:

| Command | Purpose | NightBot Setup |
|---------|---------|----------------|
| `!tablet` | View tablet model | ```!addcom -cd=5 !tablet $(eval const api = $(urlfetch json https://osettings.flimixst.dev/api/lookup?name=USERNAME&all=true); api[0] && api[0].tablet ? `${api[0].tablet.name}` : 'Failed to get stats';)``` |
| `!area` | Check tablet area | ```!addcom -cd=5 !area $(eval const api = $(urlfetch json https://osettings.flimixst.dev/api/lookup?name=USERNAME&all=true); api[0] && api[0].tablet && api[0].tablet.area ? `${api[0].tablet.area.width}x${api[0].tablet.area.height}` : 'Failed to get stats';)``` |
| `!grip` | Display tablet grip style | ```!addcom -cd=5 !grip $(eval const api = $(urlfetch json https://osettings.flimixst.dev/api/lookup?name=USERNAME&all=true); api[0] && api[0].tablet && api[0].tablet.grip ? `${api[0].tablet.grip}` : 'Failed to get stats';)``` |

### 🖱️ Mouse Configuration

Detailed mouse settings commands:

| Command | Purpose | NightBot Setup |
|---------|---------|----------------|
| `!mouse` | Show mouse model | ```!addcom -cd=5 !mouse $(eval const api = $(urlfetch json https://osettings.flimixst.dev/api/lookup?name=USERNAME&all=true); api[0] && api[0].mouse ? `${api[0].mouse.name}` : 'Failed to get stats';)``` |
| `!sens` | Display sensitivity | ```!addcom -cd=5 !sens $(eval const api = $(urlfetch json https://osettings.flimixst.dev/api/lookup?name=USERNAME&all=true); api[0] && api[0].mouse && api[0].mouse.sens ? `${api[0].mouse.sens}` : 'Failed to get stats';)``` |
| `!dpi` | Check DPI settings | ```!addcom -cd=5 !dpi $(eval const api = $(urlfetch json https://osettings.flimixst.dev/api/lookup?name=USERNAME&all=true); api[0] && api[0].mouse && api[0].mouse.dpi ? `${api[0].mouse.dpi}` : 'Failed to get stats';)``` |
| `!mousegrip` | View mouse grip style | ```!addcom -cd=5 !mousegrip $(eval const api = $(urlfetch json https://osettings.flimixst.dev/api/lookup?name=USERNAME&all=true); api[0] && api[0].mouse && api[0].mouse.grip ? `${api[0].mouse.grip}` : 'Failed to get stats';)``` |

### ⌨️ Keyboard Settings

Keyboard configuration commands:

| Command | Purpose | NightBot Setup |
|---------|---------|----------------|
| `!keyboard` | Display keyboard model | ```!addcom -cd=5 !keyboard $(eval const api = $(urlfetch json https://osettings.flimixst.dev/api/lookup?name=USERNAME&all=true); api[0] && api[0].keyboard ? `${api[0].keyboard.name}` : 'Failed to get stats';)``` |
| `!rt` | Show rapid trigger config | ```!addcom -cd=5 !rt $(eval const api = $(urlfetch json https://osettings.flimixst.dev/api/lookup?name=USERNAME&all=true); api[0] && api[0].keyboard && api[0].keyboard.rapidtrigger ? (api[0].keyboard.rapidtrigger.enabled ? `RT Press: ${api[0].keyboard.rapidtrigger.rtpress}, RT Release: ${api[0].keyboard.rapidtrigger.rtrelease}, Actuation Point: ${api[0].keyboard.rapidtrigger.actpoint}.` : 'Disabled') : 'Failed to get stats';)``` |

## 🔧 Setup Instructions

1. **Prepare Username**: Replace all instances of `USERNAME` in the commands with your actual osu! username
2. **Add Commands**: Copy your chosen command and paste it into your Twitch chat
3. **Verify**: NightBot will confirm with a success message
4. **Test**: Try the command in chat (e.g., `!tablet`, `!area`)

## 📝 Notes

- All commands have a 5-second cooldown by default
- Commands can be modified through NightBot's dashboard for custom cooldowns or permissions
- Keep your osu!Settings profile updated for accurate command responses
