### Using GPU
**option:** `--execution-provider`
**default:** `CPUExecutionProvider`

Depending on what **onnxruntime** package you installed, specify the respective execution provider with this option to utilize your GPU. Below is a list of popular execution providers, the complete list can be found [here](https://onnxruntime.ai/docs/execution-providers/).

- `CUDAExecutionProvider`: for NVIDIA
- `ROCMExecutionProvider`: for AMD (linux only)
- `DmlExecutionProvider`: for windows
- `CoreMLExecutionProvider`: for mac

### Choosing a frame processor
**option:** `--frame-processor`\
**default:** `face_swapper`

This option lets you choose one or more "frame processor" that apply various affect to the video. Following frame processors are available:
- `face_swapper`: swaps face(s)
- `face_enchancer`: enhances the face(s) using GFPGAN v1.4

### Preserving video's FPS
**option:** `--keep-fps`\
**default:** `False`

roop reduces the FPS of the video to 30 by default for faster processing but if you would like to preserve the original FPS, you can use this switch.

### Don't delete generate frames
**option:** `--keep-frames`
**default:** `False`

While processing a video, roop extracts all of its frames and stores them locally. The directory containing them is deleted once the process has been finished. Using `--keep-frames` switch will prevent deletion.

### Replace all faces
**option:** `--many-faces`
**default:** `False`

By default, only one face is replaced in each frame that too the leftmost face in the frame. If you want to replace all of the faces, use this switch.

### Choose a video encoder
**option:** `--video-encoder`
**default:** `libx264`

This lets you choose a video encoder, currently available encoders are: libx264, libx265, libvpx-vp9`

### Set video quality
**option:** `--video-quality`
**default:** `18`

You wouldn't need to touch this option but in case you do, it accepts an number from 1 to 51.

#### Limit VRAM
**option:** `--max-memory`
**default:** `16`

If you want to limit how much VRAM roop can use, use this option. It accepts a number e.g. `--max-memory 4` means 4GB limit.