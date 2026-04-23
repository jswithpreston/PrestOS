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
- [x] Phase 1 — Cross Toolchain
  - [x] Binutils 2.45 Pass 1
  - [x] GCC 15.2.0 Pass 1
  - [x] Linux 6.16.1 API Headers
  - [x] Glibc 2.42
  - [x] Libstdc++ from GCC 15.2.0
- [ ] Phase 2 — Temporary Tools
- [ ] Phase 3 — Chroot & Final System
- [ ] Phase 4 — Bootloader & First Boot
- [ ] Phase 5 — PrestOS Customization
- [ ] Phase 6 — Security Hardening
- [ ] Phase 7 — JavaScript Developer Toolchain

## Target Specs
- RAM: 4GB minimum, 8GB recommended
- Arch: x86_64
- Init: Systemd
- Display: Sway (Wayland)
- Shell: Bash → Zsh

## Built by
Preston — Junior Developer, Uganda
