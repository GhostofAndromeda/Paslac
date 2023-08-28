Make sure you have Termux app from
https://github.com/termux/termux-app#f-droid
https://f-droid.org/en/packages/com.termux/
not from google play store, it's deprecated there.

Open Termux
Type all of this:
~$ termux-setup-storage
Allow storage access
~$ pkg search ffmpeg
~$ pkg install ffmpeg
Type: y
enter and wait
~$ apt full-upgrade
Type: y
to everything

You can use git to have my files
~$ pkg install git
Change directory to the one you want to put my files
example to internal storage:
~$ cd /sdcard
then after that
~$ git clone https://github.com/GhostofAndromeda/Plac.git
My files are now in /sdcard/Plac/here

Navigate to my files using cd command
example:
~$ cd /sdcard/Plac
This will change your directory to:
/sdcard/Plac $

If you get error, "fatal: could not create work dir 'Plac': Permission denied"
If you haven't done this already:
~$ termux-setup-storage then allow storage access
or else navigate out of the directory then come back

Put your video or audio, and subtitle file in the Plac folder next to my files 
To cancel a process, press ctrl then c

[time] file 
~$ bash timing
Subtitle must be in srt format because that's the only format I worked on.
After waiting, it will give a file marked with [time] in the name.

[condensed] file
~$ bash condense
Choose video or audio file
then choose [time] marked file
If you chose a video, then it will ask you to pick the language of audio to use (no unique audio stream will always be 1|eng)
If you choose an audio, this will skip the converting to audio part.
Wait, do something else instead. This thing takes like 5 minutes
After waiting, you'll get your condensed audio marked with [condensed] in the name.
enjoy your passive listening 

[subsrt] file
~$ bash subtitle
Type number from the left side
Choosing video: extract subtitle file by title
Choosing subtitle: convert to srt
Either will give subtitle file marked with [subsrt] in the name.

[excepted] file
~$ bash except
You can modify the except.txt file
The default is: (youtube ambiguous noise subtitle kanjis or something)
[音楽] and [拍手]
Every subtitle entry you want to remove is put in that file seperated by newlines
Your chosen srt subtitle will remove all subtitle entries with the text you put in the except.txt file and will give a subtitle file marked with [excepted] in the name.
