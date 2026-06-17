# RCSIM RPi5 Deployment Tool

## Overview
This application facilitates the deployment of the RCSIM software stack to a Raspberry Pi 5. It handles SSH connections, project archiving, file uploads, and remote configuration including Docker container management, Tailscale setup, and hardware setup. The interface is served via a Flask web server, allowing control from any modern browser.

## Key Features
*   **Automated Deployment:** Archives the project, uploads it to RPi, builds Docker images, and starts services.
*   **Hardware Configuration:** Configure IMU, GPS, LiDAR, and Camera settings via Web GUI.
*   **Network Setup:** Integrates with Tailscale for secure remote access.
*   **Diagnostics:** Built-in tools to check system status, logs, and service health.
*   **Modern Web UI:** Easy to use, cross-platform interface served locally.
*   **Bilingual Interface:** Supports English and Polish.

## File Structure
*   `RCsimRPi5deploymentapp.py`: Main entry point / launcher.
*   `web_server.py`: Flask application handling the Web UI and API.
*   `core/deployment_logic.py`: Core logic for SSH, SFTP, and remote commands.
*   `core/config_manager.py`: Manages configuration profiles and settings.
*   `core/service_monitor.py`: Background threads for remote service status tracking.
*   `ui/ui_components.py`: Tkinter-based legacy UI components if fallback is needed.
*   `web/`: Web UI static templates and frontend assets.

## Requirements
*   Python 3.8+
*   Libraries: `flask`, `paramiko`, `requests`
*   Raspberry Pi 5 with Hailo-8L (for AI features)

## Usage
1.  Run `python RCsimRPi5deploymentapp.py`.
2.  Open your browser and navigate to the address shown in the terminal (usually `http://127.0.0.1:5000`).
3.  Configure Connection details (IP, User, Password/Key).
4.  Select Project Source Directory.
5.  Configure Hardware and click "Start Deployment".
