
### Only CPUExecutionProvider is working

Do not install `onnxruntime` and `onnxruntime-xxx` at the same time.

```
pip uninstall onnxruntime onnxruntime-xxx
```

```
pip install onnxruntime-xxx
```

### Learn from others

Tips from people who are running it successfully: https://github.com/s0md3v/roop/issues/68