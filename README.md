# EX 02: Image_Acqusition-_using_Web_Camera

## Aim:
To write a python program using OpenCV to capture the image from the web camera and do the following image manipulations.

i) Write the frame as JPG 

ii) Display the video 

iii) Display the video by resizing the window

iv) Rotate and display the video

## Software Used:
Anaconda - Python 3.7

## Algorithm:
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
``` Python
### Developed By: AALIYA FATHIMA M
### Register No: 212223230001

## i) Write the frame as JPG file
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite("captured_frame.jpg", frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
```

<img width="634" height="524" alt="Screenshot 2025-09-15 091319" src="https://github.com/user-attachments/assets/d5e2da77-71d8-4836-8a33-b4c5279cb57f" />




```
## ii) Display the video
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    frame_rgb = cv2.cvtColor(frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
<img width="615" height="506" alt="Screenshot 2025-09-15 091337" src="https://github.com/user-attachments/assets/aeba9c19-b6ff-4656-8b7a-424fe17f5fb0" />



```
## iii) Display the video by resizing the window
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    resized_frame = cv2.resize(frame, (100, 150))  # Resize to 320x240
    frame_rgb = cv2.cvtColor(resized_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
<img width="313" height="473" alt="Screenshot 2025-09-15 091351" src="https://github.com/user-attachments/assets/498ff65e-be7e-4758-ba7c-718ff4c2607d" />



```
## iv) Rotate and display the video
cap = cv2.VideoCapture(0)

for i in range(50):
    ret, frame = cap.read()
    if not ret:
        break
    rotated_frame = cv2.rotate(frame, cv2.ROTATE_90_CLOCKWISE)
    frame_rgb = cv2.cvtColor(rotated_frame, cv2.COLOR_BGR2RGB)
    clear_output(wait=True)
    plt.imshow(frame_rgb)
    plt.axis('off')
    plt.show()
    time.sleep(0.05)

cap.release()
```
<img width="345" height="463" alt="Screenshot 2025-09-15 091401" src="https://github.com/user-attachments/assets/7c47ef0d-aba4-4309-9cc6-1863a0fae6c9" />



## Result:
Thus the image is accessed from webcamera and displayed using openCV.
