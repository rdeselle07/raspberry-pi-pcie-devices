---
layout: card
title: "AMD Radeon RX 7600"
picture: "/images/gpu-amd-radeon-rx-7600.jpeg"
functionality_cm4: "None"
functionality_pi5: "Full"
driver_required: "Yes"
github_issue: "https://github.com/geerlingguy/raspberry-pi-pcie-devices/issues/684"
buy_link: https://amzn.to/3OboSn4
videos:
  - https://www.youtube.com/watch?v=AyR7iCS7gNI
  - https://www.youtube.com/watch?v=AyR7iCS7gNI
---
The Radeon RX 7600 is a low-end graphics card supported by the open source `amdgpu` driver in the Linux Kernel.

It requires a 16x PCIe card slot. You will need to supply power to the card directly through a 1x8-Pin PCIe power cable.

### `amdgpu` (open source) driver

To get the amdgpu driver loaded, you have to [recompile the Linux kernel for Pi OS](https://github.com/geerlingguy/raspberry-pi-pcie-devices/tree/master/extras/cross-compile).

Go to `Device Drivers` > `Graphics support` on the `menuconfig` step, and select the `amdgpu` driver to install.

Also make sure you have the AMD firmware installed (`sudo apt install -y firmware-amd-graphics`) or the driver will complain about missing files.

On the Compute Module 4, it doesn't seem we can get `amdgpu` drivers to work with the Pi's PCIe bus.

On the Pi 5, we have tested Coreforge's Pi OS Linux GPU support branch, and it runs great!

See the linked GitHub issue for more details.
