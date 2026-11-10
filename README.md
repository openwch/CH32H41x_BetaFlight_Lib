# CH32H41x SDK for Betaflight

Vendor CMSIS headers, standard peripheral driver library, and USB device middleware for WCH `CH32H41x` (QingKe V5F RISC-V) microcontrollers, maintained for Betaflight at `lib/modules/CH32H41x`.

## Directory Structure

- `Cmsis/` — QingKe V5F RISC-V core peripheral access layer and debug support (`Nanjing Qinheng Microelectronics Co., Ltd.`).
- `Peripheral/` — CH32H41x Standard Peripheral Driver (`V1.0.0`), including targeted Betaflight integration fixes for 32-bit DMA `CFGR` mask handling, ADC sampling mode configuration, and bounded fast-page Flash programming/erase state recovery.
- `middlewares/` — CherryUSB (`v1.5.0`) USB device core, CDC-ACM, and MSC class drivers, paired with the CH32H41x USBHS device controller driver (DCD) and VCP board glue.

## Betaflight Integration

This repository is consumed as a Git submodule at `lib/modules/CH32H41x` in Betaflight and is hydrated automatically when building `CH32H4` targets (or explicitly via `make ch32_sdk_submodule`; see `src/platform/CH32/mk/tools.mk`).

Keep changes to vendor and middleware files minimal and hardware-scoped; Betaflight platform drivers belong in `src/platform/CH32/` in the main Betaflight repository.

## Licensing

- `Cmsis/` and `Peripheral/`: Copyright (c) 2025 Nanjing Qinheng Microelectronics Co., Ltd. Permitted for use (modified or unmodified) on microcontrollers manufactured by Nanjing Qinheng Microelectronics; preserve all file header notices.
- `middlewares/`: CherryUSB components are licensed under `Apache-2.0` (`Copyright (c) 2022, sakumisu`), with CH32H41x USBHS register definitions provided by Nanjing Qinheng Microelectronics Co., Ltd.
