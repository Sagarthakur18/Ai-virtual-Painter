
# Ai Virtual Painter with Hand Tracking

## Overview
This project is a hand gesture-controlled paint application that uses a webcam feed to detect hand movements and perform drawing or erasing actions. The application utilizes the **Mediapipe** library for hand tracking and **OpenCV** for video processing and drawing. Users can select different brush colors, draw on a virtual canvas, or erase parts of their drawings using hand gestures.

---

## Features
- **Hand Tracking**: Detects and tracks hand landmarks in real-time using Mediapipe.
- **Drawing Modes**:
  - **Brush Mode**: Use your index finger to draw on the canvas.
  - **Selection Mode**: Use two fingers to select brush colors or switch to eraser mode.
- **Dynamic Canvas**: The drawing is maintained on a virtual canvas that can be merged with the live video feed.
- **Eraser Tool**: Erase parts of the drawing by selecting the eraser tool.
- **Customizable Tools**:
  - Adjustable brush and eraser thickness.
  - Add new brush colors by updating the header images.

---

## Dependencies
Ensure the following Python libraries are installed:
- `opencv-python`
- `numpy`
- `mediapipe`

Install them using pip:
```bash
pip install opencv-python numpy mediapipe
```

---

## File Structure
- **Main Code**: The Python script that runs the application.
- **Header Folder**: Contains images used for the header bar (brush and eraser selection).
- **Hand Tracking Module (`handtrackingmodule.py`)**: A custom module to detect hand landmarks and their positions.

---

## How It Works
1. **Initialization**:
   - The application initializes the webcam feed and sets up the virtual canvas.
   - Predefined header images are loaded for brush and eraser selection.

2. **Hand Detection**:
   - The Mediapipe hand tracking model detects hand landmarks.
   - The position of specific fingers (index and middle) is used to determine the mode (drawing or selection).

3. **Drawing and Erasing**:
   - **Single Finger Up (Index)**: Activates drawing mode.
   - **Two Fingers Up (Index and Middle)**: Activates selection mode for changing colors or switching to the eraser.

4. **Canvas Updates**:
   - A binary mask is created for merging the drawings onto the webcam feed.
   - The drawing and video feed are combined into a single output window.

---

## Usage
1. Place header images (for brush colors and eraser) in a folder named `Header`.
2. Run the Python script:
   ```bash
   python <script_name>.py
   ```
3. The application opens a webcam feed:
   - Use two fingers to select tools/colors from the header.
   - Use one finger to draw or erase on the canvas.

4. Exit the application by closing the webcam window.

---

## Gesture Controls
- **Two Fingers Up**: Selection mode.
  - Click on a header image to change brush color or activate the eraser.
- **Index Finger Up**: Drawing mode.
  - Move the index finger to draw on the canvas.
  - Use the eraser if the eraser mode is active.

---

## Customization
1. **Adding Brush Colors**:
   - Add a new image to the `Header` folder.
   - Update the script to include the new color's conditions in the header selection logic.
2. **Adjusting Brush and Eraser Thickness**:
   - Modify the `brushThickness` and `eraserThickness` variables in the script.

---

## Key Functions
- **`findHands`**: Detects and draws hand landmarks on the image.
- **`findPosition`**: Identifies and returns the positions of all hand landmarks.
- **`fingersUp`**: Determines which fingers are up based on landmark positions.
- **`findDistance`**: Calculates the distance between two specific landmarks.

---

## Demo



### Header Section
("![image](https://github.com/user-attachments/assets/fcdfa1f6-3db7-4aa3-ac7b-087dcff8726c)
")

---

## Acknowledgments
This project uses:
- **Mediapipe**: For real-time hand tracking.
- **OpenCV**: For image and video processing.

---

## License
This project is open-source and available under the MIT License.
```
