# drowsiness-detection-system
This is a sophisticated, browser-based application I developed to detect driver drowsiness in real-time using a standard webcam. The system goes beyond simple eye-tracking by analyzing multiple facial biometrics to create a robust fatigue score, providing timely audio-visual alerts to enhance driver safety.
Advanced Real-Time Drowsiness Detection System
This is a sophisticated, browser-based application I developed to detect driver drowsiness in real-time using a standard webcam. The system goes beyond simple eye-tracking by analyzing multiple facial biometrics to create a robust fatigue score, providing timely audio-visual alerts to enhance driver safety.

Features
Real-Time Webcam Analysis: Processes video directly in the browser with high efficiency.

Dynamic Calibration: The system initiates with a 5-second calibration phase to learn the user's unique facial structure and neutral state, significantly reducing false positives.

Multi-Metric Analysis:

Eye Aspect Ratio (EAR): Accurately detects eye closure and prolonged blinks.

3D Head Pose Estimation: Tracks head pitch to identify dangerous "head slump" or nodding events.

Intelligent Fatigue Score: Instead of simple triggers, the application uses a persistent fatigue score that builds up with signs of drowsiness and recovers when the driver is alert.

Two-Stage Alert System:

Pre-Alert Warning: A visual orange warning for "Drowsiness Detected" gives the user a chance to refocus.

Full Alarm: If the drowsy state persists, a high-volume voice alert ("Drowsiness detected. Please be careful.") is triggered, accompanied by a flashing red screen.

Zero Installation: The entire application is a single HTML file that runs in any modern web browser. No dependencies or installations are required.

How to Use
Download the index.html file from this repository.

Open the file in a modern web browser (like Google Chrome or Firefox).

Grant the browser permission to access your webcam when prompted.

Follow the on-screen instructions to calibrate the system by looking straight at the camera for 5 seconds.

The application will then start monitoring your status in real-time.

How It Works
The application leverages the power of Google's MediaPipe Face Mesh library, which runs directly in the browser via JavaScript.

Facial Landmark Detection: MediaPipe identifies 478 key points on the face in real-time.

Feature Extraction: From these landmarks, I calculate:

The Eye Aspect Ratio (EAR) for both eyes. A sharp drop in EAR indicates a blink or eye closure.

The 3D Head Pitch by estimating the head's rotation. A significant negative pitch indicates a head slump.

Calibration: During the initial 5 seconds, the application calculates the user's baseline average EAR and head pitch. These averages are then used to set personalized thresholds for drowsiness.

Fatigue Scoring: The system maintains a "fatigue score." This score increases when the smoothed EAR or pitch values cross their calibrated thresholds. The score slowly decreases when the user appears alert.

Alerting: When the fatigue score surpasses a pre-defined limit, the two-stage alarm system is triggered to alert the user.

Technologies Used
HTML5

JavaScript (ES6 Modules)

Tailwind CSS for styling

Google MediaPipe for facial landmark detection

License
This project is licensed under the MIT License. See the LICENSE file for details.
