# GTX 1050 Ti Linux

i use [LTS](https://en.wikipedia.org/wiki/Long-term_support) releases, </br>
i like Kernel 6.7 or higher because [Focusrite USB mk2/3 ](https://github.com/geoffreybennett/alsa-scarlett-gui/blob/master/docs/INSTALL.md) drivers are Activated by Default. </br> 
but [pearOS Monterrey (2021.07.01)](https://archive.org/details/pearOS_Monterey_64bit-12-beta-2021.07.01) 20.04.4 LTS + [liquorix](https://liquorix.net/) kernel: 6.3.13-1-liquorix-amd64 </br>
20.04 does Not have Gtk4, Focusrite app requires Gtk4 to compile, without Gtk4 ALSA Scarlett Control Panel requires Flatpak version. </br>

32-Bit: </br>
[Unigine Tropics-1.3 (2008-2010)](https://benchmark.unigine.com/tropics) [.run](https://assets.unigine.com/d/Unigine_Tropics-1.3.run) [Benchmark](https://benchmark.unigine.com/) for Linux OpenGL </br>
[Sanctuary-2.3 (2007)](https://benchmark.unigine.com/sanctuary) </br>
64-Bit: </br>
[Heaven-4.0 (2009)](https://benchmark.unigine.com/heaven) </br>
[Valley-1.0 (2013)](https://benchmark.unigine.com/valley) </br>
[Superposition-1.1 (2017)](https://benchmark.unigine.com/superposition) </br>

Heaven works flawless in most systems, most drivers, tested 17.04, 20.04, 22.04 </br>
problem is 32-Bit Tropics-1.3 & Sanctuary, require 32-Bit OpenGL drivers </br>

Latest Nvidia RTX 5000 GPU's removed 32-Bit support for [Physx](https://www.nvidia.com/en-us/drivers/physx/physx-9-23-1019-driver/).[Legacy](https://www.nvidia.com/en-us/drivers/physx/physx-9-13-0604-legacy-driver/).[9.19](https://www.nvidia.com/en-us/drivers/physx/physx-9-19-0218-driver/) </br>
to run 32-Bit games, requires older GPU. </br>

Tropics-1.3 sometimes works flawless, but clean install Fails & [Never works](https://forums.linuxmint.com/viewtopic.php?t=337657) </br>
requires [MesaGL, OpenAL, xorg libs](https://freebsd.pkgs.org/14/freebsd-amd64/linux-unigine-tropics-1.3.pkg.html) but still does Not work, </br>
i think found the problem, but tested all OS without knowing, have to re-test. </br>

Kubuntu 22.04.5 </br>
"worked" when installed something, but unable to reproduce. </br>
Clean install Fail. </br>
same happens with other OS like pearOS, i have other M.2 works flawless, but clean install does Not work. </br>

.run installer needs [X] executable in properties. </br>
creates ~/Downloads/tropics </br>

> copy 1024x768_windowed.sh to 1920x1080_windowed.sh </br>
> edit 1920x1080_windowed.sh
with Tea, Kate, microsoft edit, vim, nano or similar </br>
replace 1024 with 1920, & 768 with 1080 & save. </br>

3440x1440 WQHD monitors: benchmark at 1920x1080 is better windowed. </br>

64-bit OS requires to [Enable 32-bit](https://gitlab.winehq.org/wine/wine/-/wikis/Debian-Ubuntu) architecture: </br>
> sudo dpkg --add-architecture i386 </br>

> $ ./1024x768_windowed.sh </br>
or... </br>
> $ ./1920x1080_windowed.sh </br>

#### Problem #1. 
> App path:  /home/j/AppImage/tropics/bin/ </br>
> Data path: /home/j/AppImage/tropics/data/ </br>
> Save path: /home/j/.Unigine Tropics/ </br>

./tropics/bin/Tropics </br>
does Not detect Data path: /tropics/data </br>
if .run was in a different folder than /Downloads or /home </br>
./tropics/bin/Tropics search for: /tropics/bin/data </br>
but there is Nothing on /tropics/bin/data </br>

copy: /tropics/data to /tropics/bin/data </br>
or... </br>
delete: .cache .log .cfg in Save path: "/.Unigine Tropics" </br>
> $ ./1024x768_windowed.sh </br> 
> </br>
or... </br>
> $ ./1920x1080_windowed.sh </br>

Works! </br>
but... </br>

#### Problem #2. </br>

Nouveau NV driver runs very slow with 1050 Ti, but works ok with intel iGPU 10110u </br>
GTX 1050 Ti also runs very slow with Nvidia propietary driver 570 & 535 </br>
requires driver 470.256.02 </br>
and Legacy GL Support "Libgl1" drivers: </br>
![image](https://github.com/user-attachments/assets/3d7409b7-8bb8-4433-8906-011468566e7e) </br>

Problem: </br>
LibGl1 i386 drivers are Not 100% compatible with All Nvidia & Nouveau drivers, </br>
and Nvidia & Nouveau drivers are Not 100% compatible with All GPU's. </br>

i've seen tropics-1.3 run flawless. </br>
The goal is to run Tropics-1.3 on modern hardware:  </br>
x670e + 7600x </br>
Z790 + i3-12100 / i5-12600 on Linux. </br>

The reason is: </br>
Nvidia GPU's run faster with faster CPU's. </br>
Faster Single-core... </br>
[R15](https://www.cpu-monkey.com/en/cpu_benchmark-cinebench_r15_single_core), [R20](https://www.cpu-monkey.com/en/cpu_benchmark-cinebench_r20_single_core), [R23](https://www.cpu-monkey.com/en/cpu_benchmark-cinebench_r23_single_core), [2024](https://www.cpu-monkey.com/en/cpu_benchmark-cinebench_2024_single_core) </br>
Games load faster in Newer boards with PCIe v4 & PCIe v5 NVMe </br>
PCIe v3 GPU's run very slow on older PCIe v2.0 boards. </br>

IF Unigine Tropics-1.3 does Not work, </br>
Older games like [Batman Arkham Asylum](https://www.gog.com/en/game/batman_arkham_asylum_goty).[steem](https://store.steampowered.com/app/35140/Batman_Arkham_Asylum_Game_of_the_Year_Edition/).[epic](https://store.epicgames.com/en-US/p/batman-arkham-asylum).[wiki](https://en.wikipedia.org/wiki/Batman:_Arkham_Asylum) & [many other](https://en.wikipedia.org/wiki/Category:Video_games_using_PhysX) also does Not work. </br>
requires Linux 32-Bit OpenGL drivers. </br>
32-Bit 3D graphics have issues on Linux. </br>

Unigine Tropics-1.3 on Win8.1x64 & W10 is easy, just needs NET3.5 </br>
Linux is tricky. </br>

Win 32-bit 3D games could run flawless on Wine 9.x because Wine was designed mostly for 32-Bits, </br>
problem is GPU drivers, Not All work for 32-Bits on Linux. </br>

Legal Games require a "middle finger" software like [EA "Origin"](https://www.ea.com/ea-app) or [Steem](https://store.steampowered.com/about/) + useless anti-cheat, that can be bypass with DMA PCIe cards </br>
Those Game Stores are designed for latest 64-Bit Win11 & W10 </br>
Support for Win8.1x64 was Deleted </br>
But Win8.1x64 works ok for 32-Bits </br>

Stores does Not work in W8.1x64. </br>
games work, but... </br>
without store app, games do Not run/install. </br>
Original [DVD](https://archive.org/details/NFSRUN) [installers](https://www.old-games.com/download/11915/need-for-speed-the-run) for [Need for Speed The Run Special Edition](https://www.gog.com/dreamlist/game/need-for-speed-the-run-2011).[moby](https://www.mobygames.com/game/53576/need-for-speed-the-run/).[wiki](https://en.wikipedia.org/wiki/Need_for_Speed%3A_The_Run).[Origin](https://web.archive.org/web/20160322050632/https://www.origin.com/en-us/store/buy/nfs-the-run-2012/pc-download/base-game/standard-edition).[YT](https://www.youtube.com/watch?v=v-4msZsoe18&t=6s) for PC, are almost useless. </br>
game was designed to require Online, Original SE installers were Not designed for W8.1 </br>
game was updated several times & discontinued, updates cannot be downloaded. </br>

Win10 Tropics-1.3 OpenGL had strange results </br>
#### Quadro M6000 24GB | HP Z | lga3647 Platinum CPU </br>
4x Anisotropy: <5500 points. </br>

Other results: </br>
#### GTX 1050 Ti </br>
1920x1080 windowed | High, Trilinear </br>
Linux: 470.256.02 | 7600x CPU + x670e </br>
No Anisotropy: 3538 points. </br>
16x Anisotropy: 3137 points. </br>

#### Win8.1x64 | driver 416 | i3-12100 CPU + Z790 </br>
1920x1080: 3047 points. </br>
3440x1440: 1367 points. </br>
#### Quadro P400 | AMD Opteron 6308 </br>
4x Anisotropy: 965 points </br>
#### Quadro 6000 | AMD Opteron 6308 </br>
4x Anisotropy: 1502 points. </br>
#### Quadro M2000 4GB | AMD Opteron 6308 </br>
4x Anisotropy: 2028 points. </br>
#### Quadro M6000 24GB | AMD Opteron 6308 Supermicro H8SGL </br>
4x Anisotropy: 3364 points. </br>
#### Quadro M6000 24GB | Dual Opteron 6328 "2x8 16-cores" Tyan S8232 | Win8.1 limited to 8-cores </br>
4x Anisotropy: 3811 points. </br>
#### Quadro M6000 24GB | 7600x x670e </br>
4x Anisotropy: 6537 ponts. </br>

---------------

Linux + Lutris + Proton allows to install EA "Origin" & Steem to Run Windows games, </br>
problem is the 32-Bit driver support on Linux. </br>

Ubuntu 17.04 was the last to release a 32-Bit "100% Bios" .iso installer. </br>

Installing 17.04 on VirtualBox 6.1.44 </br>
"works" but VirtualBox 6.1 3D acceleration is incomplete, </br>
does Not have the minimum OpenGL requirements for Unigine Heaven-4.0 </br>
Fails to run. </br>

VirtualBox 6.1 allows to install Win8.1x64 2D works ok. </br>
VirtualBox 7 has a problem with video drivers for Win8.1 </br>

Its a combination lock to make Unigine Tropics-1.3 work. </br>

Unigine Heaven-4.0 works Flawless on 17.04 x64 & 20.04.4 LTS </br>
Problem is pure 32-Bit like Tropics-1.3 </br>

#### Problem #3. </br>

No sound. </br>

Kubuntu installer 22.04.5 does something strange/different when detects Nvidia GPU, vs. iGPU </br>
.iso propietary drivers seem different from nvidia web drivers, </br>
web drivers does Not install easy. </br>

> Loading "libopenal.so.1"... </br>
> ALWrapper::init(): can't load "libopenal.so.1" library </br>
> libopenal.so.1: cannot open shared object file: No such file or directory </br>
> Can't initialize OpenAL wrapper </br>

$ whereis libopenal.so.1 </br>
libopenal.so: /usr/lib/x86_64-linux-gnu/libopenal.so.1 /usr/lib/x86_64-linux-gnu/libopenal.so </br>
$ ls /etc/ld.so.conf.d </br>
fakeroot-x86_64-linux-gnu.conf  i386-linux-gnu.conf  libc.conf  x86_64-linux-gnu.conf </br>
$ sudo cat /etc/ld.so.conf.d/x86_64-linux-gnu.conf </br>
> ####### Multiarch support </br>
> /usr/local/lib/x86_64-linux-gnu </br>
> /lib/x86_64-linux-gnu </br>
> /usr/lib/x86_64-linux-gnu </br>
$ sudo ldconfig </br>


--------------------------

[Unigine Tropics-1.3 (2008-2010)](https://benchmark.unigine.com/tropics)  & [Sanctuary-2.3 (2007)](https://benchmark.unigine.com/sanctuary) require OpenAL, </br>
OpenAL requires manual copy [32-Bit pre-compiled binary OpenAL](https://github.com/Lulu04/ALSound/releases?page=2) to /tropics/bin folder </br>
latest version 3.0.3, but downloaded tested 3.0.0 </br>
Tropics requires i386 libs, in the /tropics/bin folder, but renamed to .so.1 </br>
if Not, gives install OpenAl error: </br>
```
Loading "libopenal.so.1"...
ALWrapper::init(): can't load "libopenal.so.1" library
libopenal.so.1: cannot open shared object file: No such file or directory
Can't initialize OpenAL wrapper
Install latest OpenAL
```

and still does Not work... </br>

installing 32-Bit .so.1 </br>

```
$ ./1024x768_windowed.sh
Loading "/home/j/.Unigine Tropics/unigine.cfg"...
Loading "libGL.so.1"...
Loading "libopenal.so.1"...
ALSA lib conf.c:3722:(snd_config_hooks_call) Cannot open shared library libasound_module_conf_pulse.so (/usr/lib/i386-linux-gnu/alsa-lib/libasound_module_conf_pulse.so: libasound_module_conf_pulse.so: cannot open shared object file: No such file or directory)
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM default
ALExt::init(): can't open device
Set 1024x768 windowed video mode
Set 1.00 gamma value
Unigine engine http://unigine.com/
Binary: Linux 32bit GCC 4.3.2 Release May 20 2010
App path:  /home/j/Downloads/tropics/bin/
Data path: /home/j/Downloads/tropics/data/
Save path: /home/j/.Unigine Tropics/

---- System ----
System: Linux 6.3.13-1-liquorix-amd64 x86_64
CPU: 12th Gen Intel(R) Core(TM) i3-12100 3302MHz MMX SSE SSE2 SSE3 SSSE3 SSE41 SSE42 HTT
GPU: NVIDIA GeForce GTX 1050 Ti PCI Express 470.256.02
System memory: 64167 Mb
Video memory:  4096 Mb

---- MathLib ----
Set SSE3 simd processor

---- Sound ----
NULL
```

installing x64-bit .so.1 </br>
gives wrong ELF class error </br>
```
Loading "libopenal.so.1"...
ALWrapper::init(): can't load "libopenal.so.1" library
libopenal.so.1: wrong ELF class: ELFCLASS64
Can't initialize OpenAL wrapper
Install latest OpenAL

```

also requires manual copy: </br>
> $ cp /usr/lib/i386-linux-gnu/alsa-lib/libasound_module_conf_pulse.so ./bin </br>

and gives a different error: </br>
```
Loading "libopenal.so.1"...
ALSA lib conf.c:3722:(snd_config_hooks_call) Cannot open shared library libasound_module_conf_pulse.so (/usr/lib/i386-linux-gnu/alsa-lib/libasound_module_conf_pulse.so: libmpg123.so.0: wrong ELF class: ELFCLASS64)
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM default
ALExt::init(): can't open device
```
also requires manual copy: </br>
> $ cp /usr/lib/x86_64-linux-gnu/libmpg123.so.0 ./bin </br>

and gives another error: </br>
libmpg123 is 64-bits, requires 32-Bit. </br>
pearOS 12.0.0 updated to Ubuntu 20.04.6 LTS "Focal" comes with 64-Bit [libmpg123](https://sourceforge.net/projects/mpg123/files/mpg123/) [v1.25](http://mpg123.org/download/?V=1&O=D) </br>

installing mpg123 v1.25 :i386 from [Launchpad](https://launchpad.net/ubuntu/+source/mpg123)</br>
requires to satisfy a lot of dependencies, </br>
or from: </br>
$ sudo synaptic </br>
architecture </br>
then tropics gives another error: </br>
```
Loading "libopenal.so.1"...
ALSA lib conf.c:3722:(snd_config_hooks_call) Cannot open shared library libasound_module_conf_pulse.so (/usr/lib/i386-linux-gnu/alsa-lib/libasound_module_conf_pulse.so: libmp3lame.so.0: cannot open shared object file: No such file or directory)
ALSA lib pcm.c:2642:(snd_pcm_open_noupdate) Unknown PCM default
ALExt::init(): can't open device
```
libmp3lame.so.0 </br>
installing libmp3lame0 :i386 from [Launchpad](https://launchpad.net/ubuntu/+source/lame) </br>
> $ sudo dpkg -i libmp3lame0_3.100-3_i386.deb </br>

### Works! </br>
```
---- Sound ----
Renderer: OpenAL Soft
OpenAL vendor:   OpenAL Community
OpenAL renderer: OpenAL Soft
OpenAL version:  1.1 ALSOFT 1.22.0
Found AL_EXT_LINEAR_DISTANCE
Found AL_EXT_OFFSET
Found ALC_EXT_EFX
Found EFX Filter
Found EFX Reverb
Found EAX Reverb
Found QUAD16 format
Found 51CHN16 format
Found 61CHN16 format
Found 71CHN16 format
Maximum sources:         256
Maximum effect slots:    16
Maximum auxiliary sends: 2
```
but does Not solve the slow GPU problem. </br>
same problem 20.04.6 and 22.04.5 </br>
drivers 470 & 535 </br>
i've seen tropics run flawless in 22.04 and 20.04 with driver 510 </br>
but clean install does Not work. </br>
ppa apt rolling repository makes harder clean install. </br>

2 more errors: </br>
```
---- Render ----
GLRender::GLRender(): Unknown GPU
---- Interpreter ----
Version: 2.31
OpenGL error: invalid enum
```
installing Nvidia-510 webdriver, is complicated. </br>
requires to completely dissable Nouveau drivers, </br>
but i've seen Nouveau driver NV137 work flawless in 20.04.4 LTS. </br>

22.04.5 and 24.04.0 Uninstalling default Nvidia driver damages / removes Realtek propietary drivers from Kernel module, </br>
requires compiling [Realtek webdriver](https://www.realtek.com/Download/Index?cate_id=194&menu_id=297) before uninstalling Nvidia default driver. </br>
board has 2.5GbE r8125, but Linux default is: r8169 </br>
$ lsmod | grep r81* </br>
$ rmmod </br>
$ modprobe </br>

[Unigine Tropics-1.3](https://benchmark.unigine.com/tropics) & [Sanctuary-2.3](https://benchmark.unigine.com/sanctuary) does Not work well. </br>
all others work ok.</br>
[Heaven 4.0 (2009)](https://benchmark.unigine.com/heaven) </br>
[Valley 1.0 (2013)](https://benchmark.unigine.com/valley) </br>
[Superposition 1.1 (2017)](https://benchmark.unigine.com/superposition) </br>
but Tropics works flawless sometimes, </br>
i've seen 22.04.3 LTS with 510 Not from installer .iso, Not web driver. </br>
from Software & Update Driver. </br>

somehow [software-properties-qt](https://www.kubuntuforums.net/forum/general/documentation/the-laboratory/674904-software-updates?p=674922#post674922) got uninstalled, </br>
> $ sudo apt install software-properties-qt </br>

or </br>
> $ sudo apt install software-properties-kde </br>
> $ sudo apt install software-properties-gtk </br>

works again. </br>

there is something strange with linux .iso installers, propietary drivers & i386 </br>

--------------------------

There is many DOS/W95/98/XP games that were Open sourced by developers & converted to Linux by others, </br>
80.GB of Games </br>

There has been other mayor changes that break backward compatibility: </br>
Ubuntu 16 had Ext4 v1.x, but Ext4 was upgraded to v2.0 since Ubuntu 17 or 18 </br>
Superblock & Magic Numbers from 32-Bit to 64-Bit and Journal changes. </br>
if you Open an HDD formatted with ext4 v2 in [Ext2Fsb](https://sourceforge.net/projects/ext2fsd/files/Ext2fsd/).[v0.69](https://github.com/LiveMirror/ext2fsd) designed for Ext4 v1.x </br>
will Damage the Superblock & Magic Number </br>
Ext4 v2.0 Requires [Ext2Fsb](https://www.accum.se/~bosse/).[v0.71](https://github.com/bobranten/Ext4Fsd/releases) designed for Ext4 v2 </br>

similar happens with XFS: </br>
XFS developed by sgi for Unix/IRIX, Open sourced and made compatible with Linux </br>
XFS works ok for many years, but has the [2038 bug/limit](https://en.wikipedia.org/wiki/Year_2038_problem) </br>
since xfs_tools v6.x XFS was changed, becoming backward incompatible; </br>
If you open a drive formatted with XFS v5.x and copy the partition with xfs_tools v6.x </br>
will Damage the Superblock, becoming backward incompatible. </br>

for those reasons its recommended to use Gparted / Gnome Disk that comes with the Distribution .iso </br>
[Not the latest Gparted](https://gparted.org/download.php) from website... </br>

other was a special version of libc.so.6 that is only available in Ubuntu 17.x, </br>
if you try to compile software designed for 17 on other version wont compile, </br>
unless its modified, the special version of libc.so.6 cannot be installed on other OS, </br>
because its linked to kernel version and other dependecies only available in 17. </br>
older & newer versions of libc.so.6 in Ubuntu 16 & 18 do Not compile. </br>

--------------

# 20.04.x LTS </br>

[pearOS Monterrey (2021.07.01)](https://archive.org/details/pearOS_Monterey_64bit-12-beta-2021.07.01) </br>
based on Ubuntu 20.04.4 LTS </br>
Unigine Tropics 1.3 works ok,  </br>
intel [i3-10110u](https://www.cpu-monkey.com/en/compare_cpu-intel_core_i3_10110u-vs-intel_core_i3_12100) iGPU </br>
but clean install does Not. </br>
probably installer detects UEFI vs. Normal Boot and also changes other things appart from /boot/efi </br>
maybe installer when installing proprietary Nvidia drivers, also changes other things. </br>


[Tropics 1.3 (2010)](https://benchmark.unigine.com/tropics) works with 20.04.4 & 22.04.1 Only. </br>
Maybe 22.04.5 if using a lower version Nvidia driver, </br>
535 fail, seems 510 is the last driver that works with GTX 1050 Ti </br>
but 22.04.5 does Not have 510, has 470. </br>
requires manual install from [Nvidia archive](https://www.nvidia.com/en-us/drivers/unix/linux-amd64-display-archive/) </br>

Tropics 1.3 does Not work with 24.04.0 </br>
Tested [UbuntuStudio 20.04.5](https://web.archive.org/web/20220901194445/https://cdimage.ubuntu.com/ubuntustudio/releases/20.04.5/release/ubuntustudio-20.04.5-dvd-amd64.iso.torrent) up to 22.04.5 None work. </br>
[Ubuntu Cinnamon 20.04.5](https://sourceforge.net/projects/ubuntu-cinnamon-remix/files/) </br>

FireFox & VLC HW acceleration requires All VDPAU GL & Mesa drivers, </br>
or CPU load will be very high decoding h.264 / VP9 / h.265 videos on YT. </br>

------------------------

[Ubuntu 22.04.0 LTS](https://web.archive.org/web/20220421144653/https://releases.ubuntu.com/22.04/ubuntu-22.04-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.0 LTS](https://web.archive.org/web/20220421153412/https://cdimage.ubuntu.com/kubuntu/releases/22.04/release/kubuntu-22.04-desktop-amd64.iso.torrent) </br>
[UbuntuStudio 22.04.0](https://web.archive.org/web/20220421203035/https://cdimage.ubuntu.com/ubuntustudio/releases/22.04/release/ubuntustudio-22.04-dvd-amd64.iso.torrent) </br>

[Ubuntu 22.04.1 LTS](https://web.archive.org/web/20221225065350/https://releases.ubuntu.com/22.04/ubuntu-22.04.1-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.1 LTS](https://web.archive.org/web/20220819101631/https://cdimage.ubuntu.com/kubuntu/releases/22.04.1/release/kubuntu-22.04.1-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 22.04.1](https://sourceforge.net/projects/ubuntu-cinnamon-remix/files/) </br>
[UbuntuStudio 22.04.1](https://web.archive.org/web/20220824233538/https://cdimage.ubuntu.com/ubuntustudio/releases/22.04.1/release/ubuntustudio-22.04.1-dvd-amd64.iso.torrent) </br>

[Ubuntu 22.04.2 LTS](https://web.archive.org/web/20230226173353/https://releases.ubuntu.com/22.04/ubuntu-22.04.2-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.2 LTS](https://web.archive.org/web/20230304093850/https://cdimage.ubuntu.com/kubuntu/releases/22.04.2/release/kubuntu-22.04.2-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 22.04.2](https://sourceforge.net/projects/ubuntu-cinnamon-remix/files/) </br>
"Try Ubuntu Cinnamon" has Aquantia AQtion AQC100 drivers pre-compiled in the Kernel. </br>
Kubuntu 22.04.2 is the best installer, works Flawless, Fast.  </br>
Cinnamon 22.04.2 installer works super slow if cannot find DNS server, Network Manager is different. </br>
Unigine Tropics 1.3 does Not work in 22.04.2 has sh, execvp and syntax errors. </br>
updating all apt, Unigine Tropics 1.3 has the same error as 24.04.0 libxrandr v2:1.5.x Not backward compatible with libxrandr v1.x </br> 
[UbuntuStudio 22.04.2](https://web.archive.org/web/20230227132827/https://cdimage.ubuntu.com/ubuntustudio/releases/22.04.2/release/ubuntustudio-22.04.2-dvd-amd64.iso.torrent) </br>

[Ubuntu 22.04.3 LTS](https://web.archive.org/web/20231012154014/https://releases.ubuntu.com/22.04/ubuntu-22.04.3-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.3 LTS](https://web.archive.org/web/20230814215535/https://cdimage.ubuntu.com/kubuntu/releases/22.04.3/release/kubuntu-22.04.3-desktop-amd64.iso.torrent) </br>
Kubuntu 22.04.3 Installer Requires Safe Graphics Mode, Wayland Not working, X11 phased out. </br>
22.04.3 is the worse installer. </br>
OS works, but Unigine Tropics 1.3 does Not, has sh, execvp and syntax errors. </br>
[UbuntuStudio 22.04.3](https://web.archive.org/web/20230813114706/https://cdimage.ubuntu.com/ubuntustudio/releases/22.04.3/release/ubuntustudio-22.04.3-dvd-amd64.iso.torrent) </br>

[Ubuntu 22.04.4 LTS](https://web.archive.org/web/20240618125657/https://releases.ubuntu.com/22.04/ubuntu-22.04.4-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.4 LTS](https://web.archive.org/web/20240225143127/https://cdimage.ubuntu.com/kubuntu/releases/22.04.4/release/kubuntu-22.04.4-desktop-amd64.iso.torrent) </br>
Wayland installer work, but has glitches. </br>
NVIDIA propietary driver 510 work ok. </br>
Unigine Tropics 1.3 work ok. </br>
[UbuntuStudio 22.04.4](https://web.archive.org/web/20240223072006/https://cdimage.ubuntu.com/ubuntustudio/releases/22.04.4/release/ubuntustudio-22.04.4-dvd-amd64.iso.torrent) </br>
installer has glitches </br>
Nvidia propietary driver 470 </br> 
Unigine Tropics 1.3 error: libxrandr v2:1.5.x Not backward compatible with libxrandr v1.x </br>
Nvidia NV137 Nouveau Open Source driver: execvp error. </br>

[Ubuntu 22.04.5 LTS](https://releases.ubuntu.com/22.04/ubuntu-22.04.5-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.5 LTS](https://cdimage.ubuntu.com/kubuntu/releases/22.04.5/release/kubuntu-22.04.5-desktop-amd64.iso.torrent) </br>
Wayland installer work, but has glitches. </br>
Unigine Tropics 1.3 </br>
3D FAIL, NVIDIA propietary driver 535 </br>
2D Desktop works, but... may have small issues. </br>
3440x1440 160fps </br>
DisplayPort out. </br>
[UbuntuStudio 22.04.5](https://cdimage.ubuntu.com/ubuntustudio/releases/22.04.5/release/ubuntustudio-22.04.5-dvd-amd64.iso.torrent) </br>
Nvidia propietary driver 470 </br> 
Unigine Tropics 1.3 error: libxrandr v2:1.5.x Not backward compatible with libxrandr v1.x </br>
Nvidia NV137 Nouveau Open Source driver: execvp error. </br>


> $ neofetch --off </br>
> </br>
> OS: Kubuntu 22.04.5 LTS x86_64  </br>
> Host: Z790 LiveMixer  </br>
> Kernel: 6.8.0-40-generic  </br>
> Uptime: 1 day, 1 hour, 44 mins  </br>
> Packages: 2578 (dpkg), 9 (snap)  </br>
> Shell: bash 5.1.16  </br>
> Resolution: 3440x1440  </br>
> DE: Plasma 5.24.7  </br>
> WM: KWin  </br>
> Theme: [Plasma], Breeze [GTK2/3]  </br>
> Icons: [Plasma], breeze-dark [GTK2/3]  </br>
> Terminal: konsole  </br>
> CPU: 12th Gen Intel i3-12100 (4) @ 4.300GHz  </br>
> GPU: NVIDIA GeForce GTX 1050 Ti  </br>
> Memory: 3986MiB / 64161MiB  </br>

https://ubuntu.com/download/alternative-downloads </br>
https://kubuntu.org/alternative-downloads/ </br>
https://cdimage.ubuntu.com/ubuntucinnamon/releases/24.04.1/release/ </br>

-------------------------

# 22.10 Non-LTS: </br>

[Ubuntu 22.10](https://web.archive.org/web/20231012153418/https://releases.ubuntu.com/mantic/ubuntu-23.10-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.10](https://web.archive.org/web/20240225143127/https://cdimage.ubuntu.com/kubuntu/releases/23.10/release/kubuntu-23.10-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 22.10](https://sourceforge.net/projects/ubuntu-cinnamon-remix/files/) </br>

-------------------------

# 23.04 Lunar Lobster </br>

[Ubuntu Cinnamon 23.04.0](https://web.archive.org/web/20230519041234/https://cdimage.ubuntu.com/ubuntucinnamon/releases/23.04/release/ubuntucinnamon-23.04-desktop-amd64.iso.torrent) </br>

-------------------------

# 23.10  </br>

-------------------------

# 24.04.x LTS </br>

I had to reinstall several times,  </br>
Kubuntu 24.04.0 installer does Not allow to install propietary drivers like older installers, </br>
if install nvidia 1st, realtek network cannot be installed later. </br>
if all network devices require propietary drivers, OS becomes offline. </br>
does not allow to "download dependencies" to compile drivers without internet, like [Marvell Aquantia AQtion ACQ100 SFP+ 10G Fiber PCIe](https://github.com/juanpc2018/Aquantia-PCIe-SFP-) </br>
Offline OS requires erase & reinstall, or buy a network device that does not require propietary drivers, nor compile drivers, </br>
tested 8 different brands of network adapters: pcie, usb, wifi, rj45, sfp+ </br>
all require internet. </br>

[Apple USB 2 to RJ45 100Mbps Ethernet Adapter A1277](https://www.apple.com/shop/product/MC704LL/A/apple-usb-ethernet-adapter) has [asix AX88772A](https://www.asix.com.tw/en/support/download) </br>
[Belkin USB 2 to RJ45 100Mbps Adapter F4U047](https://www.belkin.com/support-article/?articleNum=4908) Realtek </br>
Qpcom QP-W24HPUSB "1 Watt" Wi-Fi USB, Realtek RTL8187 </br>
Belkin N300 Wi-Fi USB F9L1002V1 Realtek </br>
TP-Link 150Mbps High Power "1 Watt" Wi-Fi USB TL-WN7200ND, MediaTek Ralink RT3070 </br>
ASUS XG-C100F SFP+ 10G PCIe, AQC100 </br>
Sonnet 10G Solo PCIe, AQC100 </br>
The board i have: Realtek 2.5GbE </br>

[Ubuntu 24.04.1 LTS](https://releases.ubuntu.com/24.04/ubuntu-24.04.1-desktop-amd64.iso.torrent) </br>
[Kubuntu 24.04.1 LTS](https://cdimage.ubuntu.com/kubuntu/releases/noble/release/kubuntu-24.04.1-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 24.04.1 (Noble Numbat)](https://cdimage.ubuntu.com/ubuntucinnamon/releases/24.04.1/release/ubuntucinnamon-24.04.1-desktop-amd64.iso.torrent) </br>

https://cdimage.ubuntu.com/ubuntucinnamon/releases/24.04.1/release/ </br>

--------------------------

Real GPU is Required for Dual Boot with legacy OS like Win8.1 in Z790 boards + 12th gen cpu's. </br>
intel iGPU removed Legacy boot support in 12th gen, works up to 10th gen cpu's, 11th gen CPU's Unknown / Untested. </br>


Linux developers delete source code for Non-LTS releases </br>
example: Ubuntu 23.10 (Mantic Minotaur) </br>
released on 12 October 2023, supported for nine months until July 2024. </br>
[Source code Deleted](https://cdimage.ubuntu.com/releases/23.10/release/source/) January 2025. </br>
to me it´s insane to delete source code, goes against the laws of [Reversible Computing](https://en.wikipedia.org/wiki/Reversible_computing) </br>
but thats one of the ways they have to keep open source closed as possible. </br>
other methods like robots.txt to stop [archive.org](https://web.archive.org/web/20240303064513/https://cdimage.ubuntu.com/releases/23.10/release/source/) to make a [copy](https://web.archive.org/web/20240421133031/http://cdimage.ubuntu.com/releases/mantic/release/source/) </br>
other is to hide the directory, stop mirrors, etc... </br>
i wish i could find [10.04.4](https://archive.org/download/ubuntu-repo-lucid-lynx-10.04-20210302) and [10.10](https://archive.org/download/ubuntu-repo-maverick-meerkat-10.10-20210302) [source](https://old-releases.ubuntu.com/releases/releases/) to see the changes, </br>
[Ubuntu Version History](https://en.wikipedia.org/wiki/Ubuntu_version_history) </br>
[Ubuntu old-releases](http://old-releases.ubuntu.com/releases/) </br>

for VLC developers: Non-LTS = LTS </br> 
they link [VLC version to OS version](https://packages.ubuntu.com/search?searchon=sourcenames&keywords=vlc) </br>


[AV Linux 23.x](https://www.bandshed.net/avlinux/)
