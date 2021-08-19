---
layout: page
title: "/report"
permalink: /report/
---

# Libcamera


This is Google Summer of Code 2021 project under Libcamera aimed at achieving:

1.  Add support to Libcamera's gstreamer element to support multistreaming.
2.  Add unit test to test gstreamer element functionality in Libcamera.

## Project Details

-   Name: Vedant Paranjape
-   Mentors: Paul Elder, Nicolas Dufresne
-   Organization: Libcamera
-   Code: <https://git.libcamera.org/libcamera/libcamera.git/>
-   Project Page: <https://summerofcode.withgoogle.com/projects/#6332672818806784>
-   Progress log: <https://ve0x10.in/gsoc2021/>
-   Midway Blog: <https://ve0x10.in/blog/2021/07/19/gsoc-libcamera.html>

## Brief overview

The GStreamer libcamera element allows libcamera to be used in GStreamer pipelines. Libcamera supports simultaneous streaming, for example having lower quality one stream for preview, while another higher quality one is used for recording. This project extends support for the GStreamer libcamera element to support this multistreaming.

## Usage

Multistream is supported on devices with IPU3, rkisp1 and raspberrypi camera pipeline. This will only work on those devices.

1.  Install libcamera and gstreamer using this guide: <https://libcamera.org/getting-started.html>
2.  If gstreamer element isn't installed system wide, set the environment variable specifying the location:
    
    ```
    export GST_PLUGIN_PATH=$(pwd)/build/src/gstreamer
    ```

3.  Install gst-plugins-bad as follows

    ```
    sudo apt install gstreamer1.0-plugins-bad
    ```

4.  Run the following command on the terminal

    ```
    gst-launch-1.0 libcamerasrc name=src src.src ! queue ! videoconvert ! autovideosink src.src_0 ! queue ! videoconvert ! autovideosink
    ```
    
**If it runs correctly, you should see such two windows with camera output as follows:**

<img src="https://ve0x10.in/blog/assets/gsoc-log-1/multistream-pass.png" height="416" width="740">

## Examples

This functionality can be done programmatically, the example codes are [here](https://github.com/VedantParanjape/gstreamer-libcamerasrc-examples)

1.  [Single Stream](https://github.com/VedantParanjape/gstreamer-libcamerasrc-examples/blob/master/singlestream.c)
2.  [Multi Stream](https://github.com/VedantParanjape/gstreamer-libcamerasrc-examples/blob/master/multistream.c)
3.  [Using Device Provider](https://github.com/VedantParanjape/gstreamer-libcamerasrc-examples/blob/master/device-provider.c)

## Work Summary

All the patches submitted by me that merged can be seen [here](https://git.libcamera.org/libcamera/libcamera.git/log/?qt=grep&q=Vedant+Paranjape)

1.  [gstreamer: Add error checking in gst\_libcamera\_src\_task\_enter()](https://git.libcamera.org/libcamera/libcamera.git/commit/?id=1e5cee701781276fb03f18e704a5a6ea8f24eff8)
2.  [libcamera: Add OV5647 sensor properties](https://git.libcamera.org/libcamera/libcamera.git/commit/?id=1d134197c7af5fd669f833e1c537b7eb3cc5b644)
3.  [gstreamer: Added virtual functions needed to support request pads](https://git.libcamera.org/libcamera/libcamera.git/commit/?id=53a0d80af0f9983d6bc0d54b0e85403a08721488)
4.  [libcamera: Fix the V4L2 pixel format for formats::XBGR8888](https://git.libcamera.org/libcamera/libcamera.git/commit/?id=3715d1b21d9c73a7af56c845db7c8e412e28f5c2)
5.  [libcamera: Add pixel format BGRX8888](https://git.libcamera.org/libcamera/libcamera.git/commit/?id=4889464fd82aa11738ce00d9079adec339878f90)
6.  [gstreamer: Store group\_id in GstLibcameraSrcState](https://git.libcamera.org/libcamera/libcamera.git/commit/?id=f573198d3e4200cc8e203ecf638c20f8ed41547a)
7.  [gstreamer: Update format specifier in Request Pad template](https://git.libcamera.org/libcamera/libcamera.git/commit/?id=0e8d8fbd4e47217c897b410cfe0163b88ae1dade)
8.  [test: gstreamer: Add test for gstreamer single stream](https://git.libcamera.org/libcamera/libcamera.git/commit/?id=25462474f8bb56153995f44f2f2996673321f871)

## Notes

* Use the following command to verify working of multistream on Raspberry Pi 4B+ using Raspberry Pi Cam v1

    ```
    gst-launch-1.0 libcamerasrc camera-name="/base/soc/i2c0mux/i2c@1/ov5647@36" name=src src.src ! queue ! videoconvert ! autovideosink src.src_0 ! queue ! videoconvert ! autovideosink`
    ````

* Use the following command to compile gst code

    ```
    gcc basic-tutorial-3.c -o basic-tutorial-3 `pkg-config --cflags --libs gstreamer-1.0`
    ```

* Use the following to view camera using libcamerasrc

    ```
    gst-launch-1.0 libcamerasrc camera-name="Camera 1" ! videoconvert ! autovideosink
    ```

* Use the following to export gstreamer libcamera element, execute this in libcamera root path

    ```
    export GST_PLUGIN_PATH=$(pwd)/build/src/gstreamer
    ```

## Conclusion

All goals that were originally proposed have been completed. I will continue to support this project in the future, take care of any bugs, issues and will continue implementing additional features whenever required.

It has been a really great experience for me. I have learned so much in these 10 weeks, which will surely help me achieve my future goals in life. I would like to thank libcamera and Google for giving me such an amazing opportunity. Furthermore, I would also like to thank my mentors Paul and Nicolas for helping me out and supporting me throughout the project, also the members of Libcamera community, namely Laurent, Kieran, Umang and Jacopo.

On an ending note, if my words or actions hurt anyone, I am extremely sorry !