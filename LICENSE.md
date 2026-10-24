# regmsg licence

Copyright (c) 2025-2026 the REG-Linux authors (Romain Tisserand,
Carlos Martins), except the parts listed in section 2.

This file covers regmsg as REG-Linux ships it, in REG-Linux images and in
the release archives published at
https://github.com/REG-Linux/regmsg-binaries. It contains parts under
different licences. They are listed below.

## 1. Proprietary components

- `/usr/bin/regmsgd`
- `/usr/bin/regmsg`
- `/usr/bin/regmsg_shell`
- the launch generators and controller action tables,
  `/usr/share/regmsg/launcher/generators/**`

These components are proprietary. The source code of the programs is not
published. The launch generators (Lua scripts) and the action tables (JSON) ship
in readable form, but they are covered by this licence all the same.

You may:

- install and use these components on a device running REG-Linux;
- redistribute them unmodified, either as part of an official or
  unmodified REG-Linux image or inside the archive they shipped in,
  provided this file goes with them;
- change the launch generators and action tables on your own device,
  for your own use.

You may not:

- distribute modified copies, including modified launch generators or
  action tables;
- sell these components on their own;
- use them outside REG-Linux in a way that relies on, or gets around,
  their integrity checks (see "Integrity checks" below).

This licence does not take away any right you have by law. That includes
the right to observe, study and test how a program works, and to
decompile it for interoperability, under EU Directive 2009/24/EC
(Articles 5(3), 6) and the UK CDPA 1988 (ss. 50B, 50BA). It also includes
the right to modify and reverse engineer these programs in order to
debug changes you make to the LGPL libraries they link to (glibc,
libpulse, libudev), as LGPL-2.1 section 6 requires.

## 2. Open-source components

| Path | Licence | Notice |
|------|---------|--------|
| `/usr/lib/libdrmhook.so`, and regmsg's original code inside `regmsgd`, `regmsg` and `regmsg_shell` (display management, IPC server, Wi-Fi, command-line client and shell) | MIT | `/usr/share/regmsg/THIRD_PARTY_LICENSES` |
| `/etc/init.d/S06regmsgd` | MIT | The file itself |
| Rust crates and the bundled Lua 5.4 interpreter and jemalloc allocator, statically linked into the binaries | MIT, Apache-2.0, BSD, ISC, Zlib, Unicode-3.0, CDLA-Permissive-2.0 and others | `/usr/share/regmsg/THIRD_PARTY_LICENSES` |

Each of these components is under its own licence. Nothing in section 1
restricts them.

## 3. Integrity checks

`regmsgd` checks that its own executable and a small set of REG-Linux
boot and branding files have not been changed. It also checks that no
debugger is attached. If any check fails, our scraper credentials stay
locked and the daemon will not launch games. It does not delete,
encrypt or upload anything, and it never contacts a server to make this
decision.

Changing the launch generators, or GPL-licensed software on the system
(the kernel, Plymouth, emulators and so on), does not trigger these
checks. Only `regmsgd` itself and the REG-Linux files it names do.

## 4. No warranty

THE SOFTWARE IS PROVIDED "AS IS", WITHOUT WARRANTY OF ANY KIND, EXPRESS
OR IMPLIED, INCLUDING BUT NOT LIMITED TO THE WARRANTIES OF
MERCHANTABILITY, FITNESS FOR A PARTICULAR PURPOSE AND NONINFRINGEMENT.
IN NO EVENT SHALL THE AUTHORS BE LIABLE FOR ANY CLAIM, DAMAGES OR OTHER
LIABILITY, WHETHER IN AN ACTION OF CONTRACT, TORT OR OTHERWISE, ARISING
FROM, OUT OF OR IN CONNECTION WITH THE SOFTWARE OR THE USE OR OTHER
DEALINGS IN THE SOFTWARE.
