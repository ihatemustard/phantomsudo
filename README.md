# phantomsudo 👻

A minimalist compatibility shim for FreeBSD that transparently routes `sudo` calls to `doas`.

## Why?
Maintains muscle memory and script compatibility on FreeBSD without installing the heavy `security/sudo` port.

## Installation
Run this one-liner to install:
```bash
doas sh -c 'printf "#!/bin/sh\nexec doas \"\$@\"\n" > /usr/local/bin/sudo && chmod 555 /usr/local/bin/sudo'
