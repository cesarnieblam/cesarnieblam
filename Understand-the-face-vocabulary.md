### Face reference

Describes the snapshot of a face being used for the face recognition during processing frames.

#### Different approaches

1. Define the face position via `--reference-face-position` on a frame `--reference-frame-number` of the target video
2. Upload a image via `--reference-path` to extract the reference face (not implemented yet)

### Face recognition

Describes the process of comparing two faces against a given threshold, called face distance.

You can adjust the threshold via `--similar-face-distance`. Default is `0.85`. In case you experience bouncing on a single person video, try to increase the threshold to `1.5` or disable face recognition by using `--many-faces`.

### Face distance

Describes how similar two faces are.

### Face bouncing

Describes flicker between persons during processing frames as of failing face recognition.