# android-publisher
The android live publisher to SRS over HTTP-FLV.

## Features

* Only java files, without any native code.
* Realtime live streaming, similar to RTMP.
* Stable for POST HTTP FLV stream to [SRS](https://github.com/simple-rtmp-server/srs).
* Hardware encoding with low cpu usage.

## Requirements

Android SDK level 16+, Android 4.1, 4.1.1, the JELLY_BEAN

## WorkFlow

The workflow of the android publisher is:

1. Setup the Camera preview, callback with the YUV(YV12) image frame.
1. Setup the MediaCodec and MediaFormat, encode the YUV to h.264/avc in annexb.
1. Remux the annexb to flv stream.
1. HTTP POST the flv stream to SRS.

## Low Latency

The latency is same to RTMP, 0.8s in lan and 3-5s in wan.

![0.8s latency](https://github.com/simple-rtmp-server/android-publisher/wiki/images/ap.delay1.jpg)

## Lightweight

![800kbps](https://github.com/simple-rtmp-server/android-publisher/wiki/images/ap.800kbps.jpg)

CPU 13% for publishing live to SRS over HTTP FLV, bitrate is 800kbps, fps is 25 and gop is 10s.

![125kbps](https://github.com/simple-rtmp-server/android-publisher/wiki/images/ap.125kbps.jpg)

CPU 6% for publishing live to SRS over HTTP FLV, bitrate is 125kbps, fps is 15 and gop is 5s.

Winlin 2015.5
