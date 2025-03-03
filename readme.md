# ChipWhisperer Setup Guide

## Windows Setup

### Prerequisites
1. Open Command Prompt
2. Install WSL (Windows Subsystem for Linux):
   ```
   wsl --install
   ```
   *Skip this step if WSL is already installed*
3. Install USBIPD:
   ```
   winget install usbipd
   ```
4. Download and install Docker Desktop from the official website
5. Reboot your computer after installation

### Running ChipWhisperer Docker Image
1. Open Docker Desktop
2. Run the ChipWhisperer docker image by navigating to the Docker terminal in the bottom right of the app
3. Enter the following command:
   ```
   docker run -it --device=/dev/bus/usb:/dev/bus/usb --privileged -p 8888:8888 saravan29/hhh-notebooks4:latest
   ```
4. After the docker image downloads and runs, open your browser
5. Navigate to `localhost:8888`
6. Enter the password: `bob`

### Connecting Hardware (Windows)
To connect your ChipWhisperer hardware to the Docker container via WSL:

1. List available USB devices:
   ```
   usbipd list
   ```
2. Bind ChipWhisperer to USBIPD:
   ```
   usbipd bind --busid <BUS_ID of chipwhispers>
   ```
3. Attach ChipWhisperer to WSL:
   ```
   usbipd attach --wsl --busid <BUS_ID of chipwhispers>
   ```
4. Once these steps are completed, you can proceed with hardware operations

## Linux Setup

1. Install Docker from the official website
   * Follow the installation steps provided in the documentation
   * Complete the post-installation steps as mentioned in the official website for Linux
2. Run the ChipWhisperer Docker image with the following command:
   ```
   docker run -it --device=/dev/bus/usb:/dev/bus/usb --privileged -p 8888:8888 saravan29/hhh-notebooks4:latest
   ```
3. Setup is now complete for both simulation and hardware use
