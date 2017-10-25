# bash-cheatsheet
> Bash commands that have proven to be very useful for me

## Working with the file system

`# find folders and files in the file system`

```bash
# finding all files (-type f) with name starting with 'sidekiq' (-name "sidekiq*")
find /path/to/folder -type f -name "sidekiq*"
```

`# unzip all *.zip files in the current folder`

```bash
unzip \*.zip
```

## Network

`# list available network interfaces`

```bash
ip link show
```

`# mirror an entire website: http://www.linuxjournal.com/content/downloading-entire-web-site-wget`

```bash
wget \
     --recursive \
     --no-clobber \
     --page-requisites \
     --html-extension \
     --convert-links \
     --no-parent \
         www.website.org
```


## Miscellaneous

`# extracting the audio from video files`

```bash
ffmpeg -i /input/path/to/video/file.mp4 /output/path/to/audio/file.mp3
```

`# making a bootable usb drive by simply mounting an image`

```bash
# listing block devices
lsblk

# if: file to load the image from
# of: partition to mount the image in
sudo dd if=/path/to/linux/distro/iso/image/file.iso of=/dev/sdb1 
```

