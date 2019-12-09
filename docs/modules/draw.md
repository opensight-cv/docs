The Draw module contains nodes used to draw on images. These nodes can be found under the opsi-draw tab.

## BitwiseAND
* Input
    * img
    * mask (type imgBW)
* Output
    * img

Uses a mask to select and output only the pixels of the input `img` that are white on the `mask` input. These pixels are taken and put to an output `img`, with the rest of the pixels being black.

## DrawContours
* Inputs
    * contours
    * img
* Output
    * img

Takes an image `img` and draws the `contours` inputted onto the image, outputting it.

## DrawFPS
* Input
    * img
* Output
    * img

This node puts the FPS (Frames per Second) of the video feed onto the `img` and outputs this updated image. 
