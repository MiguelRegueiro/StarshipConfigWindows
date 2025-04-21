# Starship Config for Windows

![Starship Prompt Example](https://starship.rs/example.png)

A clean and customized Starship prompt configuration optimized for **Windows PowerShell** and **PowerShell 7+**.

## Features

- 🪟 Windows-optimized with proper icons (no Linux symbols)
- 🎨 Sleek, dark-themed prompt with good visibility
- ⚡ Fast and responsive
- 🛠️ Pre-configured modules for:
  - Git status
  - Directory path
  - Command duration
  - Programming language indicators
  - And more!

## Installation

### Prerequisites
- [PowerShell 7+](https://docs.microsoft.com/en-us/powershell/scripting/install/installing-powershell-on-windows)
- [Starship](https://starship.rs/guide/#%F0%9F%9A%80-installation)
- A [Nerd Font](https://www.nerdfonts.com/) installed and configured in your terminal (recommended: "CaskaydiaCove Nerd Font")

### Setup
1. Clone this repo or download the files
2. Place the files in the correct locations:

```powershell
# Copy starship.toml to Starship config directory
Copy-Item -Path .\starship.toml -Destination ~\.config\starship.toml -Force

# Ensure the PowerShell profile directory exists
if (!(Test-Path ~\Documents\PowerShell)) {
    New-Item -ItemType Directory -Path ~\Documents\PowerShell
}

# Copy or create the profile
Copy-Item -Path .\Microsoft.PowerShell_profile.ps1 -Destination ~\Documents\PowerShell\Microsoft.PowerShell_profile.ps1 -Force
```

3. Restart your terminal or run:
```powershell
. $PROFILE
```

## Customization

### Key Configuration Options

| File | Purpose |
|------|---------|
| `starship.toml` | Main Starship configuration |
| `Microsoft.PowerShell_profile.ps1` | PowerShell profile that initializes Starship |

### Common Modifications
- Change colors in `starship.toml`
- Adjust path truncation: `truncation_length` in `[directory]`
- Modify git symbols in `[git_status]`
- Enable/disable modules by setting `disabled = true/false`

## Recommended Terminal Setup

For best experience:
1. Use [Windows Terminal](https://apps.microsoft.com/store/detail/windows-terminal/9N0DX20HK701)
2. Configure it with:
   - CaskaydiaCove Nerd Font
   - Dark color scheme
   - Minimum font size 12

## Troubleshooting

### Symbols Not Displaying Properly
- Ensure you have a Nerd Font installed and selected in your terminal settings
- Restart your terminal after font changes

### Profile Not Loading
- Check the file exists in the correct location:
  ```powershell
  Test-Path $PROFILE
  ```
- Verify execution policy allows profile loading:
  ```powershell
  Set-ExecutionPolicy RemoteSigned -Scope CurrentUser
  ```

## License

MIT License - Free to use and modify

---

Enjoy your new PowerShell prompt! 🚀

For Starship documentation, visit: [starship.rs](https://starship.rs)
