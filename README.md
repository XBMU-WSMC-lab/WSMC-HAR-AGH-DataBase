# The WSMC-HAR-AGH Dataset: Multimodal Wearable Sensor Data for Human Activity Recognition

## 1. Overview
The **WSMC-HAR-AGH** database is a multimodal dataset designed for Human Activity Recognition (HAR). It contains synchronized inertial motion data and physiological signals collected from 15 participants using a custom **Arm-Wearable Equipment (AWE)** device. 

## 2. Technical Specifications
- **Sampling Frequency:** 50 Hz (20ms interval).
- **Participants:** 15 healthy subjects (11 males, 4 females).
- **Sensors:** 
  - Tri-axial Accelerometer (±2g)
  - Tri-axial Gyroscope (±500 dps)
  - Physiological Sensor (MAX30102 for Heart Rate & SpO2)
- **Device:** AWE (STM32F103ZET6 MCU based)

## 3. Data Format
The dataset is provided in space-separated text files (`.txt`). Each line represents a single timestamped observation.

### 3.1 Data Instance Example
`1 11906 14382 -2744 -66 -1367 34 xxxxx xxxxx Claping 2025-03-29 10:05:00`

### 3.2 Column Definitions
| Column | Field | Description |
| :--- | :--- | :--- |
| 1 | **user-id** | Unique ID of the subject (1–15). |
| 2–4 | **acc-x, acc-y, acc-z** | Raw tri-axial acceleration data (16-bit). |
| 5–7 | **gyr-x, gyr-y, gyr-z** | Raw tri-axial angular velocity data (16-bit). |
| 8 | **heart-x** | Raw physiological metric (Heart Rate related). |
| 9 | **heart-y** | Raw physiological metric (Blood Oxygen related). |
| 10 | **label** | Ground truth activity category (e.g., Claping). |
| 11 | **date** | Recording date (YYYY-MM-DD). |
| 12 | **time** | Recording time (HH:MM:SS). |

## 4. Activity Taxonomy
The dataset includes the following 10 activities:
- **ADLs:** Sweeping, Waving, Claping, Sitting, Upstairs, Downstairs.
- **Fitness (FRA):** Jogging, Running, Skipping, Squatting.

## 5. File Structure

<pre>
WSMC-HAR-AGH-Dataset/
└── s_user[1-15]/                # Subject ID
    ├── Exp/                    # Main experiment phase
    │   ├── Activity[1-10]/     # Activity folders
    │   │   ├── s_user1_Exp_1_IMU.txt   # Inertial & physiological data
    │   │   └── s_user1_Exp_1_EX.txt    # Explanatory metadata
    └── Pre/                    # Preliminary phase
</pre>


## 6. Data Availability
The dataset is categorized into two subsets based on privacy requirements:

### 6.1 Publicly Available Data
The **anonymized inertial sensor data** (Accelerometer and Gyroscope) for all 11 subjects is publicly accessible via our repository:

- **Repository:** [(https://github.com/XBMU-WSMC-lab/WSMC-HAR-AGH-DataBase)]
- **Access License:** Open Access under [CC BY 4.0](https://creativecommons.org/licenses/by/4.0/)

### 6.2 Data Available on Request
The **raw physiological signals** (Heart Rate/SpO2) and **verification images** are restricted due to ethical and privacy constraints (potential for participant re-identification). Researchers may request access through the following process:

*   **Contact:** Reach out to the corresponding author via email.
*   **Requirements:** A formal application explaining the research purpose and a signed **Data Use Agreement (DUA)**.
*   **Approval:** Access is granted upon review by the institutional ethics committee to ensure compliance with privacy standards.

## 7. License
This project is licensed under the Creative Commons Attribution 4.0 International (CC BY 4.0). You are free to share and adapt the material, provided you give appropriate credit to the original authors.
