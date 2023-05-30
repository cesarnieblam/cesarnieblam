## AMD
> Note: AMD GPUs can't be used with windows. Following instructions work for linux only.

1. `pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/rocm5.4.2`
2. `pip uninstall onnxruntime`
3. `git clone https://github.com/microsoft/onnxruntime && cd onnxruntime`
4. `./build.sh --config Release --build_wheel --update --build --parallel --cmake_extra_defines CMAKE_PREFIX_PATH=/opt/rocm/lib/cmake ONNXRUNTIME_VERSION=$ONNXRUNTIME_VERSION onnxruntime_BUILD_UNIT_TESTS=off --use_rocm --rocm_home=/opt/rocm`
5. `pip install build/Linux/Release/dist/*.whl`

## NVIDIA
1. `pip uninstall onnxruntime onnxruntime-gpu`
2. `pip install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu118`
3. `pip install onnxruntime-gpu`

## Mac
1. `brew install wget cmake protobuf git git-lfs`
2. `git clone https://github.com/cansik/onnxruntime-silicon && cd onnxruntime-silicon`
3. `./build-macos.sh`
4. `pip install dist/*whl` (this step may need improvisation)