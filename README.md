# pardus-17-grub-recovery


## Pardus'un(versiyon 17) (Debian 9) 1. sata diskte kurulu olduğunu ve boot için ayrı bir bölüm olmadığını kabul ediyoruz.
## Disk yapısı aşağıdaki şekildedir:
![Disk Bölümleri](disk-bolumleri.png)
<code>
sudo mount /dev/sda1 /mnt 

sudo mount --bind /dev /mnt/dev &&

sudo mount --bind /dev/pts /mnt/dev/pts &&

sudo mount --bind /proc /mnt/proc &&

sudo mount --bind /sys /mnt/sys

sudo chroot /mnt

sudo apt install grub2
</code>

## Grub2 paketi kurulurken aynı zamanda grub'ı da diske kurmak için sizden ilgili diski seçmenizi istiyor.
## Eğer ki kurulmazsa aşağıdaki şekilde tekrar kurulum yapabilirsiniz.

<code>
grub-install /dev/sda
</code>
<code>
exit &&
sudo umount /mnt/sys &&

sudo umount /mnt/proc &&

sudo umount /mnt/dev/pts &&

sudo umount /mnt/dev &&

sudo umount /mnt
</code>