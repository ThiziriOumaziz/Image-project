# Image-project
The goal of this project is to develop an automatic method for detecting blood vessels in histological images of brain tumors stained using the Hematoxylin and Eosin (H&E) method. The developed method follows these steps:

- Color space conversion: Conversion from RGB to HSV color space.
- Blood vessel segmentation: A segmentation step is implemented to obtain a binary mask representing an initial detection of blood vessels. Two approaches, K-means and the use of fixed thresholds derived from channel and histogram analysis, yielded good results.
- Noise elimination: Three approaches were tested:
    - The use of a simple median filter.
    - Detection of connected components (in 8-connectivity) and elimination of components below a certain size threshold.
    - Application of erosion, which is a mathematical morphology process.
- Enhancement of the morphological appearance of blood vessels: The objective here is to improve the visual appearance of the blood vessels in terms of shape, size, continuity, regularity, etc. Two approaches were used: the closing operation and interpolation of components using cubic splines.

**Results:** The method shows promising results but has some limitations. Specifically, it is limited to detecting blood vessels with clear visual characteristics of blood presence, and in some cases, it fails to detect the entire vessel. Furthermore, the different steps must be adjusted based on the size and shape of the vessels, especially concerning thresholds and the shape and size of the structuring element used in morphological operations.

**Future work:** In future work, it would be interesting to combine the steps of the classical approach with deep learning models to automate detection and identify vessels that are less visually explicit. However, this would require the availability of large, labeled datasets. In a deep learning approach, it would also be beneficial to combine the images with information and insights provided by medical professionals.

The project was under the supervision of Professor Isabelle Bloch.