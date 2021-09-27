# GPU passthrough on optimus-laptop

I create this guide as a reminder for me, and to help people to successfully do a VM with full GPU passthrough on NVIDIA powered laptop with optimus-system.

I'm using Arch so this guide is possible thanks to [the guide of the ArchLinux Wiki](https://wiki.archlinux.org/title/PCI_passthrough_via_OVMF).

For this guide, i'm using a MSI Leopard GP73 8RE. I have an Intel i7-8750h, 16go DDR4 and a GTX 1060 6GB mobile.

## Pre-requisites

- You need a laptop with NVIDIA GPU and using optimus system. This are laptops using processor integrated iGPU and more powerfull NVIDIA dGPU.

- I'm using Manjaro (based on arch) but normally, it works on any linux system, you juste have to thinker a little bit to adapt.

- An external monitor could be useful to check if GPU works as intended.

- Latest NVIDIA driver installed.

## 1. Install

I will using optimus-manager as it's easier to switch between iGPU and dGPU.

1. Update your system: `sudo pacman -Syu`.

2. Install optimus-manager: `sudo pacman -S optimus-manager`. If you're using gnome or kde for example, you can install optimus-manager-qt, as it provides a graphical interface for switching between GPUs. To install, enter `pamac install optimus-manager-qt`. (You need AUR enabled, so you can use yay if you want)

3. Next, install all the dependencies we're using.
   `sudo pacman -S virt-manager libvirt qemu edk2-ovmf`
