---
layout: page
title: "/notes"
permalink: /notes/
---

# Notes

* Use the following command to verify working of multistream

```bash
gst-launch-1.0 libcamerasrc camera-name="/base/soc/i2c0mux/i2c@1/ov5647@36" name=src src.src ! queue ! videoconvert ! autovideosink src.src_0 ! queue ! videoconvert ! autovideosink`
```

* Use the following command to compile gst code

```bash
gcc basic-tutorial-3.c -o basic-tutorial-3 `pkg-config --cflags --libs gstreamer-1.0`
```

* Use the following to view camera using libcamerasrc

```bash
gst-launch-1.0 libcamerasrc camera-name="Camera 1" ! videoconvert ! autovideosink
```

* Use the following to export gstreamer libcamera element, execute this in libcamera root path

```bash
export GST_PLUGIN_PATH=$(pwd)/build/src/gstreamer
```
