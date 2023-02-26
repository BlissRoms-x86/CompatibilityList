---
label : Intel
---
# Intel GPUs

Intel Graphics is considered the best GPU to run on Bliss OS or Android-x86. Due to the fact that Intel does put a lot of effort in bringing Android to x86 platform, especially their hardware. 

In this sections, the test results will split into 3 part : pre-Skylake, post-Skylate and discrete GPU (For example: Intel ARC). We split between pre-Skylate and post-Skylake because although they are using the same kernel driver (i915), [Mesa3d Gallium](https://docs.mesa3d.org/gallium/index.html) has 2 different graphics drivers. One is `crocus` (pre-Skylake) and one is `iris` (post-Skylake). 

## pre-Skylake 

|        **Name**        | **OpenGLES version** | **Vulkan version** | **Working** | **Tested Gralloc/HWC combination**                                                                                                                                                                                | **Tested CPU** | [**VA-API**](https://en.wikipedia.org/wiki/Video_Acceleration_API) | **Notes** |
|:----------------------:|:--------------------:|:------------------:|:-------------:|:-------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|--------------------------------------------------------------------|:---------|
| Intel Graphics HD 4000 |          3.0         |         1.0        |      ✅      | - default (gbm + drmfb) ✅<br>- gbm_nohack ⬛<br>- gbm_noscanout + drm_hwc ⬛<br>- gbm + drm_hwc ✅<br>- minigbm + drmfb ⬛<br>- minigbm + drm_hwc ⬛<br>- minigbm_gbm_mesa + drmfb ✅<br>- minigbm_gbm_mesa + drm_hwc ✅ | i7-3770K            | ⬛                                                                  |           |

## post-Skylake

| **Name** | **OpenGLES version** | **Vulkan version** | **Working** | **Tested Gralloc/HWC combination** | **Tested CPU** | [**VA-API**](https://en.wikipedia.org/wiki/Video_Acceleration_API) | **Notes** |
|:---:|:---:|:---:|:---:|---|---|---|---|
| Intel Graphics UHD 620 | 3.2 | 1.1<br>1.3 (A13+) | ✅ | - default (gbm + drmfb) ✅<br>- gbm + drm_hwc ✅<br>- gbm_nohack 🚫<br>- gbm_noscanout + drm_hwc ✅<br>- minigbm + drmfb ✅<br>- minigbm + drm_hwc ✅<br>- minigbm_gbm_mesa + drmfb ✅<br>- minigbm_gbm_mesa + drm_hwc ✅ | i7-8550U | ✅ | - Without the hack on gbm_gralloc the UI will crash immediately as soon as the cursor show up.<br>- The hack on gbm_gralloc affect the render of video so it will show broken color whenever you play a video |
| Intel Graphics Iris Plus | 3.2 | 1.1<br>1.3 (A13+) | ✅ | - default (gbm + drmfb) ✅<br>- gbm + drm_hwc ✅<br>- gbm_nohack 🚫<br>- gbm_noscanout + drm_hwc ✅<br>- minigbm + drmfb ✅<br>- minigbm + drm_hwc ✅<br>- minigbm_gbm_mesa + drmfb ✅<br>- minigbm_gbm_mesa + drm_hwc ✅ | i7-1065G7 | ✅ | - Without the hack on gbm_gralloc the UI will crash immediately as soon as the cursor show up.<br>- The hack on gbm_gralloc affect the render of video so it will show broken color whenever you play a video |

## Discrete GPUs

| **Name** | **OpenGLES version** | **Vulkan version** | **Working** | **Tested Gralloc/HWC combination** | **Tested CPU** | [**VA-API**](https://en.wikipedia.org/wiki/Video_Acceleration_API) | **Notes** |
|:---:|:---:|:---:|:---:|---|---|---|---|


Explanation : <br>
✅ : Tested device is working fine<br>
⚠️ : Tested device is working, but there are some limitation or require additional workaround<br>
🚫 : Tested device is not working<br>
⬛ : Device is untested<br>
