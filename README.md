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
