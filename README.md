# Offensive Security Tools in Termux

NO ROOT REQUIRED ;)

[![Powered by JFrog Bintray](./.github/static/powered-by-bintray.png)](https://bintray.com)

There are located packages which were requested, but not added to the
[main][termux-packages] Termux repository due to various reasons. Packages
available here may have lower quality, be unstable or not work at all.

## Pre-Requisite
Each one of this 3 steps needs and independent session, for that just slide from left to rigth in termux for see the option. "New Session"


## 1. Prepare Termux
```ShellSession
pkg install termux-tools
```

```ShellSession
termux-setup-storage
```
```ShellSession
termux-wake-lock && export PATH=/sbin:/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin && export PATH=$PATH:/usr/local/sbin:/usr/local/bin
```

## 2. Install Metasploit + Nmap + Kali:

```ShellSession
pkg install unstable-repo root-repo x11-repo -y && pkg install neofetch coreutils busybox screenfetch -y && screenfetch
```
#
```ShellSession
gem install nokogiri
```
#
```ShellSession
pkg install metasploit -y && pkg update -y && pkg upgrade -y && pkg install python python2 ruby git php perl nmap bash clang nano figlet cowsay curl tar zip unzip tor tsu wget wcalc openssl bmon -y && pkg update -y && pkg upgrade -y && cp $(which pip) $PREFIX/bin/pip3 && neofetch && pkg install wget openssl-tool proot -y && neofetch
```
#
```ShellSession
apt install neofetch -y && neofetch && gem install nokogiri && apt-get autoclean && apt install -f && apt -f install && apt autoremove -y && apt-get clean cache && apt update && apt-get autoclean && apt-get clean cache && apt update && apt update -y && apt full-upgrade -y --allow-downgrades && sudo dpkg --configure -a && grub-mkconfig && cd && neofetch
```
#
```ShellSession
hash -r && wget https://raw.githubusercontent.com/EXALAB/AnLinux-Resources/master/Scripts/Installer/Kali/kali.sh && bash kali.sh && ./start-kali.sh && apt install git apt-utils figlet procps -y && apt-get update --fix-missing && neofetch
```

## 3. Install Bind-apk tool:
```ShellSession
cd && git clone https://github.com/remo7777/Termux-Kali-apktool.git && cd Termux-Kali-apktool && bash setup  
```
## 4. Install Kali Linux NetHunter

```ShellSession
termux-wake-lock;\
termux-setup-storage;\
apt-get update -y;\
apt-get install wget -y;\
wget https://raw.githubusercontent.com/Hax4us/Nethunter-In-Termux/master/kalinethunter;\
bash kalinethunter;\
rm *;\
startkali



apt-key adv --keyserver hkp://keys.gnupg.net --recv-keys 7D8D0BF6;\
wget https://http.kali.org/kali/pool/main/k/kali-archive-keyring/kali-archive-keyring_2018.1_all.deb;\
apt --fix-broken install;\
dpkg -i ./kali-archive-keyring_2018.1_all.deb;\
rm kali-archive-keyring_2018.1_all.deb;\
apt-get update -y;\
apt-get install neofetch lolcat -y;\
echo "neofetch --logo | lolcat;neofetch model distro os kernel shell memory" >> ~/.bashrc;\
echo "PS1='
 ╭──────────[ $(whoami)@$(uname -n) ]─[ $PWD ]
 ╰── • '" >> /etc/bash.bashrc;exit



echo "clear;startkali;exit" >> ~/.bashrc;bash;exit
```

## 5. Update Nokogiri

```ShellSession
gem install nokogiri
```
# Start Nmap + Metasploit Ninja

```ShellSession
apt install neofetch -y && neofetch && neofetch && apt install nmap metasploit-framework coreutils busybox screenfetch python python2 ruby git php perl nmap bash clang nano figlet cowsay curl tar zip unzip tor wget wcalc openssl bmon -y && screenfetch && cd /usr/share/nmap/scripts && git clone https://github.com/scipag/vulscan && git clone https://github.com/vulnersCom/nmap-vulners.git && cd vulscan/utilities/updater/ && chmod +x updateFiles.sh && ./updateFiles.sh && neofetch && cd /opt/metasploit/common/share/nmap/scripts && git clone https://github.com/scipag/vulscan && git clone https://github.com/vulnersCom/nmap-vulners.git && cd vulscan/utilities/updater/ && chmod +x updateFiles.sh && ./updateFiles.sh && screenfetch && apt-get autoclean && apt install -f && apt -f install && apt autoremove -y && apt-get clean cache && apt update && apt-get autoclean && apt-get clean cache && apt update && apt update -y && apt full-upgrade -y --allow-downgrades && sudo dpkg --configure -a && grub-mkconfig && cd && neofetch && msfconsole
```

#
#
#
## (Optional) Building packages manually

You can build all packages manually by using provided docker image. The only
requirements are Linux-based host with Docker installed.

1. Clone this repository:
	```ShellSession
	git clone https://github.com/termux/unstable-packages
	```

2. Enter build environment (will download docker image if necessary):
	```ShellSession
	cd ./unstable-packages
	./start-builder.sh
	```
	Command shown above will start builder for Android 7 (API level 24). If you
	need to build package for Android 5, use `./start-builder-legacy.sh`.

3. Choose package you want to build and run:
	```ShellSession
	./build-package.sh -a ${arch} ${package name}
	```
	Replace `${arch}` with target CPU architecture and `${package name}` with
	package name you want to build.

## Contributing

If you wish to contribute, please take a look on our [contributing guide](./CONTRIBUTING.md).

[termux-packages]: <https://github.com/termux/termux-packages>
