# Homelab Setup — Night 1

## What I set out to do
Build the start of a home lab: a Kali Linux VM in VirtualBox on my Mac, 
and Pi-hole running on a Raspberry Pi for DNS monitoring.

## What happened
- Downloaded VirtualBox and Kali; discovered Kali now ships as a .7z 
  archive instead of .ova — had to extract it and use Machine > Open 
  (formerly "Add") to import the .vbox file directly.
- Ran into an interrupted apt upgrade after my laptop went to sleep 
  mid-update, requiring `dpkg --configure -a` to recover.
- Installed Pi-hole on a Raspberry Pi running Bookworm — the installer's 
  static IP step failed because Bookworm uses NetworkManager instead of 
  dhcpcd. Set a static IP manually with `nmtui` instead.
- Installed VirtualBox Guest Additions in Kali; screen auto-resize is 
  still not working perfectly despite Guest Additions installing 
  successfully and the Graphics Controller set to VMSVGA.

## How I fixed it
- Used `Machine > Open` on the extracted `.vbox` file instead of File > 
  Import Appliance (which is only for `.ova` files).
- Let `dpkg --configure -a` finish rather than force-quitting it again.
- Set a static IP directly on the Pi via `nmtui` (Manual IPv4, address/
  gateway/DNS) instead of relying on the Pi-hole installer or router 
  admin page — my ISP's router doesn't expose a usable local admin page.

## What I learned
- Distro/tool packaging changes over time (7z vs ova) — always check 
  what you actually downloaded before following a guide verbatim.
- Raspberry Pi OS Bookworm's networking stack (NetworkManager) is a 
  common source of outdated-tutorial mismatches; nmtui/nmcli are the 
  current tools, not dhcpcd.conf.
- Snapshots in VirtualBox are worth taking immediately after a clean, 
  updated install — cheap insurance before doing anything risky.

## Still open
- Pi-hole isn't showing live traffic yet — likely DNS-over-HTTPS in the 
  browser bypassing system DNS settings. Debugging tomorrow with `dig`.

## In My Own Words 
-To start I previously built a small "cyber deck" if you can even call it that, it is 
raspberry pi5 with a 2.8in capacitive touchscreen attached to it as well as a PiSugar 
Battery. I call it the PiStack, and this is what was sued for the PiHole installation and 
what I will be using for the DNS Monitoring 
-Like everything I seem to set out to do in the tech world, setup was a lot longer then 
expected. Was hoping to learn more about git and start putting together a tech resume but 
was consumed with troubleshooting the virtual machine and PiHole setup. 
-Tomorrow I intend to learn more about GitHub, fix the minor issues I left alone tonight
in the virtual box and fix the PiStack running PiHole so I can monitor live traffic, because
for some reason it was not working. 
