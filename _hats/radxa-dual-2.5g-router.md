---
layout: hat
title: "Radxa Dual 2.5G Router HAT"
short_description: A Pi 5 HAT for 2 2.5G network interfaces, NVMe SSD, and an additional PCIe device.
status: prototype
picture: "/images/hat-radxa-dual-2.5g-router.jpg"
github_issue: "https://github.com/geerlingguy/raspberry-pi-pcie-devices/issues/647"
link: "https://docs.radxa.com/en/accessories/dual-2.5-router-hat"
videos: []
---
This HAT includes two 2.5 Gbps Ethernet ports (Realtek 8125BG), an M.2 M-key NVMe slot (2230, 2242, 2260, 2280), an additional PCIe FPC connector (to stack an additional PCIe HAT on top) and a 12V power input.

The interfaces are adapted through an ASM2806 PCIe Gen 3 switch, with 2 uplinks (the Pi 5 can only use 1), and 4 downlinks.

It has a 40 pin GPIO plug, which supplies power to the Pi, and it is not pass-through type, so you would not be able to mount another HAT requiring GPIO on top of this board.

**You must manually enable the external PCIe connector** to get this HAT to work on the Pi 5. Also, if you want Gen 3.0 speeds, also add that setting in `/boot/firmware/config.txt` and reboot:

```
dtparam=pciex1
dtparam=pciex1_gen=3
```

Because this HAT is not 'HAT+' compatible, if you want to [boot from PCIe](https://www.raspberrypi.com/documentation/computers/raspberry-pi.html#boot-from-pcie), you must also edit the Raspberry Pi EEPROM (`sudo rpi-eeprom-config -e`) and add the following line:

```
PCIE_PROBE=1
```

I am currently testing the board and will update this page with more information later.
