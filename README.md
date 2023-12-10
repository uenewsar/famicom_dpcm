# Simulating sounds generated by DPCM on NES/Famicom

## Overview
The NES/Famicom sound function has a DPCM channel that plays sampled audio.
I show a Python script to simulate the sounds of DPCM sound.

For the specifications of the DPCM channel, I referred to this article.
[https://dic.nicovideo.jp/a/fc%E9%9F%B3%E6%BA%90]

## Environment
I tested it in `Python 3.11.6`.
Install the necessary libraries by the following command.
```
$ pip install -r requirements.txt
```

## Usage
To create an audio file `out.wav` simulating outputs of the DPCM channel converted from an input audio file `in.wav`, run the following command.
```
$ python dpcm.py in.wav out.wav
```
In the DPCM channel, we can specify a sampling frequency of the generated sound from 16 choices.
The default setting for the sampling frequency is 33144 Hz, which is the highest.

To change the sampling frequency of the playback sound, use the `-ds` option to specify a value (0-15).
The correspondence between this value and the sampling frequency is described in the script's usage message.

In the actual NES/Famicom, the sampling frequency of the playback sound seems to be a decimal number.
In this script, the sampling frequency is rounded as wav file does not allow the sampling frequency with numbers after the decimal point.


## Example
I show an example of DPCM sound using a drum sound.
The output sound's sampling frequency is 33144Hz (default value).

### Original sound
[[Original](https://soundcloud.com/uenewsar/loop01?utm_source=clipboard&utm_medium=text&utm_campaign=social_sharing)]

### Converted sound generated by DPCM
[[Converted](https://soundcloud.com/uenewsar/converted?utm_source=clipboard&utm_medium=text&utm_campaign=social_sharing)]

I used a sound from [[musicisvfr.com](http://musicisvfr.com)] as the original sound.
