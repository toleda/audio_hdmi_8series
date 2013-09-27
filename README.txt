audio_hdmi_8series
============
OS X Haswell/8 Series/Soclet 1150 HD4600/ AMD/Nvidia HDMI Audio
With or Without DSDT Edits

Mountain Lion HDMI audio for Haswell systems with either: 1. HDMI audio edited dsdt or 2. the Haswell HDMI audio ssdt. Both techniques enable native Haswell graphics power management.  Haswelll HDMI audio is not native; an AppleIntelFramebufferAzul.kext edit is always required as well as an AppleHDA.kext edit.  Credit, PikeRAlpha for both fixes.

Supported HDMI audio graphics systems are AMD discrete graphics cards (HD5xxx, HD6xxx, HD7xxx), Nvidia discrete graphics cards (4xx, 5xxx and 6xx, 7xx) and Intel HD4600 integrated graphics systems.  The Optimized AppleHDA.kext supports HDMI audio and Realtek audio codecs (ALC887, ALC892, ALC898 and 1150) for onboard audio.  The native ML AppleHDA.kext supports HDMI audio only when configured properly. 

Requirements (this version, Haswell HDMI audio)
1. AMI UEFI/Haswell/8 Series/Socket 1150 Intel motherboard
2. OS X 10.8.5 and newer.

Notes
1. Haswell/AppleHDA.kext edit, use audio_hdmi_hd5K-hda-85_patch.command
2. Haswell/AppleIntelFramebufferAzul.kext, use audio_hdmi_hd5k_azul-85_patch.command
3. Haswell HDMI audio woks with two ML Audio IDs
3a. Audio_ID: 1 supports HD4600/AMD/Nvidia HDMI and 3, 5 and 6 port ALC8xx onboard audio
3b. Audio_ID: 2 supports HD4600/AMD/Nvidia HDMI and 3 port ALC8xx onboard audio
4. Haswell patches must be applied after each software update.  
5.No testing on laptops has been performed to date.

More Information
1. Mountain Lion: Optimized AppleHDA for Realtek ALC8xx
2. ML: Haswell/8 Series HDMI Audio

Two ML Haswell HDMI audio enabling techniques - select one
1. ML: Haswell HDMI Audio dsdt (with dsdt edits) 
2. ML: Haswell HDMI Audio ssdt (no dsdt/no dsdt edits)

ML: Haswells HDMI Audio dsdt
1. MaciASL - http://sourceforge.net/projects/maciasl/?source=navbar
2. Configuration: MaciASL/Preferences/Sources/+/
3. URL: https://raw.github.com/toleda/audio_uefi/master
4. Download/ZIP: https://github.com/toleda/audio_hdmi_uefi

Usage
1. If no dsdt; extract dsdt, MaciASL/File/New from ACPI/DSDT
2. MaciASL/File/Open dsdt
3. MaciASL/Patch/taudio_hdmi_8series/Select Patch
4. MaciASL/Patch/Apply (Repeat, as necessary) 
5. MaciASL/Patch/Close
6. MaciASL/Compile
7. MaciASL/File/Save As…/ACPI Machine Language Binary/dsdt.aml

Installation - edited dsdt.aml to Extra
1. MaciASL/File/Save As…/ACPI Machine Language Binary/Extra/dsdt.aml (add extension)
2. Rebuild kernel cache
3. Restart

ML: Haswell HDMI Audio ssdt
1. https://github.com/toleda/audio_hdmi_8series/hdmi_ssdt
2. Copy Downloads/ssdt-ami-8_series_hdmi_audio-1/SSDT-1.aml to Extra
2a. If Extra/SSDT.aml is present, install Downloads/audio_ssdt-uefi_hdmi_v3/SSDT-1.aml as Extra/SSDT-1.aml
2b. If no Extra/SSDT.aml, rename Downloads/audio_ssdt-uefi_hdmi_v3/SSDT-1.aml to SSDT.aml and install as Extra/SSDT.aml
3. Rebuild kernel cache
4. Restart

Guides
1. OS X Haswell HD4600/AMD/Nvidia HDMI Audio
1a. [Guide] ML-8_series-hdmi_audio_(dsdt_or_ssdt)_v1.0
1b. Patches
<<<<<<< HEAD
    ib1. 8series-Clean Compile - fix native dsdt compiler errors for successful dsdt edits
    has1-dsdt-ami-8_series_hdmi_audio-1.txt
    has1-dsdt-ami-8_series_hdmi_audio-2.txt
1c. ssdts
    ssdt-ami-8_series_hdmi_audio-1.zip
    ssdt-ami-8_series_hdmi_audio-2.zip
1c. Troubleshooting/Post to http://www.tonymacx86.com/hdmi-audio/
=======
    ib1. UEFI-Clean Compile - fix native dsdt compiler errors for successful dsdt edits
    uefi1. Desktop-AMD/Nvidia-A1 - AMD/Nvidia HDMI audio dsdt edits
    uefi2. Desktop-HD4K/HD3K/AMD/Nvidia-A3 - HD4000 HDMI audio dsdt edits
    uefi3. Laptop-A3-FB_01 - Laptop HD4K/HD3K HDMI audio dsdt edits
    uefi4. Laptop-A3-FB_03 - Laptop HD4K/HD3K HDMI audio dsdt edits
    uefi5. NUC-HD4K-A1 - NUC HDMI audio edits (2xHDMI and TB)
    ib4. HD4K-on-6_Series_MEI - HD4K MEI dsdt edit (apply once, only with uefi1 - uefi4)
    3b5. HD3K-on-7_Series_MEI - HD3K MEI dsdt edit (apply once, only with uefi1 - uefi4)

Troubleshooting/Post
1. http://www.tonymacx86.com/hdmi-audio/100492-easy-guide-ml-uefi-hdmi-audio.html
2. http://www.insanelymac.com/forum/topic/291103-mountain-lion-hdmi-audio/
>>>>>>> 7a13c3ee5dadb8a29f6b38e1802fab8eaae21673

toleda
https://github.com/toleda/audio_hdmi_8series
Patches
ssdt_8series
README.txt