# Motion Detection and Email Notification System

This Python script captures video from a webcam, detects motion, and performs specific actions when motion is detected. It uses OpenCV for image processing and employs multithreading to handle tasks such as sending email notifications and cleaning up generated images.

## Features

- **Motion Detection**: Detects significant motion using frame differencing and contour analysis.
- **Image Capture**: Captures and saves frames with detected motion.
- **Email Notification**: Sends an email with an image of the detected motion.
- **Folder Cleanup**: Automatically removes saved images after processing.
- **Multithreading**: Ensures smooth execution by running email sending and folder cleanup tasks in separate threads.

## Prerequisites

Before running this script, ensure you have the following installed:

- Python 3.x
- OpenCV (`cv2`)
- `emailing` module (custom or third-party module for sending emails)
- Necessary email configuration (e.g., SMTP setup in the `emailing` module)

## Installation

1. Clone or download this repository.
2. Install required Python packages:
   ```bash
   pip install opencv-python


Here’s a detailed README.md file for your script:

markdown
Copy code
# Motion Detection and Email Notification System

This Python script captures video from a webcam, detects motion, and performs specific actions when motion is detected. It uses OpenCV for image processing and employs multithreading to handle tasks such as sending email notifications and cleaning up generated images.

## Features

- **Motion Detection**: Detects significant motion using frame differencing and contour analysis.
- **Image Capture**: Captures and saves frames with detected motion.
- **Email Notification**: Sends an email with an image of the detected motion.
- **Folder Cleanup**: Automatically removes saved images after processing.
- **Multithreading**: Ensures smooth execution by running email sending and folder cleanup tasks in separate threads.

## Prerequisites

Before running this script, ensure you have the following installed:

- Python 3.x
- OpenCV (`cv2`)
- `emailing` module (custom or third-party module for sending emails)
- Necessary email configuration (e.g., SMTP setup in the `emailing` module)

## Installation

1. Clone or download this repository.
2. Install required Python packages:
   ```bash
   pip install opencv-python
Ensure you have a directory named images in the same location as the script. This is where captured images will be saved.
How It Works
Initialization:

The webcam is activated using OpenCV.
A reference frame is captured to detect changes in subsequent frames.
Motion Detection:

Each frame is converted to grayscale and blurred for better processing.
The difference between the current frame and the reference frame is calculated.
Thresholding and contour detection are used to identify motion.
Actions on Motion:

If motion is detected:
A frame with motion is saved to the images directory.
An email with the captured image is sent (using the emailing module).
If no motion is detected, previously saved images are cleaned up.
Stopping the Script:

The script runs indefinitely until the user presses the "q" key to exit.
Usage
Run the script using the following command:

bash
Copy code
python motion_detection.py
Multithreading
The script uses threads for:

Email Notifications: Sending emails without blocking the main program.
Folder Cleanup: Deleting images after they have been processed.
