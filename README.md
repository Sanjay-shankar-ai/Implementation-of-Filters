# Implementation-of-Filters
## Aim:
To implement filters for smoothing and sharpening the images in the spatial domain.

## Software Required:
Anaconda - Python 3.7

## Algorithm:
### Step1:
Import cv2, matplotlib.py libraries and read the saved images using cv2.imread().

### Step2:
 Convert the saved BGR image to RGB using cvtColor().

### Step3:
By using the following filters for image smoothing:filter2D(src, ddepth, kernel), Box filter,Weighted Average filter,GaussianBlur(src, ksize, sigmaX[, dst[, sigmaY[, borderType]]]), medianBlur(src, ksize),and for image sharpening:Laplacian Kernel,Laplacian Operator.

### Step4:
Apply the filters using cv2.filter2D() for each respective filters.

### Step5:
Plot the images of the original one and the filtered one using plt.figure() and cv2.imshow().

## Program:
```
Developed By   :Sanjay S
Register Number:2122212300086
```

### 1. Smoothing Filters

### i) Using Averaging Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('baby.jpg')
image2=cv2.cvtColor (image1,cv2.COLOR_BGR2RGB) 
kernel = np.ones ((11,11), np.float32)/121
image3=cv2.filter2D(image2,-1, kernel)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1) 
plt.imshow(image2)
plt.title('Orignal') 
plt.axis('off')
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')



```
### ii) Using Weighted Averaging Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('baby.jpg')
image2=cv2.cvtColor (image1,cv2.COLOR_BGR2RGB) 
kernal2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16 
image3 = cv2.filter2D(image2,-1,kernal2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1) 
plt.imshow(image2)
plt.title('Orignal') 
plt.axis('off')
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')




```
### iii) Using Gaussian Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('baby.jpg')
image2=cv2.cvtColor (image1,cv2.COLOR_BGR2RGB) 
gaussian_blur=cv2.GaussianBlur(src=image2,ksize=(11,11),sigmaX=0,sigmaY=0)
kernal2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16 
image3 = cv2.filter2D(image2,-1,kernal2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1) 
plt.imshow(image2)
plt.title('Orignal') 
plt.axis('off')
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')




```

### iv) Using Median Filter
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('baby.jpg')
image2=cv2.cvtColor (image1,cv2.COLOR_BGR2RGB) 
median=cv2.medianBlur(src=image2, ksize=11)
kernal2 = np.array([[1,2,1],[2,4,2],[1,2,1]])/16 
image3 = cv2.filter2D(image2,-1,kernal2)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1) 
plt.imshow(image2)
plt.title('Orignal') 
plt.axis('off')
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')




```

### 2. Sharpening Filters
### i) Using Laplacian Kernal
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('baby.jpg')
image2=cv2.cvtColor (image1,cv2.COLOR_BGR2RGB) 
kernel3=np.array([[0,1,0],[1,-4,1],[0,1,0]])
image3=cv2.filter2D(image2,-1, kernel3)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1) 
plt.imshow(image2)
plt.title('Orignal') 
plt.axis('off')
plt.subplot(1,2,2)
plt.imshow(image3)
plt.title('Filtered')
plt.axis('off')





```
### ii) Using Laplacian Operator
```py
import cv2
import numpy as np
import matplotlib.pyplot as plt
image1=cv2.imread('baby.jpg')
image2=cv2.cvtColor (image1,cv2.COLOR_BGR2RGB) 
new_image = cv2.Laplacian(image2, cv2.CV_64F)
plt.figure(figsize = (9,9))
plt.subplot(1,2,1) 
plt.imshow(image2)
plt.title('Orignal') 
plt.axis('off')
plt.subplot(1,2,2)
plt.imshow(new_image)
plt.title('Filtered')
plt.axis('off')





```

## OUTPUT:
### 1. Smoothing Filters

### i) Using Averaging Filter
![s3](https://user-images.githubusercontent.com/94231938/230848239-2d7d4c6b-bbd5-439b-8a59-f5ca29e8c791.png)


### ii) Using Weighted Averaging Filter
![s4](https://user-images.githubusercontent.com/94231938/230848287-361f9209-b7f9-4984-8b29-e994d10fdf4b.png))

### iii) Using Gaussian Filter
![s5](https://user-images.githubusercontent.com/94231938/230848335-e34750a5-4797-4156-abfe-c7b120b55e15.png)

### iv) Using Median Filter
![s6](https://user-images.githubusercontent.com/94231938/230848382-35bf91a6-fa4b-4212-aff5-3aace79cd36e.png)

### 2. Sharpening Filters


### i) Using Laplacian Kernal
![s7](https://user-images.githubusercontent.com/94231938/230848414-8d1fb8b7-83f5-4dd8-b9ba-cac7fc828f4f.png)

### ii) Using Laplacian Operator
![s8](https://user-images.githubusercontent.com/94231938/230848441-c7a1e982-ee65-4cc7-830d-4ba2e54c4f97.png)


## Result:
Thus the filters are designed for smoothing and sharpening the images in the spatial domain.
