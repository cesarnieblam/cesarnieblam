### 1: Create a new Python module

Create a new Python file in the `roop/processors/frame` directory. This file, for example `your_frame_processor.py`, will be your frame processor module.

### 2: Define required functions

Every frame processor must define the following hooks:

#### `pre_check()`
This function is called before starting. It should return a boolean indicating whether the pre-check was successful or not.

#### `pre_start()`
This function is called before processing. It should return a boolean indicating whether the pre-start was successful or not.

#### `process_frame(source_face: Face, temp_frame: Frame)`
This function is called to process one frames.

#### `process_frames(source_path: str, temp_frame_paths: List[str], update: Callable[[], None])`
This function is called to process multiple frames and update the progress bar.

#### `process_image(source_path: str, output_path: str)`
This function is called when processing an image. It should process the image and save the result to the output path.

#### `process_video(source_path: str, frame_paths: List[str])`
This function is called when processing a video. It should process each frame in the video and save the result to the output path.

### Use this skeleton

```
import roop.globals
import roop.processors.frame.core
from roop.typing import Frame, Face

NAME = 'ROOP.YOUR-FRAME_PROCESSOR'

def pre_check() -> bool:
    return True

def pre_start() -> bool:
    return True

def process_frame(source_face: Face, temp_frame: Frame) -> Frame:
    pass

def process_frames(source_path: str, temp_frame_paths: List[str], update: Callable[[], None]) -> None:
    pass

def process_image(source_path: str, target_path: str, output_path: str) -> None:
    pass

def process_video(source_path: str, temp_frame_paths: List[str]) -> None:
    roop.processors.frame.core.process_video(source_path, temp_frame_paths, process_frames)
```

### 3: Test Your Custom Processor

Once you have defined the required hooks in your frame processor module, you can test it by running Roop with the `--frame-processor` argument set to process the logic you defined.

```
python run.py --frame-processor your_frame_processor
```