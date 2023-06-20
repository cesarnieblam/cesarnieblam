### Falsy Dependencies resolution

Make sure to run Python 3.10 to prevent dependencies conflicts.


### No module named 'xxx'

A `ModuleNotFoundError` indicates that the dependencies have not been correctly installed.


### Module 'xxx' has no attribute 'xxx'

A `AttributeError` indicates that the dependencies have not been correctly installed.


### Only CPU processing

Do not install `onnxruntime` and `onnxruntime-xxx` at the same time, otherwise only `CPUExecutionProvider` will run.

```
pip uninstall onnxruntime onnxruntime-xxx
pip install onnxruntime-xxx
```

### Learn from others

Tips from people who are running it successfully: https://github.com/s0md3v/roop/issues/68