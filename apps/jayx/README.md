# JAYX v0.3

Live PC stats on Flipper Zero over **USB**.

**Bluetooth is still in development** — check GitHub for updates. Use USB for now.

## Pages

| Page | Content |
|------|---------|
| **System** | CPU / RAM / GPU / VRAM usage + temps |
| **Game** | Title strip, large FPS, frametime |
| **Specs** | Scrollable system info (sections) |
| **About** | App version, link type |

### Specs controls
- **Left / Right** — change page  
- **Up / Down** — switch system-info section (card view)  

Sections: **SYSTEM | OS | CPU | MEMORY | GPU** (one clean card each)

## Build & install

```sh
cd apps/jayx
ufbt launch
```

**Apps → USB → JAYX**

## PC agent

```sh
cd pc_agent
pip install -r requirements.txt
python monitor.py --usb    # or --bt
```

Stop the agent before `ufbt launch` (COM port lock).

## Optional

| Feature | Need |
|---------|------|
| GPU live + VRAM | NVIDIA drivers |
| FPS | RTSS |
| CPU temp | LibreHardwareMonitor |

## Protocol v3

- **Live** (44 B, ~1 Hz)  
- **Specs section** (126 B × 5, on connect + every 30 s)  
