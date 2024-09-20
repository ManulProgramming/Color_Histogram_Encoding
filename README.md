# Color Histogram Encoding
![image](https://github.com/user-attachments/assets/f3cb0379-f4ad-4340-8161-16f6fc694132)

Color Histogram Encoding – while not traditionally named as a proper encoding method, can still be considered one. This encoding method is used to represent an image’s color distribution, including the intensity and frequency of general colors used in the RGB (Red, Green, Blue) system. It can be used to show an image in numerical values and forms used in analysis and processing. 
As a non-standard image encoding method, it does not have a proper decoder class or method, making it almost impossible to use it in the decoding process of encoded data. The word “almost” is a key in that sentence, as there is a way to use Color Histogram in a decoder class alongside other data and information of the original image. For example, specialized cases, like image generation or approximation, may use histograms as a feature for tasks like [image synthesis](https://arxiv.org/pdf/2005.03995v1).

## Installation:

This application was developed and tested on Windows 11 with Python 3.10. It is unknown if the application works with different versions of OS and Python.

Clone the repository from git clone: [https://github.com/ManulProgramming/Color_Histogram_Encoding](https://github.com/ManulProgramming/Color_Histogram_Encoding)

Got to the /Color_Histogram_Encoding and install requirements using pip:

```bash
pip install -r requirements.txt
```

## Usage:

The application is contained in the main.py file, where at the end of the file there are two lines of code:
```python
r_hist, g_hist, b_hist = color_histogram_encode("examples/Cat.png", 40)
plot_color_histograms(r_hist, g_hist, b_hist)
```
Those lines are used to find frequencies for each RGB (Red, Green, Blue) color channel in the color_histogram_encode() function and then plot it using plot_color_histograms().

### Help on each function:
- color_histogram_encode(image_path, bins)
  Args:
    - image_path: string, providing a path to the image file, accepted by Pillow library.
    - bins: int, amount of bins to use in the histogram (in other words, amount of bars to show).

  This algorithm converts an image into an array of pixels in an RGB channel.
  Then by going through every single pixel, it divides color intensity of each pixel into groups of Red, Green, and Blue channels.
  It also takes into account the number of bins, which will decide what color intensities are "close" enough.
  For example, with bin=8, it will take the range 0-32 level of intensity as one first group.
  In other words, all of those intensities will be added to the first bar you see in the histogram.

- plot_color_histograms(r_hist, g_hist, b_hist)
  Args:
    - r_hist: list or numpy array, that contains frequencies of each red color intensity.
    - g_hist: list or numpy array, that contains frequencies of each green color intensity.
    - b_hist: list or numpy array, that contains frequencies of each blue color intensity.

  This just uses matplotlib to plot the data received from the function color_histogram_encode.
  Nothing too crazy.

## Example:

As an example, we will use an image of a cat as an input for our program:

![Cat](examples/Cat.png)

Then to use this image in Python we need to use this code:
```python
r_hist, g_hist, b_hist = color_histogram_encode("examples/Cat.png", 100)
plot_color_histograms(r_hist, g_hist, b_hist)
```
Where “Cat.png” is a file path to our image of a cat, and 100 – is the number of bins.
The result of the code will be this histogram:

![Color_Histogram_encoding_Cat_example](https://github.com/user-attachments/assets/3ed7d638-18e7-4ce9-9610-7117930222bb)

## Notes:

This is a project for the Information theory discipline at my University, because of it, the application is created for educational purposes. It should not be considered as a serious tool or encoding method, but rather as a basic Python project. The image of the cat was generated using Stable-Diffusion and the [PixelWaveTurbo](https://civitai.com/models/215538/pixelwaveturbo-excellent-images-in-5-steps).

## Licence:

[MIT](https://github.com/ManulProgramming/Color_Histogram_Encoding/blob/main/LICENSE)
