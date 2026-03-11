# Lenovo Legion Pro 7 16IAX10H - Linux 7.0 Compatibility Patch

## Overview

This patch set updates the AW88399 HDA side-codec audio driver for Linux 7.0+ compatibility. The driver supports audio on the Lenovo Legion Pro 7 16IAX10H (models 83F5, 83RU, 83F4) with the Realtek ALC287 codec and Awinic AW88399 smart amplifier.

## Key Changes for Linux 7.0 Compatibility

### 1. **ACPI API Improvements**
- Better error handling for `acpi_dev_uid_to_integer()` - now handles `-ENODATA` return code
- Fallback to I2C address-based indexing when ACPI _UID is not available
- More robust ACPI device companion detection

### 2. **Regmap Configuration Enhancements**
```c
.use_single_read = true,
.use_single_write = true,
.cache_type = REGCACHE_RBTREE,