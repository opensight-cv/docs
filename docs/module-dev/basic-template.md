# Basic Template

Here is a basic module template you can you to get started:

```python
from dataclasses import dataclass

from opsi.manager.manager_schema import Function
from opsi.manager.types import Mat

__package__ = "opsi.MODULE_NAME"
__version__ = "0.XXX"


class FUNCTION_NAME(Function):
    @dataclass
    class Settings:
        name: type

    @dataclass
    class Inputs:
        name: type

    @dataclass
    class Outputs:
        name: type

    def run(self, inputs):
        img = inputs.img
        return self.Outputs(img=img)
```
