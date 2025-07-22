👩‍🏫 Face Recognition Attendance System
This project is a simple face recognition-based attendance system built using Python, OpenCV, and LBPH Face Recognizer. It enables capturing face images for dataset creation and then recognizes faces in real-time to mark attendance.

📸 Features
📷 Face Dataset Creation: Captures and saves 50 grayscale face images per user in the dataset/ folder.


🧠 Face Recognition: Uses LBPH (Local Binary Pattern Histogram) to recognize known faces from a trained model.


📋 Attendance Logging: Logs the recognized user's attendance to a local Excel sheet using xlwrite.


🔒 Security Feature: Unrecognized faces are flagged and blocked after multiple attempts.


🔊 Audio Feedback: Plays a welcome sound for valid users.



🛠 Requirements
Python 3.x


OpenCV with contrib modules (opencv-contrib-python)


playsound


firebase-admin (optional, for future Firebase integration)


xlwrite.py (your custom module for Excel logging)


Install dependencies:
pip install opencv-contrib-python playsound firebase-admin


📁 Folder Structure

├── Create_dataset.py          # Script to capture and save face images
├── Recognise.py               # Script to recognize and mark attendance
├── dataset/                   # Saved face images
├── trainer/                   # Trained face model (trainer.yml)
├── haarcascade_frontalface_default.xml  # Haar cascade for face detection
├── Welcome.mp3                # Welcome audio for recognized users
├── xlwrite.py                 # Excel logging module


🚀 How It Works
1. Create Dataset (Face Capture)
Run the script to capture images for a new user:
Create_dataset.py

Prompts you to enter a user ID


Captures 50 face images using your webcam


Saves them in the dataset/ directory


2. Train the Recognizer
⚠️ Note: Training code isn't shown here but you should use OpenCV’s LBPHFaceRecognizer to train on the dataset and save the model to trainer/trainer.yml.
3. Recognize Faces & Mark Attendance

Recognise.py

Starts webcam


Recognizes faces using the trained model


Displays name and confidence score


Calls xlwrite.output() to mark attendance


Flags unknown faces and plays audio for valid users



🧠 Technologies Used
OpenCV (LBPH Face Recognizer, Haar Cascades)


Python (cv2, os, time, playsound)


Excel Writing (via xlwrite.py)


Firebase (optional setup shown in comments)



🤝 Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

📄 License
This project is open-source and available under the MIT License.

