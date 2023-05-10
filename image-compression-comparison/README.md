# Image Compression and Quality Metrics


This code utilizes the Pillow library to compress images using its built-in compression algorithms while calculating quality metrics for PNG, JPEG, and WebP formats. The quality metrics include the compression ratio, mean squared error (MSE), peak signal-to-noise ratio (PSNR), and structural similarity index (SSIM).


## Compression Algorithms

The code employs the following compression algorithms:

### PNG Compression

Pillow utilizes the Deflate algorithm for PNG compression. Deflate combines the LZ77 algorithm and Huffman coding, resulting in an efficient lossless compression algorithm. It achieves high compression ratios with fast compression and decompression speeds. The implementation of Deflate in Pillow relies on the zlib library.


### JPEG Compression

For JPEG compression, Pillow uses the Discrete Cosine Transform (DCT) algorithm. This algorithm converts image data from the spatial domain to the frequency domain. Pillow quantizes the DCT coefficients and applies entropy encoding using the Huffman coding algorithm to achieve lossy compression. The compression level is determined by the degree of quantization applied to the DCT coefficients. Additionally, the quality of JPEG compression can be adjusted by changing the quantization level.

### WebP Compression

Pillow utilizes the WebP library, based on the VP8 video codec, for WebP compression. WebP format employs a combination of lossy and lossless compression techniques, including variable length coding (VLC) and predictive coding, to achieve high compression rates without significant loss of image quality. Pillow allows you to adjust the quality of the image and the compression level when saving an image in WebP format.



## Installation

Before running the code, ensure that you have the following packages installed:

* NumPy
* Pillow
* scikit-image

You can install these packages by running the following command:

```
pip install numpy Pillow scikit-image
```


## Usage and Output

1. Place the images you want to compress in the "images" folder located in the same path as the Python code. Alternatively, you can specify a different folder path by modifying the "image_folder_path" variable in the code.
2. Run the code using a Python interpreter.
3. after excuting the program, 4 new folders will be created (each folder contains noisy images based on the name of the folder)
4. morover, 5 new folders will be created with "_compressed" at the end of thier names. these folders denote the compressed images
5. finally, 5 txt files will be created showing the quality metrics for each folder


each txt file will include


* compression ratio for (JPEG, PNG, WEBP) for each image
* MSE for (JPEG, PNG, WEBP) for each image
* PSNR for (JPEG, PNG, WEBP) for each image
* SSIM for (JPEG, PNG, WEBP) for each image

Additionally, the each txt file will include the average metrics for each compression algorithm:

* Average CR for (JPEG, PNG, WEBP)
* Average MSE for (JPEG, PNG, WEBP)
* Average PSNR for (JPEG, PNG, WEBP)
* Average SSIM for (JPEG, PNG, WEBP)


# The code has been modified as follow:

## structural similarity index (SSIM)

The code now incorporates the structural similarity index (SSIM) as a quality metric. SSIM provides a more comprehensive assessment of image similarity by considering both pixel-level differences and structural information. It captures perceptual quality by evaluating the similarity of structural patterns and textures between images. SSIM is particularly useful for capturing distortions related to texture, edges, and global structure, providing a more accurate representation of image quality perceived by humans.


## Noise Addition

The code now introduces four types of noise (Gaussian, Salt and Pepper, Poisson, and Speckle) to the images. Each type of noise is added to all images, and the resulting noisy images are stored in specific folders corresponding to each noise type. This allows for evaluating the performance of each compression algorithm under different types of noise, providing a better overview of their performance.

## Showing Output

The code store txt files for showing the outputs in more clear and concise way rather than the previous way of showing the output in the console

## Code Refactoring: 

The code has undergone significant refactoring to improve its clarity, maintainability, and efficiency. The key refinements include:

* Restructuring the code into modular functions, enhancing code organization and reusability.
* Adopting meaningful variable and function names, making the code more self-explanatory.
* Incorporating proper documentation and comments throughout the code to explain its purpose, inputs, and outputs.
* Optimizing code logic and reducing redundancy to improve performance.

These code refinements not only make the codebase more maintainable and extensible but also improve its overall performance and reliability.


> The modified code now provides a more comprehensive evaluation of image quality by incorporating the SSIM metric and assessing the performance of compression algorithms under different types of noise. Additionally, the code has been refactored to enhance its clarity, organization, and efficiency.
As a result, the updated code delivers a more powerful and user-friendly image compression and quality assessment tool.