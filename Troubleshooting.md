### Falsy Dependencies resolution

Make sure to run Python 3.10 to prevent dependencies conflicts.


### Runtime errors during processing

A `Non zero status code...` or `Cannot allocate memory...` during processing results in lost frames and indicate that your GPU is out of VRAM or just overwhelmed - you need to lower the execution threads.


### No module named 'xxx'

A `ModuleNotFoundError` indicates that the dependencies have not been correctly installed.


### Module 'xxx' has no attribute 'xxx'

A `AttributeError` indicates that the dependencies have not been correctly installed.


### Solution to most OpenCV errors

In most cases it helps to reinstall OpenCV.

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

You triggered the NSFW filter and the application stopped processing.


### Preview crashed

You triggered the NSFW filter and the application closed itself.


### Ask the community

Please do not open platform and installation related issues on GitHub. We have a very helpful [Discord](https://discord.gg/Y9p4ZQ2sB9) community that will guide you through your journey to successfully install roop.