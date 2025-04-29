# Hand Gesture Jump Control

This project uses computer vision to detect hand gestures and simulate a jump action (spacebar press) in games or applications. It leverages the MediaPipe library for hand tracking and OpenCV for webcam input processing.

## Features
- Detects an open hand gesture using the distance between the thumb and index finger tips.
- Simulates a spacebar press to trigger a jump action when an open hand is detected.
- Includes a cooldown mechanism to prevent multiple rapid jump triggers.
- Displays real-time hand landmarks on the webcam feed for visual feedback.

## Prerequisites
- Python 3.6+
- Required Python libraries:
  - `opencv-python`
  - `mediapipe`
  - `keyboard`

## Installation
1. Clone this repository:
   ```bash
   git clone https://github.com/your-username/hand-gesture-jump.git
   cd hand-gesture-jump
   ```
2. Install the required dependencies:
   ```bash
   pip install opencv-python mediapipe keyboard
   ```
3. Ensure you have a webcam connected to your computer.

## Usage
1. Run the script:
   ```bash
   python hand_gesture_jump.py
   ```
2. Position your hand in front of the webcam.
3. Open your hand (spread thumb and index finger) to trigger a jump (spacebar press).
4. Press the `q` key to exit the program.

## How It Works
- The script captures video from the webcam using OpenCV.
- MediaPipe Hands processes the video frames to detect hand landmarks.
- The distance between the thumb tip and index finger tip is calculated to identify an open hand gesture.
- When an open hand is detected (and the cooldown period has passed), the `keyboard` library simulates a spacebar press.
- The webcam feed is displayed with hand landmarks drawn for visualization.

## Notes
- The `keyboard` library may require root/admin privileges on some systems (e.g., Linux or macOS).
- Adjust the `jump_cooldown` (default: 0.5 seconds) or `distance` threshold (default: 0.1) in the script to fine-tune gesture sensitivity.
- Ensure good lighting and a clear view of your hand for accurate detection.

## Troubleshooting
- If the webcam fails to open, check that it is connected and not in use by another application.
- If hand detection is inconsistent, ensure proper lighting and adjust the `min_detection_confidence` parameter in the script.
- On Linux/macOS, run the script with `sudo` if you encounter keyboard permission issues:
  ```bash
  sudo python hand_gesture_jump.py
  ```

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for details.

## Acknowledgments
- [MediaPipe](https://mediapipe.dev/) for hand tracking.
- [OpenCV](https://opencv.org/) for video processing.
- [keyboard](https://github.com/boppreh/keyboard) for simulating key presses.