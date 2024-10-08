# Workstatus-Python-Agent

# User Activity Monitor

## Overview
The **User Activity Monitor** is a Python-based desktop application designed to monitor and log user activity in real-time on a Windows system. The application tracks key presses, mouse clicks, active window usage, and captures screenshots of the active window. The logs and screenshots are automatically uploaded to an S3 bucket for secure storage.

### Project Structure

- **user_activity_monitor.py**: Main application file
- **s3_uploader.py**: Handles S3 uploads
- **mfa_config.py**: Manages Multi-Factor Authentication
- **setup.py**: Used for building the executable

## Features
- **Activity Monitoring:** Tracks key presses, mouse clicks, active window usage time.
- **Screenshot Capture:** Captures and displays screenshots of the currently active window.
- **S3 Integration**: Automatically uploads activity logs and screenshots to an Amazon S3 bucket for secure cloud storage.
- **Multi-Factor Authentication (MFA):** Implements MFA for enhanced security.
- **Low Battery Detection:** Suspends tracking when battery is low (for laptops).
- **Console-based Application**: activity logs are now monitored via the console.
- **Real-time Updates**: Activity logs and screenshots are updated every 5 minutes.

## Dependencies
The following libraries are required to run the project:

- **cx_Freeze**: Used for packaging the Python script into an executable.
- **platform**: For identifying the operating system.
- **time**: For managing time-related functions.
- **datetime**: For handling date and time.
- **threading**: For running background tasks concurrently.
- **psutil**: For fetching system and process information.
- **Pillow (PIL)**: For handling image processing, specifically screenshot capture and display.
- **pynput**: For monitoring keyboard and mouse events.
- **pywin32**: For Windows-specific functions such as window title fetching and screenshot capturing.


## Install Dependencies
pip install cx_Freeze boto3 pillow pynput psutil python-dotenv filelock pyotp qrcode

## For Windows-specific functionality:
pip install pywin32

## Environment Setup
Create a `.env` file in the project root directory with the following content:

- S3_BUCKET_NAME=your_bucket_name
- AWS_ACCESS_KEY_ID=your_access_key_id
- AWS_SECRET_ACCESS_KEY=your_secret_access_key

Replace the placeholder values with your actual AWS credentials.

Ensure you have the necessary permissions to write to the specified S3 bucket.

## run the project
python user_activity_monitor.py

## On first run, you'll be prompted to set up Multi-Factor Authentication (MFA).

### Configuration

During startup, you can configure:
- Whether to capture screenshots
- Whether to blur screenshots
- Screenshot capture interval

