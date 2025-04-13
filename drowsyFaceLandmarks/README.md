
![image](https://github.com/user-attachments/assets/d8b9c29c-7a06-4915-8134-66cde5863d8d)

# Drowsy Face Detection with OpenCV and Facial Landmarks

This project demonstrates a simple yet effective way to detect drowsiness using facial landmarks and OpenCV. It tracks eye aspect ratio (EAR) in real-time via webcam, and alerts the user when signs of drowsiness (e.g., prolonged eye closure) are detected.

## 🚀 Features

- Real-time webcam feed processing
- Facial landmark detection using `dlib`
- Eye Aspect Ratio (EAR) calculation for blink/drowsiness detection
- Sound alert when drowsiness is detected
- Visualization of EAR and landmark points

## 🛠️ Requirements

Install the following Python libraries:

```bash
pip install opencv-python dlib imutils scipy playsound
```

You also need:

- `shape_predictor_68_face_landmarks.dat`.

## Files

- `DrowsyFaceLandmarksOpenCV.ipynb`: Jupyter Notebook with the implementation
- `shape_predictor_68_face_landmarks.dat`: Pretrained model for landmark detection (not included, see above)

## How It Works

1. **Facial Detection**:
   - Uses `dlib.get_frontal_face_detector()` to detect faces.
2. **Landmark Prediction**:
   - Uses 68-point facial landmark detection to locate eyes.
3. **Eye Aspect Ratio (EAR)**:
   - Computes EAR for both eyes.
   - If the average EAR drops below a threshold (e.g., 0.25) for a certain number of frames, drowsiness is triggered.
4. **Alert**:
   - Plays an alert sound using `playsound`.

## Key Functions

### `eye_aspect_ratio(eye)`

Calculates the Eye Aspect Ratio based on 6 landmark points.

```python
EAR = (||p2 - p6|| + ||p3 - p5||) / (2 * ||p1 - p4||)
```

If EAR < 0.25 consistently for ~48 frames (customizable), it flags drowsiness.

### `cv2.VideoCapture(0)`

Opens the default webcam for real-time detection.


##  Parameters

You can tune:

- `EYE_AR_THRESH`: EAR threshold below which eyes are considered closed
- `EYE_AR_CONSEC_FRAMES`: Number of consecutive frames the eyes must be below the threshold

## Audio Alert

Ensure an `alarm.wav` or another sound file exists and is accessible to the `playsound` function to enable sound alerts.



