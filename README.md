# Face Recognition Attendance System

A Python-based attendance system using [OpenCV](https://opencv.org/) for face detection and recognition. It captures facial data, trains a recognizer, and identifies known users in real time, logging attendance locally via Excel.

---

## 🔍 Description

This system uses a webcam to register faces and recognize them using OpenCV’s [LBPHFaceRecognizer](https://docs.opencv.org/4.x/dc/dc3/tutorial_py_matcher.html). Each recognized face is mapped to a name and ID, which is logged in a local Excel file through a custom module. Unknown faces are flagged and blocked after multiple failed attempts. Audio feedback is provided for successful recognition.

* [`Create_dataset.py`](./Create_dataset.py): Captures and stores 50 grayscale images per user using Haar cascades.
* [`Recognise.py`](./Recognise.py): Loads a trained LBPH model to recognize and log users in real-time with audio feedback.

---

## 🧠 Techniques Used

* **Face detection with Haar Cascades** using [`cv2.CascadeClassifier`](https://docs.opencv.org/4.x/d7/d8b/tutorial_py_face_detection.html) for lightweight, fast face localization.
* **Face recognition with LBPH** via `cv2.face.LBPHFaceRecognizer_create()`, suited for real-time applications with limited datasets.
* **Excel file writing** using a custom `xlwrite.py` module for attendance tracking.
* **Video streaming** and frame analysis via [`cv2.VideoCapture`](https://docs.opencv.org/4.x/dd/d43/tutorial_py_video_display.html).
* **Real-time rectangle overlay** using `cv2.rectangle()` to visually tag faces in the stream.
* **Audio playback** through [`playsound`](https://pypi.org/project/playsound/) for basic user feedback.

---

## 📦 Libraries and Tools

* [`opencv-contrib-python`](https://pypi.org/project/opencv-contrib-python/): Required for `cv2.face` module (LBPH).
* [`playsound`](https://pypi.org/project/playsound/): Cross-platform audio player for simple sound notifications.
* [`firebase-admin`](https://pypi.org/project/firebase-admin/) *(optional)*: Intended for future integration with Firebase backend.
* Custom `xlwrite.py`: Handles Excel-based attendance logging.

---

## 📁 Project Structure

```
.
├── Create_dataset.py
├── Recognise.py
├── xlwrite.py
├── dataset/
├── trainer/
├── haarcascade_frontalface_default.xml
├── Welcome.mp3
```

* `dataset/`: Stores 50 grayscale face images per user (named by ID).
* `trainer/`: Contains the trained LBPH face model (`trainer.yml`).
* `haarcascade_frontalface_default.xml`: Pre-trained Haar cascade classifier from OpenCV.
* `Welcome.mp3`: Sound file used for recognized users.
* `xlwrite.py`: A custom Python module for writing attendance logs to Excel.
