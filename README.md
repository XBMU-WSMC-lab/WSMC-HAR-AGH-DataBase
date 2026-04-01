Dataset: WSMC-HAR-AGH Multimodal Wearable Sensor Data for Human Activity Recognition
License: CC BY 4.0

1. Description
The WSMC-HAR-AGH (Wearable Sensor Multimodal Classification - Human Activity Recognition) dataset is a high-fidelity multimodal repository. It synchronizes kinematic motion (acceleration/angular velocity) with physiological metrics (heart rate/blood oxygen). Collected via a custom Arm-Wearable Equipment (AWE) device, it is designed to support advanced research in sensor fusion and deep learning for HAR.

2. Technical Specifications
Sampling Rate: 50 Hz (1 sample every 20ms).
Hardware: AWE Prototype (STM32F103ZET6 MCU).
Inertial Sensor: MPU-6050 (Range: Acc ±2g, Gyro ±500 dps).
Physiological Sensor: MAX30102 (Pulse Oximetry & Heart-Rate).
Participants: 15 healthy young adults (11 males, 4 females).
Activities: 10 categories (6 ADLs, 4 Fitness-related).

3. Data Structure & Files
The data is provided in .txt (Inertial) and .csv (Physiological) formats. Each file is organized by Subject ID and Activity type.
WSMC-HAR-AGH-Dataset/
└── s_user[1-15]/              # Unique Subject Identifier
    ├── Exp/                   # Main Experiment Phase
    │   ├── Activity[1-10]/    # Specific Activity Folders
    │   │   ├── s_user1_Exp_1_IMU.txt  # Core Data File (IMU + Physiological)
    │   │   └── s_user1_Exp_1_EX.txt   # Documentation/Images
    └── Pre/                   # Preliminary Phase

4. Data Record Example & Definitions
Each line in the data file follows a space-separated or tab-separated format. Below is an example of a single record:
Data Instance:
1 11906 14382 -2744 -66 -1367 34 xxxxx xxxxxx Claping 2025-03-29 10:05:00

Column Definitions:
Column Index	Field Name	Description	Physical Units / Format
1	user-id	Unique ID of the participant	Integer (e.g., 1)
2-4	acc-X/Y/Z	Tri-axial Accelerometer data	Raw 16-bit signed integer
5-7	ang-X/Y/Z	Tri-axial Gyroscope data	Raw 16-bit signed integer
8	heart-X	Raw Heart Rate signal (MAX30102)	Raw sensor value
9	heart-Y	Raw Blood Oxygen signal (MAX30102)	Raw sensor value
10	label	Ground truth activity category	String (e.g., "Claping")
11	date	Date of acquisition	YYYY-MM-DD
12	time	System timestamp	HH:MM:SS

5. Activity Taxonomy
The following 10 activities are included in the dataset:

Sweeping
Waving
Clapping (Label: "Claping")
Sitting
Upstairs
Downstairs
Jogging
Running
Skipping
Squatting
6. Data Availability Statement
Public Dataset: The anonymized inertial sensor data (Accelerometer and Gyroscope) for all 15 subjects is publicly available via the [GitHub/Zenodo Link].
Restricted Data: Raw physiological signals (MAX30102 red/IR channels) and participant-related images used for verification are available upon reasonable request from the corresponding author, subject to a Data Use Agreement (DUA).

7. License & Citation
License
This dataset is licensed under the Creative Commons Attribution 4.0 International (CC BY 4.0) license.
