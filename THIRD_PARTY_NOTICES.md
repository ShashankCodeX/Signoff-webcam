# Third-party notices

This repository keeps its own code license separate from bundled or downloaded third-party materials. See the scope paragraph in [LICENSE](LICENSE).

## Google MediaPipe Hand Landmarker model

- File: `hand_landmarker.task`
- Upstream model: [Google MediaPipe Hand Landmarker](https://storage.googleapis.com/mediapipe-models/hand_landmarker/hand_landmarker/float16/1/hand_landmarker.task)
- The official [Google model card](https://storage.googleapis.com/mediapipe-assets/Model%20Card%20Hand%20Tracking%20%28Lite_Full%29%20with%20Fairness%20Oct%202021.pdf) identifies the hand tracking model as Apache License 2.0.
- A copy of Apache-2.0 is included in [LICENSES-APACHE-2.0.txt](LICENSES-APACHE-2.0.txt).

## MediaPipe models downloaded when the app starts

The app downloads these files into the ignored `models/` directory:

- `selfie_segmenter_landscape.tflite` from [Google MediaPipe model storage](https://storage.googleapis.com/mediapipe-models/image_segmenter/selfie_segmenter_landscape/float16/latest/selfie_segmenter_landscape.tflite)
- `gesture_recognizer.task` from [Google MediaPipe model storage](https://storage.googleapis.com/mediapipe-models/gesture_recognizer/gesture_recognizer/float16/1/gesture_recognizer.task)

These model files are not included in this repository. Their applicable terms are set by their respective upstream model cards and Google/MediaPipe notices, not by the project MIT license.

## Audio with unrecorded provenance

- File: `assets/vanish.MP3`
- The repository does not record where this audio came from or a license for it. The project MIT license does not cover this file and does not grant permission to redistribute it. Confirm the source and rights or replace the file before redistributing copies that include it.

## Icon with unrecorded provenance

- File: `assets/vanish_icon.ico`
- The repository does not record this file's origin or license. It is excluded from the project MIT license unless its own license notice is added.

## Dependencies

Packages installed from `requirements.txt` remain subject to their respective upstream licenses. This repository does not relicense those packages.

## Names and trademarks

The Naruto-inspired effect is an unofficial fan-style feature. Names and marks belonging to their respective rights holders are used only to describe the visual reference; this project is not affiliated with or endorsed by them.
