
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

### Developed By: J.JANANI
### Register No: 212223230085

## i) Write the frame as JPG file
```
import cv2
import numpy as np
viedoCaptureObject=cv2.VideoCapture(0)
ret,frame=viedoCaptureObject.read()
cv2.imwrite("captured_frame.jpg",frame)
viedoCaptureObject.release()
cv2.destroyAllWindows()
```



## ii) Display the video
```
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
cv2.imshow('captured_frame', frame)
cv2.waitKey(10000)
cap.release()
cv2.destroyAllWindows()
```



## iii) Display the video by resizing the window
```
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=smaller_frame
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=smaller_frame
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000)  
image_dict = {'captured_image1': image}
cv2.imwrite('captured_image1.jpg', image)
cap.release()
cv2.destroyAllWindows()
```



## iv) Rotate and display the video


```
cap=cv2.VideoCapture(0)
ret,frame=cap.read()
width=int(cap.get(3))
height=int(cap.get(4))
image=np.zeros(frame.shape,np.uint8)
smaller_frame=cv2.resize(frame,(0,0),fx=0.5,fy=0.5)
image[:height//2, :width//2]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, :width//2]=smaller_frame
image[:height//2, width//2:]=cv2.rotate(smaller_frame,cv2.ROTATE_180)
image[height//2:, width//2:]=smaller_frame
cv2.imshow('',image)
cv2.waitKey(5000) 
image_dict = {'captured_image2': image}
cv2.imwrite('captured_image2.jpg', image)
cap.release()
cv2.destroyAllWindows()

```
## Output

### i) Write the frame as JPG image
![437143214-1e30f2d4-e2fd-40b9-8de0-a7c65550a33a](https://github.com/user-attachments/assets/ac0f117e-3998-4d56-992b-16da6184ba96)



### ii) Display the video

![437143226-be847620-b370-449f-9922-e81f5135d1da](https://github.com/user-attachments/assets/76af811c-11e7-4552-9c24-3e3b6b0352e7)


### iii) Display the video by resizing the window

![437139773-b1eb82d5-4f34-456c-9b35-32764433350a](https://github.com/user-attachments/assets/5d778b2b-32ae-45dc-b1cd-157ceb634922)


### iv) Rotate and display the video

![437139885-79f68e19-356a-4324-b0f5-68c23224b338](https://github.com/user-attachments/assets/5dd3ea5e-c8e8-4977-89aa-5eb2cfcef205)






## Result:
Thus the image is accessed from webcamera and displayed using openCV.
