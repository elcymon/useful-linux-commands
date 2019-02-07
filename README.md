# useful-linux-commands
Some useful linux commands I have used from time to time for my work. I wish I started keeping track of them early. But better late than never

## Video
1. increase video playback rate x8: ```mencoder -speed 8 -o <output-file> -ovc lavc -oac mp3lame -srate 8000 <input-file>```
1. extract frames from video at 1fps: ```ffmpeg -i <video-file> -vf fps=1 -vsync 0 <out-file>_%d.JPG```
