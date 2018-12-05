# kickercam

Foosball (Kicker, Tablesoccer) live camera with goal detection and slow-motion replay

python3 main2.py starts the camera and outputs to a Monitor. Replay is Implemented but currently not used.  

# train

python3 classifier.py

trains and saves the model. Note that classifier.py is also used for predictions (see main.py)


# TODOs

If you apply all these TODOs it will work perfectly!

- [x]  Add heat sink

It's getting to hot with the analysis

Add a heat sink to the raspberry chip (we should still have some). Furthermore add a small fan!


- [x]  adjust cam and cut out field area

Center the image. Use hotglue on the camera and adjust it perfectly. make sure the pi sits still as well

There is an option to cut out (and zoom) an area of the capture frame.
Look here for zoom:
https://picamera.readthedocs.io/en/release-1.13/api_camera.html?highlight=zoom

- [x]  After cutting the stream as indicated above, it should be possible to increase the frame rate to about 42 FPS (which is enough for a cool slowmo already).

Increase the FPS until the program crashes

- [x] Use different resolutions

We can use the full 1600x1200 for the preview (and replay) and use 600x480 for the image processing to speed up everything
(The PICamera does not see the whole field in 600x480. Therefore capturing the low resolution image for processing does not work

- [ ]  video formats

Right now we use h264 for the circular replay buffer and mjpeg for the analysis. It's probably faster to use the same codec for both (we NEED mjpeg for the analysis).

- [ ] use real multiprocessing

Right now only multithreading is used (python does not have real multithreading and only and core is used at a time). Use multiprocessing in order to use all kernels...

- [ ] Integrate the Buffer and the Goal Detection

We do have a working buffer and a working goal detection. They need to be combined and the buffer replayed when a goal is detected

- [ ] Combine with Arcade Kicker

As the kicker has RGB-Led stripes with WLAN, it would be cool if the Kicker is lightened in the color of the team that scored during replay time. 
