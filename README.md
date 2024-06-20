# ffmpeg-commands

compress video
```bash
fmpeg -i input.mp4 -vcodec libx265 -crf 30 output.mp4
```

compress image
```bash
ffmpeg -i input.jpg -compression_level 50 output.jpg
```

compress all *.jpg in a directory
```bash
for i in ./*.jpg; do ffmpeg -i "$i" -compression_level 50 "./compressed/$i"; done
```
Creating a video screenshot
```bash
ffmpeg -ss 5 -i input.mp4 -frames 1 screenshot.png
```
The -ss 5 argument tells FFmpeg to jump to the 5-second mark.

Next, it extracts a single image with the -frames 1 argument.
