# Computer vision Baiscs
## CV image_read_crop_write
```python
#read
img = cv2.imread((sound_dir+filename))
shape = img.shape
#crop
crop1 = img[0:230, 0:160]
crop2 = img[0:230, 160: 330]
crop3 = img[0:230, 330:]
#write
cv2.imwrite('data/practice/1-' + filename, crop1)
cv2.imwrite('data/practice/2-' + filename, crop2)
cv2.imwrite('data/practice/3-' + filename, crop3)
```
## Disaply Image
```python
cv2.imshow()
cv2.destroyAllWindows()
```
## Advanced
```python
# Draw Contour
img=cv2.imread(fname)
imgray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
ret, thresh = cv2.threshold(imgray, 127, 255, 0)
contours, hierarchy = cv2.findContours(thresh, cv2.RETR_TREE, cv2.CHAIN_APPROX_SIMPLE)
img2=cv2.drawContours(img, contours, -1, (0,255,0), 3)
plt.imshow(img)
```