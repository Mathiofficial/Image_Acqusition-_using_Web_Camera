# Image_Acqusition-_using_Web_Camera
## Aim

To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Import OpenCV Package.

### Step 2:
Capture Video from Webcam. Use VideoCapture(0) to access the webcam and start capturing video.

### Step 3:
Read Video or Image. Utilize 'imread' to read a video frame or image from the webcam.

### Step 4:
Save Image to File. Employ 'imwrite' to save the captured image to a file.

### Step 5:
Display Video or Image. Use 'imshow' to display the captured video frame or image.

### Step 6:
End Program with 'q'. Allow the program to be terminated by pressing the 'q' key.



## Program:
``` Python
### Developed By: Mathiyazhagan.A
### Register No: 212222240063

## i) Write the frame as JPG file

import cv2
videoCaptureObject = cv2.VideoCapture(0)
while (True):
    ret,frame = videoCaptureObject.read()
    cv2.imwrite("WIN_20240221_16_02_28_Pro.jpg",frame)
    result = False
videoCaptureObject.release()
cv2.destroyAllWindows()
```
```python

## ii) Display the video
import cv2
videoCaptureObject = cv2.VideoCapture(0)
while(True):
    ret,frame = videoCaptureObject.read()
    cv2.imshow('myimage',frame)
    if cv2.waitKey(1) == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```
```python
## iii) Display the video by resizing the window
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = smaller_frame
    image[height//2:, :width//2] = smaller_frame
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
```python
## iv) Rotate and display the video
import cv2
import numpy as np
cap = cv2.VideoCapture(0)
while True:
    ret, frame = cap.read() 
    width = int(cap.get(3))
    height = int(cap.get(4))
    image = np.zeros(frame.shape, np.uint8) 
    smaller_frame = cv2.resize(frame, (0,0), fx = 0.5, fy=0.5) 
    image[:height//2, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[height//2:, :width//2] = cv2.rotate(smaller_frame,cv2.ROTATE_180)
    image[:height//2, width//2:] = smaller_frame 
    image [height//2:, width//2:] = smaller_frame
    cv2.imshow('myimage', image)
    if cv2.waitKey(1) == ord('q'):
        break
cap.release()
cv2.destroyAllWindows()
```
## Output

### i) Write the frame as JPG image
</br>

![WIN_20240221_16_02_28_Pro](https://github.com/Mathiofficial/Image_Acqusition-_using_Web_Camera/assets/118787327/c922a02f-e272-4388-a04b-7174e92320f3)


### ii) Display the video
</br>

![Screenshot 2024-02-22 090604](https://github.com/Mathiofficial/Image_Acqusition-_using_Web_Camera/assets/118787327/6dd81f15-b75a-4dbb-b712-2220c3d50911)



### iii) Display the video by resizing the window
</br>

![Screenshot 2024-02-22 090729](https://github.com/Mathiofficial/Image_Acqusition-_using_Web_Camera/assets/118787327/b3941ab7-04a2-4a12-a57d-811693e3fe4f)




### iv) Rotate and display the video
</br>

![Screenshot 2024-02-22 090833](https://github.com/Mathiofficial/Image_Acqusition-_using_Web_Camera/assets/118787327/4816a9df-994f-40d2-9b10-7a7f71c00bc4)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
