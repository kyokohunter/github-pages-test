CD-based games

MacOS

As ISO
Use Disk Utility
Or
```
drutil status
diskutil unmount disk4
dd if=/dev/disk4 of=~/Desktop/Title\ Of\ Game.iso bs=2048
```

As CUE/BIN - useful for mixed media discs
Install MacPorts if not already installed
Install cdrdao
```
sudo port install cdrdao
```
Backup CD using cdrdao
```
$ diskutil list
$ diskutil unmountDisk /dev/disk3
$ cdrdao read-cd --datafile image.bin --driver generic-mmc:0x20000 --read-raw image.toc
$ toc2cue image.toc image.cue
```
