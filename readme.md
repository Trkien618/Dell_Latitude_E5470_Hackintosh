My hackintosh works on an old laptop, curently running MacOS 12 Monterey, it may work for Big Sur and previous versions (I haven't try yet)
### Specs:
- Intel i5-6300U Sky Lake 6th gen
- HD Graphics 520
- 8GB DDR4 SDRAM 2133MHz (Max supported: 16GB)
- Audio Realtek ALC293
- LAN: Intel Ethernet Connection I219-LM
- Wi-fi card: Intel Wireless-AC 7265
- SSD: SK Hynix SC311 128GB
- PS/2 keyboard and Alps touchpad
### Working
- Graphics
	- iGPU
	- Built-in display
	- Native resolution (use tools like [one-key hidpi](https://github.com/xzhih/one-key-hidpi) or [RDM](https://github.com/avibrazil/RDM) to get hiDPI)
	- Metal supported
	- VDA Decoder fully supported
- External connection
	- USB ports
	- Ethernet
	- Wi-fi
	- HDMI
	- Camera (Photo Booth, FaceTime, Zoom)
- Power
	- Sleep and wake
	- Sleep by close lid
	- Shutdown, restart, sleep from Apple menu
	- Hibernate Mode 3
	- Power button: [Press to turn on your Mac or wake it from sleep. Press and hold for 1.5 seconds to put your Mac to sleep. Continue holding to force your Mac to turn off](https://support.apple.com/en-us/HT201236#sleep)
- Battery
	- Showing percentage
	- Showing capacity/health(CoconutBattery)
	- Charge plug/unplug detected
- CPU 
	- Power Management
	- Temperature sensor
	- Fan sensor and control
- Audio
	- Built-in speaker
	- Built-in microphone
	- Headphones jack (mic broken)
- Touchpad
	- Three fingers gestures (four fingers may not work well)
	- BetterTouchTool
	- Left and right buttons
	- Two fingers scroll
- Keyboard
	- Mute, vol-up, vol-down function keys
 	- Sleep key
	- Brightness keys
	- Backlight
	- Numpad 
	- Trackpoint (hold middle button and use trackpoint to scroll)
- OS features
	- iMessage, FaceTime, App Store, iTunes Store
	- AirPlay (audio, videos, screen extend/mirror)
- Other
	- CFG Lock can be unlock, [read this](https://dortania.github.io/OpenCore-Post-Install/misc/msr-lock.html#disabling-cfg-lock)
	- Boot chimes
### Not working
- D-sub port
- Bluetooth
- AirDrop, Handoff, SideCar (require native supported wi-fi card)
- Keyboard/trackpad/mouse wake, you have to use power button to wake
- SmartCard reader
- No OC theme included because I think it slow down boot process
- Some function keys
# I have a question
#### How to use?
- Create MacOS installer 
- Download EFI folder, get [GenSMBIOS](https://github.com/corpnewt/GenSMBIOS) and generate your own serial number. [Guide](https://dortania.github.io/OpenCore-Install-Guide/config-laptop.plist/skylake.html#platforminfo).
- Then put inside your EFI folder
- Restart and boot into your USB drive and hope it shows the Mac recovery screen
- Install and enjoy
#### Where your SD Card reader?
- It's broken before so i don't need it to work on Mac
#### Will you update kexts, OC,etc?
- Yes I will but occasionally because I think new version are not necessary so just stay in current version.
#### I have a problem/error/stuck
- [Google it](https://www.google.com).
- [Troubleshoot guide](https://dortania.github.io/OpenCore-Install-Guide/troubleshooting/troubleshooting.html)
- [r/Hackintosh](https://www.reddit.com/r/hackintosh/)
- [r/Hackintosh Discord](https://discord.gg/u8V7N5C)
- [Make your own EFI](https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html)
- I'm not a hackintosh expert, some problem I can help you but not all.
#### Can you make X to work?
- If I find out a way to make it works, I will update it.
### BIOS settings
* Press F2 to boot to BIOS, press F12 or Delete for boot menu
* `Restore Settings` then:
- Setting
	- System Configurations
		- Parallel Port: Disabled
		- Sata Operation: AHCI
		- USB Configuration: Enable "Enable USB boot support"
	- Security
		- TPM Security: Disable 
		- CPU XD Support: Enable
		- Intel SGX Enable: Disabled
	- POST Behavior
		- Fastboot: Thorough
	- Virtualization Support
		- Virtualization: Enable
		- VT for Direct I/O/: Disable
