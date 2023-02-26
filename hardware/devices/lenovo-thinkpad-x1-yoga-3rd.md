---
icon : /assets/oem_logo/lenovo.png
---

# Lenovo ThinkPad X1 Yoga (Gen 3)

This is a 2-in-1 convertible laptop and it's the 3rd revision of the Thinkpad X1 Yoga series.

## Tested version
- 20LDS0YR00 (20LD)

## Test result

| Hardware | PCI/USB ID | Working? |
|:---:|:---:|:---:|
| Touchpad | (I2C) | ✅ |
| TrackPoint | (I2C) | ✅ |
| Touchscreen | 056a:5144 (?) | ✅ |
| Pen | 056a:5146 | ✅ |
| Keyboard |  | ✅ |
| GPU | 8086:5917 | ✅ |
| Webcam | 04f2:b61e | ✅ |
| Ethernet | 8086:15d7 | ⬛ |
| Bluetooth | 8087:0a2b | ✅ |
| MicroSD card slot | 0bda:0328 | ✅ |
| Audio | 8086:9d71 | ✅ |
| Wireless | 8086:24fd | ✅ |
| Mobile broadband (PCI mode) | 8086:7360 | 🚫 |
| Mobile broadband (USB mode) | 2cb7:0007 | 🚫 |
| Fingerprint Reader | 06cb:009a | 🚫 |


Explanation : <br>
✅ : Tested device is working fine<br>
⚠️ : Tested device is working, but there are some limitation or require additional workaround<br>
🚫 : Tested device is not working<br>
⬛ : Device is untested<br>

## Workaround

None 

## Reference

https://wiki.archlinux.org/title/Lenovo_ThinkPad_X1_Yoga_(Gen_3)
