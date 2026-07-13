# JAYX v0.3

Live PC stats on Flipper Zero over **USB**.

**Bluetooth is still in development** — check GitHub for updates. Use USB for now.

**Full setup guide:** [docs/SETUP.md](../../docs/SETUP.md)

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

See **[docs/SETUP.md](../../docs/SETUP.md)** for the complete walkthrough.

```sh
cd apps/jayx
ufbt launch          # stop monitor.py first — it locks COM
```

**Apps → USB → JAYX** → **USB** → OK

## PC agent

```sh
cd pc_agent
pip install -r requirements.txt
python monitor.py --usb
```

## Optional

| Feature | Need |
|---------|------|
| GPU live + VRAM | NVIDIA drivers |
| FPS | RTSS |
| CPU temp | LibreHardwareMonitor |

## Protocol v3

- **Live** (44 B, ~1 Hz)  
- **Specs section** (126 B × 5, on connect + every 30 s)  
