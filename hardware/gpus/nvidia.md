---
label : Nvidia
---

# Nvidia GPUs

Nvidia GPUs has always been a headache to run on Bliss OS. One of the reason is that apart from Nvidia own Terga SoC, there's no official support on Android for Nvidia GPUs.<br>
On Bliss OS (or Android-x86 as a whole), Nvidia GPUs use an open-source driver called `nouveau` (same as [Mesa3d Gallium](https://docs.mesa3d.org/gallium/index.html) driver). The driver is considered unstable compare to the official Nvidia driver on Linux, especially when it comes to reclocking support. `nouveau` can only be able to run in lowest clock speed due to lack of reclocking.

In this section, we will split the test results into 2 parts : laptop GPUs and desktop GPUs. Different from Intel or AMD, all of the current hardware support are using `nouveau`, nothing else.

## Desktop GPUs

| **Name** | **OpenGLES version** | **Vulkan version** | **Working** | **Tested Gralloc/HWC combination** | [**VA-API**](https://en.wikipedia.org/wiki/Video_Acceleration_API) | **Notes** |
|:---:|:---:|:---:|:---:|:---:|:---|:---|
| Nvidia Geforce GTX 1660 Super | 3.1 | N/A | ⚠️ | - default (gbm + drmfb) ⚠️<br>- gbm_nohack ⬛<br>- gbm_noscanout + drm_hwc ⬛<br>- gbm + drm_hwc ⬛<br>- minigbm + drmfb 🚫<br>- minigbm + drm_hwc 🚫<br>- minigbm_gbm_mesa + drmfb ⚠️<br>- minigbm_gbm_mesa + drm_hwc ⚠️ | 🚫 | - On Bliss OS 15.8.4, Launcher3 will crash, But switching to other launcher is fine.<br>- Lots of graphics bug<br>- `vainfo` only show the GPU, meaning that this card isn't ready for hwaccel video decode yet. |

## Laptop GPUs

| **Name** | **OpenGLES version** | **Vulkan version** | **Working** | **Tested Gralloc/HWC combination** | [**VA-API**](https://en.wikipedia.org/wiki/Video_Acceleration_API) | **Tested Hardware** | **Notes** |
|:---:|:---:|:---:|:---:|:---:|:---:|---|---|
| Nvidia GeForce MX230 | N/A | N/A | 🚫 | N/A | 🚫 | - Dell Inspiron 3593 | - This card is Muxless GPU, Android doesn't support hybrid graphics yet. It's better to just blacklist loading `nouveau` for integrated GPUs instead |


Explanation : <br>
✅ : Tested device is working fine<br>
⚠️ : Tested device is working, but there are some limitation or require additional workaround<br>
🚫 : Tested device is not working<br>
⬛ : Device is untested<br>
