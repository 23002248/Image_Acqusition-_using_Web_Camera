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
Import the cv2 and numpy package.

### Step 2:
Read the Video frame using the cv2.VideoCapture(0)

### Step 3:
Write the image using imwrite().

### Step 4:
Display the frame using the imshow().

### Step 5:
Divide the frame into halves and assign the smaller frame and Rotate the frame using the cv2.rotate().

## Program:

### Developed By: EASWAR R
### Register No: 212223230053

## i) Write the frame as JPG file
``` Python
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
## ii) Display the video
``` Python
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


## iii) Display the video by resizing the window
```python
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
## iv) Rotate and display the video
```python
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
## Output

### i) Write the frame as JPG image
<img width="490" height="368" alt="image" src="https://github.com/user-attachments/assets/33b00996-7d21-46ff-9260-27ee02009923" />

### ii) Display the video
<img width="586" height="436" alt="image" src="https://github.com/user-attachments/assets/0cc33d51-627c-4720-996a-6dd96ec98193" />

### iii) Display the video by resizing the window
<img width="245" height="370" alt="image" src="https://github.com/user-attachments/assets/e5bb959d-17f4-41fd-b12b-a30b957b1481" />

### iv) Rotate and display the video
<img width="273" height="368" alt="image" src="https://github.com/user-attachments/assets/0b5cd8b5-8d26-4c84-b585-255ba94fe5a3" />

## Result:
Thus the image is accessed from webcamera and displayed using openCV.
