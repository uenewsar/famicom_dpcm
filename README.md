# Simulate the sound played by DPCM on NES / Famicom

## Overview
The NES /Famicom sound function has a DPCM channel that plays sampled audio.
Here I show a Python script to simulate what DPCM channel.

For the specifications of the DPCM channel, I referred to this article.
[https://dic.nicovideo.jp/a/fc%E9%9F%B3%E6%BA%90]

## Environment
I tested it in `Python 3.11.6`.
Install depencency library by the following command.
```
$ pip install -r requirements.txt
```

## Usage
To create an audio file (out.wav) simulating DPCM channel from an input audio file (in.wav), run the following command.
```
$ python dpcm.py in.wav out.wav
```

The NES/Famicom DPCM channel allows to select the sampling frequency of the playback sound from 16 choices.
The default setting for the sampling frequency is 33144 Hz, which is the highest.

To change the sampling frequency of the playback sound, use the `-ds` option to specify a value (0-15).
The correspondence between this value and the sampling frequency is described in the script's usage message.

In the actual NES/Famicom, the sampling frequency of the playback sound seems to be a decimal number.
In this script, the sampling frequency is rounded to a whole number for the purpose of output as a wav file.


## Example
I show an example of DPCM sound using a drum sound.
The output sound's sampling frequency is 33144Hz (default value).

### Original sound
[https://soundcloud.com/uenewsar/loop01:embed]
[https://soundcloud.com/uenewsar/loop01:title]

### Converted sound generted by DPCM
[https://soundcloud.com/uenewsar/converted:embed]
[https://soundcloud.com/uenewsar/converted:title]

I used these sounds from [http://musicisvfr.com:title].

