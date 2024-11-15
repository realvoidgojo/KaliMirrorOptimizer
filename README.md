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
[+] Fetching mirrors...
[+] Found 136 mirrors.
[+] Finding the best mirror...
[+] Best mirror: https://fonts.googleapis.com/kali
[+] Backing up sources.list...
[+] Backup created at /etc/apt/sources.list.bk
[+] Updating sources.list...
[+] Updated sources.list with the best mirror.
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
