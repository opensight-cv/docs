The Mask module contains nodes used to manipulate masks (which take the form of `imgBW`). Masks can be turned into contours using [FindContours](contours.md#findcontours) or filter images using [BitwiseAND](draw.md#bitwiseand). These nodes can be found under the opsi-draw tab.

![Mask Module Add Nodes Image](../assets/images/modules/mask/module_mask.png)

## Dilate

![Dilate Node Image](../assets/images/modules/mask/node_dilate.png)

Takes a mask (`imgBW`) and extends all of its borders by the number of pixels defined in the `size` setting.

## Erode

![Erode Node Image](../assets/images/modules/mask/node_erode.png)

Takes a mask (`imgBW`) and removes the number of pixels around all its borders as defined in the `size` setting.

## Invert

![Invert Node Image](../assets/images/modules/mask/node_invert.png)

Inverts the mask such that all white areas become black and vise versa, essentially inverting the mask's effect.

## Join

![Join Node Image](../assets/images/modules/mask/node_join.png)

Joins two masks (`imgBW1` and `imgBW2`) such that if a pixel is white on either mask, it is white on the output mask.
