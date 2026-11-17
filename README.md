<div align="center">

# ASUS VivoBook K15 OLED · Brightness Fix

**Experimental OpenCore backlight helper for ASUS K513EA · Intel Iris Xe**

![macOS](https://img.shields.io/badge/macOS-Hackintosh-111111?style=for-the-badge&logo=apple)
![CPU](https://img.shields.io/badge/CPU-i5--1135G7-0071C5?style=for-the-badge&logo=intel)
![GPU](https://img.shields.io/badge/GPU-Iris%20Xe-00A98F?style=for-the-badge)
![License](https://img.shields.io/badge/License-MIT-green?style=for-the-badge)

</div>

A hardware-specific shell helper intended to prepare an ACPI backlight patch and update an OpenCore configuration. Review the script and generated files before applying anything to a bootable EFI.

## Target hardware

| Component | Target |
|---|---|
| Laptop | ASUS VivoBook K15 OLED K513EA |
| CPU | Intel Core i5-1135G7 (Tiger Lake-U) |
| iGPU | Intel Iris Xe · PCI ID `8086:9A49` |
| Bootloader | OpenCore |

## Before running

- Back up the EFI you actually boot and test from a separate USB EFI.
- Read `fix_brightness.sh` before running it with write access.
- The supplied `templates/brightness_fix.aml.template` is a placeholder, not a compiled SSDT. Compile and validate your own SSDT before relying on it.
- Do not assume the default path matches every OpenCore folder layout.

## Usage

Preview intended changes:

```bash
./fix_brightness.sh --dry-run
./fix_brightness.sh --dry-run --verbose
```

Apply only after reviewing the script's output and confirming the target EFI path:

```bash
./fix_brightness.sh
```

Verify that timestamped backups exist before rebooting.

## Repository contents

- `fix_brightness.sh` — detection and OpenCore update helper
- `templates/brightness_fix.aml.template` — placeholder template; not a ready-to-install AML

## Compatibility

Written for the K513EA / i5-1135G7 / Iris Xe configuration. Other laptop revisions, macOS releases, panels, and ACPI layouts are not established as compatible.

## Contributing

Include the exact laptop variant, macOS build, OpenCore version, and sanitized logs. Never attach SMBIOS serials, MLB, ROM, UUID, passwords, Wi-Fi credentials, or personal identifiers.

## License

MIT. See the repository license terms.

## Disclaimer

Experimental community software, provided as-is without warranty. Keep a known-good EFI and recovery USB. A faulty display/ACPI change can result in a black internal display.
