### README.md

# CVE-2024-4956 Bulk Scanner

## Disclaimer

> This tool is intended only for educational purposes and for testing in corporate environments. 
> https://twitter.com/nav1n0x/ and https://github.com/ifconfig-me take no responsibility for the code. 
> Use it at your own risk. Do not attack a target you don't have permission to engage with.

This scanner helps security enthusiasts to scan Path Traversal Vulnerability in Nexus Repository targets in bulk. 

The scanner will show the number of targets loaded and the state of the current scanning. The URLs will be listed with three status messages: Timeout, Fail, or Success, based on the results. Ensure that `targets.txt` contains the list of domains and `lfi-payloads.txt` contains the list of payloads. The scanner will display the current URL being tested, updating with each new request, and indicate success or failure respectively. The script as well saves a list of succful urls in the directory as `successful_urls.txt`. It will provide a summary of the number of successful attempts at the end.

![image](https://github.com/ifconfig-me/CVE-2024-4956-Bulk-Scanner/assets/25315805/190f357d-d8b6-490b-bfa3-97a907a8ca53)

## Installation

Ensure you have Python 3.6+ and `pip` installed.

1. Clone the repository:

    * git clone `https://github.com/ifconfig-me/CVE-2024-4956-Bulk-Scanner.git`
    * cd `CVE-2024-4956-Bulk-Scanner`

3. Install the required dependencies:

    `pip install -r requirements.txt`

### Usage Instructions

1. Prepare your `targets.txt` file with the list of domains and `lfi-payloads.txt` with the list of payloads.

2. Run the scanner:

    `python3 lfi-scanner.py -d targets.txt -p lfi-payloads.txt`

## Example Output

```
                   ____        
  ____ _____ ___  _/_   | ____  
 /    \\__  \\  \/ /|   |/    \ 
|   |  \/ __ \\   / |   |   |  \
|___|  (____  /\_/  |___|___|  /
     \/     \/               \/
Total targets to scan: 100
Testing URL 1/100: http://example.com {Success|Fail|Timeout}
...
Task execution completed.
Successful attempts: 5/100
```

## Disclaimer

> This tool is intended only for educational purposes and for testing in corporate environments. 
> https://twitter.com/nav1n0x/ and https://github.com/ifconfig-me take no responsibility for the code. 
> Use it at your own risk. Do not attack a target you don't have permission to engage with.
