# TIL - ffmpeg

## Decrease size

```
ffmpeg -i input.mp4 -vcodec libx265 -crf 28 output.mp4
```

## Cut

```
ffmpeg -i input.mp4 -ss 00:00:05 -to 00:00:10 -c copy output.mp4
```

## Play video

```
ffplay output.mp4
```

## Play audio only

```
ffplay -nodisp output.mp4
```

## Audio streaming of a youtube video

```
youtube-dl https://www.youtube.com/watch?v=dQw4w9WgXcQ -f bestaudio -o - | ffplay - -nodisp
```

## Record screen and save as video

```
ffmpeg -f x11grab -i :0.0 -f pulse -i 0 output.mp4
```

## Record part of the screen as gif for 5 seconds with 800x600 resolution, 0 x-offset and 30 the y-offset

```
ffmpeg -f x11grab -framerate 10 -video_size 800x600 -i :0.0+0,30 -t 5 output.gif
```

## Take a screenshot and save as png

```
ffmpeg -f x11grab -i :0 -t 1 -f mjpeg output.png
```

