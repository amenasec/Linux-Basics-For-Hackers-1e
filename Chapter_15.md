<!---
  Name          : Chapter_15.md
  Project       : Linux Basics for Hackers 1e
  Description   : Solutions to chapter 15 exercise problems
  Creation Date : 09 September 2020
  Author        : amenasec
  Link          : https://github.com/amenasec
--->


# Chapter 15 Exercise Problems

### 1.
Check the version of your kernel.

---

````shell
kali@kali:~$ uname -a
Linux kali 5.7.0-kali1-amd64 #1 SMP Debian 5.7.6-1kali2 (2020-07-01) x86_64 GNU/Linux
````

---


### 2.
List the modules in your kernel.

---

````shell
kali@kali:~$ lsmod
Module                  Size  Used by
vsock_loopback         16384  0
vmw_vsock_virtio_transport_common    40960  1 vsock_loopback
vmw_vsock_vmci_transport    32768  2
vsock                  49152  7 vmw_vsock_virtio_transport_common,vsock_loopback,vmw_vsock_vmci_transport
intel_rapl_msr         20480  0
intel_rapl_common      32768  1 intel_rapl_msr
vmw_balloon            24576  0
intel_rapl_perf        16384  0
joydev                 28672  0
uvcvideo              114688  0
pcspkr                 16384  0
serio_raw              20480  0
videobuf2_vmalloc      20480  1 uvcvideo
videobuf2_memops       20480  1 videobuf2_vmalloc
videobuf2_v4l2         28672  1 uvcvideo
videobuf2_common       57344  2 videobuf2_v4l2,uvcvideo
videodev              266240  3 videobuf2_v4l2,uvcvideo,videobuf2_common
mc                     57344  4 videodev,videobuf2_v4l2,uvcvideo,videobuf2_common
snd_ens1371            36864  2
snd_ac97_codec        155648  1 snd_ens1371
ac97_bus               16384  1 snd_ac97_codec
gameport               16384  1 snd_ens1371
snd_rawmidi            45056  1 snd_ens1371
snd_seq_device         16384  1 snd_rawmidi
snd_pcm               131072  2 snd_ac97_codec,snd_ens1371
snd_timer              45056  1 snd_pcm
snd                   106496  10 snd_seq_device,snd_timer,snd_ac97_codec,snd_pcm,snd_rawmidi,snd_ens1371
soundcore              16384  1 snd
sg                     36864  0
vmw_vmci               81920  2 vmw_balloon,vmw_vsock_vmci_transport
btusb                  57344  0
btrtl                  24576  1 btusb
btbcm                  20480  1 btusb
btintel                32768  1 btusb
bluetooth             688128  5 btrtl,btintel,btbcm,btusb
drbg                   28672  1
evdev                  28672  7
ac                     16384  0
ansi_cprng             16384  0
ecdh_generic           16384  1 bluetooth
ecc                    36864  1 ecdh_generic
rfkill                 28672  3 bluetooth
binfmt_misc            24576  1
fuse                  139264  5
sunrpc                503808  1
ip_tables              32768  0
x_tables               53248  1 ip_tables
autofs4                53248  2
ext4                  778240  1
crc16                  16384  2 bluetooth,ext4
mbcache                16384  1 ext4
jbd2                  139264  1 ext4
crc32c_generic         16384  0
sd_mod                 57344  3
t10_pi                 16384  1 sd_mod
crc_t10dif             20480  1 t10_pi
crct10dif_generic      16384  0
hid_generic            16384  0
usbhid                 65536  0
hid                   147456  2 usbhid,hid_generic
crct10dif_pclmul       16384  1
crct10dif_common       16384  3 crct10dif_generic,crc_t10dif,crct10dif_pclmul
crc32_pclmul           16384  0
crc32c_intel           24576  2
ghash_clmulni_intel    16384  0
sr_mod                 28672  0
cdrom                  73728  1 sr_mod
ata_generic            16384  0
aesni_intel           368640  0
libaes                 16384  2 bluetooth,aesni_intel
crypto_simd            16384  1 aesni_intel
cryptd                 24576  2 crypto_simd,ghash_clmulni_intel
glue_helper            16384  1 aesni_intel
psmouse               180224  0
vmwgfx                372736  3
ata_piix               36864  0
ttm                   118784  1 vmwgfx
drm_kms_helper        249856  1 vmwgfx
cec                    61440  1 drm_kms_helper
ehci_pci               20480  0
libata                286720  2 ata_piix,ata_generic
e1000                 155648  0
uhci_hcd               53248  0
ehci_hcd               98304  1 ehci_pci
usbcore               315392  6 ehci_pci,usbhid,uvcvideo,ehci_hcd,btusb,uhci_hcd
usb_common             16384  4 usbcore,uvcvideo,ehci_hcd,uhci_hcd
mptspi                 24576  2
mptscsih               32768  1 mptspi
mptbase                77824  2 mptspi,mptscsih
scsi_transport_spi     40960  1 mptspi
drm                   606208  6 vmwgfx,drm_kms_helper,ttm
i2c_piix4              28672  0
scsi_mod              258048  7 mptspi,sd_mod,scsi_transport_spi,mptscsih,libata,sg,sr_mod
button                 24576  0
````

---


### 3.
Enable IP forwarding with a `sysctl` command.

---

````shell
root@kali:/home/kali# sysctl -w net.ipv4.ip_forward=1
net.ipv4.ip_forward = 1
````

---


### 4.
Edit your `/etc/sysctl.conf` file to enable IP forwarding. Now, disable IP forwarding.

---

````shell
root@kali:/home/kali# vi /etc/sysctl.conf
--snip--
sysctl -w net.ipv4.ip_forward=0
net.ipv4.ip_forward = 0
````

---


### 5.
Select one kernel module and learn more about it using `modinfo`.

---

````shell
root@kali:/home/kali# modinfo bluetooth
filename:       /lib/modules/5.7.0-kali1-amd64/kernel/net/bluetooth/bluetooth.ko
alias:          net-pf-31
license:        GPL
version:        2.22
description:    Bluetooth Core ver 2.22
author:         Marcel Holtmann <marcel@holtmann.org>
srcversion:     10CFBB471D0159F7D6CBD34
depends:        libaes,rfkill,ecdh_generic,crc16
retpoline:      Y
intree:         Y
name:           bluetooth
vermagic:       5.7.0-kali1-amd64 SMP mod_unload modversions
parm:           disable_esco:Disable eSCO connection creation (bool)
parm:           disable_ertm:Disable enhanced retransmission mode (bool)
parm:           enable_ecred:Enable enhanced credit flow control mode (bool)
````

---
