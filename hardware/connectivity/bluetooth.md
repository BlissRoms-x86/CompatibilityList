# Bluetooth

This section contains all the Bluetooth cards that are tested, including both PCI or USB one.

## PCI Cards

These are tested Bluetooth PCI cards, usually it's wifi card but integrated with bluetooth.

|          **Name**          | **Working** | **Max Bluetooth version** | **Tested Hardware**                      |                                       **Notes**                                       |
|:--------------------------:|:-----------:|:-------------------------:|------------------------------------------|:-------------------------------------------------------------------------------------:|
| Intel Wireless 8265 / 8275 |      ✅      |                           | - Lenovo Thinkpad X1 Yoga 3rd Gen (20LD) | - Although it connected using PCI, the Bluetooth part is using USB interface instead. |
| Qualcomm QCA9377           |      ✅      |                           | - Dell Inspiron 3593 (0GTW73)            |                                                                                       |

## USB Cards

These are tested Bluetooth USB cards, here we will list the usb device name first then the actual card name.

|  **Devices**  |               **Card Name**              | **Working** | **Max Bluetooth version** |                                                          **Notes**                                                          |
|:-------------:|:----------------------------------------:|:-----------:|:-------------------------:|:---------------------------------------------------------------------------------------------------------------------------:|
| Orico BTA-403 | Cambridge Silicon Radio Bluetooth Dongle |      ✅      |                           | - When connect to a device like a speaker, after reboot you can't be able to connect it again unless you forget the speaker |


Explanation : <br>
✅ : Tested device is working fine<br>
⚠️ : Tested device is working, but there are some limitation or require additional workaround<br>
🚫 : Tested device is not working<br>
⬛ : Device is untested<br>

***Max Bluetooth version** is the maximum version that the OS support, not the card limitation*