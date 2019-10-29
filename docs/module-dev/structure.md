# Module Structure

# Modules

TODO: explain module package structure

# Functions (break into separate file?)

TODO: explain general class setup

A function has three main user-facing components: **Inputs**, **Outputs**, and **Settings**. Each one of these is a statically defined Python [dataclass](https://docs.python.org/3/library/dataclasses.html). You can create a dataclass by creating a class with the `@dataclass` decorator, as shown here:

```python
@dataclass
class Inputs:
    x: int
```
