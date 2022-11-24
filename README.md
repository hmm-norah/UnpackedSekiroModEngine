# UnpackedSekiroModEngine
patch for ModEngine 0.1.16 that adds the unpacked Sekiro 1.06 executable to the allowlist, I couldn't find the source code for a new enough version of ModEngine, thus this exists. Fiddling with a companion program to get ultrawide support was a bit too much, and I didn't want to downgrade the game version, so here we are.

# ModEngine patch
### bsdiff
```
bspatch dinput8.dll dinput8new.dll unpacked106.bspatch
mv dinput8.dll dinput8.dllbak
mv dinput8new.dll dinput8.dll
```
### hex editing
replace ```58 3A EA 03``` with ```48 88 0A 04```, there should be only one match and it starts at offset 21FD.

# Sekiro.exe patches
## 120 fps
###hex editing 
After unpacking Sekiro's exe, replace ``88`` with ``08`` at offset 11AAB52
## 21:9 Ultrawide
###hex editing
replace ``74`` with ``EB`` at offset 12A26A
