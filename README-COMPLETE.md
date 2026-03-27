# 🔒 Dronat Black - Advanced Penetration Testing & Security Research Environment

[![Docker](https://img.shields.io/badge/Docker-Ready-blue)](https://www.docker.com/)
[![BlackArch](https://img.shields.io/badge/BlackArch-Linux-red)](https://blackarch.org/)
[![Security](https://img.shields.io/badge/Security-Research-green)](https://github.com/Eihabhalaio/Dronat-Black)
[![License](https://img.shields.io/badge/License-Educational-yellow)](LICENSE)
[![Python 3.11+](https://img.shields.io/badge/Python-3.11+-blue)](https://www.python.org/)
[![ML/AI Ready](https://img.shields.io/badge/ML%2FAI-Enabled-brightgreen)](https://www.tensorflow.org/)

> **A comprehensive Docker-based penetration testing environment combining BlackArch Linux with modern ML/AI security research capabilities**

---

## 📋 Table of Contents

- [Overview](#-overview)
- [Key Features](#-key-features)
- [Quick Start](#-quick-start)
- [Installation](#-installation)
- [Usage Guide](#-usage-guide)
- [Security Tools](#-security-tools)
- [ML/AI Security Research](#-mlai-security-research)
- [Service Ports](#-service-ports)
- [Directory Structure](#-directory-structure)
- [Configuration](#-configuration)
- [Testing](#-testing)
- [Troubleshooting](#-troubleshooting)
- [Security & Ethics](#-security--ethics)
- [Contributing](#-contributing)
- [License](#-license)

---

## 🎯 Overview

**Dronat Black** is a state-of-the-art penetration testing and security research environment built on BlackArch Linux. It provides security professionals, researchers, and ethical hackers with a complete toolkit for:

- **Network Penetration Testing** - Comprehensive network scanning and exploitation tools
- **Web Application Security** - Full suite of web vulnerability assessment tools
- **Password Security** - Advanced password cracking and recovery tools
- **Wireless Security** - WiFi and wireless protocol testing capabilities
- **Exploit Development** - Binary analysis and exploit creation tools
- **ML/AI Security Research** - Machine learning for security applications
- **Adversarial ML** - Testing ML model robustness against attacks

### ⚠️ Ethical Use Notice

This tool is designed **exclusively** for authorized security testing, educational purposes, and legitimate security research. Users must:

- Only test systems they own or have explicit written permission to test
- Comply with all applicable local, state, federal, and international laws
- Follow responsible vulnerability disclosure practices
- Respect privacy and data protection regulations

**Unauthorized access to computer systems is illegal and unethical.**

---

## ✨ Key Features

### 🛡️ Comprehensive Security Toolkit

#### Network Reconnaissance
- **nmap** - Network discovery and security auditing
- **masscan** - High-speed port scanner
- **gobuster** - Directory/file brute-forcer
- **dirb** - Web content scanner
- **nikto** - Web server vulnerability scanner
- **recon-ng** - Web reconnaissance framework
- **theHarvester** - Email and subdomain enumeration

#### Web Application Security
- **burpsuite** - Web application security testing platform
- **sqlmap** - Automatic SQL injection tool
- **OWASP ZAP** - Web application security scanner
- **wfuzz** - Web application fuzzer
- **dirbuster** - Directory brute-force scanner

#### Password Cracking
- **hashcat** - Advanced password recovery tool
- **john** (John the Ripper) - Password cracker
- **hydra** - Network login cracker
- **medusa** - Parallel network login brute-forcer
- **crackmapexec** - Post-exploitation tool

#### Wireless Security
- **aircrack-ng** - WiFi security auditing suite
- **kismet** - Wireless network detector
- **wifite** - Automated wireless attack tool
- **reaver** - WPS attack tool

#### Exploit Development
- **metasploit** - Penetration testing framework
- **gdb** - GNU debugger
- **radare2** - Reverse engineering framework
- **ropper** - ROP gadget finder
- **pwntools** - Exploit development library

#### Binary Analysis
- **capstone** - Disassembly framework
- **keystone** - Assembler framework
- **unicorn** - CPU emulator framework
- **angr** - Binary analysis platform
- **ghidra** - Software reverse engineering suite

### 🧠 ML/AI Security Research

#### Machine Learning Frameworks
- **TensorFlow 2.16+** - Open-source ML platform
- **PyTorch 2.0+** - Deep learning framework
- **scikit-learn** - ML algorithms library
- **Keras** - Neural network API

#### Security Applications
- **Adversarial Example Generation** - Test ML model robustness
- **Network Traffic Analysis** - Anomaly detection with ML
- **Malware Classification** - AI-powered malware detection
- **Phishing Detection** - ML-based phishing identification
- **Intrusion Detection** - Intelligent threat detection

#### Data Science Stack
- **JupyterLab** - Interactive development environment
- **pandas** - Data manipulation library
- **NumPy** - Numerical computing library
- **Matplotlib/Seaborn** - Data visualization
- **Polars** - Fast DataFrame library

### 🔧 Development Environment

#### Code Editors
- **Neovim** - Enhanced security-focused IDE configuration
- **VSCode support** - Remote development ready

#### Runtime Environments
- **Anaconda 2024.10** - Complete Python data science stack
- **Python 3.11+** - Latest stable Python
- **Node.js 22 LTS** - JavaScript runtime
- **npm/npx** - Node package manager

#### Automation & Workflow
- **n8n** - Workflow automation for security tasks
- **Shellngn Pro** - Web-based terminal access
- **tmux** - Terminal multiplexer

---

## 🚀 Quick Start

### Prerequisites

Before you begin, ensure you have:

- **Docker** (version 20.10 or higher)
- **Docker Compose** (version 2.0 or higher)
- **8GB RAM minimum** (16GB recommended)
- **20GB free disk space**
- **Linux, macOS, or Windows with WSL2**

### Method 1: Quick Start Script (Recommended)

```bash
# Clone the repository
git clone https://github.com/Eihabhalaio/Dronat-Black.git
cd Dronat-Black

# Make scripts executable
chmod +x start-blackarch.sh

# Build, test, and run everything automatically
./start-blackarch.sh all
```

This script will:
1. Check Docker availability
2. Build the BlackArch container
3. Run comprehensive tests
4. Start the interactive environment

### Method 2: Manual Docker Build

```bash
# Clone the repository
git clone https://github.com/Eihabhalaio/Dronat-Black.git
cd Dronat-Black

# Build the container
docker build -f Dockerfile.blackarch -t dronat-blackarch:latest .

# Run with full capabilities
docker run -it --rm \
  --name dronat-blackarch \
  --privileged \
  --network host \
  -v $(pwd)/workspace:/home/devuser/workspace \
  -v $(pwd)/reports:/home/devuser/reports \
  dronat-blackarch:latest
```

### Method 3: Docker Compose (Full Orchestration)

```bash
# Start all services
docker-compose -f docker-compose-blackarch.yml up -d

# Access the container
docker exec -it dronat-blackarch-dev bash

# Stop all services
docker-compose -f docker-compose-blackarch.yml down
```

---

## 📦 Installation

### Step-by-Step Installation Guide

#### 1. Clone the Repository

```bash
git clone https://github.com/Eihabhalaio/Dronat-Black.git
cd Dronat-Black
```

#### 2. Verify Docker Installation

```bash
docker --version
docker-compose --version
docker info
```

#### 3. Build the Image

```bash
# Standard build
docker build -f Dockerfile.blackarch -t dronat-blackarch:latest .

# Build with no cache (fresh build)
docker build --no-cache -f Dockerfile.blackarch -t dronat-blackarch:latest .
```

#### 4. Configure Environment (Optional)

Create a `.env` file for custom configurations:

```bash
# Custom database password
POSTGRES_PASSWORD=your_secure_password

# Display variable for GUI apps
DISPLAY=:0
```

#### 5. Create Workspace Directories

```bash
mkdir -p workspace reports wordlists exploits configs
```

---

## 🎛️ Usage Guide

### Interactive Menu System

When you start the container, you'll be presented with an interactive menu:

```
╔═══════════════════════════════════════════════════╗
║     DRONAT BLACKARCH SECURITY ENVIRONMENT         ║
╠═══════════════════════════════════════════════════╣
║  1. 📝 Neovim Security IDE                        ║
║  2. 🔄 n8n Workflow Editor                        ║
║  3. 💻 Bash Shell                                 ║
║  4. 🔍 Network Reconnaissance                     ║
║  5. 🌐 Web Security Testing                       ║
║  6. 🔓 Password Cracking                          ║
║  7. 📡 Wireless Security                          ║
║  8. 🕷️ Exploit Development                        ║
║  9. 🧠 ML/AI Security Research                    ║
║ 10. 🌐 Shellngn Pro                               ║
║ 11. 🔧 System Tools                               ║
║ 12. 📚 Help & Documentation                       ║
╚═══════════════════════════════════════════════════╝
```

### Common Workflows

#### Network Penetration Testing

```bash
# 1. Network Discovery
nmap -sn 192.168.1.0/24

# 2. Port Scanning
nmap -sS -sV -O -A target_ip

# 3. Service Enumeration
gobuster dir -u http://target -w /usr/share/wordlists/SecLists/Discovery/Web-Content/common.txt

# 4. Vulnerability Assessment
nikto -h http://target
```

#### Web Application Testing

```bash
# Directory Bruteforcing
gobuster dir -u http://target \
  -w /usr/share/wordlists/SecLists/Discovery/Web-Content/directory-list-2.3-medium.txt \
  -x php,txt,html

# SQL Injection Testing
sqlmap -u "http://target/page.php?id=1" \
  --batch \
  --random-agent \
  --dbs

# XSS Testing
xsstrike -u "http://target/search?q=test"
```

#### Password Cracking

```bash
# Hashcat (GPU-accelerated)
hashcat -m 0 -a 0 hashes.txt /usr/share/wordlists/rockyou.txt

# John the Ripper
john --wordlist=/usr/share/wordlists/rockyou.txt hashes.txt

# Hydra (Network Services)
hydra -l admin -P passwords.txt ssh://target
hydra -L users.txt -P passwords.txt ftp://target
```

#### Wireless Security

```bash
# Monitor Mode
airmon-ng start wlan0

# Capture Handshake
airodump-ng wlan0mon --bssid TARGET_BSSID -c 6 -c capture.pcap

# Crack WPA/WPA2
aircrack-ng -w rockyou.txt capture.pcap
```

---

## 🧠 ML/AI Security Research

### Adversarial Machine Learning

```python
import tensorflow as tf
import numpy as np

def create_adversarial_example(model, input_image, target_label, epsilon=0.1):
    """
    Generate adversarial examples using Fast Gradient Sign Method (FGSM)
    """
    input_image = tf.convert_to_tensor(input_image, dtype=tf.float32)
    
    with tf.GradientTape() as tape:
        tape.watch(input_image)
        prediction = model(input_image, training=False)
        loss = tf.keras.losses.categorical_crossentropy(target_label, prediction)
    
    gradient = tape.gradient(loss, input_image)
    signed_grad = tf.sign(gradient)
    
    adversarial_image = input_image + epsilon * signed_grad
    adversarial_image = tf.clip_by_value(adversarial_image, 0, 1)
    
    return adversarial_image

# Example usage
adversarial_img = create_adversarial_example(model, test_image, target_label)
```

### Network Traffic Anomaly Detection

```python
from scapy.all import rdpcap
import pandas as pd
from sklearn.ensemble import IsolationForest

def analyze_network_traffic(pcap_file):
    """
    Detect anomalies in network traffic using ML
    """
    # Load packets
    packets = rdpcap(pcap_file)
    
    # Extract features
    features = []
    for packet in packets:
        feature_vector = {
            'length': len(packet),
            'time': float(packet.time),
        }
        features.append(feature_vector)
    
    df = pd.DataFrame(features)
    
    # Train anomaly detection model
    model = IsolationForest(contamination=0.1, random_state=42)
    anomalies = model.fit_predict(df)
    
    # Return anomalous packets
    anomaly_indices = np.where(anomalies == -1)[0]
    return [packets[i] for i in anomaly_indices]
```

### Malware Classification

```python
import pefile
import numpy as np
from sklearn.ensemble import RandomForestClassifier

def extract_pe_features(file_path):
    """
    Extract features from PE files for malware classification
    """
    pe = pefile.PE(file_path)
    
    features = {
        'entry_point': pe.OPTIONAL_HEADER.AddressOfEntryPoint,
        'num_sections': len(pe.sections),
        'image_size': pe.OPTIONAL_HEADER.SizeOfImage,
        'dll_characteristics': pe.OPTIONAL_HEADER.DllCharacteristics,
    }
    
    return np.array(list(features.values()))

# Train classifier
X_train = np.array([extract_pe_features(f) for f in benign_files])
y_train = np.zeros(len(X_train))

X_test = np.array([extract_pe_features(f) for f in malware_files])
y_test = np.ones(len(X_test))

clf = RandomForestClassifier(n_estimators=100)
clf.fit(np.vstack([X_train, X_test]), np.hstack([y_train, y_test]))
```

---

## 🌐 Service Ports

| Port  | Service                      | Description                              |
|-------|------------------------------|------------------------------------------|
| 8888  | JupyterLab                   | Interactive ML/AI development            |
| 5678  | n8n                          | Workflow automation platform             |
| 8080  | Shellngn Pro                 | Web-based terminal access                |
| 6006  | TensorBoard                  | ML model visualization                   |
| 7860  | Gradio                       | ML model interface builder               |
| 8501  | Streamlit                    | Security dashboard framework             |
| 5000  | MLflow                       | ML experiment tracking                   |
| 3000  | Additional Web Service       | Custom web applications                  |
| 4444  | Metasploit RPC               | Penetration testing framework            |
| 8000  | HTTP Server                  | Simple HTTP server                       |
| 5432  | PostgreSQL                   | Database (optional profile)              |
| 6379  | Redis                        | Cache/session storage (optional profile) |

Access services via `http://localhost:<PORT>` in your browser.

---

## 🗂️ Directory Structure

```
Dronat-Black/
├── Dockerfile.blackarch          # Main Docker image definition
├── docker-compose-blackarch.yml  # Multi-container orchestration
├── requirements-blackarch.txt    # Python dependencies
├── install_packages_blackarch.py # Package installation script
├── start-blackarch.sh           # Quick start automation script
├── menu-blackarch.sh            # Interactive menu system
├── test_blackarch_environment.sh # Comprehensive test suite
├── nvim/                         # Neovim configuration
│   ├── init.lua
│   ├── plugins/
│   └── lua/
├── workspace/                    # Persistent workspace (mounted volume)
├── reports/                      # Security assessment reports
├── wordlists/                    # Custom wordlists
├── exploits/                     # Custom exploit code
└── configs/                      # Configuration files
```

Inside the container:

```
/home/devuser/
├── pentest/              # Penetration testing workspace
├── wordlists/            # Custom wordlists
├── exploits/             # Exploit development
├── reports/              # Security reports
├── workspace/            # General workspace
├── anaconda3/            # Python environment
└── .config/nvim/         # Neovim configuration
```

---

## ⚙️ Configuration

### Docker Configuration

Edit `docker-compose-blackarch.yml` to customize:

```yaml
services:
  dronat-blackarch:
    # Change resource limits
    deploy:
      resources:
        limits:
          memory: 16G    # Increase for heavy ML workloads
          cpus: '8.0'
```

### Neovim Configuration

The container includes a pre-configured Neovim setup with:

- **Syntax highlighting** for multiple languages
- **Code completion** with LSP support
- **Git integration** with Gitsigns
- **File tree** with NeoTree
- **Terminal integration**
- **Security-focused plugins**

Customize by editing files in `~/.config/nvim/` inside the container.

### Anaconda Environment

```bash
# Activate base environment
source ~/anaconda3/bin/activate

# Create custom environment
conda create -n security python=3.11
conda activate security

# Install packages
conda install scikit-learn pandas numpy
```

---

## 🧪 Testing

### Automated Test Suite

```bash
# Run comprehensive tests
./test_blackarch_environment.sh

# Quick test via start script
./start-blackarch.sh test
```

### Manual Testing

```bash
# Test basic container functionality
docker run --rm dronat-blackarch:latest python3 --version

# Test security tools
docker run --rm dronat-blackarch:latest nmap --version

# Test Python libraries
docker run --rm dronat-blackarch:latest python3 -c "import scapy; print('Scapy OK')"
```

---

## 🔧 Troubleshooting

### Common Issues

#### 1. Network Tools Require Privileges

**Problem:** nmap, aircrack-ng, or other network tools fail

**Solution:**
```bash
docker run --privileged --network host dronat-blackarch:latest
```

#### 2. GUI Applications Not Displaying

**Problem:** BurpSuite or other GUI tools don't show

**Solution:**
```bash
# On Linux
xhost +local:docker
docker run -e DISPLAY=$DISPLAY -v /tmp/.X11-unix:/tmp/.X11-unix dronat-blackarch

# On Windows with WSL2
export DISPLAY=$(grep nameserver /etc/resolv.conf | awk '{print $2}'):0
```

#### 3. Out of Disk Space

**Problem:** Container runs out of space during package installation

**Solution:**
```bash
# Clean Docker cache
docker system prune -a

# Increase Docker disk limit (Docker Desktop)
# Settings -> Resources -> Disk Image Size
```

#### 4. Memory Issues

**Problem:** Container crashes due to insufficient RAM

**Solution:**
```bash
# Limit container memory
docker run -m 8g dronat-blackarch:latest

# Close other applications
# Add swap space (Linux)
sudo fallocate -l 4G /swapfile
sudo chmod 600 /swapfile
sudo mkswap /swapfile
sudo swapon /swapfile
```

#### 5. Package Installation Failures

**Problem:** Some packages fail to install

**Solution:**
```bash
# Update package database inside container
docker exec -it dronat-blackarch-dev bash
sudo pacman -Sy

# Retry installation
sudo pacman -S package-name

# Check logs
cat /tmp/install_log.txt
```

### Getting Help

- **Built-in Help:** Option 12 in the interactive menu
- **Tool Documentation:** `man toolname` or `toolname --help`
- **GitHub Issues:** Report bugs on the repository
- **Community:** Security research forums and Discord channels

---

## 🔒 Security & Ethics

### ⚠️ IMPORTANT LEGAL NOTICE

This tool contains powerful security testing capabilities. **Users are legally and ethically responsible** for their actions.

#### You MUST:

✅ **Only test systems you own** or have **explicit written permission** to test  
✅ **Follow responsible disclosure practices** for discovered vulnerabilities  
✅ **Comply with all applicable laws** including CFAA, GDPR, and local regulations  
✅ **Respect privacy** and data protection rights  
✅ **Document all testing activities** for accountability  
✅ **Use isolated lab environments** whenever possible  

#### You MUST NOT:

❌ **Access systems without authorization** (this is illegal)  
❌ **Conduct attacks on production systems** without explicit permission  
❌ **Share or distribute discovered vulnerabilities** irresponsibly  
❌ **Use for malicious purposes** including data theft, disruption, or harm  
❌ **Violate terms of service** of any online platforms  

### Legal Consequences

Unauthorized computer access may result in:

- **Criminal charges** under laws like the Computer Fraud and Abuse Act (CFAA)
- **Civil lawsuits** for damages
- **Fines and imprisonment**
- **Professional consequences**

### Best Practices

1. **Set up a legal lab environment** using virtual machines
2. **Obtain written authorization** before any external testing
3. **Define clear scope** and rules of engagement
4. **Maintain detailed logs** of all activities
5. **Follow industry standards** like PTES, OWASP, NIST
6. **Continuously educate yourself** on legal and ethical considerations

---

## 🤝 Contributing

We welcome contributions from the security community!

### How to Contribute

1. **Fork the repository**
2. **Create a feature branch** (`git checkout -b feature/amazing-feature`)
3. **Make your changes** with thorough testing
4. **Commit your changes** (`git commit -m 'Add amazing feature'`)
5. **Push to the branch** (`git push origin feature/amazing-feature`)
6. **Open a Pull Request** with detailed description

### Contribution Guidelines

- **Test thoroughly** in isolated environments
- **Document new tools** and features
- **Follow security-first** development practices
- **Respect ethical guidelines** in all contributions
- **Include examples** for new capabilities

### Areas for Contribution

- New security tool integrations
- ML/AI security research examples
- Documentation improvements
- Bug fixes and optimizations
- Workflow automation templates
- Educational materials

---

## 📄 License

This project is provided for **educational and authorized security testing purposes only**.

By using this software, you agree to:
- Use it only for lawful and ethical purposes
- Obtain proper authorization before testing
- Take full responsibility for your actions
- Comply with all applicable laws and regulations

The authors and contributors are **not liable** for any misuse or damages resulting from the use of this tool.

---

## 🙏 Acknowledgments

We gratefully acknowledge:

- **BlackArch Linux** team for the security-focused distribution
- **Open source security community** for tool development
- **OWASP Foundation** for web security resources
- **Offensive Security** for penetration testing methodologies
- **All contributors** who make this project possible

---

## 📞 Support & Resources

### Documentation

- [Complete User Guide](README-BLACKARCH.md)
- [Security Tools Reference](README-BLACKARCH.md#security-tools-reference)
- [Quick Start Guide](start-blackarch.sh)
- [Testing Guide](test_blackarch_environment.sh)

### External Resources

- [BlackArch Documentation](https://blackarch.org/)
- [OWASP Testing Guide](https://owasp.org/www-project-web-security-testing-guide/)
- [Penetration Testing Execution Standard](http://www.pentest-standard.org/)
- [HackTricks](https://book.hacktricks.xyz/)

### Contact

- **GitHub Issues:** For bug reports and feature requests
- **Discussions:** For questions and community support

---

## 🔗 Related Projects

- **DEBT (Development Environment for Business Trading)** - Comprehensive trading platform
- **OpenBB Terminal** - Financial research terminal
- **n8n** - Workflow automation platform

---

**🔒 Remember: With great power comes great responsibility. Always use these tools ethically and legally.**

**⭐ If this project helps your security research, please consider starring the repository!**

---

*Last Updated: March 2026*  
*Version: 2.0.0*  
*Maintained by: @Eihabhalaio*
