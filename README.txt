audio_hdmi_8series
============
OS X Haswell/8 Series/Socket 1150 - HD4600/AMD/Nvidia HDMI Audio
With or Without DSDT Edits

Mountain Lion HDMI audio for Haswell HD4600 systems with either: 1. HDMI audio edited dsdt or 2. the Haswell HDMI audio ssdt. Both techniques enable native Haswell graphics power management.  Haswelll HDMI audio is not native; AppleHDA.kext and AppleIntelFramebufferAzul.kext require edits (Note 1 and 2, below).
Credit, PikeRAlpha for both fixes.

Supported HDMI audio graphics systems are AMD discrete graphics cards (HD5xxx, HD6xxx, HD7xxx), Nvidia discrete graphics cards (4xx, 5xxx and 6xx, 7xx) and Intel HD4600 integrated graphics systems.  The Optimized AppleHDA.kext supports HDMI audio and Realtek audio codecs (ALC887, ALC892, ALC898 and 1150) for onboard audio.  For unsupported onboard audio codecs, the native 10.8.5 AppleHDA.kext supports HDMI audio only when configured properly (Notes 1, 2 and 3a, below).

Requirements (this version, Haswell HDMI audio)
1. AMI UEFI/Haswell/8 Series/Socket 1150 Intel motherboard
2. OS X 10.8.5/AppleHDA_v2.4.7 and newer.

Details
[Guide] ML-Haswell-hdmi_audio_(dsdt_or_ssdt)_v1.0.pdf

Notes
1. Haswell/AppleHDA.kext_v2.4.7 only edit, use audio_hdmi_hd5K-hda-85_patch.command
2. Haswell/AppleIntelFramebufferAzul.kext, use audio_hdmi_hd5k-azul-85_patch.command
3. Haswell HDMI audio woks with two ML Audio IDs
3a. Audio_ID: 1 supports HD4600/AMD/Nvidia HDMI and 3, 5 and 6 port ALC8xx onboard audio
3b. Audio_ID: 2 supports HD4600/AMD/Nvidia HDMI and 3 port ALC8xx onboard audio
4. For unsupported motherboard audio codecs, the native 10.8.5 AppleHDA.kext supports HDMI audio only when configured properly (Notes 1, 2 and 3a)
5. Haswell patches must be applied after each software update.  
6. No testing on laptops has been performed to date.

Two ML Haswell HDMI audio enabling techniques - select one
1. ML: Haswell HDMI Audio dsdt (with dsdt edits) 
2. ML: Haswell HDMI Audio ssdt (with native dsdt)

ML: Haswells HDMI Audio dsdt
1. MaciASL - http://sourceforge.net/projects/maciasl/?source=navbar
2. Configuration: MaciASL/Preferences/Sources/+/  (copy/paste URL, don't click)
3. URL: https://raw.github.com/toleda/audio_hdmi_8series/master

Usage
1. If no dsdt; extract dsdt, MaciASL/File/New from ACPI/DSDT
2. MaciASL/File/Open dsdt
3. MaciASL/Patch/audio_hdmi_8series/Select Patch
4. MaciASL/Patch/Apply (Repeat, as necessary) 
5. MaciASL/Patch/Close
6. MaciASL/Compile
7. MaciASL/File/Save As…/ACPI Machine Language Binary/dsdt.aml

Installation - edited dsdt.aml to Extra
1. MaciASL/File/Save As…/ACPI Machine Language Binary/Extra/dsdt.aml (add extension)
2. Rebuild kernel cache
3. Restart

ML: Haswell HDMI Audio ssdt
1. https://github.com/toleda/audio_hdmi_8series/tree/master/ssdt_8series
2. Copy Downloads/ssdt-ami-8_series_hdmi_audio-1/SSDT-1.aml to Extra
2a. If Extra/SSDT.aml is present, install Downloads/audio_ssdt-uefi_hdmi_v3/SSDT-1.aml as Extra/SSDT-1.aml
2b. If no Extra/SSDT.aml, rename Downloads/audio_ssdt-uefi_hdmi_v3/SSDT-1.aml to SSDT.aml and install as Extra/SSDT.aml
3. Rebuild kernel cache
4. Restart

Problem Reporting
1. Motherboard/BIOS version/processor/graphics/OS and version
2. Copy of dsdt (if edited)
3. Copy of HDMI audio SSDT ((if installed)
4. Copy of IORegistryExplorer/IOJones
5. Post w/attachments to:
5a. http://www.tonymacx86.com/hdmi-audio/108302-haswell-hdmi-audio.html#post658883
5b. http://www.insanelymac.com/forum/topic/291103-mountain-lion-hdmi-audio/

OS X Haswell HD4600/AMD/Nvidia HDMI Audio
1a. [Guide] [Guide] ML-Haswell-hdmi_audio_(dsdt_or_ssdt)_v1.0
1b. patches (kext)
    audio_hdmi_hd5k_azul-85_patch.command
    audio_hdmi_hd5k_hda-85_patch.command    
1b. Patches (dsdt)
    has0-8series-Clean_Compile - fix native dsdt compiler errors (TBA)
    has1-dsdt-ami-8_series_hdmi_audio-1.txt
    has1-dsdt-ami-8_series_hdmi_audio-2.txt
1c. ssdts
    ssdt-ami-8_series_hdmi_audio-1.zip
    ssdt-ami-8_series_hdmi_audio-2.zip

toleda
https://github.com/toleda/audio_hdmi_8series
README.txt