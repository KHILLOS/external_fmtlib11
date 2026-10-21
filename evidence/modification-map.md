# Modification Map: external/fmtlib11

## Source: BlissOS android-x86 reference (external/fmtlib11)
- BlissOS reference: android-generic/fmtlib11 (commit 0eda9670 / b6310357)
- UPSTREAM commits:
  - b6310357 (initial KhillOS port - Android.bp with 3 modules)
  - 0eda9670 (AOSP 17 conventions - extended Android.bp)
- Upstream base: fmtlib/fmt 11.2.0 (tag 40626af)

## Modifications Applied to UPSTREAM/external_fmtlib11 (khillos-17 branch)

### 1. Android.bp Build System (EXTENDED from BlissOS in 2 commits)
**Commit b6310357 - Basic port:**
- `cc_defaults` fmtlib11_defaults with common flags
- `cc_library_headers` fmtlib11_headers
- `cc_library_static` fmtlib11 and fmtlib11_ndk
- Basic partition availability (vendor_available, host_supported)

**Commit 0eda9670 - AOSP 17 conventions (reference for other ports):**
- Package-level license configuration with `default_applicable_licenses`
- License module with 5 license kinds (BSD, CC0-1.0, MIT, PSF-2.0, legacy_unencumbered)
- Full partition availability (product, ramdisk, vendor_ramdisk, recovery)
- Added native_bridge_supported, target (linux_bionic + windows)
- Added min_sdk_version: "29", sdk_version: "current"
- Added apex_available with anyapex + platform
- Added visibility: //external/spdlog (for spdlog dependency)
- fmtlib11_ndk: sdk_version: "current", stl: "c++_static"

### 2. AOSP 17 Compliance Metadata Files (NEW)
**Files:** `METADATA`, `MODULE_LICENSE_BSD`, `OWNERS`
- METADATA: Package metadata per AOSP external_updater format
- NOTICE: Already existed (updated with proper content)
- MODULE_LICENSE_BSD: Primary SPDX identifier for Soong license module
- OWNERS: Standard AOSP OWNERS file

### 3. SPDX Headers - NOT REQUIRED
fmtlib uses multiple licenses handled via license module in Android.bp. Source files have license headers but per-file SPDX not standard.

## Summary
- **Total files modified:** 4 (3 new metadata + NOTICE updated)
- **Source files unchanged:** Yes
- **Logic/behavior changes:** None
- **Build system changes:** Extended Android.bp with AOSP 17 conventions (reference implementation)