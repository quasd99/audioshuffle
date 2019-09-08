# audioshuffle

This is bash-script for randomly searching and chopping up audiofiles in a directory and generate a result-file with all generated audio-slices.

This script uses sox [http://sox.sourceforge.net/](http://sox.sourceforge.net/).

## Installation of sox via apt:
`sudo apt-get install sox libsox-fmt-all`

## Description
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

## Simple Usage Example

Use audioshuffle with default values: 120BPM, 16 Slices, sample-rate 44100, bitrate 16, stereo, autoplay 1

`audioshuffle path/to/dir`
