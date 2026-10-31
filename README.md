# VanishCam

VanishCam is a Python webcam effects app that processes video locally. Choose
between a gesture-triggered disappearance and a Naruto-inspired substitution
effect. The app can show the result in its preview window or send it to a
virtual camera for use in other apps.

## Features

- **Normal Vanish:** make a V sign with your index and middle fingers to trigger
  a roughly 3.6-second dissolve.
- **Naruto Vanish:** bring both palms together, fingers side by side, to vanish
  in animated smoke while a wooden log falls into view.
- Background capture and person segmentation to replace the person with the
  captured scene.
- Optional virtual-camera output for video-call and streaming apps.
- Local video processing: webcam footage is not recorded or sent to a server.

## Requirements

- Python 3 and a webcam.
- Internet access on first launch so the app can download the MediaPipe models.
- Optional: OBS Studio (with OBS Virtual Camera) or Unity Capture for virtual
  camera output.

## Install and launch

### Windows

1. Download or clone this repository and open its folder.
2. Double-click `AVVIA_LOCALE.bat`. It creates a Python virtual environment,
   installs the requirements, and starts the app.
3. If prompted, allow the app to access your camera.

To start without virtual-camera output, run `AVVIA_OBS.bat`. To require a
virtual camera, run `AVVIA_VIRTUAL.bat`.

### macOS or Linux

Open a terminal in the project folder and create an environment and install
the dependencies:

```sh
python3 -m venv .venv
source .venv/bin/activate
python -m pip install -r requirements.txt
```

Start the app:

```sh
python vanish_cam.py
```

On macOS, allow camera access for the terminal or app running Python in
**System Settings → Privacy & Security → Camera**.

The first launch downloads the segmentation and gesture-recognition models
into `models/`. Allow the download to finish. Naruto mode also uses the
`hand_landmarker.task` file included in this repository.

## Choose and use an effect

When the app opens, click an option in the menu or press `1` for Normal Vanish
or `2` for Naruto Vanish. You can also launch a mode directly:

```sh
python vanish_cam.py --mode normal
python vanish_cam.py --mode naruto
```

When the preview begins, stand out of the camera's view while the app captures
the background. It waits for a clear scene before accepting it. Return to the
frame and use the gesture for your selected effect:

- **Normal Vanish:** hold up your index and middle fingers in a V sign.
- **Naruto Vanish:** bring your palms together in front of the camera. Keep
  both hands visible and your fingers side by side, not interlaced. The sound
  effect plays through your computer's speakers; no microphone is required.

## Controls

- `SPACE` — capture the background again.
- `R` — reappear after vanishing.
- `V` — trigger the selected effect manually.
- `F` — toggle fullscreen.
- `Q` or `ESC` — quit.

## Use the output in other apps

By default, VanishCam tries to open an available virtual camera and falls back
to the preview if one is unavailable. In a video-call app, select the virtual
camera provided by OBS or Unity Capture as the camera source.

For OBS scene capture, run `AVVIA_OBS.bat` on Windows to disable VanishCam's
virtual-camera output, then add a **Window Capture** source for the VanishCam
preview. In OBS, start the OBS Virtual Camera and select it as the camera in
your video-call app. Avoid having VanishCam and OBS both try to start the OBS
Virtual Camera at the same time.

To explicitly control virtual-camera output from the command line:

```sh
python vanish_cam.py --no-virtual-camera
python vanish_cam.py --virtual-camera
```

## Camera options and troubleshooting

Choose a different camera, resolution, or virtual-output frame rate:

```sh
python vanish_cam.py --camera 1 --width 1280 --height 720 --fps 30
```

Camera indexes usually start at `0`; try `1` if the default camera is
unavailable. Close other apps that may be using the webcam. If the gesture is
not detected, make sure your hand(s) are visible and well lit. Add
`--gesture-debug` to print recognition diagnostics in the terminal.

To run the tests:

```sh
python -m unittest discover -s . -p 'test_*.py'
```

## Credit

Created and maintained by [ShashankCodeX](https://github.com/ShashankCodeX).
