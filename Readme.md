# Direct Imaging of Electron Orbital Cross Sections with a Scanning Transmission Electron Microscope

This repository houses the data and analysis workflow for the publication [full citation when available]. The data is contained in the files:

SEEBIC image `Recording of SuperScan(Ext).tif`

HAADF image `Recording of SuperScan(HAADF).tif`

These images are 32 bit and do not display in most image viewers ([Imagej](https://imagej.nih.gov/ij/)/[Fiji](https://imagej.net/software/fiji/) does display them). The analysis workflow is contained in the Jupyter notebook `atomai_analysis.ipynb`. All other files are produced by the notebook.

Here are example frames from the image stacks.

[<img src="Recording_of_SuperScan_(HAADF)_HAADF_SEEBIC_comparison.png" width="400"/>](Recording_of_SuperScan_(HAADF)_HAADF_SEEBIC_comparison.png)

The analysis workflow uses a pre-trained deep convolutional neural network (DCNN) from [AtomAI](https://github.com/pycroscopy/atomai/) to find atoms in the HAADF image.

[<img src="Recording_of_SuperScan_(HAADF)_DCNN.png" width="400"/>](Recording_of_SuperScan_(HAADF)_DCNN.png)

Image tiles are then extracted from the images centered on the lattice positions.

[<img src="Recording_of_SuperScan_(HAADF)_example_tiles.png" width="400"/>](Recording_of_SuperScan_(HAADF)_example_tiles.png)

K-means clustering is used on the tiles to discriminate between the different lattice sites.

[<img src="Recording_of_SuperScan_(HAADF)_classified_histogram.png" width="400"/>](Recording_of_SuperScan_(HAADF)_classified_histogram.png)

Finally, the mean response for HAADF and SEEBIC signals is calculated.

[<img src="Recording_of_SuperScan_(HAADF)_mean_response.png" width="400"/>](Recording_of_SuperScan_(HAADF)_mean_response.png)
