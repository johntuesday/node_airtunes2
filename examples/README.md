Examples
========

Simple examples to demonstrate the module. You can try it with (AirFoil Speakers)[http://rogueamoeba.com/airfoil/] if you do not own an AirPlay device.

`play_stdin.js`: Play PCM data passed from stdin:

Usage: `cat ./sample.pcm | node play_stdin.js --host <AirTunes host>`

`play_ffmpeg.js`: Harness FFmpeg to transcode a source on-the-fly.

Both examples require optimist, although the module itself doesn't.

`scan_airtunes.js`: Simple wrapper around mDNS to list nearby AirTunes devices (OS X only).

Finding Your Device's Host & Port
----------------------------------
From the `examples/` subdirectory, running `node ./scan-airtunes.js` will return a list of AirPlay devices on your network, e.g.:

```
My Speaker My-Speaker.local.:7000
```
In the above example, the device's information is:
* **Name:** My Speaker
* **Hostname:** My-Speaker.local.
* **Port:** 7000

To get the IP address of your speaker, run `ping hostname`. The IP address should be used as the host value for running the examples, e.g.:

```
cat sample.pcm | node play_lame.js --host 192.168.123.123 --port 7000
```