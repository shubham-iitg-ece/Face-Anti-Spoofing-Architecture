# Face-Anti-Spoofing-Architecture

### Under the guidance of [Dr. Kannan Karthik, Associate Professor, Dept. of EEE, IIT Guwahati](http://www.iitg.ac.in/engfac/k.karthik/ "Dr. Kannan Karthik's Homepage")

### BTP Members:

1. [**Shubham, ECE, IITG**](https://www.linkedin.com/in/shubham-iitg-ece/ "Shubham's LinkedIn")
2. [**Shubham Lohiya, ECE, IITG**](https://www.linkedin.com/in/shubham-lohiya/ "Shubham Lohiya's LinkedIn")

### Application layer:

Facial anti-spoofing has been essential in recent times, with the natural integration of biometric-based access control systems, either based on fingerprint or face in SMART PHONES. The same anti-spoofing frame (implemented at a slightly advanced level), is also required in unmanned surveillance stations to detect the presence of disguises or prosthetics deployed by illegal traffickers to avoid being snapped by hidden cameras.

### Technical setting - BROAD:

There are two modes in which anti-spoofing can be performed: 1) Identity independent setting in which the anti-spoofing algorithm has no PRIOR idea regarding the subject in the FACIAL SNAPSHOT or VIDEO presented to the camera; 2) Reference based anti-spoofing wherein a person may claim to be someone else by presenting a prosthetic of that individual's face. Here, the anti-spoofing system has prior information (pre-stored genuine images available) regarding the subject who may have been impersonated.

The IDENTITY independent problem is less challenging from a technical viewpoint as compared to the REFERENCE based anti-spoofing problem. In the case of the latter one has to deliberately ignore recognition based features and focus on "condition/acquisition-specific features" to detect some form of spoofing.

### Technical setting - NARROW/SPECIFIC (our problem):

In our problem, we propose to develop a REFERENCE based anti-spoofing system for a closed unmanned authentication system, implemented for an organization. Natural full frontal poses under different lighting conditions will be stored in the database for different subjects. When a person presents his face (natural or disguised as someone else) to the camera, claiming to be SUBJECT-X, multiple snapshots will be taken and then a NATURALNESS check will be done by comparing the TEST-SNAPSHOTS with the pre-stored NATURAL FACIAL IMAGES of that specific subject-X.

### Technical challenges (our problem):

Once the base-feature set for anti-spoofing is designed and calibrated, the problem becomes tantamount to an outlier detection algorithm, assuming that there is sufficient information in the database to learn the statistical model for SUBJECT-SPECIFIC NATURALNESS  (from the point of view of the face). Any attempt to produce a SPOOFED version of the face should be detected by this anti-spoofing algorithm by treating this test-query set as an outlier. Ideas involving 1-class SVM and other anomaly detection algorithms will be explored.

### Block Diagram of Project:

![alt text](https://github.com/shubham-iitg-ece/Face-Anti-Spoofing-Architecture/blob/master/report.png "Face Anti-Spoofing Experimental Set-Up")

### Work Done until Aug-Nov 2018 Semester:

In this work, we have used CASIA face anti-spoofing dataset as base database. The dataset is divided into 80:20 train-test split. For the training data, statistical features are calculated and concatenated to form a 14-dimensional feature vector which is inputted to train the Support Vector Machine (SVM). Subsequent to the offline training, same feature vectors are created for the test images and is tested using the trained SVM. For the second module, similar approach is adopted. We compute a 16-dimensional feature for each training image. We compute LBP histogram (8-bins) and t-LBP (8-bins), further normalized and concatenates them to the form the feature vector. Offline training was done, post which testing was done using test dataset.

### Future Works

In the work presented, we have mainly focussed on sharpness, locality and textural based features. We have planned to work on image distortion analysis which consists of designing specularity, color and contrast based features for the purpose of classification to real and spoofed faces. 

Our work till now focuses on classifying any given input image as real or spoofed face image, hence a non-referential model. But as stated in the problem statement, our final goal is to build an referential model for an organization. We have planned to achieve this through building feature set for each individual of the organization, and do a cluster analysis to validate the person as an employee of the organization(which he/she has stated to be). 

### References

[1] J. Galbally and S. Marcel, "Face Anti-spoofing Based on General Image Quality Assessment," 2014 22nd International Conference on Pattern Recognition, Stockholm, 2014, pp. 1173-1178.

[2] Trefný, Jiří & Matas, Jiri. (2010). Extended Set of Local Binary Patterns for Rapid Object Detection. 15th Computer Vision Winter Workshop, Volume 2010.
