# audioshuffle

This is bash-script for randomly searching and chopping up audiofiles in a directory and generate a result-file with all generated audio-slices.

## Simple Usage Example

Use audioshuffle with default values: 120BPM, 16 Slices, sample-rate 44100, bitrate 16, stereo, autoplay 1

`audioshuffle path/to/dir`

### Functionality

`audioshuffle /media/fra/MUSICPOOL/__Samples/Extern/Loops`<br>

Example-Output
```
start reading directory recursively with maxdepth 2
start processing files

audio/Anthony Rother_-_62 Minutes On Mars__2011_Fax +49-69450464/Anthony Rother_02_Star Orgy.mp3
audio/Aphex Twin_-_Cheetah EP__2016/Aphex Twin_01_Cheetah2 (Ld spectrum).mp3
audio/BUZZ002__B+S_-_EP No.01#reboot, emotion...__2009/bs_05_syeedas_other_edit.mp3
audio/VA_-_SPEX - Musik zur Zeit - 35 aus 35 (CD1)__2015/PJ Harvey_03_Down By The Water.mp3
audio/Aphex Twin_-_Cheetah EP__2016/Aphex Twin_04_Cheetah2 ms800.mp3
audio/Anthony Rother_-_62 Minutes On Mars__2011_Fax +49-69450464/Anthony Rother_07_Alpha Cephei.mp3
audio/VA_-_SPEX - Musik zur Zeit - 35 aus 35 (CD2)__2015/Der Plan_16_Gummitwist.mp3
audio/BUZZ007__B+S_-_EP No.03#neutral code__2010/B+S_01_simple & plain.mp3
audio/Alpha 606__Afro-Cuban Electronics_2016/Alpha 606_06_Whale Memory.mp3
audio/Primus_-_Frizzle Fry__1990/13 - Primus - To Defy.ogg
audio/Primus_-_The Brown Album__1997/08 - Primus - Puddin' Taine.ogg
audio/Aleksi Perälä_-_Colundi Level 4__2014/Aleksi Perälä_03_UK74R1406030.mp3
audio/Primus__Antipop_1999/Primus_05_The Antipop.mp3
audio/Aphex Twin_-_Selected Ambient Works 85-92__1992_Apollo/Aphex Twin_05_i.mp3
audio/Aleksi Perälä__The Colundi Sequence Level 16_2016/Aleksi Perälä_10_UK74R1618100.mp3
audio/Primus_-_Sailing The Seas Of Cheese__1991/02 - Primus - Here Come The Bastards.ogg

audioshuffle_2019-09-08_19_57_25__120bpm_16beats.wav
```

In this example `audioshuffle` processed 16 audio files in the directory 'audio'. 
For each file 0.5 seconds (120BPM quarter-note) of audio at a random startpoint were extracted and
concatenated into the result-file named 'audioshuffle_2019-09-08_19_57_25__120bpm_16beats.wav'.

## why?
Maybe you are a Musician and into sampling and you are searching for new abstract sample sources?<br>
Maybe audioshuffle just points you to music you have forgotten on your harddisk :)

## sox
This script uses sox [http://sox.sourceforge.net/](http://sox.sourceforge.net/).

### Installation of sox via apt:
`sudo apt-get install sox libsox-fmt-all`

## Help (audioshuffle -h)
```
usage: audioshuffle [options] [dir]

audioshuffle searches recursivley for audiofiles (mp3,wav,ogg,m4a} in the specified directory.
randomly files will be chopped up and concatenated into a new file.

EXAMPLES:

audioshuffle path/to/dir
  audioshuffle with default values: 120BPM, 16 Slices, sample-rate 44100, bitrate 16, stereo, autoplay 1

audioshuffle -b8 -c1 -r8000 -d60 -s8
  audioshuffle with bit-rate 8, sample-rate 8000, mono, 60BPM, 8 slices


  -a	autoplay: 0 don't play audiofile, 1: play audiofile and prompt to keep file
  -b	bitrate: set bitrate 8, 16, 24
  -c	channels: 1 = mono, 2 = stereo
  -h	help: print this help
  -m	maxdepth: level for recursive directory search
  -r	samplerate: specifiy sample-rate e.g 8000, 41000, 48000
      	uncommon sample-rates are allowed  too
  -s	slices: amount of slices/files that are processed
  -t	tempo: define BPM for length of slices

```

## Local Installation
```
git clone https://github.com/quasd99/audioshuffle.git
cd audioshuffle
sudo cp audioshuffle /usr/local/bin/
```
