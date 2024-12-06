
# CMS Exploiter & Enumerator

## Overview
**CMS Exploiter & Enumerator** is a Bash script designed to test and exploit vulnerabilities in CMS platforms, specifically WordPress. It features user enumeration, brute force login, vulnerability scanning, and mass attack capabilities.

## Features
- **WordPress Detection**  
  Automatically detects if the target website is powered by WordPress.
- **Login URL Detection**  
  Identifies common login paths for WordPress and other CMS platforms.
- **User Enumeration**  
  Extracts usernames using REST API and author ID enumeration techniques.
- **Brute Force Login**  
  Attempts to log in using a list of usernames and passwords.
- **Mass Attack**  
  Targets multiple websites from a provided list.
- **Color-Coded Alerts**  
  Displays results with animated and color-coded text for better clarity.

## Requirements
- **Bash Shell**  
  Tested on Bash version 4+.
- **Curl**  
  For sending HTTP requests.
- **jq**  
  For parsing JSON responses during user enumeration.

## Installation
1. Clone the repository or download the script:
   ```bash
   git clone https://github.com/your-repo/cms-exploiter.git
   cd cms-exploiter
   ```
2. Ensure the script has execution permissions:
   ```bash
   chmod +x cms_exploiter.sh
   ```
3. Install required tools if missing:
   ```bash
   sudo apt update && sudo apt install curl jq -y
   ```

## Usage
### Single Target Attack
1. **Detect WordPress and Enumerate Users**:
   ```bash
   ./cms_exploiter.sh -u https://example.com --enumerate
   ```
2. **Brute Force Login**:
   ```bash
   ./cms_exploiter.sh -u https://example.com --brute usernames.txt passwords.txt
   ```

### Mass Attack
- **Target Multiple Websites**:
  ```bash
  ./cms_exploiter.sh --mass targets.txt
  ```

### Options
- `-u, --url`  
  Specify the target URL.
- `--mass <targets.txt>`  
  Perform mass attacks on a list of target URLs.
- `--enumerate`  
  Enumerate usernames from the target.
- `--brute <usernames.txt> <passwords.txt>`  
  Perform brute force attacks using username and password files.

### Example Targets File
Each target URL should be on a new line:
```
https://victim1.com
https://victim2.com
https://victim3.com
```

## Outputs
- **Valid Credentials**  
  Saved to `results.txt`.
- **Enumerated Usernames**  
  Appended to `usernames.txt`.

## Disclaimer
This script is for **educational purposes only**. Unauthorized use against websites without explicit permission is illegal. The author is not responsible for any misuse.

## Author
- **k0ur1i**  
  A script crafted for ethical penetration testing and education.  

---

### License
MIT License - Use, modify, and distribute as you see fit.
