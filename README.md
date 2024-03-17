Python Image Converter using PIL/Pillow Library
This Python script utilizes the PIL/Pillow library for photo editing tasks and provides a convenient way to convert images from JPG to PNG format. It includes functionality to mass convert images within a directory.

Requirements
Python 3.x
PIL/Pillow library (install using pip install Pillow)
Usage
Ensure you have Python 3.x installed on your system.
Install the PIL/Pillow library by running pip install Pillow.
Run the script using the command python image_converter.py <input_folder> <output_folder>, where <input_folder> is the directory containing the JPG images to convert, and <output_folder> is the directory where the converted PNG images will be saved.
Script Explanation

import sys
import os
from PIL import Image

image_folder = sys.argv[1]
output_folder = sys.argv[2]

if not os.path.exists(output_folder): 
    os.makedirs(output_folder)

for filename in os.listdir(image_folder):
    img = Image.open(os.path.join(image_folder, filename))
    clean_name = os.path.splitext(filename)[0]
    img.save(os.path.join(output_folder, f'{clean_name}.png'), 'png')
    print('Conversion complete.')
The script takes two command-line arguments: <input_folder> (the folder containing JPG images) and <output_folder> (the folder where PNG images will be saved).
It uses the os module to handle file system operations and the Image module from PIL for image manipulation tasks.
The script checks if the output folder exists. If not, it creates one.
It iterates through each file in the input folder, opens it with PIL, converts it to PNG format, and saves it in the output folder with the same name.
Example
Suppose you have the following directory structure:

/images
    |- photo1.jpg
    |- photo2.jpg
    |- photo3.jpg
/image_converter.py
You can run the script as follows:

python image_converter.py ./images/ ./converted_images/
After running the script:

/images
    |- photo1.jpg
    |- photo2.jpg
    |- photo3.jpg
/converted_images
    |- photo1.png
    |- photo2.png
    |- photo3.png
/image_converter.py
