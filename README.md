# Nvrx PC Tweaking Utility

**A Windows performance utility that debloats Windows, reduces network latency, tunes NVIDIA/CPU settings and hardens privacy — built in C#/WPF.**

A Windows PC tweaking utility built in **C# / WPF (.NET 9)**. It debloats Windows, optimizes network latency, tunes your GPU, and squeezes performance out of desktop hardware.

> **Note:** This repository is **source-available only**. You may read and learn from the code, but copying, modifying, redistributing, or using it in your own projects is prohibited. See [LICENSE](LICENSE).

---

## Features

| Category | What it does |
| --- | --- |
| **System Debloat** | Remove AI (Copilot/Recall), UWP apps, telemetry and bloat from Windows, browsers, Office and gaming apps; manage startup and updates. |
| **Network Optimization** | Reset and tune the TCP/IP stack, disable offloads and power-saving, set Cloudflare DNS, harden SMB/LAN security. |
| **GPU & Display Tuning** | Install Nvidia Profile Inspector and import the tuned profile, disable dynamic P-States, enable MSI mode. |
| **CPU & Power Tweaks** | Import the Ultimate Power Plan, tune scheduling/timers/interrupt steering, optimize MMCSS, per-CPU tick scheduling. |
| **Privacy Shield** | Disable telemetry, diagnostic data, advertising/location tracking, Windows AI and personalized content. |
| **Deep OS Tweaks** | Optimize NTFS/startup, restore file-type associations, Run-as-TrustedInstaller menu, TDR config, USB/mouse/keyboard input. |

Plus 5 one-click **Dashboard** actions: Disk Cleanup, Activate Windows, Create System Restore Point, Install Important Runtimes, and Restore Corrupted System Files.

---

## Requirements

- 64-bit **Windows 11**
- **.NET 9 Desktop Runtime**
- **Administrator privileges** (the app runs elevated to apply tweaks)

> A small, self-contained build is available from the website so most users don't need anything installed.

---

## Getting Started

```bash
dotnet restore
dotnet build -c Release
```

Run the resulting executable **as Administrator**.

### Build the portable single-file exe

```bash
# Self-contained (runs anywhere, ~120 MB)
dotnet publish -c Release -r win-x64 --self-contained true \
  -p:PublishSingleFile=true -p:IncludeNativeLibrariesForSelfExtract=true -o dist

# Framework-dependent (tiny, ~0.6 MB, needs .NET 9 Desktop Runtime)
dotnet publish -c Release -r win-x64 --self-contained false \
  -p:PublishSingleFile=true -p:IncludeNativeLibrariesForSelfExtract=true -o dist
```

---

## Recommended safety steps

Before applying tweaks, use the **"Prepare PC Before Tuning"** section on the Dashboard:

1. **Create System Restore Point** — so you can roll back.
2. **Restore Corrupted System Files** — runs `DISM /RestoreHealth` and `sfc /scannow`.

Each tweak runs elevated and logs every step to `Nvrx_Log.txt` on the Desktop (also visible in the in-app log panel).

---

## License

See [LICENSE](LICENSE). Source is available for reading only — all rights reserved by Nvrx.

## Links

- [Discord](https://discord.gg/zCkcdZar5w)

---

Want me to tweak the wording, add a screenshot/logo, or install `git`+`gh` to create and push the repo?
