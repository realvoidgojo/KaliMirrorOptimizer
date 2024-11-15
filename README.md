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
 sudo python3 KaliMirrorOptimizer.py -v -https -src

[+] Starting script execution...
[+] Fetching mirrors list from Kali official repository...
[+] Found 20 valid mirrors.
[+] Found 20 mirrors.
[+] Checking mirror: https://archive-4.kali.org/kali/
[+] Mirror https://archive-4.kali.org/kali/ is valid.
[+] Checking mirror: http://http.kali.org/README?mirrorlist
[+] Mirror http://http.kali.org/README?mirrorlist is valid.
[+] Checking mirror: https://www.kali.org/
[-] Mirror https://www.kali.org/ is invalid or inaccessible (HTTP 404).
[+] Checking mirror: https://ftp.halifax.rwth-aachen.de/kali/
[+] Mirror https://ftp.halifax.rwth-aachen.de/kali/ is valid.
[+] Checking mirror: https://mirrors.ocf.berkeley.edu/kali/
[+] Mirror https://mirrors.ocf.berkeley.edu/kali/ is valid.
[+] Checking mirror: http://mirror.accum.se/mirror/kali.org/kali/
[+] Mirror http://mirror.accum.se/mirror/kali.org/kali/ is valid.
[+] Checking mirror: https://www.kali.org/get-kali/
[-] Mirror https://www.kali.org/get-kali/ is invalid or inaccessible (HTTP 404).
[+] Checking mirror: http://archive-4.kali.org/kali/
[+] Mirror http://archive-4.kali.org/kali/ is valid.
[+] Checking mirror: http://mirrors.ocf.berkeley.edu/kali/
[+] Mirror http://mirrors.ocf.berkeley.edu/kali/ is valid.
[+] Checking mirror: https://ftp.nluug.nl/os/Linux/distr/kali/
[+] Mirror https://ftp.nluug.nl/os/Linux/distr/kali/ is valid.
[+] Checking mirror: https://www.kali.org/blog/
[-] Mirror https://www.kali.org/blog/ is invalid or inaccessible (HTTP 404).
[+] Checking mirror: https://mirror.accum.se/mirror/kali.org/kali/
[+] Mirror https://mirror.accum.se/mirror/kali.org/kali/ is valid.
[+] Checking mirror: https://www.kali.org/docs/
[-] Mirror https://www.kali.org/docs/ is invalid or inaccessible (HTTP 404).
[+] Checking mirror: https://www.kali.org/docs/community/setting-up-a-kali-linux-mirror/
[-] Mirror https://www.kali.org/docs/community/setting-up-a-kali-linux-mirror/ is invalid or inaccessible (HTTP 404).
[+] Checking mirror: https://mirrors.dotsrc.org/kali/
[+] Mirror https://mirrors.dotsrc.org/kali/ is valid.
[+] Checking mirror: http://ftp.nluug.nl/os/Linux/distr/kali/
[+] Mirror http://ftp.nluug.nl/os/Linux/distr/kali/ is valid.
[+] Checking mirror: http://cdimage.kali.org/README?mirrorlist
[+] Mirror http://cdimage.kali.org/README?mirrorlist is valid.
[+] Checking mirror: http://mirrors.dotsrc.org/kali/
[+] Mirror http://mirrors.dotsrc.org/kali/ is valid.
[+] Checking mirror: http://ftp.halifax.rwth-aachen.de/kali/
[+] Mirror http://ftp.halifax.rwth-aachen.de/kali/ is valid.
[+] Checking mirror: https://www.kali.org/images/kali-logo.svg)
[-] Mirror https://www.kali.org/images/kali-logo.svg) is invalid or inaccessible (HTTP 404).
[+] Pinging mirrors to find the best one...
[+] Checking latency for archive-4.kali.org...
[+] Checking latency for http.kali.org...
[+] Checking latency for ftp.halifax.rwth-aachen.de...
[+] Checking latency for mirrors.ocf.berkeley.edu...
[+] Checking latency for mirror.accum.se...
[+] Checking latency for archive-4.kali.org...
[+] Checking latency for mirrors.ocf.berkeley.edu...
[+] Latency for ftp.halifax.rwth-aachen.de: 169.674 ms
[+] Checking latency for ftp.nluug.nl...
[+] Latency for archive-4.kali.org: 149.362 ms
[+] Checking latency for mirror.accum.se...
[+] Latency for archive-4.kali.org: 149.954 ms
[+] Checking latency for mirrors.dotsrc.org...
[+] Latency for mirrors.ocf.berkeley.edu: 293.050 ms
[+] Checking latency for ftp.nluug.nl...
[+] Latency for mirrors.ocf.berkeley.edu: 299.140 ms
[+] Checking latency for cdimage.kali.org...
[+] Latency for ftp.nluug.nl: 157.557 ms
[+] Checking latency for mirrors.dotsrc.org...
[+] Latency for mirrors.dotsrc.org: 253.154 ms
[+] Checking latency for ftp.halifax.rwth-aachen.de...
[+] Latency for ftp.nluug.nl: 157.078 ms
[+] Latency for mirrors.dotsrc.org: 252.340 ms
[+] Latency for ftp.halifax.rwth-aachen.de: 168.723 ms
[+] Latency for mirror.accum.se: 268.519 ms
[+] Latency for mirror.accum.se: 268.377 ms
[-] Failed to ping http.kali.org.
[-] Failed to ping cdimage.kali.org.
[+] Best mirror selected: http://archive-4.kali.org/kali/
[+] Best mirror: http://archive-4.kali.org/kali/
[+] Backing up sources.list...
[+] Backup already exists, skipping backup.
[+] Updating sources.list...
[+] Updating /etc/apt/sources.list with the new mirror: http://archive-4.kali.org/kali/...
[+] /etc/apt/sources.list updated successfully.
[+] Done! Run 'sudo apt clean; sudo apt update' to apply changes.

```

## Features

- **Automatic Mirror Selection:** Finds and selects the mirror with the lowest latency.
- **HTTPS Support:** Enables secure transport for package downloads.
- **Source Packages:** Optional support for source package configuration.
- **Verbose Output:** Detailed logging for better insights during execution.

## Author

Developed/Enhanced by **realvoidgojo**. Contributions are welcome!

Thanks to OG author [IceM4nn](https://github.com/IceM4nn).
