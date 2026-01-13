# n8n for Zyntax

[n8n](https://n8n.io) workflow automation tool, pre-built for Android arm64.

## Version

- **n8n:** 2.3.3
- **Node.js:** 24.x required

## Download

| File | Size | Files |
|------|------|-------|
| [n8n-core.tar.zst](https://github.com/amitkhare/zyntax-packages/releases/download/n8n-v2.3.3/n8n-core.tar.zst) | ~1MB | 11 |
| [n8n-modules.tar.zst](https://github.com/amitkhare/zyntax-packages/releases/download/n8n-v2.3.3/n8n-modules.tar.zst) | ~104MB | 147,791 |

## Install

**Prerequisites:**
```bash
kpg install nodejs
```

## Via zpx:


# Download archives
curl -LO https://github.com/amitkhare/zyntax-packages/releases/download/n8n-v2.3.3/n8n-core.tar.zst
curl -LO https://github.com/amitkhare/zyntax-packages/releases/download/n8n-v2.3.3/n8n-modules.tar.zst

# Extract
zpx n8n-core.tar.zst n8n-modules.tar.zst $PREFIX/lib/n8n

# Create symlink
ln -s ../lib/n8n/bin/n8n $PREFIX/bin/n8n


## Usage

# Start n8n (default port 5678)
n8n start

# Start with tunnel (public URL)
n8n start --tunnel

# Run in background
n8n start &


Access at: http://localhost:5678

## Data Location
n8n stores data in ~/.n8n/:

config - Settings
database.sqlite - Workflows, credentials
nodes/ - Custom nodes

## Notes
Node version check is patched out (works with any Node 18+)
First start may take a moment to initialize database
Use --tunnel for webhook testing without port forwarding

## Uninstall
rm -rf $PREFIX/lib/n8n
rm $PREFIX/bin/n8n
