# lsbt

A simple command-line utility for listing Bluetooth devices on Linux using `bluetoothctl`.

## Requirements

- Linux with `bluetoothctl` available (part of the `bluez` package)
- Python 3

## Installation

Make the script executable and optionally move it to your PATH:

```bash
chmod +x lsbt.py
sudo mv lsbt.py /usr/local/bin/lsbt
```

## Usage

```
lsbt <paired|p|connected|c>
```

### Arguments

| Argument | Short | Description |
|---|---|---|
| `paired` | `p` | List all paired Bluetooth devices |
| `connected` | `c` | List currently connected Bluetooth devices |
| `--help` | `-h` | Show help message |

### Examples

```bash
lsbt paired       # List all paired devices
lsbt p            # Same as above

lsbt connected    # List currently connected devices
lsbt c            # Same as above

lsbt -h           # Show help
```

## Notes

- Only paired or connected devices can be queried. Nearby/discoverable devices are not listed.
- Requires `bluetoothctl` to be installed:
  - Debian/Ubuntu: `sudo apt install bluez`
  - Fedora/RHEL: `sudo dnf install bluez`
  - Arch Linux: `sudo pacman -S bluez bluez-utils`
- After installing, you may need to enable and start the Bluetooth service:
  ```bash
  sudo systemctl enable --now bluetooth
  ```
