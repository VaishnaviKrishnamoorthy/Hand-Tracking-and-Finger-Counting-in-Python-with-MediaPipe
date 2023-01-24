# Hand-Tracking-and-Finger-Counting-in-Python-with-MediaPipe

# Implementation
The implementation below works by running the MediaPipe Hands process function in each frame of the webcam video capture. For each frame, the results provide a 3D landmark model for each hand detected. For each of the hands detected, these are the steps followed:

1.Check detected hand label.

2.Store x and y coordinates of each landmark.

3.Check each finger’s coordinates to determine if it is raised to increase finger count.

4.Draw hand landmarks with draw_landmarks function.

# For the third step, there are two approaches to test if a finger is raised:

1.For the thumb, we’ll check the values of the THUMB_TIP and THUMB_IP x coordinates, and the hand label. The thumb is considered raised if the _TIP is located to the right of the _IP, for the left hand, and the opposite for the right hand.

2.For the other fingers, we’ll check the values of the _TIP and _PIP y coordinates. The finger is considered raised if the _TIP is located higher than the _PIP.

# Two important notes for the implementation of the third step are:

1.Because we are using the webcam input capture, the left hand is labeled as “right”, and the right hand is labeled as “left”.

2.The image’s origin [0, 0] when using the OpenCV library is in the upper left corner.
