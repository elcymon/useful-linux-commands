# useful-linux-commands
Some useful linux commands I have used from time to time for my work. I wish I started keeping track of them early. But better late than never

## Video
1. increase video playback rate x8: ```mencoder -speed 8 -o <output-file> -ovc lavc -oac mp3lame -srate 8000 <input-file>```
1. extract frames from video at 1fps: ```ffmpeg -i <video-file> -vf fps=1 -vsync 0 <out-file>_%d.JPG``` [source](https://askubuntu.com/questions/1019356/how-can-l-use-ffmpeg-to-extract-frames-with-a-certain-fps-ans-scaling)

## GIT
1. copy a directory from master branch to current branch ```git checkout master -- <dir-name>``` [source](https://stackoverflow.com/questions/2668886/git-copy-all-files-in-a-directory-from-another-branch)

## FILE OPERATIONS
1. Truncate a text file to 3600 lines. This command deletes from line 3601 to the end sed -i '3601,$ d' <filename>. This file operation is done inplace, for other variants, look at [source](https://stackoverflow.com/questions/19017994/how-do-i-limit-or-truncate-text-file-by-number-of-lines)
1. list 5 most recently modified files ```ls -1t | tail -5``` [source](https://stackoverflow.com/questions/15691359/how-can-i-list-ls-the-5-last-modified-files-in-a-directory)
1. view size of files and directories in a directory ```du -sh <path/to/directory>/*```

## USEFUL OPERATIONS
1. kill a process using by name ```pkill <process-name>```
