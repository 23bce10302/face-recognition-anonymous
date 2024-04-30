Face Recognition Project submitted to Dr. D Lakshmi

## Face Recognition Attendance System with KNN - README

This project implements a face recognition system for attendance recording using K-Nearest Neighbors (KNN) classification. It utilizes a webcam to capture video frames, detects faces within the frames, and predicts the names and registration numbers of those faces based on a pre-trained model. 

### Functionality

1. **Face Detection:** The system utilizes the OpenCV library's Haar cascade classifier to detect faces within the video frames captured from the webcam.
2. **Face Recognition:** The system employs a KNeighborsClassifier model trained on labeled face images and their corresponding names. When a face is detected, the model predicts the name of the person.
3. **Registration Number Recognition:** Another KNeighborsClassifier model is trained on faces and their corresponding registration numbers. This allows for predicting the registration number along with the name.
4. **Attendance Recording:** Upon confirming attendance (pressing 'o' key), the system records the name, registration number, and timestamp in a CSV file named "Attendance_Date.csv" (where Date is the current date in DD-MM-YYYY format). 
5. **Optional Features:**
    - Text-to-Speech announcement upon attendance confirmation (requires `win32com` library).
    - Background image overlay on the captured video frame.

### Prerequisites

- Python 3.x
- OpenCV library (`pip install opencv-python`)
- NumPy library (`pip install numpy`)
- Scikit-learn library (`pip install scikit-learn`)
- Pickle library (usually included in Python installation)
- CSV library (usually included in Python installation)
- `win32com` library (optional, for Text-to-Speech)

### Instructions

1. **Download the pre-trained face detection classifier:** You can download the Haar cascade classifier for frontal face detection from the OpenCV website ([https://docs.opencv.org/4.x/db/d28/tutorial_cascade_classifier.html](https://docs.opencv.org/4.x/db/d28/tutorial_cascade_classifier.html)) and place it in the `data` folder of this project (create the `data` folder if it doesn't exist).
2. **Train the KNN models:** You'll need to have a dataset of labeled face images and their corresponding names and registration numbers. Use the provided scripts or create your own to train the KNN models and save them as pickle files (`names.pkl`, `faces_data.pkl`, and `regs.pkl`) in the `data` folder.
3. **Run the script:** Execute the `test.py` script using Python. This will activate the webcam, perform face detection and recognition, and record attendance upon confirmation.

### Notes

- The accuracy of the system depends on the quality of the training data and the chosen KNN parameters.
- This is a basic implementation and can be further enhanced with features like distance thresholding for confidence in predictions, handling multiple faces in a frame, etc.

### Further Development

- Implement distance thresholding for more reliable predictions.
- Handle multiple faces detected in a single frame.
- Integrate with a database for attendance management.
