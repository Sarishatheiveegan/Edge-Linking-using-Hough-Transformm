# Edge-Linking-using-Hough-Transformm
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

Using the HoughLinesP(),detect line co-ordinates for every points in the images.Using For loop,draw the lines on the found co-ordinates.Display the image.

## PROGRAM
#### DONE BY:MARINO SARISHA T
#### REG NO:212223240084
```python
plt.figure(figsize = [15,4])
plt.subplot(121); plt.hist(img.ravel(),256,range = [0, 256]); plt.title('Original Image')
plt.subplot(122); plt.hist(img_eq.ravel(),256,range = [0, 256]); plt.title('Histogram Equalized')
```
```python
image = cv2.imread('chess.png')
gray_image = cv2.cvtColor(image, cv2.COLOR_BGR2GRAY)
```
```python
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Input Image")
plt.axis('off')
plt.show()
```
![Screenshot 2025-04-30 110626](https://github.com/user-attachments/assets/f4bb5694-8d77-43dc-999c-6a7a74082443)

```python
plt.imshow(gray_image, cmap='gray')
plt.title("Grayscale Image")
plt.axis('off')
plt.show()
```
![Screenshot 2025-04-30 110633](https://github.com/user-attachments/assets/080b4f51-0be9-4cfd-aade-707395cf9d46)

```
edges = cv2.Canny(gray_image, 50, 150)
```
```python
plt.imshow(edges, cmap='gray')
plt.title("Canny Edge Detector")
plt.axis('off')
plt.show()
```
![Screenshot 2025-04-30 110642](https://github.com/user-attachments/assets/063e749a-aeda-4805-aee3-e206655a23c5)

```python
lines = cv2.HoughLinesP(edges, 1, np.pi / 180, 100, minLineLength=50, maxLineGap=10)
```
```python
for line in lines:
    x1, y1, x2, y2 = line[0] 
    cv2.line(image, (x1, y1), (x2, y2), (0, 255, 0), 2)
```
```python
plt.imshow(cv2.cvtColor(image, cv2.COLOR_BGR2RGB))  
plt.title("Result of Hough Transform")
plt.axis('off')
plt.show()
```
![Screenshot 2025-04-30 110651](https://github.com/user-attachments/assets/ab3f41d9-4378-4420-93e4-f06723d52885)



## Output

### Input image and grayscale image
![Screenshot 2025-04-30 110626](https://github.com/user-attachments/assets/ccb0d7d8-a2be-451c-8e9e-5f3cf725e820)
![Screenshot 2025-04-30 110633](https://github.com/user-attachments/assets/92611b36-7234-4e2a-8a4d-2387c0377b19)


### Canny Edge detector output
![Screenshot 2025-04-30 110642](https://github.com/user-attachments/assets/67228618-e0a4-4375-815b-06888c75e99f)


### Display the result of Hough transform
![Screenshot 2025-04-30 110651](https://github.com/user-attachments/assets/c3c8bffe-9c68-4a6c-ae9b-a03c71bb8b16)

## RESULT
Thus the python program toto detect the lines using Hough Transform is done successfully.
