# Changelog

All notable changes to WAIR (Who Am I Really) will be documented in this file.

## [1.5.0] — 2026-03-22

### Fixed
- **Config toggle freeze** — toggling field checkboxes no longer re-fetches all system info via PowerShell, eliminating the "Not Responding" hang. Field visibility is now derived from in-memory state instantly.

### Changed
- **Windows Update → Windows Version** — field now shows the OS feature version (e.g. "25H2") from the registry `DisplayVersion` instead of the last installed KB update title. Label renamed to "Windows Version".

## [1.2.0] — 2026-03-22

### Changed
- Replaced all `wmic` commands with PowerShell `Get-CimInstance` equivalents for compatibility with Windows 11 24H2+ where wmic is deprecated and may not be installed
- Bumped version to v1.2.260322

### Added
- **About panel** — accessible via the info icon in the title bar; shows version, developer attribution (Adam Sharp / E-Hounds, Inc.), license info, and GitHub link
- **README.md** — full project documentation with features, install instructions, and tech stack
- **LICENSE** — MIT License with attribution requirement
- **CHANGELOG.md** — this file

## [1.1.0] — 2026-03-22

### Added
- **Windows Edition** field — shows actual product name (e.g., "Microsoft Windows 11 Pro")
- **Windows Update** field — queries update history for latest installed KB with full title
- **Full User (whoami)** field — runs `whoami` to show `DOMAIN\username`
- **FQDN** field — fully qualified domain name below Computer Name
- **Multi-adapter network selection** — dropdown in settings when multiple NICs are present
- **Smart gateway detection** — auto-selects the adapter with an active internet gateway
- **Per-disk display** — each storage device shown on its own line with volume name, size, usage %, and free space
- **Credit link** — "Designed by ASharpDude" link to ehounds.com in settings panel
- Version number displayed in title bar
- Tray icon generated programmatically (indigo "W" on dark background)
- NSIS installer via electron-builder

## [1.0.0] — 2026-03-22

### Added
- Initial release
- System tray app with popup info panel
- Configurable fields: Hostname, User, Domain, OS Version, Build, BIOS, CPU, RAM, Serial Number, IPv4, MAC, Gateway, DNS, Public IP, Uptime, Last Boot, Disk Info
- One-click copy to clipboard for all fields
- Settings panel with per-category checkboxes
- Config persistence via electron-store
- Dark theme with Tailwind CSS
