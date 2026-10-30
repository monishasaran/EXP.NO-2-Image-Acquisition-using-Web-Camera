# EXP.NO-2-Image Capture and Video Processing Using OpenCV
# Aim
To write a Python program using OpenCV to capture an image from the webcam and perform the following operations:

Write the frame as a JPG file
Display the video
Display the video by resizing the window
Rotate and display the video

# 🛠️ Software Used
Anaconda – Python 3.7
Jupyter Notebook / VS Code
OpenCV (cv2)

# ⚙️ Algorithm
Step 1:
Import the required libraries and initialize the webcam using cv2.VideoCapture().

Step 2:
Capture frames continuously from the webcam.

Step 3:
Save a frame as a JPG image using cv2.imwrite().

Step 4:
Display the live video stream using cv2.imshow().

Step 5:
Resize the frame and rotate it using OpenCV functions, then display the processed frames.

# 💻 Program
## Developed By:
## Name: MONISHA S
## Register No: 212225040258

# CODE:
```
import cv2
import matplotlib.pyplot as plt
from IPython.display import clear_output
import time
cap = cv2.VideoCapture(0)
ret, frame = cap.read()
if ret:
    cv2.imwrite('captured_frame.jpg', frame)
cap.release()
captured_image = cv2.imread('captured_frame.jpg')
plt.imshow(captured_image[:,:,::-1])
plt.title('Captured Frame')
plt.axis('off')
plt.show()
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

# OUTPUT:
<img width="622" height="512" alt="image" src="https://github.com/user-attachments/assets/133f6869-96f5-470d-aae4-aabd98082868" /> <img width="620" height="473" alt="image" src="https://github.com/user-attachments/assets/e61d179b-17ce-46d7-a4d3-dbe9a4b8d22b" />
<img width="325" height="485" alt="image" src="https://github.com/user-attachments/assets/cdfcdf97-2a23-4ba0-a7b1-9e0a8c24424d" /> <img width="367" height="486" alt="image" src="https://github.com/user-attachments/assets/baedd11f-6219-4dfe-9c19-0834e1f2335c" />

# Result:
Thus, the image is successfully captured from the webcam and various video processing operations such as saving, displaying, resizing, and rotating are performed using OpenCV.






