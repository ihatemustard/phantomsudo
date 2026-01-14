# phantomsudo

A minimalist compatibility shim for FreeBSD that transparently routes `sudo` calls to `doas` using `/bin/sh`.

## Why?
Maintains muscle memory and script compatibility on FreeBSD without the `security/sudo` package. *It uses explicit `sh` execution to avoid "Illegal variable name" errors common in `tcsh`.*

## Installation
Run this one-liner to install:
```bash
doas sh -c 'printf "#!/bin/sh\nexec doas \"\$@\"\n" > /usr/local/bin/sudo' && doas chmod 555 /usr/local/bin/sudo
