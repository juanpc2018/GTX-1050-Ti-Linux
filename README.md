# GTX 1050 Ti Linux

# 22.04.x LTS

i try to use [LTS](https://en.wikipedia.org/wiki/Long-term_support) releases, </br>
and Linux developers also, they delete the source code for Non-LTS releases, </br>
example: Ubuntu 23.10 (Mantic Minotaur) </br>
released on 12 October 2023, supported for nine months until July 2024. </br>
[Source code](https://cdimage.ubuntu.com/releases/23.10/release/source/) Deleted January 2025. </br>
to me it´s insane to delete source code, goes against the laws of [Reversible Computing](https://en.wikipedia.org/wiki/Reversible_computing) </br>
but thats one of the ways they have to keep open source closed as possible. </br>
other methods like robots.txt to stop [archive.org](https://web.archive.org/web/20240303064513/https://cdimage.ubuntu.com/releases/23.10/release/source/) to make a copy. </br>
other is to hide the diractory, stop mirrors, etc... </br>
i wish i could find 10.04 and 10.10 source code, and older to see the changes, </br>
[Ubuntu Version History](https://en.wikipedia.org/wiki/Ubuntu_version_history) </br>

for VLC developers: Non-LTS = LTS </br> 
they link VLC version to [OS version](https://packages.ubuntu.com/search?searchon=sourcenames&keywords=vlc) </br>

i prefer Kernel 6.7 or higher because [Focusrite USB mk2/3 ](https://github.com/geoffreybennett/alsa-scarlett-gui/blob/master/docs/INSTALL.md) drivers are Activated by Default. </br> 

Real GPU is Required for Dual Boot legacy OS like Windows8.1 in Z790 boards + 12th gen cpu's. </br>
iGPU removed Legacy boot support, works up to 10th gen cpu's, 11th gen CPU's Unknown / Untested. </br>

i like [Unigine Tropics 1.3 (2010)](https://benchmark.unigine.com/tropics) [.run](https://assets.unigine.com/d/Unigine_Tropics-1.3.run) Benchmark for Linux OpenGL </br>
But 24.04.0 has libxrandr v2, Not backward compatible with libxrandr v1.x </br>
making a lot of old software incompatible with 24.04.0 </br>
Like Uninige Tropics </br>

[Ubuntu 22.04.0 LTS](https://web.archive.org/web/20220421144653/https://releases.ubuntu.com/22.04/ubuntu-22.04-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.0 LTS](https://web.archive.org/web/20220421153412/https://cdimage.ubuntu.com/kubuntu/releases/22.04/release/kubuntu-22.04-desktop-amd64.iso.torrent) </br>

[Ubuntu 22.04.1 LTS](https://web.archive.org/web/20221225065350/https://releases.ubuntu.com/22.04/ubuntu-22.04.1-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.1 LTS](https://web.archive.org/web/20220819101631/https://cdimage.ubuntu.com/kubuntu/releases/22.04.1/release/kubuntu-22.04.1-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 22.04.1](https://sourceforge.net/projects/ubuntu-cinnamon-remix/files/) </br>

[Ubuntu 22.04.2 LTS](https://web.archive.org/web/20230226173353/https://releases.ubuntu.com/22.04/ubuntu-22.04.2-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.2 LTS](https://web.archive.org/web/20230304093850/https://cdimage.ubuntu.com/kubuntu/releases/22.04.2/release/kubuntu-22.04.2-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 22.04.2](https://sourceforge.net/projects/ubuntu-cinnamon-remix/files/) </br>
"Try Ubuntu Cinnamon" has Aquantia AQtion AQC100 drivers pre-compiled in the Kernel. </br>

[Ubuntu 22.04.3 LTS](https://web.archive.org/web/20231012154014/https://releases.ubuntu.com/22.04/ubuntu-22.04.3-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.3 LTS](https://web.archive.org/web/20230814215535/https://cdimage.ubuntu.com/kubuntu/releases/22.04.3/release/kubuntu-22.04.3-desktop-amd64.iso.torrent) </br>
Kubuntu 22.04.3 Installer Requires Safe Graphics Mode, Wayland Not working, X11 is phased out. </br>

[Ubuntu 22.04.4 LTS](https://web.archive.org/web/20240618125657/https://releases.ubuntu.com/22.04/ubuntu-22.04.4-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.4 LTS](https://web.archive.org/web/20240225143127/https://cdimage.ubuntu.com/kubuntu/releases/22.04.4/release/kubuntu-22.04.4-desktop-amd64.iso.torrent) </br>
Wayland installer work, but has glitches.  </br>
NVIDIA propietary driver 510 work ok. </br>

[Ubuntu 22.04.5 LTS](https://releases.ubuntu.com/22.04/ubuntu-22.04.5-desktop-amd64.iso.torrent) </br>
[Kubuntu 22.04.5 LTS](https://cdimage.ubuntu.com/kubuntu/releases/22.04.5/release/kubuntu-22.04.5-desktop-amd64.iso.torrent) </br>
Clean Install  </br>
3D FAIL, NVIDIA propietary driver 535 </br>
2D Desktop works, but... may have small issues. </br>
3440x1440 160fps </br>
DisplayPort out. </br>

Non-LTS: </br>
[Ubuntu 22.10](https://web.archive.org/web/20240618125657/https://releases.ubuntu.com/23.10/ubuntu-23.10-desktop-amd64.iso.torrent) <>/br
[Kubuntu 22.10](https://web.archive.org/web/20240225143127/https://cdimage.ubuntu.com/kubuntu/releases/23.10/release/kubuntu-23.10-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 22.10](https://sourceforge.net/projects/ubuntu-cinnamon-remix/files/) </br>

FireFox / VLC HW acceleration requires All VDPAU GL & Mesa drivers, </br>
or CPU load will be very high decoding h.264 / VP9 / h.265 videos on YT. </br>

> $ neofetch --off </br>
>   </br>
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
OS becomes offline, requires erase & reinstall, or buy a network device that does not require propietary drivers, nor compile drivers, </br>
i tested 7 different brands of network adapters: pcie, usb, wifi, rj45, sfp+ </br>
all require internet. </br>
The board i have, also has realtek. </br>
[Apple USB2.0 to RJ45 100Mbps Ethernet Adapter](https://www.apple.com/shop/product/MC704LL/A/apple-usb-ethernet-adapter) has [AX88772A](https://www.asix.com.tw/en/support/download) </br>
[Belkin USB 2.0 100Mbps Adapter F4U047 v1](https://www.belkin.com/support-article/?articleNum=4908)
ASUS SFP+ 10G, Sonnet 10G Solo, etc... </br>

[Ubuntu 24.04.1 LTS](https://releases.ubuntu.com/24.04/ubuntu-24.04.1-desktop-amd64.iso.torrent) </br>
[Kubuntu 24.04.1 LTS](https://cdimage.ubuntu.com/kubuntu/releases/noble/release/kubuntu-24.04.1-desktop-amd64.iso.torrent) </br>
[Ubuntu Cinnamon 24.04.1 (Noble Numbat)](https://cdimage.ubuntu.com/ubuntucinnamon/releases/24.04.1/release/ubuntucinnamon-24.04.1-desktop-amd64.iso.torrent) </br>

https://cdimage.ubuntu.com/ubuntucinnamon/releases/24.04.1/release/ </br>
