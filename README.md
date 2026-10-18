# regmsg binaries

Prebuilt releases of **regmsg**, the REG-Linux system daemon (`regmsgd`)
and its clients (`regmsg`, `regmsg_shell`). regmsgd handles display,
audio, Wi-Fi, Bluetooth, system configuration, the game library, the
scraper and the emulator launcher.

regmsg was written for REG-Linux. It is **not open source**. Only the
binaries are published here. They are built for specific REG-Linux
versions and will not work anywhere else.

## What is open and what is not

| Component | Licence |
|-----------|---------|
| `regmsgd`, `regmsg`, `regmsg_shell` | Proprietary. See [LICENSE.md](LICENSE.md) |
| Lua launch generators and controller action tables (readable in each archive) | Proprietary. You may change them on your own device but not distribute modified copies. See [LICENSE.md](LICENSE.md) |
| `libdrmhook.so`, `S06regmsgd`, and regmsg's original code inside the programs | MIT |
| Crates, Lua 5.4 and jemalloc compiled into the binaries | Their own permissive licences |

Each archive carries the licence (`/usr/share/regmsg/LICENSE`) and the
notices of every open-source part (`/usr/share/regmsg/THIRD_PARTY_LICENSES`).

The rest of REG-Linux (kernel, Buildroot tree, board support, patches) is
GPL-2.0 or another open-source licence. Its source is published at
https://github.com/REG-Linux/REG-Linux.

## Integrity checks

regmsgd checks that its own binary and a few REG-Linux boot and branding
files have not been modified, and that no debugger is attached. If a check
fails, game launching and authenticated scraping stop working. Editing the
launch generators or action tables does not trigger these checks.
LICENSE.md section 3 has the details.
