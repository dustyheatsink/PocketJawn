# PocketJawn Keyboard Firmware

PocketTerm35 keyboard firmware modified for PocketJawn project.

Changes the gamepad buttons to emit unique keyboard characters for use as programmable hotkeys. The D-pad is left alone.

Based on:
`https://github.com/black-ghost-off/pocketTerm35-keyboard-firmware`

- `pocketjawn-keyboard.uf2` - is ready to flash
- `pocketjawn.patch` - lists changes from the original firmware

# Flashing

Put the keyboard RP2040 into BOOTSEL mode and copy pocketjawn-keyboard.uf2 to the mounted drive.
