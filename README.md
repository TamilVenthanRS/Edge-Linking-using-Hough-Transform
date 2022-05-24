# Edge-Linking-using-Hough-Transform
## Aim:
To write a Python program to detect the lines using Hough Transform.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import all the necessary modules for the program.

### Step2:
Load a image using imread() from cv2 module.

### Step3:
Convert the image to grayscale.

### Step4:
Using Canny operator from cv2,detect the edges of the image.

### Step5:
Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.


## Program:
```python
/*
developed by: Dineshkumar V
reg no : 212220230013
*/

# Read image and convert it to grayscale image
img=cv2.imread("road.jpg",cv2.IMREAD_COLOR)
img=cv2.resize(img,(300,200))
g_img=cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow("Road",img)
cv2.imshow("GrayRoad",g_img)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Find the edges in the image using canny detector and display
img1=cv2.GaussianBlur(g_img,(3,3),0)
canny = cv2.Canny(g_img, 70, 150)
cv2.imshow("Canny edge detector",canny)
cv2.waitKey(0)
cv2.destroyAllWindows()

# Detect points that form a line using HoughLinesP
lines=cv2.HoughLinesP(canny,1,np.pi/180, threshold=100, minLineLength=50,maxLineGap=250)


# Draw lines on the image
for line in lines:
    x1, y1, x2, y2 = line [0] 
    cv2.line(img,(x1, y1),(x2, y2),(0, 0, 255),3)
 
# Display the result
cv2.imshow("Hough transform",img)
cv2.waitKey(0)
cv2.destroyAllWindows()

```
## Output

### Input image and grayscale image
<br/>![g1](https://user-images.githubusercontent.com/75235789/169962500-feecff5e-a972-408d-bd6a-dd75a2ecea45.jpg)



### Canny Edge detector output
<br/>![g2](https://user-images.githubusercontent.com/75235789/169962515-ea1a1c84-d98d-4340-913d-66bc27b9afe9.jpg)



### Display the result of Hough transform
<br/>![g3](https://user-images.githubusercontent.com/75235789/169962529-6f181531-5131-41d7-88c8-9f7156df2467.jpg)



## Result:
Thus the program is written with python and OpenCV to detect lines using Hough transform. 
