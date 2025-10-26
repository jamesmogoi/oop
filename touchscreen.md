my phone redmi on lineage 13 after reboot it locks scrreen is that hardware or softaware happenned after putting gue on the screen amerturish what next even after new screen still the same i ended up shattering the sensors at the top as i thiught they triggred no luck

This sounds like a **software/calibration issue**, not hardware. Here's what's likely happening and how to fix it:

## Why it's probably software:

1. **Started after screen repair** - digitizer/touch sensor calibration got corrupted
2. **New screen didn't fix it** - confirms it's not the screen hardware
3. **Breaking top sensors didn't help** - not triggered by proximity/ambient light sensors
4. **Only happens after reboot** - classic sign of calibration data corruption

## Fixes to try (in order):

### 1. **Recalibrate touch screen**

bash

```bash
# Boot into recovery (TWRP or LineageOS recovery)
# Wipe > Advanced Wipe > Check "Dalvik/ART Cache" and "Cache"
# Reboot

# Or via ADB:
adb shell
rm -rf /data/system/gesture.key
rm -rf /data/system/locksettings.*
reboot
```

### 2. **Delete touchscreen calibration files**

bash

```bash
adb shell
su
cd /data/system/
rm -f tsCalibration
rm -f pointercal
rm -f touchscreen_*
reboot
```

### 3. **Reset lockscreen without data loss**

Boot into **TWRP Recovery**:

- Mount > Check "System" and "Data"
- Advanced > Terminal

bash

```bash
rm /data/system/locksettings.db*
rm /data/system/gatekeeper.*
reboot system
```

### 4. **Check for stuck touch sensor (ghost touch)**

bash

```bash
# Install via adb or F-Droid
adb install <TouchScreenTest.apk>

# Or use built-in test:
# Dial: *#*#64663#*#* (or *#*#2664#*#*)
# This opens hardware test mode
```

Look for **ghost touches** registering on screen even when not touching.

### 5. **Flash clean vendor/firmware**

Your Redmi might have **vendor partition mismatch** after LineageOS 13:

- Download correct **vendor/firmware** for your exact Redmi model
- Flash via TWRP: Install > Select vendor.zip
- Wipe cache/dalvik
- Reboot

### 6. **Last resort: Format data**

bash

```bash
# In TWRP:
Wipe > Format Data (type "yes")
# This wipes encryption and all data - backup first!
```

## What likely happened with the glue:

The glue probably **shorted or corrupted the digitizer calibration matrix** in `/data/system/`. LineageOS reads bad calibration on boot → registers phantom touches → locks screen thinking someone's trying to break in.

## Quick test:

Boot into **Safe Mode** (hold Power + Volume Down during boot logo):

- If screen works = 3rd party app conflict
- If still locks = system calibration issue

Try the calibration deletion (#1-2) first - that should fix it without losing data. Let me know what happens!

[](https://support.anthropic.com/en/articles/8525154-claude-is-providing-incorrect-or-misleading-responses-what-s-going-on)