# phantomsudo 👻

A minimalist compatibility shim for FreeBSD that transparently routes `sudo` calls to `doas`.

## Why?
Avoids "Illegal variable name" and "ls: No match" errors common when trying to alias sudo in FreeBSD's default `tcsh`.

## Installation
Copy and paste this block exactly. It uses a heredoc to safely handle special characters:

```bash
doas sh << 'EOF'
printf '#!/bin/sh\nexec doas "$@"\n' > /usr/local/bin/sudo
chmod 555 /usr/local/bin/sudo
EOF
