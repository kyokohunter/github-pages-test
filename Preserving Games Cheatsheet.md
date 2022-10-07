# Backup and play CD-based games with MacOS

# Identify CD mode
[Source](https://www.bitsgalore.org/2015/11/13/preserving-optical-media-from-the-command-line)
Cd-info Part of GNU libcdio package
```
cd-info /dev/disk4
```
Check CD analysis report for mixed-mode CD

## Backup CD as ISO
Use Disk Utility
Or [source](https://emulationonmac.wordpress.com/2010/11/05/preserving-sony-playstation-1-games/)
```
drutil status
diskutil unmount disk4
dd if=/dev/disk4 of=~/Desktop/Title\ Of\ Game.iso bs=2048
```

## Backup CD as CUE/BIN
Useful for mixed media discs
Install MacPorts if not already installed
Install cdrdao
```
sudo port install cdrdao
```
Backup CD using cdrdao [source](https://emulationonmac.wordpress.com/2015/07/26/preserving-cd-and-dvd-based-console-games-pt-3-the-bin-cue-format/)
```
$ diskutil list
$ diskutil unmountDisk /dev/disk3
$ cdrdao read-cd --datafile image.bin --driver generic-mmc:0x20000 --read-raw image.toc
$ toc2cue image.toc image.cue
```

## Checksums and hashes
Verify MD5 hashes of backups on redump.org

## troubleshooting
Can't install on MS-DOS? Try installing in DOSBox and copy files to Mister
