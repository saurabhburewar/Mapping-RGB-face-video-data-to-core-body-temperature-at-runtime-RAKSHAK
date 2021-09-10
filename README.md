# Mapping-RGB-face-video-data-to-core-body-temperature-at-runtime-RAKSHAK

The objective is mapping the following -
1. RGB image <-> Temperature
2. NIR image <-> Temperature, but this requires RGB -> NIR conversion

Therfore, this project is divided into 2 parts -
1. To find a relation between the temperature of a human body and the image taken by a camera. This is to be done using both RGB and NIR images of the face of a person
2. The second part of the project is where we try to generate the NIR image from RGB images of the human faces.

## Datasets

### Dataset I

The first data was collected by taking RGB images of the forehead regions of the participants and taking their core body temperature using an IR thermometer/thermal gun in a room with artificial lighting. The images correspond to the temperatures 96 °F, 97 °F, 98 °F, 99 °F, and 100 °F. The temperature was measured for varying times of the day after various activities which were also included. However, due to the COVID restrictions, the data collection was limited to a few participants causing the data to be skewed towards the normal body temperature of about 97 / 98 °F which caused problems in training the model with the data.

### EPFL Dataset

This dataset contains a set of RGB and NIR images of different scenery ranging from forests and lakes to cities and buildings. The dataset consisted of 477 pairs of RGB and NIR images. The images were captured using separate exposures from modified SLR cameras, using visible and NIR filters. The cutoff wavelength between the two filters for RGB and NIR images is approximately 750nm.

### IITJ Dataset

The data was collected on the IITJ campus, which includes RGB and thermal videos of participants using a thermal camera, their core body temperature, and factors that can affect the data such as ambient temperature, activity before collection. This data had temperatures in the 96°F, 97°F, and 98°F range. The data presently being used still have posed the same problem that we encountered before and data from more participants on different conditions is necessary to balance the dataset.

## RGB <-> Temperature mapping (using Dataset I)

To find any relation between the RGB image of a person and the temperature of the person we have used convolutional neural networks. The images have been divided based on their respective body temperature and various convolutional neural networks were experimented with to find any underlying mapping function. The data was resized to 256 x 256 pixels for easy training. Appropriate weights were added to each temperature class in order to adjust for the unequal distribution of data.

