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

regmsgd checks that its own binary and a few REG-Linux boot and branding files
have not been modified, and that no debugger or tracer is attached. If a check fails,
game launching and scraping with our credentials stop working, without any warning.
Editing the launch generators or action tables does not trigger these checks.
LICENSE.md section 3 also addresses this subject.

The checked files are:

- `/usr/bin/regmsgd`
- `/etc/init.d/S06regmsgd`
- `/etc/init.d/S002plymouth`
- `/etc/plymouth/plymouthd.conf`
- `/usr/share/plymouth/themes/reglinux-arcade/reglinux-arcade.plymouth`
- `/usr/share/plymouth/themes/reglinux-arcade/logo_frame_9.png`

This applies to edits made on a device and to images built with these
binaries: the boot-splash files come from `package/boot/plymouth/` in the
REG-Linux tree, so changing them there breaks a self-built image too.
