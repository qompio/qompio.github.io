## Project Updates:

I figured I'd use this post as a place to organize my thoughts. As an update, I've spent the majority of my non-working quarantine time making a seedbox on my old raspberry pi 3. This has been an amazing learning experience. I have half a tutorial written will finish it up soon. Upon more research, I have found new and improved ways to accomplish my goals.

_DISCLAIMER: I DO NOT CONDONE THE USE OF ANY OF THIS FOR ILLEGAL TORRENTING. THIS IS SOLEY A RESEARCH PROJECT, MEANT ONLY TO SERVE LEGAL TORRENTS._

### My current set-up:
Currently I am running the seedbox on the rpi3. I am using nordVPN as my VPN of choice. After many hours of working through designing a 'kill switch' I found [openpyn](https://github.com/jotyGill/openpyn-nordvpn). This program is absolutely amazing.

I am using deluge as my torrent client.

I mounted a 4TB drive (reformatted to ext4) to the pi, to act as the storage space.

I installed samba file share and mapped the drive to my windows machine.

I am using an old unused laptop to act as my plex server, as I ran into issues serving plex outside my LAN when the VPN was activated (more on this later). I blasted windows 7 right off that bad boy and installed ubuntu 18.04. I mapped this machine to the file share, so the plex is served off the samba file share.

It was about this time that I cried and found god in the internet and network computing. Especially being able to tunnel into both the pi and the samsung from my WSL. Makes me really appreciate computers on a whole other level.

#### Needed updates to this system:
I have been working towards getting sonarr and radarr installed. Life has been throwing other activities in the mix so I haven't had time to fully dive into setting these up. I installed sonarr on the rpi, but haven't linked deluge to it or fully explored sonarr's capabilites. Up until now I have been using fileBot to rename the files in the plex structure. I was so stoked on that program, only to find out sonarr and radarr are free :(.

  *learning costs money*


With sonarr and radarr installed, this would help my file management system which is currently not automated enough. I am setting file storage in deluge by hand. This isn't a big deal but it's not what this project is about. I also corrupted a bunch of .torrent files the other day when rebooting the whole system. I think this was because deluged booted up before my mounted drive, so I fixed the systemd file. I also have suspicions this has to do with renaming files with fileBot. My hope is that sonarr and radarr will be able to hardlink the files to my plex file system while my .torrent files are all in some /downloads folder? _*Need more reading on this subject.*_

## NEW SYSTEM:

I have enjoyed building my current system and there is still much to learn in storage automation. But with more pressing into this whole subculture, I have found even cooler solutions to this problem.

The next stage of this project is looking into running isolated Virtual machines with docker. I could run the seedbox behind the VPN under the VM and run the plex in a separate docker environment. This could consolidate my processes. This is also a great way to learn about docker, which is something that has come up in many internet searches for things I need to learn computing wise.

It has also come to my attention the raspberry pi might not be the best computer for the job!
  * [ODRIOD N2](https://www.hardkernel.com/shop/odroid-n2-with-2gbyte-ram/)
  * [ROCK64](https://www.pine64.org/devices/single-board-computers/rock64/)




*There is a long road ahead. One step at a time*
