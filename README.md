# DIPS: Detection of Incoming Projectile System

A Raspberry Pi camera prototype that picks a colored object out of a live video feed in real time. It is the early vision prototype for D.I.P.S., our CMPE 195 senior project team at San Jose State University. The finished system adds two servos that aim the camera at the largest matching object; that version is in the team repo, [CMPE195-Group26/D.I.P.S.](https://github.com/CMPE195-Group26/D.I.P.S.).

[ObjectBinaryMappingDemo.mp4](ObjectBinaryMappingDemo.mp4) shows it running.

## How it works
- Captures 1280x720 frames at 30 fps from the Pi camera with Picamera2.
- Converts each frame to HSV and builds a binary mask of the pixels inside a hue, saturation and value range, so only the target object stays white.
- Shows three windows: the live feed with an FPS counter, the mask, and the original frame with everything but the object blacked out.
- Six sliders let you tune the HSV range live while the camera runs, which makes it quick to lock onto a new object or adjust for lighting.

## Tech stack
Python, OpenCV, NumPy, Picamera2, Raspberry Pi

## Running it
On a Raspberry Pi with a camera module and Raspberry Pi OS (Bullseye or later):

```bash
sudo apt install python3-picamera2 python3-opencv
python3 picam2test.py
```

Press `q` in a video window to quit.
