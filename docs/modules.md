# Creating Modules
**Modules** make up a great portion of OpenSight's functionality. They are special types of classes that can operate on inputs and give outputs. They can be used in a wide variety of ways, such as modifing an image, or communicating with a server.

An example module:
```python
from dataclasses import dataclass

import opsi.manager.cvwrapper as cvw
from opsi.manager.manager_schema import Function
from opsi.manager.types import Mat, MatBW

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

The source code for the modules is located under [opsi/modules in the opensight repo](https://github.com/opensight-cv/opensight/tree/master/opsi/manager).

Note that importing `cv2` directly is discouraged. All new cv2 functionality should go into [cvwrapper.py](https://github.com/opensight-cv/opensight/blob/master/opsi/manager/cvwrapper.py).


