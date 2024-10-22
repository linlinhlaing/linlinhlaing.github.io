---
title: "Image Processing Libraries"
date: 2024-10-22T15:39:52-05:00
draft: false
tags: ["Python","Machine Learning","Image Processing","Image Processing Libraries", "Learning notes"]
categories: ["Python"]
---
### OpenCV → mainly used in TensorFlow

- Purpose: Computer vision and image processing.
- Features: Real-time operations, image transformations, filtering, object detection, edge detection.
- Installation: `pip install opencv-python`


### Pillow (PIL) → PyTorch

- Purpose: Image manipulation.
- Features: Open, save, and process many image file formats; resizing, cropping, and rotating images.
- Installation: `pip install Pillow`

### **from glob import glob vs import glob**

- **`from glob import glob`**: Imports only the `glob()` function, so you can call it directly as `glob()`.
- **`import glob`**: Imports the whole `glob` module, so you need to call the function as `glob.glob()`.

### **matplotlib.pyplot vs matplotlib.pylab**

- **`matplotlib.pyplot`**: Preferred for most plotting tasks; provides a clean, modular interface for creating and customizing plots.
- **`matplotlib.pylab`**: Combines plotting with numerical operations; less commonly used due to its less modular approach and potential for namespace conflicts.