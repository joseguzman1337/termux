# Offensive Security Tools for Termux

Is not required to Unlock the Bootloader of Your Device or ROOT your Device ;)

[![Powered by JFrog Bintray](./.github/static/powered-by-bintray.png)](https://bintray.com)
[![Codacy Badge](https://app.codacy.com/project/badge/Grade/12cdb5d6ed82487385bb69104be4f6ee)](https://app.codacy.com/gh/4k4xs4pH1r3/termux/dashboard?utm_source=gh&utm_medium=referral&utm_content=&utm_campaign=Badge_grade)


## Pre-Requisite

Download [F-Droid](https://f-droid.org/F-Droid.apk) on your Android, open it, search Termux, and install it.

Free Storage Space = 33.37 GB

Now open Termux, steps 1, and 2, need to be executed in an independent Termux session, for that just slide from left to right in Termux to see the option. "New Session"

The below documentation is an improvement of this one: https://www.kali.org/docs/nethunter/nethunter-rootless/

## 0. Select Termux CloudFlare Repo
```ShellSession
termux-change-repo
```
#
## 1. Prepare Termux
```ShellSession
pkg update -y && pkg upgrade -y && pkg install termux-tools net-tools iproute2 unstable-repo root-repo x11-repo -y
```
#
```ShellSession
termux-setup-storage
```
#
```ShellSession
termux-wake-lock && export PATH=/sbin:/bin:/usr/local/sbin:/usr/local/bin:/usr/sbin:/usr/bin && export PATH=$PATH:/usr/local/sbin:/usr/local/bin
```
#
## 2. Add Termux Pre-Requisites + Install Kali Linux NetHunter:

```ShellSession
pkg update && pkg install unstable-repo root-repo x11-repo -y && apt update && apt install ruby neofetch coreutils busybox screenfetch vim nano python python-pip nodejs git openssh -y && screenfetch && pkg update -y && pkg upgrade -y && pkg install python python2 ruby git php perl nmap bash which neofetch clang nano figlet cowsay curl tar zip unzip tor tsu wget wcalc openssl bmon -y && pkg update -y && pkg upgrade -y && cp $(which pip) $PREFIX/bin/pip3 && neofetch && pkg install wget openssl-tool proot -y && neofetch && wget -O install-nethunter-termux https://offs.ec/2MceZWr && chmod +x install-nethunter-termux && ./install-nethunter-termux
```
#
## 3. Prepare Kali Linux NetHunter

## Modify DNS settings in /etc/resolv.conf
```ShellSession
sudo sed -i '/nameserver 127.0.0.53/s/^/#/' /etc/resolv.conf && echo -e "nameserver 1.1.1.1\nnameserver 8.8.8.8\n\n# Round Robin\noptions rotate" | sudo tee -a /etc/resolv.conf
```
#
## Replace content of /etc/apt/sources.list with Kali Linux CloudFlare repository
```ShellSession
echo "deb https://kali.download/kali kali-rolling main contrib non-free non-free-firmware" | sudo tee /etc/apt/sources.list
```
#
## Update Kali Linux & Add Vuln + Vulners + Vulscan NSE as root
Specialized Scripts to get CVE's details with Nmap & Metasploit
```ShellSession
sudo apt update -y && sudo apt full-upgrade -y --allow-downgrades && sudo apt install neofetch -y && neofetch && sudo gem install lolcat nokogiri bundle rails && sudo apt-get autoclean && sudo apt install -f && sudo apt -f install && sudo apt autoremove -y && sudo apt-get clean cache && sudo dpkg --configure -a && cd && neofetch && sudo apt update -y && sudo apt full-upgrade -y --allow-downgrades && cd && neofetch && apt install git neofetch screenfetch -y && cd /usr/share/nmap/scripts && git clone https://github.com/scipag/vulscan && git clone https://github.com/vulnersCom/nmap-vulners.git && cd vulscan/utilities/updater/ && chmod +x updateFiles.sh && ./updateFiles.sh && neofetch && sudo pip install --no-cache-dir -U crcmod && sudo apt-get install python2 python2-dev python-dev-is-python3 python3 python3-pip python3-dev python3-setuptools -y && bash <(wget -qO- https://git.io/vAtmB) && neofetch && sudo apt-get autoclean && sudo apt install -f && sudo apt install neofetch -y && sudo apt -f install && sudo apt autoremove -y && apt-get clean cache && sudo apt update && sudo apt-get autoclean && apt-get clean cache && sudo apt update && sudo apt update -y && neofetch
```
#
## If you have plenty of storage space available you might want to run as well
```ShellSession
sudo apt install -y kali-linux-default && sudo apt full-upgrade -y --allow-downgrades && cd && neofetch && apt-get autoclean && apt install -f && apt -f install && apt autoremove -y && apt-get clean cache && apt update && apt-get autoclean && apt-get clean cache && apt update && apt update -y && apt full-upgrade -y --allow-downgrades && dpkg --configure -a && cd && neofetch
```
#
## 5. Install Wordlists + SecLists + Python
```ShellSession
if [ ! -d "/usr/share/wordlists" ]; then sudo mkdir /usr/share/wordlists; fi && \
apt update -y && \
apt install git -y && \
[ -d "/usr/share/wordlists" ] && { sudo mv /usr/share/wordlists /usr/share/wordlists_bck || true; } && \
git clone https://github.com/4k4xs4pH1r3/SecLists.git /usr/share/wordlists && \
[ -d "/usr/share/wordlists_bck" ] && { cd /usr/share/wordlists_bck/ && sudo mv * -u -f /usr/share/wordlists/ || true; } && \
cd /usr/share/ && \
git clone https://github.com/danielmiessler/SecLists.git /usr/share/SecLists && \
cd && \
apt install neofetch screenfetch -y && \
neofetch && \
apt install nmap metasploit-framework asciinema steghide radare2 mtr firmware-realtek net-tools wpasupplicant wireless-tools -y && \
screenfetch && \
apt-get autoclean && \
apt install -f && \
apt -f install && \
apt autoremove -y && \
apt-get clean cache && \
apt update && \
apt-get autoclean && \
apt-get clean cache && \
apt update && \
apt update -y && \
apt full-upgrade -y --allow-downgrades && \
sudo dpkg --configure -a && \
cd && \
neofetch
```
#

## 6. Start Metasploit
#
The db_nmap sessions will be saved in XML so you can restart an early scan using
```ShellSession
msfconsole
```
To resume previus Metasploit session commands is here:
#
```ShellSession
db_nmap --resume /root/.msf4/local/file.xml
```
    
The history of Metasploit commands is here:
```ShellSession
/root/.msf4/history
```    
## 7. Configure the services and database of Metasploit Framework 5:
```ShellSession
su 
msfupdate
update-rc.d postgresql enable && update-rc.d nginx enable && service postgresql start 
su postgres
createuser root -P
createdb —owner=root msfdb
exit
```    
Close Terminal
   
Open a new terminal as a normal user, verify that services are running, and initiate the database of Metasploit Framework 5. 
  #   

```ShellSession
service --status-all
```

It's time to open Metasploit Framework 5 (Works in Kali Linux and Ubuntu Cosmic)

```ShellSession
neofetch && msfdb init && /opt/metasploit-framework/bin/./msfconsole
```

#
 (for repair use "msfdb reinit")

   

## Update and Check Metasploit Framework:

```ShellSession
msfupdate
db_status
db_rebuild_cache
load nexpose
load nessus
save
```
#   
#
#
#
 

## 7. Create and Save your workspace
```ShellSession
workspace -a ad
    
setg Prompt x(%whi%H/%grn%U/%whi%L%grn%D/%whi%T/%grn%W/%whiS%S/%grnJ%J)
setg ConsoleLogging y
setg LogLevel 5
setg SessionLogging y
setg TimestampOutput true
save
exit
```
Make a backup each time that you need each one of your workspaces separately
```ShellSession
db_export -f xml /root/msfuExported.xml
```
#
Importing a file from an earlier scan (This is done using db_import followed by the path to our file.)
```ShellSession
db_import /root/msfu/nmapScan
```

For display help for the individual scripts use this option
```ShellSession
--script-help=$scriptname
```   
To get an easy list of the installed scripts, use 
```ShellSession
locate nse | grep nmap
```

