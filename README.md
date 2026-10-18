# MSTAT releases

Firmware and app releases for the MSTAT wireless potentiostat (KAUST
Sensors Lab). This repository holds **release files only** - no source code.

- `feed.json` lists the current firmware (per board and hardware revision)
  and app version with sha256 checksums. The MSTAT app reads it under
  Device > Firmware update > *Check online*.
- Firmware images are signed with the lab key; a board only installs images
  signed with it, and rolls back by itself if a new image does not start.
- To install the app: download the newest `mstat-<version>.apk` from
  Releases on the tablet and open it (Android asks to allow installing from
  this source once).
