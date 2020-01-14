# Creating Modules
**Modules** make up a great portion of OpenSight's functionality. They are special types of classes that can operate on inputs and give outputs. They can be used in a wide variety of ways, such as modifing an image, performing math operations, or communicating with a server.

Here's an example module, which does the following:

* Has a setting for the radius of the blur (of type integer)
* Inputs an image (of type Mat)
* Outputs the blurred image

```python
from dataclasses import dataclass

from opsi.manager.manager_schema import Function
from opsi.util.cv.mat import Mat, MatBW

__package__ = "opsi.example_module"
__version__ = "0.123"


class Blur(Function):
    @dataclass
    class Settings:
        radius: int

    @dataclass
    class Inputs:
        img: Mat

    @dataclass
    class Outputs:
        img: Mat

    def run(self, inputs):
        img = cvw.blur(inputs.img, self.settings.radius)
        return self.Outputs(img=img)
```
There are already many useful modules included in OpenSight, but creating your own can add more complexity to your vision pipeline.

The source code for the modules is located under [opsi/modules](https://github.com/opensight-cv/opensight/tree/master/opsi/manager) in the OpenSight repo.

!!! warning
    Using the `cv2` library directly is discouraged. All new OpenCV functionality should go into [cvwrapper.py](https://github.com/opensight-cv/opensight/blob/master/opsi/manager/cvwrapper.py).
