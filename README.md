# EFI-OC-DELL-OPTIPLEX3046-skylake-I3-6100-HD530-os11-12.6.2
update oc094,os11.6.8
alcid=11,27
DELL-OPTIPLEX3046-
skylake
I3-6100-
HD530-
os11.6.8
gt710/rx560d/hd530 all well and update to 13.1 is best too.
ithwlan is good,
bluetoothfixup is well .
2308291411dellop3046h110i36100hd530-gt710 rx560d								
			bios dell optiplex 1.15.0					
1	settinggeneral		boot list option		uefi			
2			UEFI BOOT PATH  SECURITY		NEVER			
3	SUSTERM CONFIGURATION		SERIAL PORT		DISBabled			
4			sata operation		ACHI			
5			MISCELLANEOUS DEVICES		ENABLE DEDIA CARD			
6	VDIEO		MULTI-DUSPLAY		ENABLE MUTI-DISPLAY	yes		
7			primary display		auto			
8					intel HD graphics			
9					NVida HD GRAPHICS			
10								
11	SECUREBOOT		SECURE boot ENABLE		DIABLED			
12	INTEL SOFTWARE GUARD EXTENSIONS		INTEL @ SGXENABLE		ENABLED			
13			ENCLAVE MEMORY SIZE		32MB,64MB,v 128MB			
14	virtalization		virtalization		enabledIntelvt			
15			vt-direct I/O		DISBabled			
16	POST BEHAVIOR		FASt boot		MINIMAL			
17	SSR		ATUO OS RECOVERY T		2			
18	BIOS设置：	ww	BIOS5.2G BIOS设置：			注释：		
19								
20	隐藏		CFG LOCK ,		DISABLED			
21			Cfg lock		，disable。	（未解锁     ,OCEFIuefi-quirks  -appleCpuPmCfgloc/ appleXcmpCfglock/两项需勾选）。		

2308291411dellop3046h110i36100hd530-gt710 rx560d							
1	acpi		add		SSDT-PLUG-_PR.CPU0.aml		
2			add		SSDT-EC-USBX.aml		
3			add		SSDT-OLARILA.aml		
4			add				
5			add				
			quirks选项		fadtenablereset,normalizeheaders,rebase regions		
10	booter		Quirks选项		1-8th默认设置+syncruntimepermissions		
11	dp	1	 | PciRoot(0x0)/Pci(0x2,0x0) | 		 | AAPL,ig-platform-id | Data | 01001219 | 		
18	kernel patch	1	Lilu.kext				
19		2	VirtualSMC.kext			RX6650XT显卡  填入FF73000	
20		3	WhateverGreen.kext			RX6950XT显卡  填入BF73000	
21		4	IntelMausi.kext				
22		5	XHCI-unsupported.kext				
23		6	RealtekRTL8111.kext				
24		7	USBInjectAll.kext				
25		8	SMCProcessor.kext				
26		9	SMCSuperIO.kext				
27		10	NVMeFix.kext				
28		11	AppleALC.kext				
29		12	VoodooPS2Controller.kext				
30		13	VoodooPS2Controller.kext/Contents/PlugIns/VoodooInput.kext				
31		14	VoodooPS2Controller.kext/Contents/PlugIns/VoodooPS2Keyboard.kext				
32		15	VoodooPS2Controller.kext/Contents/PlugIns/VoodooPS2Mouse.kext				
33		16	VoodooPS2Controller.kext/Contents/PlugIns/VoodooPS2Trackpad.kext				
34		17	SMCDellSensors.kext				
35		18	Display-756e6b6e-717.kext				
36		19	RtWlanU.kext				
37		20	RtWlanU1827.kext				
39	kernel patch		Quirks选项		6THdell默认设置  +APPLEXCPMCFGLOCK-xhciportlimit		
40	NVRAM		 | 4D1EDE05-38C7-4A6A-9CC6-4BCCA8B38C14 | 		 | DefaultBackgroundColor | Data | 00000000 | 		
41					 | UIScale | Data | 01 | 		
42			 | 4D1FDA02-38C7-4A6A-9CC6-4BCCA8B30102 | 		 | revcpu | Number | 1 | 		
43					 | revcpuname | String | 6th Gen Intel(R) 2-Core(TM) i3-6100		
44					 | rtc-blacklist | Data |  | 	 | DefaultBackgroundColor | 	
45			 | 7C436110-AB2A-4BBB-A880-FE41995C9F82 | 		# | ForceDisplayRotationInEFI | Number | 0 | 		
46					# | SystemAudioVolume | Data | 46 | 	 | rtc-blacklist | 	
47					 | boot-args | String | nvda_drv=1 alcid=11 igfxonln=1  igfxmetal=1 | 	 | revcpu | 	
48					 | csr-active-config | Data | FF0F0000 | 	 | revcpuname | 	
49					 | prev-lang:kbd | String | zh-Hans:252 | 	 | boot-args | 	
					 | nvda_drv | Data | 31 | 		
50					 | run-efi-updater | String | No | 	 | ForceDisplayRotationInEFI | 	
51	PI		GENERIC		SystemProductName:iMac17,1    Intel Core i5-6500 @ 3.20 GHz		
52			GENERIC		ProcessorType:0		
53			GENERIC		ATUOMATIC,UPDATESMBIOS,UPDATEHUB,UPDATENVRAM,UPDATESMBIOSMODECUSTOM		
54			PROTOCOIOVERRIDES		FIRMWAREvolume		
55			Quirks选项		enablevectoracceleration,releaseusbowership,requestbootvartouting		
56					resizegpubars 5(0-10)		
57			RDNA,需要加入吗				
58	UEFI		Bios未开启cfglockdisable。		Kernel-quirks-appleCpuPmCfglock,appleXcmpCfglock =yes.		
59			Bios,resizable-Bar=yes,		uefi-quirks-resizaGpuBars=x，		
60			Ax101，ax210WiFi，《=VENTURA 		kernel=airportItlwm.kext2.20,	2^1=2，2^2=4，2^3=8，2^4=16，2^5=32,2^6=64,2^7=128,2^8=256,2^9=512,2^10=1024	
61	Acpi-ssdt定制		 patch| com.apple.driver.AppleRTC | 			五国	
62			 | F1 Startup patch | 1 | true | 75330FB7 | 0 |  | EB330FB7 |  | 0 | 			管理时间	
63			ProcessorType		3842/3841	13400	
64					3842	13600kf	
65					1538	12400	
66					4105	10900es	
67					4091	10900es	
