# bash-cheatsheet

> Bash commands that have proven to be very useful for me

## Working with the file system

`# finding all files (-type f) with name starting with 'sidekiq' (-name "sidekiq*")`

```bash
find /path/to/folder -type f -name "sidekiq*"
```

`# unzip all *.zip files in the current folder`

```bash
unzip \*.zip
```

`# compress file or folder as *.tar.gz`

`# -c: create an archive`

`# -z: compress the archive with gzip`

`# -v: verbose mode on`

`# -f: allows you to specify the filename of the archive`
```bash
tar -czvf file-name.tar.gz /path/to/file/or/folder/to/compress
```

`# extract *.tar.gz file to specified folder`
```bash
tar -xzf foo.tar.gz -C output/
```

`# list folder content as treeview`
```bash
tree -N -h -l -A
```

`# list folder content as treeview and exclude some patters`
```bash
tree -N -A -I 'logs|*out'
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

`# resume file download with wget:
https://www.cyberciti.biz/tips/wget-resume-broken-download.html`

```bash
wget --continue <url>
```

`# kill process on specific port (e.g. kill process on port 8000)`
```bash
sudo fuser -k 8000/tcp
```

## Databases

`# connect to psql console`

```bash
psql -U username -h localhost db_name
```

## Miscellaneous

`# extracting the audio from video files`

```bash
ffmpeg -i /input/path/to/video/file.mp4 /output/path/to/audio/file.mp3
```

`# convert .avi video into .mp4 video while keeping wuality`

```bash
ffmpeg -i input.avi -c:v libx264 -crf 19 -preset slow -c:a aac -b:a 192k -ac 2 -strict -2 output.mp4
```

`# reduce size and quality of video files (https://unix.stackexchange.com/questions/28803/how-can-i-reduce-a-videos-size-with-ffmpeg)`

```bash
ffmpeg -i /path/to/input/file.mp4 -vcodec libx264 -crf 20 /path/to/output/file.mp4
```

`# convert .pdf document to .doc or .docx`

```bash
soffice --infilter="writer_pdf_import" --convert-to doc /path/to/file.pdf
soffice --infilter="writer_pdf_import" --convert-to docx /path/to/file.pdf
```

`# making a bootable usb drive by simply mounting an image`

```bash
# listing block devices
lsblk

# if: file to load the image from
# of: partition to mount the image in
sudo dd if=/path/to/linux/distro/iso/image/file.iso of=/dev/sdb1
```

`# encode strings as base64 (e.g. your proxy server credentials)`

```bash
echo "username:password" | base64
```

`# decode base64 strings (e.g. your proxy server credentials)`

```bash
echo QWxhZGRpbjpvcGVuIHNlc2FtZQ== | base64 --decode
```

## Desktop Environments

`# restart Cinnamon Desktop Environment from tty (https://github.com/linuxmint/Cinnamon/issues/4763)`

```bash
pkill -HUP -f "cinnamon --replace"
```
