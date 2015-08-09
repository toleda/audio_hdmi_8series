audio_hdmi_8series/ssdt_hdmi-hd4600+
============
OS X Haswell/9 Series/Socket 1150 - HD4600 HDMI Audio ssdt
OS X Haswell/8 Series/Socket 1150 - HD4600 HDMI Audio ssdt

ssdt_hdmi-hd4600+
Supports Desktop/HD4400/HD4600/HD5000/Iris/Iris Pro
Injects Azul/framebuffer: 0x0300220D (DP DP DP)

ssdt_hdmi-hd4600+_AirPlay
Enables Airplay Mirroring without HD4600 graphics
Injects Azul/framebuffer: 0x04001204 (no connectors)

HD 4600 HDMI audio
OS X/Desktop/HD4600 audio is not native, see
[Guide]_HD4600-hdmi_audio_(dsdt_or_ssdt)
https://github.com/toleda/audio_hdmi_8series

Patches/HD4600 HDMI audio:
1. AppleHDA.kext patch required
2. If 1 is true, DP audio is native
3. If 1 is true, HDMI/DVI audio requires AppleIntelFramebufferAzul.kext patch.

HD4600 AirPlay Mirroring is native

Installation (included in download)
1. [Guide]-OSX_ssdt-installation

Problem Reporting: see https://github.com/toleda/audio_hdmi_8series README.txt

toleda
https://github.com/toleda/audio_hdmi_8series/ssdt_hdmi-hd4600+
README.txt