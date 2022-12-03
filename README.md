# ocr
## _Optical Character Recognistion(OCR) application to convert  images with text aligned horizontally that don’t require any additional image processing into text_


Source code : https://python-bloggers.com/2022/05/extract-text-from-image-using-python/

# Introduction
Extracting text from images is a very popular task in the operations units of the business (extracting information from invoices and receipts) as well as in other areas.

OCR (Optical Character Recognition) is an electronic computer-based approach to convert images of text into machine-encoded text, which can then be extracted and used in text format.

To continue following this tutorial we will need:

- Tesseract
- Two Python Libraries
  - pytesseract
  - pillow
  
Tesseract is an open source OCR (optical character recognition) engine which allows to extract text from images.

In order to use it in Python, we will also need the pytesseract library which is a wrapper for Tesseract engine.

Since we are working with images, we will also need the pillow library which adds image processing capabilities to Python.

First, search for the Tesseract installer for your operating system. For Windows, you can find the latest version of Tesseract installer here. Simply download the .exe file and install on your computer.

If you don’t have the Python libraries installed, please open “Command Prompt” (on Windows) and install them using the following code:

```sh
pip install pytesseract
pip install pillow
```



# Sample images
In order to continue in this tutorial we will use some images to work with.

Here are the few images we will use in this tutorial:


![alt text](https://github.com/dildeo1/ocr/blob/dev/miniproject/sampletext.png)
![alt text](https://github.com/dildeo1/ocr/blob/dev/miniproject/sampletext1-ocr.png)

# Extract text from a single image using Python 

Let’s start with extracting text from a single image using Python.

For this example, we will work with the first image provided in the previous section: sampletext1-ocr.png

Here is how the structure of my files look like:
[alt text](https://github.com/dildeo1/ocr/blob/dev/miniproject/image-10.webp)

Now we have everything we need and can easily extract text from image using Python:

```sh
from PIL import Image
from pytesseract import pytesseract
#Define path to tessaract.exe
path_to_tesseract = r'C:\Program Files\Tesseract-OCR\tesseract.exe'
#Define path to image
path_to_image = 'images/sampletext1-ocr.png'
#Point tessaract_cmd to tessaract.exe
pytesseract.tesseract_cmd = path_to_tesseract
#Open image with PIL
img = Image.open(path_to_image)
#Extract text from image
text = pytesseract.image_to_string(img)
print(text)
```
And you should get:

```sh
Sample Text 1
```


