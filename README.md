# bash-cheatsheet
A handful of useful bash commands

> Bash commands that have proven to be very useful for me

## Working with the file system

`# find folders and files in the file system`

```bash
# finding all files (-type f) with name starting with 'sidekiq' (-name "sidekiq*")
find /path/to/folder -type f -name "sidekiq*"
```

## Network

`# list available network interfaces`

```bash
ip link show
```

`# mirror an entire website`
`# Tutorial link: http://www.linuxjournal.com/content/downloading-entire-web-site-wget`

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


## Uncategorized

`# making a bootable usb drive by simply mounting an image`

```bash
# listing block devices
lsblk

# if: file to load the image from
# of: partition to mount the image in
sudo dd if=/path/to/linux/distro/iso/image/file.iso of=/dev/sdb1 
```

