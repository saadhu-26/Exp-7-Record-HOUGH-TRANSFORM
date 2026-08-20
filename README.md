# Exp-7-Record-HOUGH-TRANSFORM
## Aim
To write a Python program to detect lines in an image using the Hough Transform technique.

## Software Required
- Python 3.x
- OpenCV (cv2)
- NumPy
- Matplotlib
- Jupyter Notebook / VS Code

## Algorithm
- Start the program.
- Import OpenCV, NumPy and Matplotlib libraries.
- Read the input image using cv2.imread().
- Convert the input image into a grayscale image.
- Apply Canny Edge Detection to identify the edges.
- Apply Probabilistic Hough Transform (HoughLinesP) to detect straight lines.
- Extract the coordinates of the detected lines.
- Draw the detected lines on the original image using cv2.line().
- Display the input image, grayscale image, Canny edge image and Hough Transform result.
- Stop the program.

## Program
```
import cv2
import numpy as np
import matplotlib.pyplot as plt
image = cv2.imread('pic .jpg')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB)) 
plt.title("Input Image")
plt.axis('off')
```
```
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
```
```
edges = cv2.Canny(gray_image, 50, 150)
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
```
```
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
for line in lines:
    x1, y1, x2, y2 = line[0]  
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')
```

## Output
The following outputs are obtained:

- ### Input Image


<img width="592" height="334" alt="Screenshot 2026-08-20 140634" src="https://github.com/user-attachments/assets/0afd0dd0-cd60-47ce-b95e-52468298c3a4" />

- ### Grayscale Image


<img width="592" height="334" alt="Screenshot 2026-08-20 140652" src="https://github.com/user-attachments/assets/448b6a9d-e5c8-472f-b7af-3309ae9bc4b0" />

- ### Canny Edge Detector Image


<img width="599" height="345" alt="Screenshot 2026-08-20 140711" src="https://github.com/user-attachments/assets/0c11a2fc-5372-45a3-aefc-3fe2f11d2990" />

- ### Result of Hough Transform – detected lines are highlighted on the original image.


<img width="599" height="337" alt="Screenshot 2026-08-20 140724" src="https://github.com/user-attachments/assets/e6d294d4-1eea-481f-95d7-5cbd3032cb3b" />

## Result
Thus, the lines in the given input image were successfully detected using the Hough Transform technique.
