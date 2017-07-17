# 5. Create Ascii Art Applicaion

## What is an Ascii Art? {#what-is-an-ascii-art}
Ascii art is a graphic style composed of alphabets and symboles.

![Beethoven](../images/Beethoven_AsciiMSGothicRegular23.png)

![TheGirlWithThePearlEarring](../images/Johannes_Vermeer_1632-1675_-_The_Girl_With_The_Pearl_Earring_1665_AsciiMSGothicRegular23.png)

![godfatherII](../images/godfatherII_AsciiMSGothicRegular23.png)

![Mona_Lisa](../images/Mona_Lisa_AsciiMSGothicRegular23.png)

![matrix](../images/matrix_dodge.gif)

![matrix](../images/matrix_dodge_aa03.gif)

![matrix](../images/matrix_dodge_aa_fs32.gif)

## 5.2 Load Image {##load-image}
You use Python Image Library. If you installed Python with Anaconda, it alredy installed the library, otherwise execute ```pip install Pillow```.
We use the sample input image ```Lenna.png``` . Locate the image in the same folder as .py file.

First, you load an image and print its size.

```py
from PIL import Image
img = Image.open('Lenna.png')
print(img.size)
```

![Lenna](../images/Lenna.png)

## Convert into Grayscale {#convert-into-grayscale}

## Draw Ascii Art {#draw-ascii-art}

## Save Image {#save-image}
