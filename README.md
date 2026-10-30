# PocketJawn

PocketTerm35 based Linux cyberdeck with a focus on MeshCore and Meshtastic integration and TUI based apps.

<p align="center">
  <img src="images/IMG_2193.gif" alt="PocketJawn terminal interface">
</p>

<p align="center">
  <img src="images/Frontview.jpg" width="47%" alt="PocketJawn front view">
  <img src="images/IMG_2221.gif" width="47%" alt="PocketJawn in action">
</p>

# Original plan

To make a hackable base device to run MeshTerm for MeshCore, something that could be modified while still using mostly off the shelf components, and not reinventing the wheel.

<p align="center">
  <img src="images/Angle.jpg" width="31%" alt="PocketJawn angled view">
  <img src="images/Sideshot.jpg" width="31%" alt="PocketJawn side view">
</p>

# Current iteration
The base PocketTerm is designed to support a full-size Pi 4/5. However, I’m using a CM4 on a carrier board. The goal is to slim that stack down as much as possible and hopefully eliminate the extra case section in the back. I’ve also installed a WeHooper Zebra Duo HAT so that the device is running dual 1W E22P modules.

Initial case designs for a slimmer back are underway, but actual use of them waiting to see how slim I can make the hardware stack.

# Inevitable scope creep

Expanded the above to support a Meshtastic TUI, ANSI style main menu, reprogramming of some of the extra buttons to allow quick switching between TTYs, and slowly adding additional apps to support the general RF work around PhillyMesh.

<p align="center">
  <img src="images/Menu.png" width="31%" alt="PocketJawn main menu">
  <img src="images/MeshTerm-TTY2.png" width="31%" alt="MeshTerm on TTY2">
  <img src="images/TermTastic-TTY3.png" width="31%" alt="TermTastic on TTY3">
</p>

# Interface & Controls

The base PocketTerm device has touchscreen support, while functional, I have not utilized it in my current build.

More interesting to me was the controller for the keyboard. It is an RP2040. The stock CircuitPython firmware already has the directional pad mapped as standard keyboard direction keys. However, the dedicated L/R "shoulder" buttons and the X/Y/B/A pad just mapped to the corresponding keyboard letters.

Since there is the RP2040 under the hood, that opened up some options. After some research I found the open-source work by black-ghost-off, which provided the Pico SDK/TinyUSB foundation that I used for PocketJawn’s custom controls.

Keeping the D-pad mapped as regular keyboard keys, I flashed new firmware that exposed the gamepad buttons as their own events. Then I set up a listener in Linux that takes the L/R button events and triggers the TTY switching logic.

So now, when you press the L/R gamepad keys you can quickly cycle through the TTYs that load at boot running the various apps.



### License

Any original source code in this repository is licensed under the MIT License. Unless otherwise noted, photographs, graphics, logos, artwork, and other media are not licensed for reuse or redistribution without prior permission. Any third-party projects referenced retain their original licenses.
