# Online IMU-Odometer Calibration Using GNSS Measurements for Autonomous Ground Vehicle Localization

[![IEEE Xplore](https://img.shields.io/badge/IEEE-Xplore-blue.svg)](https://ieeexplore.ieee.org/abstract/document/11595203/)
[![Google Drive Data](https://img.shields.io/badge/Google%20Drive-Data%20Download-4285F4?logo=googledrive&logoColor=white)](https://drive.google.com/drive/folders/18W425u7QpHuL2fW7MLZuUjIMXgTFhm2O?usp=sharing)
[![License: MIT](https://img.shields.io/badge/License-MIT-yellow.svg)](LICENSE)

Official dataset and evaluation repository for the paper **"Online IMU-Odometer Calibration Using GNSS Measurements for Autonomous Ground Vehicle Localization"**, published in *IEEE Transactions on Intelligent Transportation Systems* (T-ITS), 2026.

> 📖 **IEEE Xplore:** [https://ieeexplore.ieee.org/abstract/document/11595203/](https://ieeexplore.ieee.org/abstract/document/11595203/)  
> 📁 **Google Drive Dataset:** [Access Dataset Files Here](https://drive.google.com/drive/folders/18W425u7QpHuL2fW7MLZuUjIMXgTFhm2O?usp=sharing)

---

## 📌 Dataset Overview

This repository provides raw and processed multi-sensor data collected by an autonomous ground vehicle (AGV) equipped with **u-blox ZED-F9P**, **Xsens MTi-300 IMU**, and an **Agilex Scout-Mini** wheel encoder platform. The dataset is specifically tailored for benchmarking online extrinsic/intrinsic calibration, GNSS/INS/Odometer tight coupling, and urban localization algorithms.

### 🛠️ Hardware Specification

| Sensor Type | Model / Details | Data Formats |
| :--- | :--- | :--- |
| **GNSS Rover** | u-blox ZED-F9P | RINEX 3.0x (`.24O`) |
| **GNSS Base** | HKSC (Hong Kong SatRef Base Station) | RINEX 3.0x (`.24O`) |
| **Ephemeris** | Multi-GNSS Broadcast Ephemeris | RINEX 3.0x (`.rnx`) |
| **IMU** | Xsens MTi-300 | ASCII (`.txt`) |
| **Wheel Odometer** | Agilex Scout-Mini | ASCII (`.txt`) |
| **Ground Truth** | High-precision RTK/INS Reference | `.kmz` / `.txt` |

---

## 📂 File Structure

```text
FieldNav-Dataset/
├── gnss/
│   ├── rover/                                  # u-blox F9P RINEX raw observations
│   │   ├── BFN15430184_2024-11-04_10-06-15.24O
│   │   ├── BFN15430184_2024-11-04_10-57-08.24O
│   │   └── BFN15430184_2024-11-04_12-04-19.24O
│   ├── base_station/                            # Base station RINEX file
│   │   └── hksc3090.24o
│   └── ephemeris/                              # Broadcast ephemeris file
│       └── BRDM00DLR_S_20243090000_01D_MN.rnx
├── imu_odometer/                                # Synchronized IMU + Wheel Odometer
│   └── imu_odometer_GNSSpos.txt                 # Raw measurements containing Xsens MTi-300 & Scout-Mini
└── ground_truth/                               # Reference trajectory
    ├── groundtruth.kmz                         # Visualization file for Google Earth
    └── groundtruth.txt                         # Time-stamped 6-DoF state reference
