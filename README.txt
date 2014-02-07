audio_hdmi_8series
============
OS X Haswell/8 Series/Socket 1150 - HD4600/AMD/Nvidia HDMI Audio
With or Without DSDT Edits

HDMI audio for OS X Haswell HD4600 systems with either: 1. HDMI audio edited dsdt or 2. the Haswell HDMI audio ssdt. Both techniques enable native Haswell graphics power management.  Haswell HDMI audio is not native; AppleHDA.kext and AppleIntelFramebufferAzul.kext require edits (Note 1 and 2, below).
Credit, PikeRAlpha for both fixes.

Supported HDMI audio graphics systems are AMD discrete graphics cards (HD5xxx, HD6xxx), Nvidia discrete graphics cards (4xx, 5xxx and 6xx, 7xx) and Intel HD4600 integrated graphics systems.  The Optimized AppleHDA.kext supports HDMI audio and Realtek audio codecs (ALC887, ALC892, ALC898 and 1150) for onboard audio.  For unsupported onboard audio codecs, the native 10.8.5 AppleHDA.kext supports HDMI audio only when configured properly (Notes 1, 2 and 3a, below).

Requirements (this version, Haswell HDMI audio)
1. AMI Haswell/8 Series/Socket 1150 Intel motherboard
2. Supported OS X versions:
2a. OS X 10.8.5/AppleHDA_v2.4.7 and newer.
2b. OS X 10.9/AppleHDA_v2.5.2 and newer.

Details
[Guide]-Haswell-hdmi_audio_(dsdt_or_ssdt)_v1.2.pdf
[Guide]-NUC-hdmi_audio_(dsdt_or_ssdt)_v1.pdf
[Case_Studies]_AMD-HD7xxx_HDMI_Audio_v1.pdf

Notes
1. Required kext patches:
1b Mavericks/10.9 and newer
1a1. Haswell/AppleHDA.kext_v2.5.2 only edit, use audio_hdmi_hd5K-hda-90_patch.command
1a2. Haswell/AppleIntelFramebufferAzul.kext, use audio_hdmi_hd5k-azul-90_patch.command
1b Mountain Lion/10.8.5
1b1. Haswell/AppleHDA.kext_v2.4.7 only edit, use audio_hdmi_hd5K-hda-85_patch.command
1b2. Haswell/AppleIntelFramebufferAzul.kext, use audio_hdmi_hd5k-azul-85_patch.command
2. Haswell HDMI audio woks with two ML Audio IDs
2a. Audio_ID: 1 supports HD4600/AMD/Nvidia HDMI and 3, 5 and 6 port ALC8xx onboard audio
2b. Audio_ID: 2 supports HD4600/AMD/Nvidia HDMI and 3 port ALC8xx onboard audio
3. For unsupported motherboard audio codecs, the native AppleHDA.kext supports HDMI audio only when configured properly (Notes 1 and 2, as appropriate)
4. Haswell patches must be applied after each software update.  
5. No testing on laptops has been performed to date.
6. 10.8.5 and 10.8.5 Supplemental Update 1.0  (works in 10.9 and newer)
6a. No HDMI audio after wake, restart required. (DP audio OK)

Two OS X Haswell HDMI audio enabling techniques - select one
1. DSDT - Haswell HDMI Audio (with dsdt edits) 
2. SSDT - Haswell HDMI Audio (with native dsdt)

Location.aml - dsdt.aml/ssdt.aml installation folder
1. Chameleon/Chimera - Extra/
2. Clover - EFI/Clover/ACPI/Patched/

DSDT - Haswell HDMI Audio (with dsdt edits) 
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

Installation - edited dsdt.aml to Location.aml 
1. MaciASL/File/Save As…/ACPI Machine Language Binary/Location.aml/dsdt.aml (add extension)
2. Rebuild kernel cache
3. Restart

SSDT - Haswell HDMI Audio (with native dsdt)
1. https://github.com/toleda/audio_hdmi_8series/tree/master/ssdt_8series
2. Copy Downloads/audio_ssdt-hdmi.. . ./SSDT-1.aml to Location.aml
2a. If Location.aml/SSDT.aml is present, install SSDT-1.aml as is: Location.aml/SSDT-1.aml
2b. If no Location.aml/SSDT.aml, rename SSDT-1.aml to SSDT.aml and install as: Location.aml/SSDT.aml
2c. The 1st SSDT is SSDT, 2nd is SSDT-1, 3rd is SSDT-2, etc.; no gaps
3. Enable ssdt
3a. Chameleon/Chimera: Add DropSSDT=Yes to org,chameleon.Boot.plist
3b. Clover: Set DropOem=YES to config.plist/ACPI/SSDT
4. Rebuild kernel cache
5. Restart

Problem Reporting
1. Motherboard/BIOS version/processor/graphics/OS and version
2. Copy of dsdt (if edited)
3. Copy of HDMI audio SSDT (if installed)
4. Copy of IORegistryExplorer

Troubleshooting/Post w/attachments 2-4, above
1. Mavericks/10.9
1a. http://www.tonymacx86.com/hdmi-audio/112469-mavericks-hdmi-audio-applehda.html
1b. http://www.insanelymac.com/forum/topic/292999-mavericks-applehda-hdmi-audio/
2. Mountain Lion/10.8
2a.http://www.tonymacx86.com/hdmi-audio/70762-mountain-lion-hdmi-audio-ami-dsdt.html
2b. http://www.insanelymac.com/forum/topic/291103-mountain-lion-hdmi-audio/

Credit:
PikeRAlpha https://pikeralpha.wordpress.com/2013/09/19/haswell-hdau-solution/
bcc9 Post #11 - http://www.insanelymac.com/forum/topic/290783-intel-hd-graphics-4600-haswell-working-displayport/?p=1934889

OS X Haswell HD4600/AMD/Nvidia HDMI Audio
1a. guides
    [Guide]-Haswell-hdmi_audio_(dsdt_or_ssdt)_v1.2.pdf.zip
    [Guide]-NUC-hdmi_audio_(dsdt_or_ssdt)_v1.pdf.zip
    [Case_Studies]_AMD-HD7xxx_HDMI_Audio_v1.pdf.zip
1b. patches (kext)
    audio_hdmi_hd5k_azul-90_patch.command.zip
    audio_hdmi_hd5k_hda-90_patch.command.zip
    audio_hdmi_hd5k_azul-85_patch.command.zip
    audio_hdmi_hd5k_hda-85_patch.command.zip
    audio_nuc_hdmi-hd5k-azul-90_patch.command.zip    
1b. Patches (dsdt)
    has0-8series-Clean_Compile - fix native dsdt compiler errors
    has1-dsdt-ami-8_series_hdmi_audio-1.txt
    has2-dsdt-ami-8_series_hdmi_audio-2.txt
    has3-dsdt-ami-8_series_add_dsdt-p0p2
    has4-dsdt-8_series_nuc_hdmi_audio-1.txt
1c. ssdts
    audio_ssdt-hdmi-ami_hd5k-amd-nvidia-1_v2.zip
    audio_ssdt-hdmi-ami_hd5k-amd-nvidia-2_v2.zip

toleda
https://github.com/toleda/audio_hdmi_8series
README.txt