# WIFI

This section contains all the wifi cards that are tested, including PCI cards or USB Wifi dongles.

## PCI Cards

These are tested PCI Wifi cards 

|          **Name**          | **Working** | **Tested Hardware**                      | **Notes** |
|:--------------------------:|:-----------:|------------------------------------------|:---------:|
| Intel Wireless 8265 / 8275 |      ✅      | - Lenovo Thinkpad X1 Yoga 3rd Gen (20LD) |           |
| Qualcomm QCA9377           |      ✅      | - Dell Inspiron 3593 (0GTW73)            |           |

## USB Cards/Adapters

These are tested USB Wifi Adapters, here we will list the adapter name first, then the actual card name inside that the adapter is using.

|         **Devices**         | **Card Name**           | **Working** |                                **Notes**                               |
|:---------------------------:|-------------------------|:-----------:|:----------------------------------------------------------------------:|
| TP-Link TL-WN722Nv1         | Qualcomm Atheros AR9271 |      ✅      |                                                                        |
| TP-Link Archer T3U Plus     | Realtek RTL8812BU       |      ⚠️      | - AP Mode is not working, only STA<br>- Can't connect to 5Ghz network. |
| LB-Link BL-WN155A           | Mediatek MT7601U        |      ✅      |                                                                        |
| Generic Adapter (SKU015073) | Realtek RTL8188FTV      |      🚫      | - Driver is available but when plugged in will freeze the entire OS    |


Explanation : <br>
✅ : Tested device is working fine<br>
⚠️ : Tested device is working, but there are some limitation or require additional workaround<br>
🚫 : Tested device is not working<br>
⬛ : Device is untested<br>
