# Author: Ashish Chokhani

# ECG Monitoring and Transmission

This project involves the development of an ECG monitoring system using an ESP32 microcontroller for data acquisition and transmission, along with MATLAB scripts for data analysis and visualization. The system is designed to monitor the electrical activity of the heart, save the data, and perform signal processing to determine the heart rate. Finally integrating machine learning for disease prediction based on the ECG data. 

## Directory Structure

```bash
ECG-Monitoring-and-Transmission
│ ECG_filesave_2.ino.ino
│ Report.pdf
│ ecgdemo.m
│ ecgdemowinmax.m
└── README.md
```


## Table of Contents

- [Introduction](#introduction)
- [Project Components](#project-components)
  - [ECG_filesave_2.ino.ino](#ecg_filesave_2inoino)
  - [ecgdemo.m](#ecgdemom)
  - [ecgdemowinmax.m](#ecgdemowinmaxm)
  - [Report.pdf](#reportpdf)
- [How to run the project](#how-to-run-the-project)
- [Features](#features)
- [Machine Learning for Disease Prediction](#machine-learning-for-disease-prediction)
- [Implementation](#implementation)
  - [Hardware](hardware)
  - [Software](software)
- [Results and Analysis](results-and-analysis)
- [Proposed Improvements](proposed-improvements)
- [Challenges Faced](#challenges-faced)
- [Proposed Improvements](#proposed-improvements)
- [Contributing](#contributing)

## Introduction

Many electrical devices are used to measure and record biological activity in the human body. One such device is the electrocardiogram (ECG), which measures the electrical signals produced by the heart. These signals provide crucial information about the heart's structure and function. This project aims to build a complete ECG monitoring system with wireless data transmission and advanced signal processing capabilities.

## Project Components

### ECG_filesave_2.ino.ino

This is the Arduino code for the ESP-32 microcontroller. It captures ECG data from a specified pin, saves the data to the SPIFFS file system, and transmits the data over WiFi.

### ecgdemo.m

This MATLAB script loads ECG data, filters the data to remove low-frequency components, and performs peak detection to calculate the average heart rate.

### ecgdemowinmax.m

A MATLAB function that filters the ECG data using a sliding window approach to detect the maximum values within the window.

### Report.pdf

The project report detailing the design, implementation, and analysis of the ECG monitoring system. It includes the circuit design, simulation results, and hardware results.

## How to Run the Project

### Arduino Sketch

1. **Setup**: Ensure you have an ESP32 and an ECG sensor connected to the appropriate GPIO pin.
2. **Wi-Fi Credentials**: Update the `ssid` and `password` variables in `ECG_filesave_2.ino.ino` with your Wi-Fi credentials.
3. **Upload**: Upload the sketch to the ESP32 using the Arduino IDE.

### MATLAB Scripts

1. **Data Acquisition**: Ensure that the ECG data is saved in a CSV file on the ESP32.
2. **Data Processing**: Run `ecgdemo.m` in MATLAB to process the ECG data, filter the signal, and calculate the heart rate.

## Features

- **Wireless ECG Signal Capture:** Designed a circuit skilled in wireless ECG signal capture using an ESP‐32 microcontroller.
- **Data Transmission:** Utilizes the ESP‐32 for transmitting ECG data wirelessly.
- **MATLAB Post-Processing:** Processes the ECG data in MATLAB to filter noise and calculate the average heart rate.
- **Machine Learning Integration:** Integrates machine learning techniques for disease prediction based on the ECG signals.

## Machine Learning for Disease Prediction

### Overview

The integration of machine learning into the ECG monitoring system aims to enhance the diagnostic capabilities of the device. By analyzing the ECG signals, the system can predict potential heart-related diseases such as arrhythmias, myocardial infarction, and other cardiovascular conditions.

### Methodology

1. **Data Preprocessing:**
   - **Filtering:** Remove noise and artifacts from the ECG signals.
   - **Feature Extraction:** Extract relevant features from the ECG signals such as heart rate variability, QRS complex duration, and ST-segment elevation.

2. **Model Training:**
   - **Dataset:** Use labeled ECG datasets from medical databases for training the machine learning model.
   - **Algorithms:** Implement various machine learning algorithms such as Support Vector Machines (SVM), Random Forests, and Neural Networks to train models on the extracted features.

3. **Model Evaluation:**
   - **Cross-Validation:** Perform cross-validation to assess the model's performance and avoid overfitting.
   - **Metrics:** Evaluate the model using metrics such as accuracy, precision, recall, and F1-score.

4. **Deployment:**
   - **Integration:** Integrate the trained model into the ECG monitoring system to provide real-time disease prediction.
   - **User Interface:** Develop a user-friendly interface to display the predictions and provide alerts for potential health issues.
  
## Implementation

### Hardware

- **ESP32 Microcontroller**: Used for data acquisition and transmission.
- **Analog Filters**: Designed to process the ECG signal, including instrumentation amplifiers and filters.

### Software

- **Arduino Sketch (ECG_filesave_2.ino.ino)**: 
  - Reads data from an ECG sensor connected to the ESP32.
  - Saves the data to a CSV file on the ESP32's SPIFFS.
  - Transmits data over Wi-Fi for remote monitoring.

- **MATLAB Scripts**: 
  - **ecgdemo.m**: Loads and processes ECG data, applying FFT for frequency domain analysis, filtering, and peak detection to determine heart rate.
  - **ecgdemowinmax.m**: Custom windowed maximum filter used by `ecgdemo.m`.

## Results and Analysis

The system successfully captures and processes ECG signals, with detailed results documented in the report. Key results include:
- Heart rate calculation based on detected peaks.
- Frequency analysis of the ECG signal.
- Filtered ECG signal visualization.

## Benefits

- **Early Detection:** Enables early detection of cardiovascular diseases, allowing timely medical intervention.
- **Continuous Monitoring:** Provides continuous monitoring and analysis of heart activity, offering insights into the patient's health over time.
- **Personalized Healthcare:** Facilitates personalized healthcare by tailoring predictions and recommendations based on individual ECG patterns.

## Challenges Faced

- **Transmission Part:** Ensuring reliable transmission of a large number of ECG samples.
- **Circuit Gain and Cutoff:** Determining the optimal gain and cutoff frequencies for the filters.
- **Peak Detection:** Deciding the optimal window size and threshold for peak detection in MATLAB.
- **Data Quality:** Ensuring the quality and accuracy of ECG data for reliable machine learning predictions.
- **Model Generalization:** Developing machine learning models that generalize well across diverse patient populations.

## Proposed Improvements

- **12 Lead Electrodes:** Modify the circuit design to operate with 12 lead electrodes for better results.
- **Raspberry Pi Integration:** Use a Raspberry Pi microcontroller for improved data rate transmission.
- **Enhanced Signal Processing:** Further improve the FIR filter for better noise reduction.
- **Machine Learning Enhancements:** Develop more robust machine learning models for accurate disease prediction.

## Contributing

Contributions are welcome! Please open an issue or submit a pull request if you have any improvements or suggestions.
