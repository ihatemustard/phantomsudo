# phantomsudo

A minimalist compatibility shim for FreeBSD that transparently routes `sudo` calls to `doas`.

## Installation
Run this command. It is escaped specifically for `tcsh` compatibility:
```bash
doas sh -c 'printf "#\!/bin/sh\nexec doas \"\$@\"\n" > /usr/local/bin/sudo && chmod 555 /usr/local/bin/sudo'
