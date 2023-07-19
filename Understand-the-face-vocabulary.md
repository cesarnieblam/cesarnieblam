## Face reference

Describes the snapshot of a face being used for the face recognition during processing frames.

### Different approaches

1. Define the face position via `--reference-face-position` on a specific frame number `--reference-frame-number`
2. Upload a image via `--reference-path` and to extract the face (not implemented yet)

## Face recognition

Describes the process of comparing two faces against a given threshold, called face distance.

You can adjust the threshold via `--similar-face-distance`. Default is `0.85`

## Face distance

Describes how different two faces are.

## Face bouncing

Describes bouncing between person during processing frames as of failing face recognition.

In case you experience this on a video with a single person: try to lower the `--similar-face-distance` or use `--many-faces` to bypass the face recognition.