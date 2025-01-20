# GTX 1050 Ti Linux

# 22.04.x LTS

i try to use [LTS](https://en.wikipedia.org/wiki/Long-term_support) releases, </br>
Linux developers also, they delete the source code for Non-LTS releases, </br>
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

i prefer Kernel 6.7 or higher because [Focusrite USB mk2/3 ](https://github.com/geoffreybennett/alsa-scarlett-gui/blob/master/docs/INSTALL.md) drivers are Activated by Default. </br> 

Real GPU is Required for Dual Boot with legacy OS like Windows8.1 in Z790 boards + 12th gen cpu's. </br>
iGPU removed Legacy boot support, works up to 10th gen cpu's, 11th gen CPU's Unknown / Untested. </br>

i like [Unigine Tropics 1.3 (2010)](https://benchmark.unigine.com/tropics) [.run](https://assets.unigine.com/d/Unigine_Tropics-1.3.run) Benchmark for Linux OpenGL </br>
But 24.04.0 has libxrandr v2:1.5.x, Not backward compatible with libxrandr v1.x </br>
making a lot of old software incompatible with 24.04.0 </br>
DOS & W95/98/XP games that were Open sourced by developer & converted to Linux by others, </br>
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

--------------

[pearOS Monterrey (2021.07.01)](https://archive.org/details/pearOS_Monterey_64bit-12-beta-2021.07.01) </br>
based on Ubuntu 20.04.4 LTS </br>
Unigine Tropics works ok, 
intel [i3-10110u](https://www.cpu-monkey.com/en/compare_cpu-intel_core_i3_10110u-vs-intel_core_i3_12100) </br>

Tropics 1.3 works with 20.04.4 & 22.04.4 Only. </br>
Maybe 22.04.5 if using a lower version Nvidia driver, </br>
535 fail, seems 510 is the last driver that works with GTX 1050 Ti </br>
but 22.04.5 does Not have 510, has 470. </br>

Tropics 1.3 does Not work with 24.04.0 </br>
Haven´t tested 20.04.5 </br>

------------------------

[Ubuntu 22.04.0 LTS](https://web.archive.org/web/20220421144653/https://releases.ubuntu.com/22.04/ubuntu-22.04-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.0 LTS](https://web.archive.org/web/20220421153412/https://cdimage.ubuntu.com/kubuntu/releases/22.04/release/kubuntu-22.04-desktop-amd64.iso.torrent) </br>

[Ubuntu 22.04.1 LTS](https://web.archive.org/web/20221225065350/https://releases.ubuntu.com/22.04/ubuntu-22.04.1-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.1 LTS](https://web.archive.org/web/20220819101631/https://cdimage.ubuntu.com/kubuntu/releases/22.04.1/release/kubuntu-22.04.1-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 22.04.1](https://sourceforge.net/projects/ubuntu-cinnamon-remix/files/) </br>

[Ubuntu 22.04.2 LTS](https://web.archive.org/web/20230226173353/https://releases.ubuntu.com/22.04/ubuntu-22.04.2-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.2 LTS](https://web.archive.org/web/20230304093850/https://cdimage.ubuntu.com/kubuntu/releases/22.04.2/release/kubuntu-22.04.2-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 22.04.2](https://sourceforge.net/projects/ubuntu-cinnamon-remix/files/) </br>
"Try Ubuntu Cinnamon" has Aquantia AQtion AQC100 drivers pre-compiled in the Kernel. </br>
Kubuntu 22.04.2 is the best installer, works Flawless, Fast.  </br>
Cinnamon 22.04.2 installer works super slow if cannot find DNS server, Network Manager is different. </br>
Unigine Tropics 1.3 does Not work in 22.04.2 has sh, execp and syntax errors. </br>
updating all apt, Unigine Tropics 1.3 has the same error as 24.04.0 libxrandr v2:1.5.x Not backward compatible with libxrandr v1.x </br> 

[Ubuntu 22.04.3 LTS](https://web.archive.org/web/20231012154014/https://releases.ubuntu.com/22.04/ubuntu-22.04.3-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.3 LTS](https://web.archive.org/web/20230814215535/https://cdimage.ubuntu.com/kubuntu/releases/22.04.3/release/kubuntu-22.04.3-desktop-amd64.iso.torrent) </br>
Kubuntu 22.04.3 Installer Requires Safe Graphics Mode, Wayland Not working, X11 phased out. </br>
22.04.3 is the worse installer. </br>
OS works, but Unigine Tropics 1.3 does Not, has sh, execp and syntax errors. </br>

[Ubuntu 22.04.4 LTS](https://web.archive.org/web/20240618125657/https://releases.ubuntu.com/22.04/ubuntu-22.04.4-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.4 LTS](https://web.archive.org/web/20240225143127/https://cdimage.ubuntu.com/kubuntu/releases/22.04.4/release/kubuntu-22.04.4-desktop-amd64.iso.torrent) </br>
Wayland installer work, but has glitches. </br>
NVIDIA propietary driver 510 work ok. </br>
Unigine Tropics 1.3 works. </br>

[Ubuntu 22.04.5 LTS](https://releases.ubuntu.com/22.04/ubuntu-22.04.5-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.5 LTS](https://cdimage.ubuntu.com/kubuntu/releases/22.04.5/release/kubuntu-22.04.5-desktop-amd64.iso.torrent) </br>
Wayland installer work, but has glitches. </br>
Unigine Tropics 1.3 </br>
3D FAIL, NVIDIA propietary driver 535 </br>
2D Desktop works, but... may have small issues. </br>
3440x1440 160fps </br>
DisplayPort out. </br>

Non-LTS: </br>
[Ubuntu 22.10](https://web.archive.org/web/20231012153418/https://releases.ubuntu.com/mantic/ubuntu-23.10-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.10](https://web.archive.org/web/20240225143127/https://cdimage.ubuntu.com/kubuntu/releases/23.10/release/kubuntu-23.10-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 22.10](https://sourceforge.net/projects/ubuntu-cinnamon-remix/files/) </br>

FireFox / VLC HW acceleration requires All VDPAU GL & Mesa drivers, </br>
or CPU load will be very high decoding h.264 / VP9 / h.265 videos on YT. </br>

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
ASUS XF-C100F SFP+ 10G PCIe, AQC100 </br>
Sonnet 10G Solo PCIe, AQC100 </br>
The board i have: Realtek 2.5GbE </br>

[Ubuntu 24.04.1 LTS](https://releases.ubuntu.com/24.04/ubuntu-24.04.1-desktop-amd64.iso.torrent) </br>
[Kubuntu 24.04.1 LTS](https://cdimage.ubuntu.com/kubuntu/releases/noble/release/kubuntu-24.04.1-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 24.04.1 (Noble Numbat)](https://cdimage.ubuntu.com/ubuntucinnamon/releases/24.04.1/release/ubuntucinnamon-24.04.1-desktop-amd64.iso.torrent) </br>

https://cdimage.ubuntu.com/ubuntucinnamon/releases/24.04.1/release/ </br>

--------------------------

# Debian 12.x Bookworm

[AV Linux 23.x](https://www.bandshed.net/avlinux/)
