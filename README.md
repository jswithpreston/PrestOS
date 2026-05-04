# PrestOS

A custom Linux-based operating system built from scratch using Linux From Scratch 12.4.

## Vision

PrestOS is designed as a fast, secure, developer-focused OS targeting JavaScript/TypeScript
developers. Built to run efficiently on 4GB RAM with an 8GB sweet spot.

## Design Goals

- Minimal memory footprint — targeting under 300MB idle RAM usage
- Sub 3-second boot time
- Security hardened kernel with KSPP flags
- Rust kernel modules for new components
- Optimized for Node.js, PostgreSQL, and modern web development
- Built by Preston — from scratch, every package compiled from source

## Base

- Linux From Scratch 12.4
- Linux Kernel 6.16.1
- GCC 15.2.0
- Glibc 2.42

## Build Status

### ✅ Phase 1 — Cross Toolchain (Complete)
- Binutils 2.45 Pass 1, GCC 15.2.0 Pass 1
- Linux 6.16.1 API Headers, Glibc 2.42, Libstdc++

### ✅ Phase 2 — Temporary Tools (Complete)
- M4, Ncurses, Bash, Coreutils, Diffutils, File, Findutils
- Gawk, Grep, Gzip, Make, Patch, Sed, Tar, Xz
- Binutils Pass 2, GCC Pass 2

### ✅ Phase 3 — Chroot & Base System (Complete)
- Virtual filesystems, directory structure, hostname: prestos
- Timezone: Africa/Kampala

### ✅ Phase 4 — Main System Packages (Complete)
- Full toolchain: GCC 15.2.0, Binutils 2.45, Glibc 2.42
- Systemd 257.8, OpenSSL 3.5.2, Python 3.13.7, Perl 5.42
- Util-linux, E2fsprogs, Elfutils, Libcap, Libxcrypt
- Inetutils, Attr, ACL, Kmod, Vim, Shadow, Procps-ng
- Sysklogd, Sysvinit, Man-DB, Intltool

### ✅ Phase 5 — Linux Kernel 6.16.1 (Complete)
- Kernel compiled and installed: /boot/vmlinuz-6.16.1-prestos
- Modules installed to /lib/modules/6.16.1

### 🔄 Phase 6 — Bootloader (In Progress)
- GRUB install pending
- /etc/fstab pending
- First boot pending

### ⏳ Phase 7 — PrestOS Customization (Upcoming)
- Package manager (pacman)
- Security hardening (KSPP kernel flags)
- JavaScript dev toolchain (Node.js, npm, etc.)
- Display server (Sway/Wayland)

## Known Build Fixes
| Issue | Fix |
|---|---|
| ftp.gnu.org blocked | Use mirrors.kernel.org |
| MB_LEN_MAX error GCC 15 | Comment out #error in bits/stdlib.h and bits/wchar2.h |
| GCC Pass 2 config cache conflict | Always rm -rf source dir before building |
| Systemd linking failure | Add -Wl,-rpath-link,/usr/lib to build.ninja |
| iproute2 libelf conflict | Remove -lelf from line 32 of config.mk |
| procps-ng LIBSYSTEMD_209 | Add LDFLAGS="-L/usr/lib -Wl,-rpath-link,/usr/lib" |
| inetutils telnet tgetent | Add --disable-telnet to configure |
| objtool libelf missing deps | Add -lz -lzstd -llzma -lbz2 to libelf.pc |

## Target Specs

- RAM: 4GB minimum, 8GB recommended
- Arch: x86_64
- Init: Systemd
- Display: Sway (Wayland)
- Shell: Bash → Zsh

## Built by

Preston — Developer, Uganda
