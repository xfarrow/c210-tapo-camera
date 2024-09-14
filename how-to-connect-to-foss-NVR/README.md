# How to connect to a NVR

Tested on: Tapo C210

## Introduction

### Capabilities
This camera is capable of transmitting its stream on the RTSP protocol on two channels: one at resolution 640x360 and another one at a higher quality, whose resolution is set in the settings (720p, 1080p, 2K).
It supports the `ONVIF` standard.

It is also possible to access the video over HTTP, but it's undocumented, unofficial and needs to be improved.

### Prerequisites
If you want to use the RTSP protocol (used also by the ONVIF), you need to create RTSP credentials. Using the official app we have to go to `Settings -> Advanced Settings -> Camera account`. We have to choose a `username` and a `password`

## Connection

### Simple RTSP stream:
High quality stream: `rtsp://username:password@IP_Address:554/stream1`

Low quality stream: `rtsp://username:password@IP_Address:554/stream2`

### ONVIF
`http://IP_Address:2020/onvif/device_service` and specify `username` and `password` when asked.

Using ONVIF will allow the NVR to properly configure the PTZ controls, allowing the camera to pan and tilt.

### HTTP (unofficial, needs more analysis)
See [this resource](https://drmnsamoliu.github.io/video.html) but I did not test it. In this way we should be able to unlock a 2K video stream.

## Test
You can test the RTSP stream on Linux by giving the following command: `ffplay rtsp://<user>:<pass>@<IP_Address>:554/stream1
`
