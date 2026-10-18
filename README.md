# MSTAT releases

Firmware and app releases for the **MSTAT** wireless potentiostat (KAUST
Sensors Lab). This repository holds **release files only** - no source code.

## Install the app (Android tablet or phone)

<img src="qr-install-app.png" alt="QR code: download the MSTAT app" width="200">

Scan the QR code with the tablet's camera, or open
**https://github.com/tsyurii/mstat-releases/releases/latest/download/modustat.apk**
in Chrome on the tablet.

1. **Download.** The file `modustat.apk` downloads (about 55 MB).
2. **Allow the install (once per device).** Tap the downloaded file. Android
   says installing from this source is blocked: tap **Settings**, turn on
   **Allow from this source** for Chrome (or your browser), go back and tap
   **Install**.
3. **Open MSTAT** and tap **Allow** when it asks to find and connect to
   nearby devices (Bluetooth).
4. **Connect to the board.** Switch the board on (connect its battery), tap
   **Scan for MSTAT**, then tap your board (e.g. *MSTAT-01*).
5. **Pair.** The first time, Android asks for a PIN: type the **6-digit PIN
   printed on the board's label**. A tablet that was paired before is not
   asked again.
6. **Done.** The *This board* card shows the board's name, firmware, serial
   and link security ("paired, encrypted").

**An older MSTAT app already installed?** Install this one first, check that
it connects, then long-press the old app's icon and choose **Uninstall**. Your
measurement files in *Download/MSTAT* and the Bluetooth pairing are kept.

## Updates

The app checks this repository for new versions on its own when a board is
connected (Wi-Fi needed), or when you tap **Device > Firmware update > Check
online**:

- **New board firmware:** tap **Install <version>**. The update goes over
  Bluetooth in about a minute; keep the tablet next to the board. Calibration
  and settings are kept. If the new firmware does not start properly, the
  board goes back to the previous version by itself.
- **New app version:** tap **Download the new app** and install it like
  above. It installs over the old one and keeps your settings.

## Troubleshooting

| Problem | What to do |
|---|---|
| The board is not found when scanning | Check the battery is connected; move within 1-2 m; the board accepts one tablet at a time |
| "Pairing failed or was cancelled" | Type the PIN from the label again (**Try again**). If the board was re-flashed, tap **Forget pairing** and connect again |
| A red **safe mode** banner | The board restarted after several crashes. Install the offered firmware update, or disconnect its battery for a few seconds. If it comes back, send the diagnostics log |
| "App not installed" when updating | An old test version signed differently is installed: uninstall it first, then install again |
| "No internet connection" on Check online | Connect the tablet to Wi-Fi; measuring works without internet |

## About the files

- `feed.json` lists the current firmware (per board and hardware revision) and
  app version with sha256 checksums; the app reads it.
- Firmware images are signed with the lab key; a board installs only images
  signed with it. The app is signed with the MSTAT release key, so every
  update installs over the previous one.
