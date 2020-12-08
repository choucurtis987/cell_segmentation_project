# Cell Segmentation Project
- [Main Script](/cell_segmentation.ipynb)
## Background
- This code was done during my Community College Internship (CCI) at Lawrence Berkeley National Lab (LBNL) as a prerequisite to my research. This code displays similar work done with similar processes and the same model. My code for the research done during the internship could not be shared as it contained confidential data.
- This project is used to display work similar to the things I worked on during my internship at LBNL
## Project Goals
- Semantic segmentation of nuclei to identify two classes: background and foreground (nuclei)
- Utilize Connected Component Analysis (CCA) on the segmented binary image to count nuclei
## Technical Background
- Semantic segmentation is segmenation of an image where the goal is link each pixel to a class label
- Fully Convolutional Networks (FCN) are a variation of traditional CNNs commonly used for tasks like semantic segmentation
- CCA is a technqiue that labels regions of an image. In our case, it labels the white pixel areas (nuclei / foreground) surrounded by blacks pixels (background) as a region. CCA then labels the entire image and simultaneously counts the regions. Thus, counting the number of nuclei in the image.
