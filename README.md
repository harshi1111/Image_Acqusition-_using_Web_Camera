### EX 2 - Image Acquisition using Web Camera

### Aim:
 
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.
i) Write the frame as JPG 
ii) Display the video 
iii) Display the video by resizing the window
iv) Rotate and display the video

## Software Used
Anaconda - Python 3.7
## Algorithm
### Step 1:
Use cv2.VideoCapture(0) to access web camera.
### Step 2:
Use cv2.imread to read the video or image.
### Step 3:
Use cv2.imwrite to save the image.
### Step 4:
Use cv2.imshow to show the video.
### Step 5:
End the program and close the output video window by pressing 'q'.

## Program:
``` 
### Developed By: HARSHITHA V
### Register No: 212223230074
```
## i) Write the frame as JPG file
```
import cv2
videoCaptureObject = cv2.VideoCapture(0)
ret, frame = videoCaptureObject.read()
if ret:
    cv2.imwrite("web.jpg", frame)
    print("Image saved as web.jpg")
else:
    print("Failed to capture image")
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## ii) Display the video
```
videoCaptureObject = cv2.VideoCapture(0)
while True:
    ret, frame = videoCaptureObject.read()
    cv2.imshow('myimage', frame)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
videoCaptureObject.release()
cv2.destroyAllWindows()
```
## iii) Display the video by resizing the window
```
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
## iv) Rotate and display the video
```
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

![image](https://github.com/user-attachments/assets/dee9a909-03aa-4c0c-a62f-d6aa45e94d6f)

### ii) Display the video

![image](https://github.com/user-attachments/assets/bd255dcd-efb4-475e-8bc2-a553f6f7aa5c)

### iii) Display the video by resizing the window

![image](https://github.com/user-attachments/assets/a466783e-4110-43d5-afc1-18f62e79f150)

### iv) Rotate and display the video

![image](https://github.com/user-attachments/assets/a7145cea-a4b3-4d9b-8622-0a9274bbef8c)





## Result:
Thus the image is accessed from webcamera and displayed using openCV.
