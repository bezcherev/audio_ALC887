
audio_ALC887
============
OS X Realtek ALC887 Onboard Audio

This guide enables OS X Realtek ALC887 onboard audio on Intel based motherboards with a bootable clean install of OS X. The Realtek AppleHDA.kext only works with the codec the kext was edited for and patches the native AppleHDA.kext.
____________________________________________________________Download ZIP >  > 

v2: 8/18/13 - 10.8.4 Shell Script Realtek ALC887 AppleHDA.kext Patching

Requirements
1. Native S/L/E/AppheHDA.kext (restore native AppleHDA.kext with Combo Update)
2. alc887-84 - Mountain Lion 10.8 - 10.8.4/AppleHDA.kext_v2.3.7

Realtek ALC AppleHDA Guides https://github.com/toleda/audio_ALCInjection
ML-Realtek ALC AppleHDA Capabilities.pdf
ML-Realtek ALC AppleHDA Screenshots.pdf
ML-Customizing the Realtek AppleHDA.pdf

Three Realtek ALC887 AppleHDA.kext Audio_IDs, select one
Audio_ID: 1 supports 5 and 6 port ALC8xx onboard and/or AMD/Nvidia HDMI audio  
Audio_ID: 2 supports 3 port ALC8xx onboard and/or AMD/Nvidia HDMI audio
Audio_ID: 3 supports 3, 5 and 6 port ALC8xx onboard HD4K/HD3K HDMI audio
	with or without AMD/Nvidia HDMI audio
Audio_IDs: 1 and 2 support analog 5.1 surround sound, 3 does not
Audio_IDs: 1, 2 and 3 require HDMI audio dsdt edits for HDMI audio 

Four techniques enable the Realtek ALC AppleHDA.kext, select one
http://www.insanelymac.com/forum/topic/290796-realtek-alc-applehda-audio-injection/
1. No dsdt/audio enabler = Audio_ID, install either kext (use 1a or 1b, not both)
1a. Audio_ID = 1/HDAEnabler1.kext https://github.com/toleda/audio_HDAEnabler1
1b. Audio_ID = 2/HDAEnabler2.kext https://github.com/toleda/audio_HDAEnabler2
2. dsdt/HDEF/layout-id = Audio_ID, see {Guide} Add or Edit dsdt/HDEF.pdf
2a. Audio_ID = 1/layout-id: 0x01, 0x00, 0x00, 0x00, 0x00
2b. Audio_ID = 2/layout-id: 0x02, 0x00, 0x00, 0x00, 0x00
2c. Audio_ID = 3, see dsdt/HD3K/HD4K HDMI audio
3. ssdt/HDEF/layout-id = Audio_ID, see {Guide} Add ssdt/HDEF.pdf
3a. Audio_ID = 1/layout-id: 0x01, 0x00, 0x00, 0x00, 0x00
3b. Audio_ID = 2/layout-id: 0x02, 0x00, 0x00, 0x00, 0x00
3c. Audio_ID = 3, see ssdt/HD3K/HD4K HDMI audio
4. Clover/Config.plist/PCI/HDAInjection, see ML-Clover Realtek ALC AppleHDA Injection.pdf
4a. Audio_ID = 1/HDAInjection=1
4b. Audio_ID = 2/HDAInjection=2
4c. Audio_ID = 3/HDAInjection=3

Download
1. https://github.com/toleda/audio_ALC887
2. Select: Download ZIP (above and right)

Two ALC887 versions supported
1. ALC887_v100302 Current - Sandy Bridge/6 Series motherboards and newer
1a. Use as is: Downloads/audio_ALC887-master
2. ALC887_v100202 Legacy - 5 Series motherboards and older
2a. Make the following changes: Downloads/audio_ALC887-master
2b. Delete 887.zip
2c. Rename 887_v100202.zip to 887.zip
3. ALC887_v100102 Not supported, use Interim AppleHDA.kext

Installation/Shell Script
1. Downloads/audio_ALC887-master/audio_alc887-84_patch.sh
2. Finder/File/Open With/Terminal
3. Enter password at prompt
4. Restart

Troubleshooting
1. ML-Realtek ALC AppleHDA Capabilities.pdf
2. Post to http://www.insanelymac.com/forum/topic/290797-mountain-lion-realtek-alc-applehda-audio/
3. Post to http://www.tonymacx86.com/audio/76309-mountain-lion-multibeast-no-audio-solutions-problem-reporting.html

Credit
THe KiNG 
VHC888
.:ErmaC:.
bcc9
RevoGirl

toleda
https://github.com/toleda/audio_ALC887
audio_alc887-84_patch.sh
README.txt
Files:
887.zip

Details - audio_ALC887-rv-patch script  (see Reqirements)

1. Verify: 
1a. native S/L/E/AppleHDA.kext
1b. Downloads/audio_ALC887-master

2. Rename or Delete (if present)
2a. Desktop/audio-ALC887 to Desktop/audio-ALC887-archive

3. Run script
3a. Downloads/audio_ALC887-master/audio_alc887-84_patch
3b. Finder/Open With/Other/Choose Application/Enable: All Applications
3c. Applications/Utilities/Terminal
3d. Enter Password when requested

4. Terminal/audio_alc887-84_patch window
_____________________________

Last login: Tue Aug 13 19:43:30 on console
$ . . ./Downloads/audio_ALC887-master/audio_alc887-84_patch.sh ; exit;
Prepare Desktop/audio_ALC887 ...
Archive:  887.zip
   creating: 887/
  inflating: 887/Info-84.plist       
 extracting: 887/layout1.xml.zlib    
 extracting: 887/layout2.xml.zlib    
 extracting: 887/layout3.xml.zlib    
  inflating: 887/Platforms.xml.zlib  
Install files ...
Password:
Patch binary ...
Fix permissions ...
Kernel cache...
Finished, restart required.
logout

[Process completed]
___________________________

5. If output is the same, success.  Restart

6. If errors or a different output;
6a. Install Desktop/audio_ALC887/AppleHDA-orig.kext to S/L/E/AppleHDA.kext
6b. Go to Step 1.
