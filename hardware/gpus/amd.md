---
label : AMD
---

# AMD GPUs

Although AMD doesn't put as much effort as Intel in bringing Android support, they are still somewhat usable. The best results comes from the post-GCN cards as the kernel driver have support for [Atomic Kernel Mode Setting (aKMS)](https://lwn.net/Articles/653071/)

In this sections, we will split the test results into 2 parts : pre-GCN & post-GCN, each part will split between integrated GPUs (or APU) and discrete GPUs.
- pre-GCN are the cards before using the GCN architechure (such as Terascale), they are using `radeon` kernel drivers with `r300/r600g` [Mesa3d Gallium](https://docs.mesa3d.org/gallium/index.html) driver.<br>
- post-GCN are the one that are using GCN and newer, they are using `amdgpu` kernel driver with `radeonsi` [Mesa3d Gallium](https://docs.mesa3d.org/gallium/index.html) driver.<br>

## pre-GCN

Due to the lack of aKMS on `radeon` kernel driver, drm_hwcomposer will not usable. Which is why all the test with drm_hwcomposer will be 🚫

### Integrated GPUs (APU)

| **Name** | **OpenGLES version** | **Working** | **Tested Gralloc/HWC combination** | **Tested CPU** | [**VA-API**](https://en.wikipedia.org/wiki/Video_Acceleration_API) | **Notes** |
|:---:|:---:|:---:|:---:|:---:|:---:|:---:|

### Discrete GPUs

| **Name** | **OpenGLES version** | **Working** | **Tested Gralloc/HWC combination** | [**VA-API**](https://en.wikipedia.org/wiki/Video_Acceleration_API) | **Notes** |
|:---:|:---:|:---:|---|---|---|
| AMD Radeon 5460 | 3.1 | ✅ | - default (gbm + drmfb) ✅<br>- gbm_nohack ⬛<br>- gbm_noscanout + drm_hwc 🚫<br>- gbm + drm_hwc 🚫<br>- minigbm + drmfb 🚫<br>- minigbm + drm_hwc 🚫<br>- minigbm_gbm_mesa + drmfb ✅<br>- minigbm_gbm_mesa + drm_hwc 🚫 | ⬛ |  |

## post-GCN

### Integrated GPUs (APU)

| **Name** | **OpenGLES version** | **Vulkan version** | **Working** | **Tested Gralloc/HWC combination** | **Tested CPU** | [**VA-API**](https://en.wikipedia.org/wiki/Video_Acceleration_API) | **Notes** |
|:---:|:---:|:---:|:---:|---|---|---|---|

### Discrete GPUs

| **Name** | **OpenGLES version** | **Vulkan version** | **Working** | **Tested Gralloc/HWC combination** | [**VA-API**](https://en.wikipedia.org/wiki/Video_Acceleration_API) | **Notes** |
|:---:|:---:|:---:|:---:|---|---|---|
| AMD Radeon RX 5500XT | 3.2 | 1.1 | ⚠️ | - default (gbm + drmfb) ✅<br>- gbm_nohack ✅<br>- gbm_noscanout + drm_hwc ⚠️<br>- gbm + drm_hwc ⬛<br>- minigbm + drmfb ✅<br>- minigbm + drm_hwc ✅<br>- minigbm_gbm_mesa + drmfb ✅<br>- minigbm_gbm_mesa + drm_hwc ✅ | ✅ | - When removing scanout from gbm_gralloc and use it with drm_hwcomposer, the render is somehow broken https://t.me/hmdumbground/59<br>- Testing Vulkan with 3DMark on recent Mesa version shows some broken render.<br>- On BlissOS 15.8.4 the Camera HAL broke when it's looking for YUV420 color format. |


Explanation : <br>
✅ : Tested device is working fine<br>
⚠️ : Tested device is working, but there are some limitation or require additional workaround<br>
🚫 : Tested device is not working<br>
⬛ : Device is untested<br>
