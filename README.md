# EX-08
# THRESHOLDING
## Aim
To segment the image using global thresholding, adaptive thresholding and Otsu's thresholding using python and OpenCV.

## Software Required
1. Anaconda - Python 3.7
2. OpenCV

## Algorithm

### Step1:
Import necessary packages
### Step2:
Read the image
### Step3:
If the read image is a color image, convert it into a grayscale image

### Step4:
perform the threshold operation you want to do(global thresholding or adaptive thresholding or otsu's thresholding)

### Step5:
Display the Results

## Program
# Developed by:JANANI.VS
# Register number:212222230050

# Read the Image and convert it to grayscale
```
img = cv2.imread('cat.jpeg',-1)
cv2.imshow('original_image',img)
cv2.waitKey(0)
cv2.destroyAllWindows
gray =cv2.cvtColor(img,cv2.COLOR_BGR2GRAY)
cv2.imshow('gray_image',gray)
cv2.waitKey(0)
cv2.destroyAllWindows
```

# Use Global thresholding to segment the image
```
ret,thresh_img1=cv2.threshold(gray,86,255,cv2.THRESH_BINARY)
ret,thresh_img2=cv2.threshold(gray,86,255,cv2.THRESH_BINARY_INV)
ret,thresh_img3=cv2.threshold(gray,86,255,cv2.THRESH_TOZERO)
ret,thresh_img4=cv2.threshold(gray,86,255,cv2.THRESH_TOZERO_INV)
ret,thresh_img5=cv2.threshold(gray,100,255,cv2.THRESH_TRUNC)
```

# Use Adaptive thresholding to segment the image
```
thresh_img6=cv2.adaptiveThreshold(gray,255,cv2.ADAPTIVE_THRESH_MEAN_C,cv2.THRESH_BINARY,11,2)
thresh_img7=cv2.adaptiveThreshold(gray,255,cv2.ADAPTIVE_THRESH_GAUSSIAN_C,cv2.THRESH_BINARY,11,2)

```
# Use Otsu's method to segment the image 
```
ret,thresh_img8=cv2.threshold(gray,0,255,cv2.THRESH_BINARY+cv2.THRESH_OTSU)
```


# Display the results
```
image =[thresh_img1,thresh_img2,thresh_img3,thresh_img4,thresh_img5,thresh_img6,thresh_img7,thresh_img8]
for i in range(0,8):
    cv2.imshow('threshold_image',image[i])
    cv2.waitKey(0)
    cv2.destroyAllWindows
```


## Output

### Original Image

![Screenshot 2024-04-03 090935](https://github.com/Anusharonselva/THRESHOLDING-/assets/119405600/43ff2957-e66a-4c9f-95b5-2bca52c0432a)

### Global Thresholding
![Screenshot 2024-04-03 090947](https://github.com/Anusharonselva/THRESHOLDING-/assets/119405600/04ad6a7a-b762-427d-bf75-8eff9a21bda6)

![Screenshot 2024-04-03 091011](https://github.com/Anusharonselva/THRESHOLDING-/assets/119405600/e326d211-c142-4e2a-8af9-3a994273d8d0)

### Adaptive Thresholding
![Screenshot 2024-04-03 091022](https://github.com/Anusharonselva/THRESHOLDING-/assets/119405600/53e63026-4934-425c-9f51-552b3d72055a)

### Optimum Global Thesholding using Otsu's Method
![Screenshot 2024-04-03 091033](https://github.com/Anusharonselva/THRESHOLDING-/assets/119405600/20314a9c-564a-4bfe-a4df-6d45d0ea19b3)

![Screenshot 2024-04-03 091042](https://github.com/Anusharonselva/THRESHOLDING-/assets/119405600/ea87f36f-639f-4543-a4f1-991ee58ffb7c)


## Result
Thus the images are segmented using global thresholding, adaptive thresholding and optimum global thresholding using python and OpenCV.
