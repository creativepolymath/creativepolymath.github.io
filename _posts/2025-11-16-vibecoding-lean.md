---
title: "Vibe Coding and LEAN Manufacturing"
date: 2026-11-16T16:30:30-04:00
categories:
  - blog
tags:
  - coding
  - ai
  - python
  - rfid
  - 
header:
---
## 🧠 Overview
This project began as a simple RFID test and evolved into a lightweight machine usage tracking system designed for LEAN manufacturing environments. The goal was to create a no-frills tool that captures real machine runtime data without adding complexity to the shop floor.

## 🎯 Objective
Develop a simple, reliable system to:
- Track machine start and stop events
- Record accurate runtime durations
- Provide clear, real-time feedback to operators
- Support LEAN principles by exposing inefficiencies

## 🛠 Tools & Technologies
- ESP32 microcontroller
- MFRC522 RFID reader
- ST7789 TFT display
- MQTT (for data transmission)
- NTP (for timestamp synchronization)
- Arduino IDE / C++
- Python (for data logging and CSV generation)

## ⚙️ Process

### 1. Initial Concept
The project started as a basic RFID reader test to detect user input and trigger events.

### 2. Workflow Expansion
Functionality was expanded to include:
- Machine start/stop logging via RFID scans
- Timestamp recording using NTP
- Prevention of conflicting inputs during active jobs

### 3. Real-Time Feedback
- Integrated a TFT display to show:
  - Active job status
  - Start time
  - Elapsed runtime counter
- Designed the interface for quick readability on the shop floor

### 4. Data Transmission
- Implemented MQTT to send scan and timing data
- Developed a Python-based receiver to log data into structured CSV files

### 5. Iteration & Refinement
- Adjusted logic to ensure accurate runtime tracking
- Improved display clarity and usability
- Debugged SPI conflicts between RFID reader and display

## 🚧 Challenges & Solutions

**Challenge:** Managing multiple SPI devices (RFID + display)  
**Solution:** Configured shared SPI bus with proper chip select handling and timing adjustments

**Challenge:** Ensuring accurate and consistent timestamps  
**Solution:** Integrated NTP synchronization to standardize time across sessions

**Challenge:** Preventing incorrect or duplicate scans during operation  
**Solution:** Implemented logic to lock input to the active RFID tag until the job is completed

**Challenge:** Keeping the interface usable in a fast-paced environment  
**Solution:** Focused on minimal, high-contrast display output with only essential information

## 📊 Results / Outcome
- Functional machine tracking system with start/stop logging
- Real-time runtime display visible to operators
- Automated data logging for later analysis
- Reduced ambiguity in machine usage tracking

## 🔄 Improvements / Next Steps
- Add multi-machine support
- Develop a web dashboard for data visualization
- Integrate downtime categorization (planned vs unplanned)
- Expand analytics for OEE (Overall Equipment Effectiveness)

## 📸 Visuals
![RFID Setup](images/rfid-machine-tracker.jpg)
![Display Output](images/runtime-display.jpg)

## 💭 Takeaways
LEAN manufacturing is not about adding more systems—it is about removing friction and making the important data visible.

This project reinforced the value of building tools that are:
- Simple to use
- Focused on real problems
- Designed for the people actually doing the work

Even a small, well-targeted system can create meaningful visibility into process inefficiencies.