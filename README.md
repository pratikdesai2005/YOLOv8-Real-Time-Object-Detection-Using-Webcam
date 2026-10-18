YOLOv8 Real-Time Object Detection Using Webcam
📌 Project Description

This project performs real-time object detection using a webcam and a custom-trained YOLOv8 model. It captures video frames from the webcam, detects objects using the trained model (best.pt), and displays the detected objects with bounding boxes, class names, and confidence scores.

The project uses OpenCV for webcam access and video display, and Ultralytics YOLO for object detection.

✨ Features
Real-time object detection using a webcam.
Custom-trained YOLOv8 model support.
Bounding boxes around detected objects.
Displays class labels and confidence scores.
Configurable detection confidence threshold.
Press q to exit the detection window safely.
🛠️ Technologies Used
Python
OpenCV (cv2)
Ultralytics YOLOv8
NumPy (installed as a dependency when required)
📂 Project Structure
YOLOv8-Webcam-Detection/
│
├── best.pt          # Trained YOLO model weights
├── main.py          # Python detection script
├── README.md        # Project documentation
└── requirements.txt # Project dependencies (optional)

⚙️ Requirements
Python 3.8 or later (use a Python version supported by your installed Ultralytics release).
A working webcam.
A trained YOLO model file named best.pt.
Required Python libraries.
📥 Installation
1. Clone or Download the Project

Download the project files and navigate to the project directory.

cd YOLOv8-Webcam-Detection

2. Create a Virtual Environment (Optional)
python -m venv venv


Activate the environment:

Windows

venv\Scripts\activate


Linux / macOS

source venv/bin/activate

3. Install Dependencies

Install the required libraries using pip:

pip install opencv-python ultralytics


Alternatively, create a requirements.txt file containing:

opencv-python
ultralytics


Then install the dependencies:

pip install -r requirements.txt

📁 Model Setup

Place your trained YOLO model file, best.pt, in the same directory as your Python script.

The model is loaded using:

model = YOLO("best.pt")


Note: The best.pt file must contain valid YOLO-compatible model weights. This project uses your custom-trained model rather than automatically downloading the pretrained YOLOv8n model.

▶️ How to Run
Connect your webcam to your computer.
Ensure that best.pt is in the project directory.
Run the Python script:
python main.py

A window titled YOLOv8 Webcam Detection will appear.
Point the webcam at the objects you want to detect.
Detected objects will be displayed with bounding boxes, labels, and confidence scores.
Press q to close the window and stop the program.
🔍 How It Works
Load the model: Loads the trained YOLO weights from best.pt.
Initialize the webcam: Opens the default camera using cv2.VideoCapture(0).
Capture frames: Reads video frames continuously from the webcam.
Detect objects: Passes each frame to the YOLO model with a confidence threshold of 0.5.
Annotate frames: Draws bounding boxes, class names, and confidence scores using results[0].plot().
Display results: Shows the annotated video in an OpenCV window.
Exit safely: Releases the webcam and closes OpenCV windows when the user quits or the loop ends.
🎚️ Confidence Threshold

The model uses the following detection setting:

results = model(frame, conf=0.5)


The conf=0.5 parameter sets the minimum detection confidence threshold to 50%.

Higher threshold: Generally reduces low-confidence detections but may miss some objects.
Lower threshold: May detect more objects but can increase false positives.

You can adjust this value depending on your application:

results = model(frame, conf=0.3)

🐛 Troubleshooting
Webcam Not Opening

If you see:

RuntimeError: Could not open the webcam.


Try the following:

Ensure the webcam is connected and functioning.
Close other applications that may be using the camera.
Check your operating system's camera permissions.
Try changing cv2.VideoCapture(0) to cv2.VideoCapture(1) if another camera is available.
Model File Not Found

If the model cannot be loaded, verify that best.pt exists in the current working directory or provide its full path:

model = YOLO("path/to/best.pt")

Missing Python Libraries

Install the required packages:

pip install opencv-python ultralytics

Slow Detection

If detection is slow:

Reduce the webcam frame resolution.
Use a smaller YOLO model if appropriate.
Use a supported GPU for inference if available.
Close unnecessary applications.
🔮 Future Improvements
Add support for multiple webcam devices.
Save detected video to a file.
Display FPS (frames per second).
Add object tracking.
Support image and video file input.
Optimize inference using GPU acceleration.
📄 License

This project is intended for educational and development purposes. Add an appropriate license if you plan to distribute or publish the project.

👨‍💻 Author

Developed using Python, OpenCV, and Ultralytics YOLO for real-time webcam object detection.
