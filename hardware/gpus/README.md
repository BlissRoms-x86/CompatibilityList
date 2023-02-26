# GPUs

Supporting graphics cards is a piority in Bliss OS, as getting hardware acceleration is very important to the Android experience

!!!info Info
Unsupported GPUs can try [software rendering](../../Software/software-rendering.md) solution.
!!!

For Gralloc and HWC, the default Gralloc we are using is gbm_gralloc, and HWC is drmfb-composer. Here are sources of them and others that we are using :

gbm_gralloc : https://github.com/BlissRoms-x86/gbm_gralloc<br>
<span style="font-size:0.8em;">*(this include gbm/gbm_nohack/gbm_noscanout)*</span><br>
drmfb-composer : https://github.com/BlissRoms-x86/drmfb-composer<br>
minigbm : https://github.com/supremegamers/minigbm<br>
<span style="font-size:0.8em;">*(this include minigbm/minigbm_gbm_mesa/minigbm_arcvm)*</span><br>
drm_hwcomposer : https://github.com/supremegamers/drm_hwcomposer<br>
