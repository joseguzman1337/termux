# Offensive Security Tools for Termux

NO ROOT REQUIRED ;)

[![Powered by JFrog Bintray](./.github/static/powered-by-bintray.png)](https://bintray.com)

There are located packages which were requested, but not added to the
[main][termux-packages] Termux repository due to various reasons. Packages
available here may have lower quality, be unstable or not work at all.

## Pre-Requisite

Storage Free Space = 3.37 GB

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
#
#
#
#
#
## 2. Install Metasploit + Nmap + Kali:

```ShellSession
pkg install unstable-repo root-repo x11-repo ruby -y && pkg install neofetch coreutils busybox screenfetch -y && screenfetch
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
apt install neofetch -y && neofetch && gem install nokogiri && apt-get autoclean && apt install -f && apt -f install && apt autoremove -y && apt-get clean cache && apt update && apt-get autoclean && apt-get clean cache && apt update && apt update -y && apt full-upgrade -y --allow-downgrades && dpkg --configure -a && cd && neofetch
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
#
```ShellSession
cat >> puneet75.sh <<- PUNIT
rm -r -f ~/.bashrc
echo "NAME=\$1" >> ~/.bashrc
echo "export PS1='
\[\033[0;31m\]┌─[\[\033[1;34m\]\\\$NAME\[\033[1;33m\]@\[\033[1;36m\]x\[\033[0;31m\]]─[\[\033[0;32m\]\w\[\033[0;31m\]]
\[\033[0;31m\]└──╼ \[\033[1;33m\]#\[\033[0m\] '" >> ~/.bashrc
echo "export LS_OPTIONS='--color=auto'" >> ~/.bashrc
echo "alias ls='ls --color=auto'" >> ~/.bashrc
echo "alias grep='grep --color=auto'" >> ~/.bashrc
PUNIT

step2

👇
 bash puneet75.sh Puneet89

step 3

👉 source ~/.bashrc
```
#
#
#
#

## 5. Install Nokogiri & Lolcat

From this point in advance execute in the same termux session

```ShellSession
apt install gem ruby -y
```

#
```ShellSession
gem install nokogiri
```

#
```ShellSession
gem install lolcat
```

## 6. Update System

```ShellSession
apt install git -y && git clone https://github.com/4k4xs4pH1r3/bbh.git /usr/share/wordlists && cd /usr/share/wordlists/wordlists && mv *.* /usr/share/wordlists && mv dirb dirbuster fern-wifi wfuzz /usr/share/wordlists && rm -r /usr/share/wordlists/wordlists && cd && apt install neofetch screenfetch -y && neofetch && apt install nmap metasploit-framework asciinema steghide radare2 mtr firmware-realtek -y && screenfetch && apt-get autoclean && apt install -f && apt -f install && apt autoremove -y && apt-get clean cache && apt update && apt-get autoclean && apt-get clean cache && apt update && apt update -y && apt full-upgrade -y --allow-downgrades && sudo dpkg --configure -a && cd && sudo apt-get install python python3 python-pip python3-pip python-dev python-setuptools -y && neofetch && bash <(wget -qO- https://git.io/vAtmB)
```

Close Termux and Open Again

## 7. Start Metasploit

```ShellSession
neofetch && msfdb init && msfconsole
```

```ShellSession
apt-get autoclean && apt install -f && apt -f install && apt autoremove -y && apt-get clean cache && apt update && apt-get autoclean && apt-get clean cache && apt update && apt update -y && apt full-upgrade -y --allow-downgrades && dpkg --configure -a && cd && neofetch
```

#
#
#
# Configure Metasploit Framework 5 

(omnibus Nightly):
```ShellSession
    apt install nmap nginx -y && curl https://raw.githubusercontent.com/rapid7/metasploit-omnibus/master/config/templates/metasploit-framework-wrappers/msfupdate.erb > msfinstall && \
    chmod 755 msfinstall && \
    ./msfinstall
```
Configure the services and database of Metasploit Framework 5:

    su 
    msfupdate
    update-rc.d postgresql enable && update-rc.d nginx enable && service postgresql start 
    su postgres
    createuser root -P
    createdb —owner=root msfdb
    exit
    
Close terminal
   
Open a new terminal as a normal user and verify that services are running and initiate the database of Metasploit Framework 5. 
  #   
    service --status-all
    msfdb init

#
 (for repair use "msfdb reinit")

It's time to open Metasploit Framework 5 (Works in Kali Linux and Ubuntu Cosmic)
   
    /opt/metasploit-framework/bin/./msfconsole

In Parrot Security:

    /usr/share/metasploit-framework/./msfconsole
    
Update and Check Metasploit Framework 5:

    msfupdate
    db_status
    db_rebuild_cache
    load nexpose
    load nessus
    save
#   
#
#
#
 

# 5. Create and Save your workspace

    workspace -a ad
    
    setg Prompt x(%whi%H/%grn%U/%whi%L%grn%D/%whi%T/%grn%W/%whiS%S/%grnJ%J)
    setg ConsoleLogging y
    setg LogLevel 5
    setg SessionLogging y
    setg TimestampOutput true
    save
    exit

Make a backup each time that you need of each one of your workspaces by separately

    db_export -f xml /root/msfuExported.xml

Importing a file from an earlier scan (This is done using db_import followed by the path to our file.)

    db_import /root/msfu/nmapScan
    
# 6. Add Vuln + Vulners + Vulscan NSE as root

Specialized Scripts to get CVE's details with Nmap & Metasploit

    apt install git neofetch screenfetch -y && cd /usr/share/nmap/scripts && git clone https://github.com/scipag/vulscan && git clone https://github.com/vulnersCom/nmap-vulners.git && cd vulscan/utilities/updater/ && chmod +x updateFiles.sh && ./updateFiles.sh && neofetch && cd /opt/metasploit/common/share/nmap/scripts && git clone https://github.com/scipag/vulscan && git clone https://github.com/vulnersCom/nmap-vulners.git && cd /usr/share/nmap/scripts/vulscan/utilities/updater && chmod +x updateFiles.sh && ./updateFiles.sh && cd && screenfetch
    
For display help for the individual scripts use this option
   
    --script-help=$scriptname
   
To get an easy list of the installed scripts, use 

    locate nse | grep nmap
#
#
The db_nmap sessions will be saved in xml for you can restart an early scan using
    
    msfconsole
    msfpro
    db_nmap --resume /root/.msf4/local/file.xml
    
The history of Metasploit commands are here:

    /root/.msf4/history
