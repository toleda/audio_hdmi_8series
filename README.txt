audio_hdmi_8series
============
OS X Haswell/8 Series/Socket 1150 - HD4600/AMD/Nvidia HDMI Audio
With or Without DSDT Edits

v3: 8/10/2015 - New ssdt method/credit RehabMan, initial 10.11, native CPU/GPU PM and
    Nvidia Maxwell support
v2: 8/15/2014

Update: 10.9.4 requires new AppleHDA patch for OS X Haswell/HD4600 HDMI audio. The v2 patch supports 10.9 and newer. Credit TimeWalker75a

HDMI audio for OS X Haswell HD4600 systems with either: 1. HDMI audio edited dsdt or 2. the Haswell HDMI audio ssdt. Both techniques enable native Haswell graphics power management.  Haswell HDMI audio is not native; AppleHDA.kext and AppleIntelFramebufferAzul.kext require edits.  Credit: PikeRAlpha for both fixes.

Details
[Guide]_HD4600-hdmi_audio_(dsdt_or_ssdt)_v3 
[Guide]_HD4600-hdmi_audio_(dsdt_or_ssdt)_v2 - DEPRECATED
[Guide]_NUC-BRIX-hdmi_audio_(dsdt_or_ssdt)_v2
[Guide]-OSX-hdmi_audio-hdef_audio-dsdt_v3, see https://github.com/toleda/audio_hdmi_guides
[Guide]-OSX-hdmi_audio-hdef_audio-ssdt_v3, see https://github.com/toleda/audio_hdmi_guides

Problem Reporting
1. Required info:
   1. [Guide]_HD4600-hdmi_audio_(dsdt_or_ssdt)_v3.pdf
2. Post to:
   1. http://www.insanelymac.com/forum/topic/301137-yosemite-applehda-hdmi-audio/
   2. http://www.tonymacx86.com/hdmi-audio/143760-audio-hdmi-audio-applehda-guide.html#post886766

Credit:
PikeRAlpha https://pikeralpha.wordpress.com/2013/09/19/haswell-hdau-solution/
bcc9 Post #11 - http://www.insanelymac.com/forum/topic/290783-intel-hd-graphics-4600-haswell-working-displayport/?p=1934889
TimeWalker75a Post #118, http://www.insanelymac.com/forum/topic/290783-intel-hd-graphics-4600-haswell-working-displayport/?p=1949558

toleda
https://github.com/toleda/audio_hdmi_8series
README.txt