# DoVi_Scripts

**A collection of drag-and-drop batch scripts for Dolby Vision, HDR10, HDR10+, video, and audio workflows.**

DoVi_Scripts helps automate common tasks such as Dolby Vision metadata extraction and editing, Profile 7 conversion, HDR-to-Dolby Vision generation, video/audio analysis, screenshots, comparisons, encoding, and muxing.

## Quick links

| Resource | Link |
|---|---|
| **Latest stable release** | [GitHub Releases](https://github.com/R3S3t9999/DoVi_Scripts/releases) |
| **Latest beta** | [Download beta](https://drive.google.com/file/d/128gq8aDUTKA_aT7SQsM9dkjA1EP1sosR/view?usp=sharing) |
| **Tools pack — Google Drive** | [Download](https://drive.google.com/file/d/1S4dqemaD8snI7QW29InG_XjI6VP0PNhk/view?usp=sharing) |
| **Tools pack — MEGA** | [Download](https://mega.nz/file/RCsWmAYC#rSF_IdSVhHx-G8U0F3EnaLXkt9eNLzqQ9qOmPggqrmc) |
| **Installation tutorial** | [Watch on YouTube](https://youtu.be/wb9191cExF8) |
| **Questions and support** | [Doom9 forum thread](https://forum.doom9.org/showthread.php?t=185317) |

**Tools pack password (case-sensitive):** `DoVi.Scripts`

> **Before reporting a bug:** Please try the [latest beta](https://drive.google.com/file/d/128gq8aDUTKA_aT7SQsM9dkjA1EP1sosR/view?usp=sharing) first.

The tools pack does **not** include the [Dolby Vision Professional Tools](https://customer.dolby.com/content-creation-and-delivery/dolby-vision-professional-tools-v541) or the **Easy Audio Encoder (EAE)** folder. See the [TOOLS & INSTALLATION instructions](https://github.com/R3S3t9999/DoVi_Scripts/blob/main/TOOLS%20%26%20INSTALLATION).

---

<!-- ADDED: quick start, built only from the information already on this page -->
## Quick Start

1. Download the [latest stable release](https://github.com/R3S3t9999/DoVi_Scripts/releases) (or the [beta](https://drive.google.com/file/d/128gq8aDUTKA_aT7SQsM9dkjA1EP1sosR/view?usp=sharing)) and the tools pack.
2. Install everything listed under [YOU MUST INSTALL](#you-must-install).
3. Add the Dolby Vision tools (and the EAE folder, if you need 7.1 EC3 encoding), which are not included in the tools pack.
4. Place the script folder (containing both `tools` and the `.bat` file) on a drive other than your OS drive, in a path without spaces or special characters.
5. Drag and drop your file(s) onto the `.bat` script and pick a mode.

Need a visual walkthrough? Watch the [installation tutorial](https://youtu.be/wb9191cExF8).

---

## YOU MUST INSTALL:

- [Python 3.12](https://www.python.org/ftp/python/3.12.10/python-3.12.10-amd64.exe)

- [Python 3.12 (Windows Store)](https://apps.microsoft.com/detail/9ncvdn91xzqp?hl=en-US&gl=US)

- Python libraries: open a command window and paste:

  ```
  pip install opencv-python colour-science scikit-image matplotlib numpy colour opencv-python-headless PyQt5 OpenImageIO plotly pyyaml librosa scipy soundfile openpyxl tkinterdnd2
  ```

  **If the heatmap workflow still fails, install Python 3.9 as well.**

- [AviSynth+ 64-bit](https://github.com/AviSynth/AviSynthPlus/releases/download/v3.7.5/AviSynthPlus_3.7.5_20250420_vcredist.exe) (not required if you just want to inject/edit DV)

- [LAV Filters](https://www.videohelp.com/software/LAV-Filters) (required for AvsPmod 3-1, 3-2 and 6-2 only)

- madVR 113b (required for 3-1, 3-2 and 6-2 only): it goes in the `dovi_scripts/tools/madvr` folder; then, with admin rights, click on the install `.bat`.

- Make sure you have the latest [Microsoft Visual C++ Redistributable](https://learn.microsoft.com/en-us/cpp/windows/latest-supported-vc-redist?view=msvc-170) installed, and if it complains about a missing DLL, install m versions.

Dolby tools can be found here:

- https://customer.dolby.com/content-creation-and-delivery/dolby-vision-professional-tools

[The EAE folder is only needed for 7.1 EC3 encoding.](https://github.com/R3S3t9999/DoVi_Scripts/blob/main/TOOLS%20%26%20INSTALLATION)

---

## Support the Project

[<img src="https://i.imgur.com/AOj1jq3.png" alt="Donate with PayPal">](https://www.paypal.com/donate/?hosted_button_id=6ML5KUZG9XGB6) - [<img src="https://i.imgur.com/07IBKqG.jpeg" alt="YouTube channel">](https://www.youtube.com/channel/UCEYM1g3nkBNCpgPuyd4JL_g)

---

## EXTERNAL SETTINGS EXAMPLES (optional)

- Settings file example: https://drive.google.com/file/d/1jQGuzZQyqhqwOTAFjkWWe-JMl6QDFeon/view?usp=drive_link

---

## MUXING BEHAVIOR AND SCRIPT FOLDER

The script's behavior for muxing (MKV, MP4, or TS) is determined by the filename of the `.bat` file. If you decide to remove these tags, the default muxing mode will be MKV, but muxing can be completely disabled at line 55.

I advise against using the script on your OS drive (usually C:), as it may result in certain functions being disabled or not functioning correctly. Furthermore, remuxing large files will slow down the Windows operating system.

To ensure optimal performance, make sure that your path and script folder (containing both `tools` and the `.bat` file) adhere to the following format. It's preferable not to include special characters or spaces in the path.

[<img src="https://i.ibb.co/xJFzDvj/folder-look.jpg" alt="Recommended folder layout">](https://github.com/R3S3t9999/DoVi_Scripts/releases)

---

# SCRIPT MODES

All the workflows are explained in this video: https://youtu.be/wb9191cExF8

<!-- ADDED: at-a-glance mode table -->
| Mode | Menu # | Purpose |
|------|:------:|---------|
| [MODE.I](#modei-1-) | 1 | Extract, parse, inject and edit DV/HDR10+ metadata |
| [MODE.F](#modef-2-) | 2 | Verify, remove, transfer and export metadata |
| [MODE.H](#modeh-3-) | 3 | Generate CMv4.0 Dolby Vision from HDR10+/HDR10/HLG |
| [MODE.7](#mode7-4-) | 4 | Process Profile 7 sources |
| [MODE.B](#modeb-5-) | 5 | Batch-mux DV sources |
| [MODE.P](#modep-6-) | 6 | Plot metadata, bitrate and audio |
| [MODE.S](#modes-7-) | 7 | Screenshots, heatmaps, comparisons and playback |
| [MODE.M](#modem-8-) | 8 | Audio and video encoding, trim passes |
| [MODE.M](#modem-9-) | 9 | Utilities (samples, frame counts, subtitles, etc.) |

## MODE.I (1) =

- Can do all the extracting, parsing, injecting, and editing of two input sources (P8 hybrid maker).
- Can easily resynchronize RPUs, edit parameters like L5/L6, and convert the profile to P8 (P8 hybrid maker).
- Can also edit a single input as well as process multiple files in a folder.
- Input can be anything: MKV/MP4/HEVC/TS/M2TS/RPU/XML/JSON (HDR10+).
- Can resync/inject HDR10plus and Dolby Vision (any profile).
- Can quickly get info from any DV source (FEL or MEL, profile, L1/L2/L5, etc.).
- Can quickly detect FEL expanded brightness.
- Can use external JSON files for advanced edits.
- Can validate metadata with the official Dolby Metafier.
- Can convert RPU to XML.
- Can disable DV tone mapping.
- Can remove CMv4.0 or upgrade a CMv2.9 RPU to 4.0.

---

## MODE.F (2) =

- Can verify the RPU synchronization and export the scene cuts to a text file.
- Can remove HDR10plus or DV.
- Can overwrite or remove L2 trims.
- Can export an EDL timeline (DV or HDR10plus) for Resolve.
- Can transfer any metadata level to another RPU.
- Can export L5 config files.
- Can batch-info your whole collection quickly.
- Can find scene-cut differences between two RPU sources.

---

## MODE.H (3) =

- Can convert any HDR10plus/HDR10/HLG source to shot-by-shot or frame-by-frame CMv4.0 DoVi.
- Uses the official Dolby `cm_analyze.exe` (best), DaVinci Resolve, HDR10plus to DV, or madVR to DV.
- Can use an external shot list for cm_analyze/Resolve DV generation.
- CMv4.0 L1 analysis tuning available.
- Can batch generate with external files for L5/MD and shot list.
- The shot list source is selected in this order:

  1. Any external file with the same filename as the input (RPU, JSON, text).
  2. Internal RPU (in the case of an original RPU that has no shots, add `IGNORERPU` to the input filename).
  3. Internal HDR10plus.
  4. If no dynamic metadata is found, madVR is used to generate a shot list. This means that if your source doesn't have any dynamic metadata, you can use the generated RPU from your previous 6-2 workflow.

---

## MODE.7 (4) =

- Can process any Profile 7 source (BD, rip or RPU) to single-layer Profile 8 or Profile 7 single-track dual-layer.

---

## MODE.B (5) =

Can batch-mux any DV source:

- MKV/MP4 to TS
- MKV/TS to MP4

---

## MODE.P (6) =

- Can batch plot DoVi Level 1, 2, 3, 4, 5, 6, 8 and HDR10, HDR10plus.
- Can plot video bitrate.
- Can plot audio waveforms, bed channels, or object-based Atmos channels.

---

## MODE.S (7) =

- Can export 16-bit RGB HDR or SDR tone-mapped screenshots (FEL, P7, P8, P5, HDR10, SDR).
- Can export SDR screenshots from a Dolby Vision 100-nit trim pass (requires DEE).
- Fully automated frame-accurate or manual modes, with up to 20 inputs at once.
- Can export HDR heatmap and gamut visualization (FEL, P5, HDR10, SDR).
- Can create a DV metadata video comparison [like this](https://drive.google.com/drive/folders/1g5I-z_sJmVu-SAIPNiiSlcdMiy2ka0mf).
- Can create a DV FEL vs BL video comparison [like this](https://drive.google.com/drive/u/0/folders/1FS42T95TOSpoy4xtwUBIQmziCe_R_IKe).
- Can create an HDR video comparison from two sources.
- Can play FEL + BL or Profile 5 DV in HDR10 or SDR with madVR + MPC (if your PC can handle it; no dynamic metadata processing).
- Can play DV with dynamic metadata (and FEL) processing in MPV.

---

## MODE.M (8) =

- Can convert audio (DDP up to 7.1, and add silent or encoded core to TrueHD).
- Can encode TrueHD Atmos to DD+ Atmos (requires DEE).
- Can bake FEL to HDR10/P8 with dovibaker + x265 or NVEnc.
- Can encode any HDR10/HLG/FEL P7/P5/ProRes source to HDR or SDR (x265, x264, NVEnc or ProRes).
- Can deliver any Dolby Vision trim passes (official Dolby `cm_offline.exe`).
- Can encode Profile 5 DV (requires DEE).
- Can encode Profile 7 DV MEL or FEL without BL mapping, or mapping to 600/1000 nits (requires DEE).
- Can create a video loop sample, [examples](https://drive.google.com/drive/u/0/folders/1qCyCTmhEVZjdY5O8gNVFna-nnkVQkhI_).

---

## MODE.M (9) =

- Can find the BD playlist.
- Can make 5-minute samples (timestamp configurable at line 109).
- Can quickly find a video frame count.
- Can quickly find an audio dialnorm value.
- Can tone-map image-based PGS (`.sup`) subtitles to a different brightness.
- Can fix or change the FPS of a bitstream, or the color range.
- Can change the framerate of SRT text subtitles.
- Can find the frame difference between two sources.
- Can edit static HDR10 metadata.

---

## L5 active area and cropping

- If the base layer is 16:9 (no black bars, fullscreen): set L5 to 0.
- If the base layer is 16:9 but has black bars: measure the BL letterbox and adjust L5 accordingly.
- If the base layer is cropped: set L5 to 0.

### Example 1

Input: 3840x2160p with an active area of 2.40 (16:9 with black bars)

L5 offsets: Left: 0, Right: 0, Top: 280, Bottom: 280

### Example 2

Input: 3840x2160p with an active area of 1.78 (16:9, no black bars)

L5 offsets: Left: 0, Right: 0, Top: 0, Bottom: 0

### Example 3

Input: 3840x1600p (cropped)

L5 offsets: Left: 0, Right: 0, Top: 0, Bottom: 0

---

## Input filename keywords that override the script's main settings

| Keyword | Effect |
|---------|--------|
| `P5BL` | Force P5 to P5 injection in 1-1 when the input is raw HEVC |
| `DONTUPSCALE` | Keep original resolution in 7-2 |
| `KEEPAUDIO` | Keep all the audio |
| `DONTMUX` | Disable muxing |
| `IGNORERPU` | Ignore internal RPU for shot list in 3-1 |
| `KEEPPRORES` | Keep ProRes file |
| `FORCESDR` | Force SDR tone mapping in 7-1 and 7-2 |
| `KEEPTRIMS` | Keep trims in XML injection for 1-1 and 3-1 |
| `KEEP1000` | Keep 1000-nit trims in XML injection for 1-1 and 3-1 |
| `KEEP600` | Keep 600-nit trims in XML injection for 1-1 and 3-1 |
| `JUSTINJECT` | Inject without changing the DV profile in 1-1 |
| `FORCEHDR10PLUS` | Force HDR10plus in workflow 3-1 |

---

## Links that may interest you

- [WEB vs BD comparisons](https://docs.google.com/spreadsheets/d/15i0a84uiBtWiHZ5CXZZ7wygLFXwYOd84/edit?gid=828864432#gid=828864432)
- [BEST Dolby Vision player](https://www.youtube.com/watch?v=HyrA3KmcJBU)
- [DV vs HDR10 samples](https://drive.google.com/drive/u/0/folders/1qCyCTmhEVZjdY5O8gNVFna-nnkVQkhI_)
- [FEL vs HDR10 samples](https://drive.google.com/drive/u/0/folders/1FS42T95TOSpoy4xtwUBIQmziCe_R_IKe)
- [Metadata comparison samples](https://drive.google.com/drive/folders/1g5I-z_sJmVu-SAIPNiiSlcdMiy2ka0mf)
- [More comparisons](https://docs.google.com/spreadsheets/d/15i0a84uiBtWiHZ5CXZZ7wygLFXwYOd84/edit?gid=1226038728#gid=1226038728)
- [HDR movies brightness plot](https://drive.google.com/drive/u/1/folders/154fBNllwOHL4Lckc7wDV8QKFJwFxnDt-)
- [DV device playback support](https://docs.google.com/spreadsheets/d/15i0a84uiBtWiHZ5CXZZ7wygLFXwYOd84/edit?gid=845372636#gid=845372636)
- [How to make P8 hybrid properly](https://www.youtube.com/watch?v=hVWZpat34oc)
- [How to batch generate DV](https://www.youtube.com/watch?v=jBqbG5XM54g)
- [Convert HDR to SDR with Dolby Vision](https://www.youtube.com/watch?v=lM56zLpKDQ8)
