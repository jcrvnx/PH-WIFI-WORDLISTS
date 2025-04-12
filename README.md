# 🇵🇭 Philippine Default Password Wordlists 📶

[![Kali Linux](https://img.shields.io/badge/OS-Kali%20Linux-blueviolet?style=for-the-badge&logo=kali-linux)](https://www.kali.org/) [![Linux](https://img.shields.io/badge/OS-Linux%20Distros-yellow?style=for-the-badge&logo=linux)](https://www.linux.org/) [![Wifite](https://img.shields.io/badge/Tool-Wifite-red?style=for-the-badge)](https://github.com/derv82/wifite2) [![Wordlist Stars](https://img.shields.io/github/stars/jcrvnx/PH-WIFI-WORDLISTS.svg?style=social&label=Star%20Wordlist%20Repo)](https://github.com/jcrvnx/PH-WIFI-WORDLISTS)

**Visualize Penetration. Automate Access.**

---

<p align="center">
  <img src="https://media.giphy.com/media/v1.Y2lkPTc5MGI3NjExZHB6ZHN1bzU4NXM2dDBqNnRsaG9ydXg1MW91NW1jN2I5OGI1MzZ1ZyZlcD12MV9naWZzX3NlYXJjaCZjdD1n/MM0Jrc8BHKx3y/giphy.gif" alt="Hacking Animation" width="300"/>
  <br/>
  <i>Scanning... Targeting... Exploiting...</i>
</p>

---

## ⚫️ Overview: Black Hat Operations

This toolkit integrates the powerful `wifite` automated wireless auditor with a curated wordlist specifically targeting default router passwords commonly found in the Philippines (`jcrvnx/PH-WIFI-WORDLISTS`). It's designed for Kali Linux but adaptable to any Linux distribution with the right hardware and dependencies.

We provide the framework; you execute the breach. This README includes setup instructions, usage patterns, and essential documentation for leveraging these tools effectively.

---

## ✨ Features

*   **🎯 Targeted Attack:** Utilizes a massive wordlist focused on PH ISP default credentials.
*   **⚙️ Automated Auditing:** Leverages `wifite` for scanning, target selection, and attack execution (WPS, WPA/WPA2 Handshake Capture & Cracking).
*   **🐧 Broad Linux Compatibility:** Optimized for Kali Linux, but functional on Ubuntu, Debian, Arch, and other distros (dependencies required).
*   **📚 Clear Documentation:** Step-by-step guidance for setup and execution.
*   **💰 Support the Cause:** Donation options available to fuel further development and tool acquisition.

---

## 🛠️ Setup & Installation (Kali Linux Focus)

**Mandatory on any Linux Distro:**

1.  **Update & Upgrade System:** Keep your attack platform sharp.
    ```bash
    sudo apt update && sudo apt upgrade -y
    # Or use your distro's package manager (e.g., pacman, dnf)
    ```

2.  **Install Dependencies:** `wifite` and `git` are essential.
    ```bash
    sudo apt install wifite git -y
    # Ensure aircrack-ng suite, hashcat/john are also installed (usually come with Kali/wifite)
    ```

3.  **Wireless Adapter Check:** Your WiFi card MUST support **Monitor Mode** and **Packet Injection**. Verify using:
    ```bash
    sudo airmon-ng check kill # Kill interfering processes
    sudo airmon-ng start <your-wireless-interface> # e.g., wlan0
    # Look for "(monitor mode enabled)"
    # If issues arise, consult Kali documentation for driver installation.
    ```

4.  **Clone the PH Wordlist Repository:** Get the ammunition.
    ```bash
    git clone https://github.com/jcrvnx/PH-WIFI-WORDLISTS.git
    cd PH-WIFI-WORDLISTS
    echo "Wordlists downloaded to $(pwd)"
    ```
    *Note the directory where the wordlists are stored. You'll need this path.*

---

## 🚀 Execution: Running Wifite with PH Wordlists

1.  **Navigate (Optional):** You don't *need* to be in the wordlist directory to run `wifite`, but know the *full path* to the wordlist file you want to use.

2.  **Launch Wifite with the Dictionary:**
    *   Identify the *specific* wordlist file you want to use within the cloned `PH-WIFI-WORDLISTS` directory (e.g., `Passwords/PLDT-WIFI-PASSWORDS.txt`, `Passwords/Converge-WIFI-PASSWORDS.txt`, etc.).
    *   Run `wifite` with `sudo` (required for network operations) and point it to your chosen dictionary using the `--dict` flag.

    ```bash
    # Example using the PLDT common password list:
    # Replace '/path/to/PH-WIFI-WORDLISTS/' with the actual path where you cloned the repo.
    sudo wifite --dict /path/to/PH-WIFI-WORDLISTS/Passwords/PLDT-WIFI-PASSWORDS.txt

    # Example using a different list:
    # sudo wifite --dict /path/to/PH-WIFI-WORDLISTS/Passwords/SKY-WIFI-PASSWORDS.txt

    # To try ALL wordlists in sequence (less efficient, wifite might not support multiple dicts easily this way, better to run separately or combine lists):
    # Consider combining relevant lists into one large file first if needed.
    # cat /path/to/PH-WIFI-WORDLISTS/Passwords/*.txt > /path/to/combined_ph_list.txt
    # sudo wifite --dict /path/to/combined_ph_list.txt
    ```

3.  **Follow Wifite Prompts:**
    *   `wifite` will scan for networks.
    *   Press `Ctrl+C` when you see your target(s).
    *   Select the target network number(s).
    *   `wifite` will attempt various attacks (WPS PIN, WPA Handshake Capture).
    *   If a WPA handshake is captured, `wifite` will automatically use the specified dictionary (`--dict`) to attempt cracking the password.

---

## 🌐 Navigation & Documentation Sections

*   [Overview](#️-overview-black-hat-operations)
*   [Features](#-features)
*   [Setup & Installation](#️-setup--installation-kali-linux-focus)
*   [Execution Guide](#-execution-running-wifite-with-ph-wordlists)
*   [Support & Donations](#-support-the-operation)
*   [Disclaimer](#️-legal--ethical-warning-️)

---

## 💰 Support the Operation

Fuel the underground. Your contributions help acquire better gear, maintain tools, and fund darker projects. Every bit counts towards expanding our capabilities.

[![Donate via PayPal](https://img.shields.io/badge/Donate-PayPal-blue.svg?style=for-the-badge&logo=paypal)](YOUR_PAYPAL_LINK_HERE) <!-- Replace YOUR_PAYPAL_LINK_HERE -->
[![Donate via Ko-fi](https://img.shields.io/badge/Donate-Ko--fi-red.svg?style=for-the-badge&logo=ko-fi)](YOUR_KOFI_LINK_HERE) <!-- Replace YOUR_KOFI_LINK_HERE -->
[![Donate via BTC](https://img.shields.io/badge/Donate-Bitcoin-orange.svg?style=for-the-badge&logo=bitcoin)](YOUR_BTC_ADDRESS_HERE) <!-- Replace YOUR_BTC_ADDRESS_HERE -->

---

## ⚠️ Legal & Ethical Warning ⚠️

**OPERATION SECURITY NOTICE:**

*   **Unauthorized Access is ILLEGAL:** Using this tool and wordlist against networks you do **NOT** own or have **explicit written permission** to test is a **CRIMINAL OFFENSE** in the Philippines (RA 10175 Cybercrime Prevention Act) and most other jurisdictions.
*   **Educational Purposes ONLY:** This toolkit is provided strictly for **educational learning** and for **auditing your OWN network security** or networks where you have **obtained explicit consent**.
*   **NO RESPONSIBILITY:** The creators and contributors of this guide, `wifite`, and the `PH-WIFI-WORDLISTS` repository are **NOT RESPONSIBLE** for any illegal activities, misuse, or damage caused by these tools.
*   **USE AT YOUR OWN EXTREME RISK:** You are solely responsible for your actions. Understand the laws and ethical implications before proceeding. **Think before you type.**

**Crack Wisely. Hack Wisely. Stay Anonymous.**
