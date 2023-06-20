1. [Using GPU](#using-gpu)
2. [Choosing a frame processor](#choosing-a-frame-processor)
3. [Preserving video's FPS](#preserving-videos-fps)
4. [Don't delete generated frames](#dont-delete-generate-frames)
5. [Replace all faces](#replace-all-faces)
6. [Choose a video encoder](#choose-a-video-encoder)
7. [Set video quality](#set-video-quality)
8. [Limit VRAM](#limit-vram)
9. [Threads](#threads)

### Using GPU
**option:** `--execution-provider`\
**default:** `cpu`

Depending on what **onnxruntime** package you installed, specify the respective execution provider with this option to utilize your GPU. Below is a list of popular execution providers, the complete list can be found [here](https://onnxruntime.ai/docs/execution-providers/). If you are not sure, use the `--help` option to see the available providers in your console.

- `cuda`: for NVIDIA
- `rocm`: for AMD (linux only)
- `dml`: for windows
- `coreml`: for mac

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
**option:** `--keep-frames`\
**default:** `False`

While processing a video, roop extracts all of its frames and stores them locally. The directory containing them is deleted once the process has been finished. Using `--keep-frames` switch will prevent deletion.

### Replace all faces
**option:** `--many-faces`\
**default:** `False`

By default, only one face is replaced in each frame that too the leftmost face in the frame. If you want to replace all of the faces, use this switch.

### Choose a video encoder
**option:** `--video-encoder`\
**default:** `libx264`

This lets you choose a video encoder, currently available encoders are: libx264, libx265, libvpx-vp9`

### Set video quality
**option:** `--video-quality`\
**default:** `18`

You wouldn't need to touch this option but in case you do, it accepts an number from 1 to 51.

#### Limit VRAM
**option:** `--max-memory`\
**default:** system dependent

If you want to limit how much VRAM roop can use, use this option. It accepts a number e.g. `--max-memory 4` means 4GB limit.

#### Threads
**option:** `--execution-threads`\
**default:** system dependent

This control how many threads should run in parallel to process the frames using the given execution provider. Play around with different values to find out what works best on your system.