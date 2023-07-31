# Content Aware Image Resizing

## Introduction

Content-Aware Image Resizing is a technique to resize images using Seam Carving. This finds portions of an image with the least details and removes them from the original image. Since only the less detailed portions are removed, the details of the image stay intact which provides better quality images as compared to other resizing techniques such as cropping or scaling.

## Methodology

Content-Aware Image Resizing works by creating an Energy Map (we used Gradient Map), essentially a grayscale map of the image which represents where there are more details and where there are fewer details. After making the energy map, we find a seam (a path of neighbouring pixels from the top to the bottom) that has the minimum cost(details) and then remove it. We then repeat the process for our desired widths (and heights by transposing the image). 

Similar to reducing size, we can also increase the size by finding the seam with the minimum cost and then replicating it to add portions of fewer details to the image.

## Results

### Before

### After

## Limitation and its mitigation

One of the limitations of Content-Aware Image Resizing is that it can deform areas where there is a high level of detail e.g. Faces. To mitigate this we used an already-built face recognition system and integrated it within our project. When the faces were recognised, we would then mark them with the highest value in the energy map to prevent them from becoming the minimum seam

### Before face recognition

### After face recognition

## Credits

- Resources and Literature used is present in the project report.
- Special thanks to my teammates Uswa and Hamna who helped me did their part in this project
