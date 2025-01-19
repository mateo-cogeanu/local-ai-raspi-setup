# Running AI Locally on Raspberry Pi 4B

## Preparation Steps

### Raspberry Pi Imager
1. Download Raspberry Pi Imager from [raspberrypi.com/software](https://www.raspberrypi.com/software/).
2. Install and open Raspberry Pi Imager.
3. **Choose Device**: Select your Raspberry Pi 4B.
4. **Choose OS**: Choose Raspberry Pi OS.
   - *(Tested alternatives: Ubuntu Server 22, Manjaro ARM. Raspberry Pi OS gave the best results.)*
5. **Choose Storage**: Select your SD card.
6. **Customize Settings**:
   - Add hostname, username, and password.
   - Enter your Wi-Fi SSID and password if not using a LAN cable.
7. Enable **SSH** under Services.
8. Save and confirm OS customization settings (**Note**: All data on the SD card will be erased).
9. Insert the SD card into your Raspberry Pi and power it on.
10. Find your Pi’s IP address using your router's interface.
    - *(Example: Using Unifi Network)*
11. Open a terminal and connect via SSH:
    ```bash
    ssh YOURUSERNAME@YOURPISIP
    ```
12. Enter your password to control the Raspberry Pi remotely.

---

## AI Tools Installation

### Chapter 1: Ollama
1. Visit [Ollama](https://ollama.com) and download the Linux version.
2. Run the installation command:
    ```bash
    curl -fsSL https://ollama.com/install.sh | sh
    ```
3. After installation, test with:
    ```bash
    ollama run llama3.2:1b
    ```
   *(Choose smaller models for better performance.)*
4. Test the setup by sending a message:
    ```
    Hello!
    ```
5. Exit Ollama with `/bye`.

---

### Chapter 2: Conda
1. Download Miniforge for Raspberry Pi:
    ```bash
    wget https://github.com/conda-forge/miniforge/releases/download/24.11.2-1/Miniforge3-24.11.2-1-Linux-aarch64.sh
    ```
2. Run the installation script:
    ```bash
    sh Miniforge3-24.11.2-1-Linux-aarch64.sh
    ```
3. Activate Conda:
    ```bash
    eval "$(/home/cogiart/miniforge3/bin/conda shell.bash hook)"
    ```
4. Verify Python version:
    ```bash
    python --version
    ```
    *(At the time of recording: Python 3.12.8)*

---

### Chapter 3: OpenWebUI
1. Stay in Conda base environment and install OpenWebUI:
    ```bash
    pip install open-webui
    ```
2. Start OpenWebUI:
    ```bash
    open-webui serve
    ```
3. Open your browser and visit:
    ```
    YOURRASPISIP:8080
    ```
4. Sign up and test with:
    ```
    Hello!
    ```
5. Customize settings:
   - Go to **Settings > Audio** and set voice to Zarvox (optional).
6. Download additional models:
   - Select a model in OpenWebUI or search for others like `smollm:1.7b` and pull it from Ollama.

---

## Conclusion
This tutorial should help you set up a working local AI environment on a Raspberry Pi. Happy experimenting!
