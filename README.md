# DNSLeak - DNS Leak Testing Tool for Termux

A Go application to test for DNS leaks. This tool checks if your DNS queries are being routed through your ISP or if they're securely routed through your VPN or DNS service.

This repository includes a setup script to easily install DNSLeak in **Termux** on Android.

---

## Features

* Checks for DNS leaks.
* Works inside Termux on Android.
* Provides a ready-to-use global command `dnsleak` once installed.

---

## Requirements

* Termux app on Android.
* Internet connection for downloading packages and the source code.
* Git and Go (installed automatically by the setup script).

---

## Installation

1. **Open Termux**.

2. **Download the setup script** (or copy it manually to a file):

```sh
cd ~
nano setup_dnsleak.sh
# Paste the setup script content here, save and exit (Ctrl+O, Enter, Ctrl+X)
```

3. **Make the script executable**:

```sh
chmod +x setup_dnsleak.sh
```

4. **Run the script**:

```sh
./setup_dnsleak.sh
```

The script will:

* Install necessary packages (`git`, `golang`, `which`).
* Set up Go environment variables (`GOPATH`, `GOBIN`).
* Clone the DNSLeak repository.
* Build the DNSLeak binary into `$GOBIN`.
* Create a symlink in Termux’s `$PREFIX/bin` so `dnsleak` is available globally.
* Verify the installation.

---

## Usage

After the script finishes:

1. **Ensure your environment is loaded** (optional, usually needed for new Termux sessions):

```sh
. ~/.profile
```

2. **Run DNSLeak**:

```sh
dnsleak
```

---

## Notes

* The `dnsleak` command will now be available globally in Termux.
* If you encounter `command not found`, make sure `$GOBIN` or the symlink in `$PREFIX/bin` is in your PATH:

```sh
echo $PATH
ls -l $HOME/go/bin/dnsleak
ls -l $PREFIX/bin/dnsleak
```

* This setup only works inside Termux. Running `dnsleak` system-wide on Android outside Termux would require root privileges, which is not recommended.

---

## Repository

[https://github.com/code3-dev/dnsleak](https://github.com/code3-dev/dnsleak)