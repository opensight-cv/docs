# Creating Modules
**Modules** make up a great portion of OpenSight's functionality. They are special types of classes that can operate on inputs and give outputs. They can be used in a wide variety of ways, such as modifing an image, or communicating with a server.

An example module:
```python
class Blur(Function):
    @dataclass
	class Settings:
		radius: int
		
	@dataclass
	class Inputs:
		img: Mat
		
	@dataclass
	class Outputs:
		blur: Mat
		
	def run(self, inputs)
		blurred = cvw.blur(inputs.img, self.settings.radius)
		return self.Outputs(blur=blurred)
```
There are already many useful modules included in OpenSight, but creating your own can add more complexity to your vision pipeline.




