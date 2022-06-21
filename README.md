# Image-Acquisition-from-Web-Camera
## Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import Opencv and numpy(selective programs).

### Step 2:
Using VideoCapture(0), you can capture the picture.



### Step 3:
Using read(),you can read the given input through webcam.


### Step 4:

Using get() or shape() we can divide the screens into many parts.
### Step 5:
End the Program.



## Program:
``` Python
### Developed By: NITHISHWAR S
### Register No: 212221230071

## i) Write the frame as JPG file

import cv2
cam=cv2.VideoCapture(0)
while(True):
    ret,frame= cam.read()
    cv2.imwrite("picture.jpg",frame)
    result = False
cam.release()
cv2.destroyAllWindows()


## ii) Display the video

import cv2
cap = cv2.VideoCapture(0)
while True:
    ret,frame = cap.read()
    cv2.imshow('frame',frame)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

## iii) Display the video by resizing the window


import numpy as np
import cv2
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame
    image[height//2:, width//2:] = smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()



## iv) Rotate and display the video

import numpy as np
import cv2
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read()
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape,np.uint8)
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5)
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, width//2:] = smaller_frame
    cv2.imshow('frame', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image

![image](https://user-images.githubusercontent.com/94164665/163959130-e36b522f-f220-4d2b-b337-64128cf1befe.png)

### ii) Display the video

![image](https://user-images.githubusercontent.com/94164665/163958305-d09fa153-41af-4f31-a623-366ee1527ecf.png)


### iii) Display the video by resizing the window

![image](https://user-images.githubusercontent.com/94164665/163959371-25d22683-45a4-419b-8733-17cba7aac77a.png)


### iv) Rotate and display the video


![image](https://user-images.githubusercontent.com/94164665/163959442-b5837634-c453-4c91-89d5-aaba989426bf.png)


## Result:
Thus the image is accessed from webcamera and displayed using openCV.
