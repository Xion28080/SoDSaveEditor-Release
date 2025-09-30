# Shape of Dreams — Save Editor

A fast, dark-themed save editor for **Shape of Dreams** that lets you tweak stardust, hero mastery, unlock skills/gems, toggle banners & hats (with exclusives respected), complete achievements, and—if you know what you’re doing—edit raw JSON safely.  

No source code is distributed in this repository; **binaries are published as Release assets only**.

> **Not affiliated with Lizard Smoothie or the Shape of Dreams team.** Use at your own risk and in accordance with the game’s EULA.

---

## Security & VirusTotal

Every release includes:
- **SHA256 checksum** (`SHA256SUMS.txt`)
- **VirusTotal scan link** (`VirusTotal.txt`)

[![VirusTotal](https://img.shields.io/badge/VirusTotal-View%20scan-blue)](https://github.com/Xion28080/SoDSaveEditor-Release/releases/latest)

> If SmartScreen warns about an unknown app, click **More info → Run anyway**.  
> Verify the SHA256 with:
> ```powershell
> Get-FileHash -Algorithm SHA256 .\SoDSaveEditor.exe
> ```

---

## Download

1. Go to this repository’s **Releases** page.
2. Download the latest `SoDSaveEditor-vX.Y.Z.zip`.
3. (Optional) Verify integrity using the matching `SHA256SUMS.txt`.

> The auto-generated “Source code (zip/tar.gz)” links on the Releases page do **not** contain the app. Use the ZIP asset described above.

---

## Requirements

- Windows 10/11 (x64)
- No .NET install needed (the app is shipped as a self-contained build)

---

## Where are my save files?

Typical location:

```
%USERPROFILE%\AppData\LocalLow\Lizard Smoothie\Shape of Dreams\QuickSave
```


Look for these two files inside that folder:

- `r_profile<UUID>.json`
- `r_stats<UUID>.json`

---

## How to use

1. **Extract** the ZIP you downloaded.  
2. **Run** `SoDSaveEditor.exe`.  
3. Click **Select Save Folder** and choose the directory that contains both `r_profile*.json` **and** `r_stats*.json`.  
   - You’ll see **Save Successfully Loaded** in green if both files are found.  
4. Make your changes on any tab.  
5. Click **Save**.  
   - The editor automatically makes time-stamped backups:  
     `r_profile*.json.bak-YYYYMMDD-HHMMSS` and `r_stats*.json.bak-YYYYMMDD-HHMMSS`.

---

## What each tab does

- **Resources**  
  - Edit **Stardust** (`profile.stardust`).

- **Heroes**  
  - Choose a hero and set **Mastery Level**.  
  - **Cumulative Mastery** auto-recalculates and writes to `stats.total.masteryLevel`.

- **Skills/Gems**  
  - View wins for each skill/gem.  
  - **Unlock All (wins = 10)** sets every entry’s `wins` to `10`.

- **Banners**  
  - Toggle banner unlocks under `profile.nametags`.  
  - Exclusives are shown as **read-only** and cannot be unlocked.

- **Hats**  
  - Toggle accessory unlocks under `profile.accessories`.   
  - Exclusives are shown as **read-only** and cannot be unlocked.

- **Achievements**  
  - Manually adjust `currentProgress` or toggle `isCompleted`.  
  - Progress automatically clamps to `maxProgress` where known.  
  - No global “unlock all” — achievements are now **manual only**.

- **Raw JSON**  
  - Tree view of both `r_profile` and `r_stats`.  
  - Select a primitive value (string/number/bool/null), change it in the right-hand panel, then press **Apply Change to Selected**.  
  - **Warning:** Editing arbitrary values can corrupt saves. Only change what you understand.

---

## Safety notes

- **Automatic backups** are created every time you save.  
- Close the game before editing to avoid overwriting changes.  
- Some antivirus tools may flag unsigned, self-contained EXEs. Verify the included `SHA256SUMS.txt` and whitelist if needed.

---

## FAQ

**Q: Will this get me banned?**  
This tool edits local save files and does not interact with online services. That said, always follow the game’s EULA and community guidelines. You are responsible for how you use modified saves.

**Q: The editor can’t find my save.**  
Make sure you pointed it to the folder that contains **both** `r_profile*.json` and `r_stats*.json`. If you use multiple profiles or cloud sync, confirm which folder the game last wrote to.

**Q: Can I unlock exclusives?**  
No. Exclusives (banners, hats, etc.) are intentionally shown as **read-only**.

**Q: Do I need .NET installed?**  
No. The release is self-contained.

---

## Reporting issues / feedback

- Open an issue on this repository (if enabled), or  
- Contact me via my Nexus Mods page for Shape of Dreams — Save Editor.  

Please include:
- The editor version (see the Release tag, e.g., `v1.1.0`)  
- A brief description + steps to reproduce  
- A redacted snippet of the affected JSON if relevant (remove any personal data)

---

## License

This project is distributed in binary form only. **No source code is provided here.**  
Usage is governed by the included `LICENSE` (proprietary; personal, non-commercial use only; no redistribution or modification).  
