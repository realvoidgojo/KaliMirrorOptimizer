# KaliMirrorOptimizer.py

**KaliMirrorOptimizer** is a Python script designed to optimize and change the official Kali Linux repository to the best available mirror. This helps enhance the speed of package updates and downloads for users. Visit the related blog post for more details: [Speed Up Kali Linux Updates](https://www.metahackers.pro/speed-kali-linux-update/).

## Requirements

- **Kali Linux**
- **Python 3**

## Usage

Run the script with elevated privileges to ensure the `sources.list` file can be edited.

### Command-line Help

```bash
# python3 KaliMirrorOptimizer.py -h
usage: KaliMirrorOptimizer.py [-h] [-v] [-https] [-src]

KaliMirrorOptimizer automatically selects the best Kali mirror server and applies the configuration.

optional arguments:
  -h, --help     Show this help message and exit.
  -v, --verbose  Enable verbose output.
  -https         Use HTTPS in apt transport (default: HTTP).
  -src           Enable source packages (default: disabled).
```

```py
# python3 KaliMirrorOptimizer.py -v -https -src

#
# KaliMirrorOptimizer
# Automatically selects the best Kali mirror and applies the configuration.
# https://github.com/realvoidgojo/kali-mirror-optimizer
# https://www.metahackers.pro/speed-kali-linux-update/
#

[-] Checking if 'apt-transport-https' package is installed.
    - apt-transport-https is installed

[+] Retrieving mirror list...
[+] Found a list of mirrors:
    - https://mirror1.example.com/kali
    - https://mirror2.example.com/kali
    - https://mirror3.example.com/kali
    - ...

[+] Testing mirrors for latency. This may take a while.
[+] Latency results:
    - mirror1.example.com: 320.567 ms
    - mirror2.example.com: 280.123 ms
    - mirror3.example.com: 300.789 ms
    - ...

[+] Fastest mirror: https://mirror2.example.com/kali (280.123 ms)
[+] Preparing sources.list...
    - Backing up existing sources.list to /etc/apt/sources.list.bk...
    - Removing older entries...
    - Updating sources.list with the new mirror...
    - Done.

[+] Finished!
    - Run 'apt clean && apt update' to apply the changes.
```

## Features

- **Automatic Mirror Selection:** Finds and selects the mirror with the lowest latency.
- **HTTPS Support:** Enables secure transport for package downloads.
- **Source Packages:** Optional support for source package configuration.
- **Verbose Output:** Detailed logging for better insights during execution.

## Author

Developed/Enhanced by **realvoidgojo**. Contributions are welcome!

Thanks to OG author [IceM4nn](https://github.com/IceM4nn).
