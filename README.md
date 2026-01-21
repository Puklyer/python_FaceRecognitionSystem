Face Recognition System using NN and kNN Algorithms
A Python-based face recognition application that implements Nearest Neighbor (NN) and k-Nearest Neighbors (kNN) algorithms with multiple distance metrics for facial image classification.
Overview
This project provides a graphical user interface (GUI) for face recognition using the AT&T Database of Faces (formerly ORL Database). The system compares input images against a trained dataset using various distance metrics and classification algorithms.
Features

Multiple Distance Metrics: Euclidean, Manhattan, Infinity (Chebyshev), and Cosine similarity
Two Classification Algorithms:

Nearest Neighbor (NN)
k-Nearest Neighbors (kNN)


Performance Analysis: Automatic calculation and visualization of Recognition Rate (RR) and Average Query Time (AQT)
Interactive GUI: Easy-to-use interface built with Tkinter
Visual Results: Displays the closest matching face from the database
Batch Testing: Evaluates algorithm performance on test images
Data Export: Saves performance metrics to CSV files

Requirements
python >= 3.7
numpy
opencv-python (cv2)
matplotlib
pillow
pandas
tkinter (usually included with Python)
Installation

Clone or download this repository
Install required packages:

bashpip install numpy opencv-python matplotlib pillow pandas

Download the AT&T Database of Faces and organize it in folders named s1, s2, ..., s40

Dataset Structure
The code expects the following folder structure:
Dataset/
├── s1/
│   ├── 1.pgm
│   ├── 2.pgm
│   └── ...
├── s2/
│   ├── 1.pgm
│   ├── 2.pgm
│   └── ...
└── ...

40 people (folders s1 to s40)
10 images per person (.pgm format)
Images 1-8 are used for training
Images 9-10 are used for testing

Usage
Running the Application

Update the base_folder path in the code to point to your dataset location
Run the script:

bashpython face_recognition.py
Using the GUI

Select Distance Metric: Choose from Euclidean, Manhattan, Infinity, or Cosine
Select Algorithm: Choose NN or kNN
Set k value: If using kNN, enter the number of neighbors (e.g., 3, 5, 7)
Load Image: Click "Încarcă imagine și rulează" to select a test image
View Results: The closest matching face will be displayed along with its index
Generate Reports: Click "Afișează grafice RR și AQT" to see performance graphs

Performance Metrics

Recognition Rate (RR): Percentage of correctly identified faces
Average Query Time (AQT): Average time taken to process one query
Results are saved to CSV files: rr_values_NN.csv, aqt_values_NN.csv, etc.

How It Works
NN Algorithm
Finds the single closest match in the training dataset using the selected distance metric.
kNN Algorithm
Finds the k closest matches and uses majority voting to determine the person's identity.
Distance Metrics

Euclidean: L2 norm, standard straight-line distance
Manhattan: L1 norm, sum of absolute differences
Infinity: L∞ norm, maximum absolute difference
Cosine: Measures angle between vectors (1 - cosine similarity)

Configuration
Key parameters in the code:
pythonimage_width = 92          # Width of resized images
image_height = 112        # Height of resized images
num_people = 40           # Number of individuals in dataset
num_images_per_person = 8 # Training images per person
Output Files

rr_values_NN.csv / rr_values_kNN.csv: Recognition rates for each norm
aqt_values_NN.csv / aqt_values_kNN.csv: Average query times for each norm
Performance graphs showing RR and AQT comparisons

Limitations

Currently supports grayscale images only
Requires specific folder structure
Images must be in PGM format (or convertible formats supported by OpenCV)

Future Improvements

Add support for more image formats
Implement PCA/LDA for dimensionality reduction
Add real-time webcam recognition
Include more sophisticated algorithms (SVM, Neural Networks)
Support for color images

License
This project is provided as-is for educational purposes.
Acknowledgments

AT&T Laboratories Cambridge (formerly Olivetti Research Laboratory) for the face database
Built using Python scientific computing libraries: NumPy, OpenCV, Matplotlib

Contact
For questions or suggestions, please open an issue in the repository.
