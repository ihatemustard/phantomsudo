[![IDC License](https://img.shields.io/badge/License-IDC-blue.svg)](LICENSE)

# phantomsudo

A minimalist compatibility shim for FreeBSD that transparently routes `sudo` calls to `doas`.

## Installation
Run this command:
```bash
doas sh -c 'printf "#\!/bin/sh\nexec doas \"\$@\"\n" > /usr/local/bin/sudo && chmod 555 /usr/local/bin/sudo'
