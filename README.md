## 🚀 CachyOS AllUpdate - Automated System Maintenance Script

A comprehensive fish shell function for automated CachyOS system updates and maintenance.

---

### 📋 Table of Contents
- [Features](#features)
- [Installation](#installation)
- [Usage](#usage)
- [Commands Breakdown](#commands-breakdown)
- [Troubleshooting](#troubleshooting)

---

### ✨ Features

| Feature | Description |
|---------|-------------|
| **Repository Updates** | Automatic CachyOS repo and AUR updates via `paru` |
| **Flatpak Support** | Integrated Flatpak update checking |
| **Orphan Package Cleanup** | Identifies and removes unused dependencies |
| **Cache Management** | Smart package cache maintenance with retention |
| **Colorized Output** | Beautiful terminal feedback for each step |

---

### 📦 Installation

1. **Add to `config.fish`**:

```fish
function allupdate
    # Your existing code here
end
```

2. **Or create a wrapper script** (`~/.allupdate.sh`):

```bash
#!/usr/bin/env fish
source ~/.config/fish/config.fish
allupdate
```

---

### 🎯 Usage

Simply run:

```fish
allupdate
```

Or add to your crontab for automated maintenance:

```cron
# Run weekly on Sunday at 3 AM
0 3 * * 0 allupdate >> /var/log/allupdate.log 2>&1
```

---

### 🔍 Commands Breakdown

| Command | Purpose |
|---------|---------|
| `paru -Syu` | Sync and upgrade CachyOS repos + AUR packages |
| `flatpak update -y` | Update all Flatpak applications |
| `pacman -Qdtq` | Query for orphaned dependencies (quiet mode) |
| `paru -Rns` | Remove specified packages with confirmation |
| `sudo paccache -r` | Recursively clean package cache |

---

### 🐛 Troubleshooting

**Issue:** Function not recognized

```fish
# Verify fish is using the updated config
source ~/.config/fish/config.fish
allupdate  # Should work now
```

**Issue:** Orphan detection failing

```fish
# Manual verification
pacman -Qdtq  # Check if orphans exist
```

---

### 📝 License

MIT License - Feel free to modify and distribute.

---

### 🤝 Contributing

1. Fork the repository
2. Create a feature branch (`git checkout -b feature/amazing-feature`)
3. Commit changes (`git commit -m 'Add amazing feature'`)
4. Push to the branch (`git push origin feature/amazing-feature`)
5. Open a Pull Request
