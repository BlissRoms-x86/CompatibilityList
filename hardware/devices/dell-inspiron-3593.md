---
icon : /assets/oem_logo/dell.png
---

# Dell Inspiron 3593

From some sources, this laptop is made for students or office with its price.

## Tested version

- 0GTW73

## Test result

| Hardware | PCI/USB ID | Working? |
|:---:|:---:|:---:|
| Touchpad |  | ✅ |
| Keyboard |  | ✅ |
| Internal GPU |  | ✅ |
| Webcam |  | ✅ |
| Ethernet |  | ⬛ |
| Bluetooth |  | ✅ |
| SD card slot |  | ⬛ |
| Audio |  | ✅ |
| Wireless |  | ✅ |
| Dedicated GPU |  | 🚫 |

Explanation : <br>
✅ : Tested device is working fine<br>
⚠️ : Tested device is working, but there are some limitation or require additional workaround<br>
🚫 : Tested device is not working<br>
⬛ : Device is untested<br>

## Workaround

### Switch Disk Operation to AHCI

To avoid the boot manager unable to see the disk or initrd to load the system, it is recommend to switch from RAID mode (which is the default) to AHCI instead on Storage -> SATA/NVMe Operation

### Disable Nvidia GPU

The dedicated card inside is MX230 and it's a Muxless GPU. Android doesn't design for hybrid graphics, especially with Muxless GPUs so running Bliss require [blacklist nouveau](/workaround/blacklist-gpu.md) and use Intel iGPU instead or else the graphics will broken.

## Reference

https://www.dell.com/support/home/en-us/product-support/product/inspiron-15-3593-laptop/docs