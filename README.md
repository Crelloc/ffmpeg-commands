# ffmpeg-commands

compress video
```bash
fmpeg -i input.mp4 -vcodec libx265 -crf 30 output.mp4
```

compress all *.mp4 | *.MP4 in a directory
```bash
mkdir -p compressed && for i in ./*.{mp4,MP4}; do [ -f "$i" ] && ffmpeg -i "$i" -vcodec libx265 -crf 30 "./compressed/$(basename "${i%.*}").mp4"; done
```

compress image
```bash
ffmpeg -i input.jpg -compression_level 50 output.jpg
```

compress all *.jpg | *.JPG in a directory
```bash
for i in ./*.jpg; do ffmpeg -i "$i" -compression_level 50 "./compressed/$i"; done
```
```bash
mkdir -p compressed && for i in ./*.{jpg,JPG}; do [ -f "$i" ] && ffmpeg -i "$i" -q:v 5 "./compressed/$(basename "$i")"; done
```

Creating a video screenshot:
The -ss 5 argument tells FFmpeg to jump to the 5-second mark.
Next, it extracts a single image with the -frames 1 argument.

```bash
ffmpeg -ss 5 -i input.mp4 -frames 1 screenshot.png
```


Removing the metadata information in multimedia files:
```bash
ffmpeg -i /path/to/input.mp4 -map 0 -map_metadata -1 -c copy /path/to/output.mp4
```
