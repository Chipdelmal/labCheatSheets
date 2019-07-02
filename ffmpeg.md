# ffmpeg


Compile timelapse into video:

```bash
ffmpeg -start_number START_NUMBER -r FRAMERATE -f image2 -s 1920x1080 -i NAME_PATTERN%DIGITSd.jpeg -vf "scale=trunc(iw/2)*2:trunc(ih/2)*2" -vcodec libx264 -preset veryslow -crf 15 -pix_fmt yuv420p OUTPUT_PATH.mp4
```

Convert video into GIF (palette & complex filtering):

```bash
ffmpeg -ss 2.6 -t 1.3 -i VIDEO_SOURCE_NAME.mp4 -vf fps=FRAMERATE,scale=320:-1:flags=lanczos,palettegen palette.png
ffmpeg -i VIDEO_SOURCE_NAME.mp4 -i palette.png -filter_complex "[0:v][1:v] paletteuse" -r FRAMERATE -lavfi paletteuse FILENAME.gif
```

Convert video into images:

```bash
ffmpeg -i VIDEO_SOURCE_NAME.mp4 -vf fps=FRAMERATE NAME_PATTERN%d.png
```
