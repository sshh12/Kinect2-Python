# LibKinect2

> A Python API for interfacing with the [Kinect2](https://www.amazon.com/Xbox-One-Kinect-Sensor/dp/B00INAX3Q2/).

## Usage

#### Install
`TODO`

#### Demos

```python
from libkinect2 import Kinect2
from libkinect2.utils import depth_map_to_image
import numpy as np
import cv2

# Init Kinect2 w/2 sensors
kinect = Kinect2(use_sensors=['color', 'depth'])
kinect.connect()
kinect.wait_for_worker()

for _, color_img, depth_map in kinect.iter_frames():
    
    # Display color and depth data
    cv2.imshow('color', color_img)
    cv2.imshow('depth', depth_map_to_image(depth_map))

    key = cv2.waitKey(1) & 0xFF
    if key == ord('q'):
        break

kinect.disconnect()
```

[Example Scripts](https://github.com/sshh12/LibKinect2/tree/master/examples)

`TODO GIFS`

#### Docs

For python docs, run:
```python
from libkinect2 import Kinect2
help(Kinect2)
```

[Other Docs](https://github.com/sshh12/LibKinect2/tree/master/Kinect2-API)

## Issues

I'm sure there are plenty of issues, so fill free to [create one](https://github.com/sshh12/LibKinect2/issues)
or [fix one](https://github.com/sshh12/LibKinect2/pulls).

## Related

There's a whole bunch of these...

* [Kinect/PyKinect2](https://github.com/Kinect/PyKinect2)
* [Qirky/PyKinectTk](https://github.com/Qirky/PyKinectTk)
* [kiddos/pykinect2](https://github.com/kiddos/pykinect2)
* [amiller/libfreenect-goodies](https://github.com/amiller/libfreenect-goodies)
* [colincsl/pyKinectTools](https://github.com/colincsl/pyKinectTools)
* [maxime-tournier/kinect2](https://github.com/maxime-tournier/kinect2)