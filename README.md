# OVIO
Overview of VIO
## Different Type of VIO
### Direct and InDirect method
<a href="http://vision.in.tum.de/lsdslam" target="_blank"><img src="https://vision.in.tum.de/_media/research/lsdslam/directvskp.png" 
alt="DSO diff from key-point" width="240" height="180" border="10" /></a>

### Hardware specifications
#### Camera Sensor specifications
This camera has a baseline of 7.5cm - the distance between left and right stereo camera. Minimal and maximal depth perception depends on camera FOV, resolution, and baseline.
```
depth = focal_length_in_pixels * baseline / disparity_in_pixels
focal_length_in_pixels = image_width_in_pixels * 0.5 / tan(HFOV * 0.5 * PI/180)
# With 400P mono camera resolution where HFOV=71.9 degrees
focal_length_in_pixels = 640 * 0.5 / tan(71.9 * 0.5 * PI / 180) = 441.25
# With 800P mono camera resolution where HFOV=71.9 degrees
focal_length_in_pixels = 1280 * 0.5 / tan(71.9 * 0.5 * PI / 180) = 882.5
```
Min perceivable distance: ~20cm (400P OR 800P, extended), ~37cm (800P)

Max perceivable distance: ~21 meters
 | Camera Specs | Color camera | Stereo pair |
 | :---     |    :----         |          :--- |
 | Sensor              | IMX378            |  OV9282 |
 | Shutter             | rolling           |  global |
 | FOV (D/H/V)         | 120°/108°/93°     |  150°/127°/79.5°  |
 | Resolution          | 12MP (4032x3040)  |  1MP (1280x800) |
 | Focus               | FF: 50cm - ∞      |  FF: 19.6cm - ∞ |
 | Max Framerate       | 60 FPS            |  120 FPS |
 | Pixel size          | 1.55µm x 1.55µm   |  3µm x 3µm |
 
#### IMU Sensor specifications
The BNO085 is a single chip 9-axis sensor with embedded sensor fusion.

 | IMU Specs | Maximum frequencies |
 | :---     |    :----         |
 | accelerometer | 500Hz |
 | gyroscope | 1000Hz |
 | combined (synced) | 500Hz |
 
