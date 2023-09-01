Make sure you have Termux app from  
https://github.com/termux/termux-app#f-droid  
or  
https://f-droid.org/en/packages/com.termux/  
not from google play store, it's deprecated there.  

Open Termux  
Type all of this:  
```bash
~$ termux-setup-storage
```
Allow storage access  
```bash
~$ pkg search ffmpeg
~$ pkg install ffmpeg
```
Type: y  
enter and wait  
```bash
~$ apt full-upgrade
```
Type: y  
to everything  

You can use git to have my files  
```bash
~$ pkg install git
```
Change directory to the one you want to put my files  
example to internal storage:  
```bash
~$ cd /sdcard
```
then after that  
```bash
/sdcard $ git clone https://github.com/GhostofAndromeda/Plac.git
```
My files are now in /sdcard/Plac/{my files}  

Navigate to my files using cd command  
example:  
```bash
~$ cd /sdcard/Plac
```
This will change your directory to:  
```bash
/sdcard/Plac $
```

If you get error, "fatal: could not create work dir 'Plac': Permission denied"  
Try this if you haven't done it already:  
```bash
~$ termux-setup-storage
```
then allow storage access  
or else navigate out of the directory then come back  

Put your video or audio, and subtitle file in the Plac folder next to my files.  

Subtitle should be in srt format because that's the only format I worked on. Although you can convert to srt, look for "[subsrt] file" in here.  

To cancel a process, press ctrl then c  

[time] file  
```bash
...$ bash timing
```
Choose srt subtitle file  
This will extract all subtitle timing and fix overlaps from an srt file.  
This will produce a file marked with [time] in the name.  
This is required before condensing audio.  

[condensed] file  
```bash
...$ bash condense
```
Choose video or audio file  
Choose "[time]" marked file  
Choosing video will ask you to pick the language of audio to use  
If there's no unique audio stream, it will always be "1|eng", even if the speaker is like japanese or something.  
Choose audio will skip the converting to audio part.  
Then you Wait, do something else instead.  
This thing should take like 5 minutes, or 49 minutes and 49.8 seconds if your condensing a 2 hours 59 minutes video on Resident Evil 2 remake gameplay by Luna princess.  
After waiting, you'll get your condensed audio marked with [condensed] in the name.  
enjoy your passive listening.  

[subsrt] file  
```bash
...$ bash subtitle
```
Choosing video will extract subtitle file by title.  
Choosing subtitle will convert to srt  
Either will give subtitle file marked with [subsrt] in the name.  

[excepted] file  
```bash
...$ bash except
```
You can modify the "except.txt" file.  
Every subtitle entry you want to remove is put in that file seperated by newlines.  
The default is: (youtube ambiguous noise subtitle kanjis or something: [音楽] and [拍手])  
Your chosen srt subtitle will remove all subtitle entries with the text you put in the except.txt file and will give a subtitle file marked with [excepted] in the name.  

[sublength] file  
```bash
...$ bash length
```
Choose srt subtitle file  
This will increase the time length subtitles are shown on the screen.  
Ex: 200  
00:02:21,234 --> 00:02:26,476  
\/ \/ \/ \/  
00:02:21,234 --> 00:02:26,676  

[subtimed] file  
```bash
...$ bash retime
```
Choose srt subtitle file  
This will offset the subtitle entries timing by milliseconds.  
Negatives allowed  
Ex: -200  
00:02:21,234 --> 00:02:26,476  
\/ \/ \/ \/  
00:02:21,034 --> 00:02:26,276  


Cancelling a process midway may leave temporary files that you should remove or things might get a lot crowded.  

Error?  
Try renaming your files temporarily, without any special characters.  
Probably not supported. I only used srt, mp4, and mkv file formats for testing.  

Why only srt?  
Because I'm lazy, and I had help from chatGPT  

Why does your code look ugly?  
man, i tried..  

Please, if you know how to code in bash, you can copy my code and improve it, or create a better one.  
