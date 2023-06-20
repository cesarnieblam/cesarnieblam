### Falsy Dependencies resolution

Make sure to run Python 3.10 to prevent dependencies conflicts.


### No module named 'xxx'

A `ModuleNotFoundError` indicates that the dependencies have not been correctly installed.


### Module 'xxx' has no attribute 'xxx'

A `AttributeError` indicates that the dependencies have not been correctly installed.


### Any OpenCV error

In most cases it helps to uninstall and then install OpenCV.

```
pip uninstall opencv-python
pip install opencv-python
```

### Only CPU is processing

Do not install `onnxruntime` and `onnxruntime-xxx` at the same time, otherwise only `CPUExecutionProvider` will run.

```
pip uninstall onnxruntime onnxruntime-xxx
pip install onnxruntime-xxx
```

### Progress bar got stucked

Congrats, you triggered the NSFW filter and the application stopped processing.


### Ask the community

Please do not open platform and installation related issues on GitHub. We have a very helpful [Discord](https://discord.gg/Y9p4ZQ2sB9) community that will guide you through your journey to successfully install roop.