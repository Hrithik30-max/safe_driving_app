Safe Driving App
The Safe Driving App is designed to enhance road safety by continuously monitoring drivers for signs of drowsiness, emotional states, and phone usage. This app provides real-time feedback and alerts to help drivers stay focused, safe, and alert on the road. The project uses a range of machine learning and computer vision techniques, providing an integrated solution for safer driving.

Features

Drowsiness Detection: Monitors the driver’s eye movements using eye aspect ratio (EAR) measurements to detect signs of fatigue and drowsiness. If sustained drowsiness is detected, an alert is triggered.

Emotion Detection: Identifies and tracks emotional states such as anger, sadness, happiness, and surprise. This can help gauge driver stress and alertness levels.

Phone Usage Detection: Uses a pre-trained YOLO model to detect when a driver is using a handheld phone. If detected, the app issues an audio warning to encourage safe driving.

Project Structure

app.html: Frontend HTML code for the user interface.
emotional_detect.py: Module for detecting and analyzing driver emotions.
sleep_detection.py: Module for detecting drowsiness based on EAR measurements.
phone_detection.py: Module for identifying phone usage.
single_code.py: Integrated code that combines all three detection features for real-time monitoring.

Methodology

1. Methodological Approach
The app uses the Flask framework to combine Python modules for drowsiness, emotion, and phone detection in a cross-platform application. Using a looped architecture, the app captures real-time video frames through the device camera and processes each frame to detect driver alertness and engagement.

The project employs:

Dlib’s facial landmark predictor for drowsiness detection.
FER (Facial Expression Recognition) library for emotion analysis.
YOLO model for phone usage detection.
Each detection module contributes to the overall driver alertness monitoring by analyzing different aspects of driver behavior.

2. Data Collection

Data is collected from real-time video frames as follows:

Drowsiness Detection: Detects eye closure using EAR measurements. Alerts are triggered if the EAR falls below a set threshold for a certain duration.
Emotion Detection: Analyzes facial expressions and labels emotions with probabilities above 10%.
Phone Usage Detection: Identifies handheld phones in the frame and issues an alert if detected.

3. Data Analysis

Data from each frame is analyzed using the following criteria:

Drowsiness Detection: EAR is continuously monitored; drowsiness is flagged if it remains below 0.30 for 15 consecutive frames.
Emotion Detection: Emotions with probabilities over a set threshold are displayed, providing feedback on the driver’s emotional state.
Phone Usage Detection: Detects phone presence with over 50% confidence and warns the driver.

4. Evaluation and Methodology Justification

The methodology balances accuracy, efficiency, and real-time processing. Selected models (Dlib, FER, YOLO) and the Flask framework ensure smooth integration and real-time data processing capabilities.

Example Data

Detection Module	Metric	Data Type	Example Value
Drowsiness Detection	EAR	Numeric (Float)	0.25
Emotion Detection	Emotion Probabilities	List of Floats	[Happy: 0.7, Sad: 0.2]
Phone Usage Detection	Phone Detected	Boolean	True

Getting Started
Clone the repository:

bash
Copy code
git clone https://github.com/your-username/safe-driving-app.git

Install dependencies:
bash
Copy code
pip install -r requirements.txt

Run the application:
bash
Copy code
python single_code.py

Access the app through http://localhost:5000.

Future Enhancements

Integration of additional driver monitoring sensors.
Analysis of external data sources (e.g., weather or traffic data).
Enhanced user interface and experience.
License
This project is licensed under the MIT License - see the LICENSE file for details.
