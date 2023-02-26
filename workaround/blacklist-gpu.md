# Blacklist GPUs

There are some reason why you want to blacklist a GPU. Most notable reason is that you want to disable your laptop dedicated GPU because it is unusable and if you don't disable it, the whole OS graphics will broke and you can only see a disorted screen.

Currently the only way to block Bliss OS from using a GPU is to blacklist the kernel driver that the GPU is using. In this example, I'm gonna assume that you use a Nvidia GPU so the kernel driver is `nouveau`, you can apply the same with other kernel driver.

## Blacklist the kernel driver

### Using kernel parameter

For example, I have this code on grub : 

```
menuentry "BlissOS 15.8" --class android { 
  set root='(hd0,6)' 
  linux /Android/kernel root=/dev/ram0 SRC=/Android DATA=/data
  initrd /Android/initrd.img 
}
```

To block `nouveau` from loading, put `nouveau.modeset=0` after `linux /Android/kernel`. You can put it anywhere in the that line but **do not put it above or below** or else it will not work.  

```
menuentry "BlissOS 15.8" --class android { 
  set root='(hd0,6)' 
  linux /Android/kernel root=/dev/ram0 SRC=/Android DATA=/data nouveau.modeset=0
  initrd /Android/initrd.img 
}
```

Save it and then try to boot.

### Put driver in modules.blocklist

Android-x86 have a blacklist for kernel modules on `/system/etc/modules.blocklist`. But in BlissOS 14.10 & 15.8 and above, you can create another blacklist at `/data/vendor/modules.blocklist` and the system will recognize it. 

Simply put this into `/data/vendor/modules.blocklist`

```
blocklist nouveau
```

and then try to boot the OS, you will see on `lsmod` output that the module is blocked.

!!!info Hint
Want to edit this file on BlissOS ? Boot the OS with [Software Rendering](/software/software-rendering.md)
!!!
