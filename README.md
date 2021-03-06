# Water Meter Reader

## Overview
Here is a workflow of automatic reading of a water meter.

### 1. Fetch pictures
An old Android phone is fixed in front of a water meter. "IP Webcam Pro" works as both a camera app and a server with REST interface. A cliant computer periodically runs a bash script (`meter.sh`) with launchd and fetches camera pictures.

### 2. Extract single-digit images
Extract region of interst with imagemagick. A Python+OpenCV script (`preprocessor`) converts a multi-digit image into a list of single-digit images. Demonstration of this part is explained in `OpenCV Water Meter.ipynb`.

### 3. Prepare labels
Manually prepare a CSV file of (image filename, human-recognized reading) pairs. Then a python script (`OpenCV Water Meter.ipynb`) prepares labels for single-digit images.

### 4. Let a machine learn
Train a neural network using Tensorflow. The procedure is exactly the same as the MNIST recognition in the tutorial.  
