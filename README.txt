audio_ALC887
============
OS X Realtek ALC887 Onboard Audio

This guide enables OS X Realtek ALC887 onboard audio on Intel based motherboards with a bootable clean install of OS X. The Realtek AppleHDA.kext only works with the codec the kext was edited for and replaces the native AppleHDA.kext.

Requirements
1. Mountain Lion 10.8 - 10.8.4
2. Native S/L/E/AppheHDA.kext (restore native AppleHDA.kext with Combo Update)

Realtek ALC AppleHDA Guides https://github.com/toleda/audio_ALCInjection
[Guide] Add or Edit dsdt/HDEF.pdf
ML-Clover Realtek ALC AppleHDA Injection.pdf 
ML-Realtek ALC AppleHDA Capabilities.pdf
ML-Realtek ALC AppleHDA Screenshots.pdf
ML-Customizing the Realtek AppleHDA.pdf

Two ALC887 versions supported
1. ALC887_v100302 Current - Sandy Bridge/6 Series motherboards and newer
2. ALC887_v100202 Legacy - 5 Series motherboards and older
3. ALC887_v100102 Not supported, use Interim AppleHDA.kext

Three Realtek ALC887 AppleHDA.kext Audio_IDs, select one
Audio_ID: 1 supports 5 and 6 port ALC8xx onboard and/or AMD/Nvidia HDMI audio  
Audio_ID: 2 supports 3 port ALC8xx onboard and/or AMD/Nvidia HDMI audio
Audio_ID: 3 supports 3, 5 and 6 port ALC8xx onboard HD4K/HD3K HDMI audio
		with or without AMD/Nvidia HDMI audio
Audio_IDs: 1 and 2 support analog 5.1 surround sound, 3 does not
Audio_IDs: 1, 2 and 3 require HDMI audio dsdt edits for HDMI audio 

Three techniques enable the Realtek ALC887 AppleHDA.kext, select one
1. no dsdt/audio enabler = Audio_ID, install one enabler, not both
1a. Audio_ID = 1/HDAEnabler1.kext https://github.com/toleda/audio_HDAEnabler1
1b. Audio_ID = 2/HDAEnabler2.kext https://github.com/toleda/audio_HDAEnabler2
2. dsdt/HDEF/layout-id = Audio_ID, Guide] Add or Edit dsdt/HDEF.pdf
2a. Audio_ID = 1/layout-id: 0x01, 0x00, 0x00, 0x00, 0x00
2b. Audio_ID = 2/layout-id: 0x02, 0x00, 0x00, 0x00, 0x00
2c. Audio_ID = 3/layout-id: 0x03, 0x00, 0x00, 0x00, 0x00
3. Clover/Config.plist/PCI/HDAInjection, ML-Clover Realtek ALC AppleHDA Injection.pdf
3a. Audio_ID = 1/HDAInjection=1
3b. Audio_ID = 2/HDAInjection=2
3c. Audio_ID = 3/HDAInjection=3

Download
1. https://github.com/toleda/audio_ALC887
2. Select: Download ZIP

Preparation/Configuration/Installation
1. Downloads/audio_ALC887-master/toledaALC887_patch.txt

Troubleshooting
1. ML-Realtek ALC AppleHDA Capabilities.pdf
2. Post to http://www.insanelymac.com/forum/topic/290796-realtek-alc-applehda-audio-injection/
3. Post to http://www.tonymacx86.com/audio/76309-mountain-lion-multibeast-no-audio-solutions-problem-reporting.html

Credit
THe KiNG 
VHC888
.:ErmaC:.
RevoGirl

toleda
https://github.com/toleda/audio_toledaALC887
toledaALC887_patch_kit
README.txt
Files:
887.zip
