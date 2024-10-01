# Attendance System Using Python

This project is an **Attendance System** that leverages facial recognition to mark attendance automatically. The system captures images via a camera, recognizes individuals based on pre-loaded images, and records their attendance details (name and timestamp) in a CSV file along with the current date.



## Overview

The **Attendance System Using Python** utilizes computer vision techniques to automate the process of recording attendance. By recognizing faces from a live camera feed, the system ensures accurate and efficient attendance management without the need for manual input.

## Features

- **Real-time Facial Recognition**: Detects and recognizes faces using a webcam.
- **Automated Attendance Logging**: Records the name and timestamp of recognized individuals into a CSV file.
- **Date-wise Attendance Tracking**: Creates separate CSV files for each date to organize attendance records.
- **User-Friendly Interface**: Displays the camera feed with annotations indicating recognized individuals.
- **Extensible**: Easily add or remove recognized individuals by updating the images in the `photos` directory.

## Technologies Used

- **Python**: Programming language.
- **OpenCV**: For capturing and processing images from the webcam.
- **face_recognition**: Library for facial recognition tasks.
- **NumPy**: For numerical operations.
- **CSV**: For storing attendance records.
- **Datetime**: For handling date and time operations.

## Data Preparation

1. **Photos Directory**:
   - Create a directory named `photos` in the project root.
   - Add clear images of individuals you want the system to recognize. Ensure each image file is named with the individual's name (e.g., `john_doe.jpg`).

2. **Image Naming Convention**:
   - Use lowercase letters and underscores for naming (e.g., `ratan_tata.jpg`).
   - Avoid spaces and special characters in file names to prevent potential issues.


## Usage

1. **Prepare the Photos**:
   - Ensure that the `photos` directory contains clear images of all individuals to be recognized. The filenames should reflect the individuals' names.

2. **Run the Attendance Script**:
    ```bash
    python attendance_system.py
    ```

3. **Using the System**:
   - A window will open displaying the webcam feed.
   - The system will attempt to recognize faces in real-time.
   - Recognized individuals will have their names displayed on the video feed with a "Present" label.
   - Attendance details (name and timestamp) will be recorded in a CSV file named with the current date (e.g., `2024-10-01.csv`).

4. **Exit the System**:
   - Press the `q` key to quit the application.

## How It Works

1. **Import Libraries**:
   - The script uses `face_recognition` for facial recognition, `cv2` (OpenCV) for handling the webcam feed, `numpy` for numerical operations, `csv` for logging attendance, and `datetime` for timestamping.

2. **Load and Encode Known Faces**:
   - The script loads images from the `photos` directory and encodes the faces for recognition.

3. **Initialize Webcam**:
   - Captures video input from the default webcam.

4. **Real-time Face Detection and Recognition**:
   - For each frame captured from the webcam:
     - Resize the frame for faster processing.
     - Detect face locations and encode them.
     - Compare detected faces with known face encodings.
     - If a match is found, annotate the frame with the individual's name and mark them as present.

5. **Logging Attendance**:
   - When a recognized individual is detected for the first time on a given day, their name and the current timestamp are appended to a CSV file named with the current date.

6. **Display Output**:
   - The annotated video feed is displayed in a window titled "Attendance System".



## Contributing

Contributions are welcome! If you find any issues or have suggestions for improvements, feel free to open an issue or submit a pull request.



