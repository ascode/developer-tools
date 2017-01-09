


<a name="vtx" id="vtx">&nbsp;</a>
问题：Enable VT-x in your BIOS security settings, ensure that your Linux distro has working KVM module.  
Looking for SDK updates...
Preparing "Install Intel x86 Emulator Accelerator (HAXM installer)".Downloading https://dl.google.com/android/repository/extras/intel/haxm-macosx_r6_0_5.ziphttps://dl.google.com/android/repository/extras/intel/haxm-macosx_r6_0_5.zip
IntelHAXM_6.0.5.dmg
silent_install.sh
silent_install_readme.txt
Release Notes.txt
HAXM installation
"Install Intel x86 Emulator Accelerator (HAXM installer)" ready.Finishing "Install Intel x86 Emulator Accelerator (HAXM installer)"Installing Intel x86 Emulator Accelerator (HAXM installer) in /Users/jinfei/Library/Android/sdk/extras/intel/Hardware_Accelerated_Execution_Manager"Install Intel x86 Emulator Accelerator (HAXM installer)" complete.Parsing /Users/jinfei/Library/Android/sdk/build-tools/25.0.0/package.xmlParsing /Users/jinfei/Library/Android/sdk/extras/android/m2repository/package.xmlParsing /Users/jinfei/Library/Android/sdk/extras/google/m2repository/package.xmlParsing /Users/jinfei/Library/Android/sdk/extras/intel/Hardware_Accelerated_Execution_Manager/package.xmlParsing /Users/jinfei/Library/Android/sdk/patcher/v1/package.xmlParsing /Users/jinfei/Library/Android/sdk/platform-tools/package.xmlParsing /Users/jinfei/Library/Android/sdk/platforms/android-22/package.xmlParsing /Users/jinfei/Library/Android/sdk/platforms/android-25/package.xmlParsing /Users/jinfei/Library/Android/sdk/sources/android-22/package.xmlParsing /Users/jinfei/Library/Android/sdk/system-images/android-25/google_apis/x86_64/package.xmlParsing /Users/jinfei/Library/Android/sdk/tools/package.xml

Android SDK is up to date.
Unable to install Intel HAXM
/dev/kvm is not found.
Enable VT-x in your BIOS security settings, ensure that your Linux distro has working KVM module.
Done

截图如下：
![](http://image.bgenius.cn/jinfei/github/developer-tools/Screen%20Shot%202017-01-10%20at%202.18.05%20AM.png)  
Just remove the previous HAXM and install IntelHAXM_6.0.3.dmg in haxm-macosx_v6_0_3.zip

here is download link haxm-macosx_v6_0_3.zip

its work for me!


找到一个解决办法如下图：
![](http://image.bgenius.cn/jinfei/github/developer-tools/Screen%20Shot%202017-01-10%20at%202.19.12%20AM.png)

实际上就是如果遇到这个问题，就安装[Intel® Hardware Accelerated Execution Manager End-User License Agreement - macOS*](https://software.intel.com/en-us/android/articles/intel-hardware-accelerated-execution-manager-end-user-license-agreement-macosx)
