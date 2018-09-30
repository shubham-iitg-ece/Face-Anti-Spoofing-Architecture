# Face-Anti-Spoofing-Architecture

### Application layer:

Facial anti-spoofing has been essential in recent times, with the natural integration of biometric-based access control systems, either based on fingerprint or face in SMART PHONES. The same anti-spoofing frame (implemented at a slightly advanced level), is also required in unmanned surveillance stations to detect the presence of disguises or prosthetics deployed by illegal traffickers to avoid being snapped by hidden cameras.

### Technical setting - BROAD:

There are two modes in which anti-spoofing can be performed: 1) Identity independent setting in which the anti-spoofing algorithm has no PRIOR idea regarding the subject in the FACIAL SNAPSHOT or VIDEO presented to the camera; 2) Reference based anti-spoofing wherein a person may claim to be someone else by presenting a prosthetic of that individual's face. Here, the anti-spoofing system has prior information (pre-stored genuine images available) regarding the subject who may have been impersonated.

The IDENTITY independent problem is less challenging from a technical viewpoint as compared to the REFERENCE based anti-spoofing problem. In the case of the latter one has to deliberately ignore recognition based features and focus on "condition/acquisition-specific features" to detect some form of spoofing.

### Technical setting - NARROW/SPECIFIC (our problem):

In our problem, we propose to develop a REFERENCE based anti-spoofing system for a closed unmanned authentication system, implemented for an organization. Natural full frontal poses under different lighting conditions will be stored in the database for different subjects. When a person presents his face (natural or disguised as someone else) to the camera, claiming to be SUBJECT-X, multiple snapshots will be taken and then a NATURALNESS check will be done by comparing the TEST-SNAPSHOTS with the pre-stored NATURAL FACIAL IMAGES of that specific subject-X.

### Technical challenges (our problem):

Once the base-feature set for anti-spoofing is designed and calibrated, the problem becomes tantamount to an outlier detection algorithm, assuming that there is sufficient information in the database to learn the statistical model for SUBJECT-SPECIFIC NATURALNESS  (from the point of view of the face). Any attempt to produce a SPOOFED version of the face should be detected by this anti-spoofing algorithm by treating this test-query set as an outlier. Ideas involving 1-class SVM and other anomaly detection algorithms will be explored.

