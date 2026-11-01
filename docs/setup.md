# Setup

Reference build:

- Raspberry Pi CM4
- Raspberry Pi OS Lite (64-bit) / 64-bit Debian 13 (Trixie)
- PocketTerm35
- CM4 to 4b carrier for pogo pin matching 
- ZebraHAT Duo / dual SX1262 (WeHooper)

## Boot config

Use the HDMI display path at 480x320. I disabled KMS or the display was blank.

In `/boot/firmware/config.txt`:

    #dtoverlay=vc4-kms-v3d

Under `[all]`:

    enable_uart=1
    dtoverlay=spi0-2cs
    dtoverlay=waveshare-35dpi-4b
    dtoverlay=dwc2,dr_mode=host

    hdmi_force_hotplug=1
    hdmi_group=2
    hdmi_mode=87
    hdmi_cvt=480 320 60 6 0 0 0
    disable_splash=1

Uusing legacy framebuffer at 480x320.

Add these options to existing `/boot/firmware/cmdline.txt`:

    fullscreen_logo=1 fullscreen_logo_name=logo.tga vt.global_cursor_default=0
