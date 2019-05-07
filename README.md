# useful-linux-commands
Some useful linux commands I have used from time to time for my work. I wish I started keeping track of them early. But better late than never

## Video
1. increase video playback rate x8: ```mencoder -speed 8 -o <output-file> -ovc lavc -oac mp3lame -srate 8000 <input-file>```
1. extract frames from video at 1fps: ```ffmpeg -i <video-file> -vf fps=1 -vsync 0 <out-file>_%d.JPG``` [source](https://askubuntu.com/questions/1019356/how-can-l-use-ffmpeg-to-extract-frames-with-a-certain-fps-ans-scaling)
1.  reducing size of video to half: ```ffmpeg -i input.mkv -vf "scale=iw/2:ih/2" half_the_frame_size.mkv```. Other approaches are available at [source](https://unix.stackexchange.com/questions/28803/how-can-i-reduce-a-videos-size-with-ffmpeg).

1. reverse video and its audio using ffmpeg and sox. Work done in [this](https://nhs.io/reverse/) first extracts video frames as jpg the joins them in reverse order. To convert frames to images ```ffmpeg -i <video-name> -an -qscale 1 %06d.jpg```. To combine video frames to 50 fps video in reverse order use piping like so: ```cat $(ls -t *.jpg) | ffmpeg -r 50 -i - <reversed-video-name>```

1. [crop video using ffmpeg](https://askubuntu.com/questions/598324/convert-a-video-to-a-fixed-screen-size-by-cropping-and-resizing). This commands centre crops the ```<input-video>``` file ```ffmpeg -i <input-video> -filter:v "crop=width:height" -c:a copy <output-video-name>```

## GIT
1. copy a directory from master branch to current branch ```git checkout master -- <dir-name>``` [source](https://stackoverflow.com/questions/2668886/git-copy-all-files-in-a-directory-from-another-branch)

## FILE OPERATIONS
1. Truncate a text file to 3600 lines. This command deletes from line 3601 to the end sed -i '3601,$ d' <filename>. This file operation is done inplace, for other variants, look at [source](https://stackoverflow.com/questions/19017994/how-do-i-limit-or-truncate-text-file-by-number-of-lines)
1. list 5 most recently modified files ```ls -1t | tail -5``` [source](https://stackoverflow.com/questions/15691359/how-can-i-list-ls-the-5-last-modified-files-in-a-directory)
1. view size of files and directories in a directory ```du -sh <path/to/directory>/*```
1. count number of files in a directory ```ld -l path/to/directory/pattern | grep ^- | wc -l ``` refer to [source](https://askubuntu.com/questions/34099/find-number-of-files-in-folder-and-sub-folders) for other similar commands.
## USEFUL OPERATIONS
1. kill a process using by name ```pkill <process-name>```
1. increase system volume beyond 100% ```pactl set-sink-volume 0 170%``` This sets volume of audio output 0 to 170%. A different value may be necessary depending on computer.
1. Create multiple folders numbered serially ```mkdir {1..10}``` Creates folders whose names are 1 through 10. 
1. [Find pattern of strings in multiple files and replace them](https://www.cyberciti.biz/faq/how-to-use-sed-to-find-and-replace-text-in-files-in-linux-unix-shell/) ```sed -i 's/oldString/newString/g' fileNameOrPattern```. If there are ```/``` in the string pattern, you can use ```+``` instead: ```sed -i 's+oldString+newString+g' fileNameOrPattern```
