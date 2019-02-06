# Hackintosh for Lenovo G50-80 (Broadwell 5200U version)

## Specs

```txt
Model: Lenovo G50-80
Bios version B0CNA0WW
CPU: i5 5200U, HD 5500 Graphic
Ram: 8GB
Hard drive: Kingston 256 GB SSD + 1 TB Seagate HDD
Audio: Conexant CX20752
Ethernet: RTL8111
```

## DSDT patches

See [patches](./DSDT-patching/patches.txt). I only patched `DSDT.aml` and ignored all `SSDT-*.aml`.

Please follow the [DSDT patching tutorial by RehabMan](https://www.tonymacx86.com/threads/guide-patching-laptop-dsdt-ssdts.152573/) carefully, and you may find [this video](https://www.youtube.com/watch?v=RVMrwMW3jOY) very helpful.

The patched results can be found at [EFI/CLOVER/ACPI/patched](EFI/CLOVER/ACPI/patched).

## Kexts

All kexts used can be found at [EFI/CLOVER/kexts/Other](EFI/CLOVER/kexts/Other).

- Audio: `VoodooPS2Controller.kext`
- Ethernet: `RealtekRTL8111.kext`
- Graphics: `Lilu.kext` + `WhateverGreen.kext`, note you will need use [config_HD5300_5500_6000.plist](https://github.com/RehabMan/OS-X-Clover-Laptop-Config/blob/master/config_HD5300_5500_6000.plist) by RehabMan to set `stolenmem` to 19 MB and `cursormem` to 9 MB, see [this](https://www.tonymacx86.com/threads/guide-alternative-to-the-minstolensize-patch-with-32mb-dvmt-prealloc.221506/) and [this](https://www.tonymacx86.com/threads/guide-intel-framebuffer-patching-using-whatevergreen.256490/). Also, you should enable 'Legacy support' in BIOS's boot tab to avoid glitches, see [this post](https://www.tonymacx86.com/threads/guide-intel-hd-graphics-5500-on-os-x-yosemite-10-10-3.162062/).

## Further working

At present, everything is working except:

1. Brightness adjustment

## Links

1. [tonymacx86 FAQ](https://www.tonymacx86.com/threads/faq-read-first-laptop-frequent-questions.164990/)
2. [The same model guide on tonymacx86](https://www.tonymacx86.com/threads/guide-lenovo-g50-80-el-capitan.171080/)
3. [Solve error when patching DSDTs](https://www.tonymacx86.com/threads/fixing-a-couple-of-errors-in-dsdt.259284/)
4. [Guide for i3 version of Lenovo G50-80 in tonymacx86](https://www.tonymacx86.com/threads/guide-lenovo-g50-80-80l0-and-high-sierra-10-13-4-updated-to-10-13-5.254285/)
5. [Video guide for i3 version](https://youtu.be/Th_G7BMNiSI)