### Only CPU processing

Do not install `onnxruntime` and `onnxruntime-xxx` at the same time, otherwise only `CPUExecutionProvider` will run.

```
pip uninstall onnxruntime onnxruntime-xxx
```
```
pip install onnxruntime-xxx
```

### Falsy Dependencies resolution

Make sure to run Python 3.10 to prevent dependencies conflicts and therfore resolution.


### Learn from others

Tips from people who are running it successfully: https://github.com/s0md3v/roop/issues/68