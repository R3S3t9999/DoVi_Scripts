# DoVi_Scripts

[<img src="https://i.ibb.co/QCq3trg/Paypal-donate.png">]( https://www.paypal.com/donate/?hosted_button_id=6ML5KUZG9XGB6)

User-friendly drag & drop scripts to process any HDR / Dolby Vision files and can do a lot more...

[<img src="https://i.ibb.co/ZGs6XMT/introduction.gif">](https://github.com/R3S3t9999/DoVi_Scripts/releases)

Most of the tools needed: https://mega.nz/file/QLFT0QRY#x-pcsQJ9mE58PzFOveaF2ZLWYpTKRPeIRQUED_V-kwY

Put this DLL file somewhere reachable by avisynth+ (only needed if you want to use the dovi baker)

https://github.com/erazortt/DoViBaker/files/10810040/libdovi-3.1.1-x86_64-pc-windows-msvc.zip

install:

https://www.python.org/downloads/release/python-390/ (3.8 should work too)

https://avs-plus.net/ (64bit)

https://www.videohelp.com/software/LAV-Filters

https://www.videohelp.com/software/madVR


external settings/files example:

config file(L5 - MD)example for 3-1: https://drive.google.com/file/d/1cxGCIvP0qnhTzwIb_Up-BsQXrHGMwuM6/view?usp=drive_link 

Settings file example: https://drive.google.com/file/d/1u8Q_drQp2CdWpqZwHfdLuvHkPoVLcOf-/view?usp=drive_link

The bat filename (MKV , MP4 or TS) determines the muxing behavior. If you rename the bat file, the default muxing mode is MKV

if you dont edit your path, your script folder must look like this:

[<img src="https://i.ibb.co/xJFzDvj/folder-look.jpg">](https://github.com/R3S3t9999/DoVi_Scripts/releases)

/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

MODE.I (1) =
- Can do all the extracting parsing and injecting/ editing of two input sources.
- One  base layer input and one P5/P8/P7/HDR10plus input (MKV/MP4/HEVC/TS/M2TS/RPU/XML/JSON).
- Can resync, edit L5/L6/source max-min_pq, can convert the profile to p8. Make hybrid
- Add "P5BL" in the filename for P5 to P5 injection.
:------------------------------------------------------------------------------------------------------------------------------------------------------

MODE.F (2) =
- Can get info(fel or mel, profile, l1/l2/l5) from any DV source as well as extract and fix any rpu that has editing errors.
- It can also verify the RPU synchronization and brightness.
- This mode does not convert the RPU profile.
- Can fix fps bitstream, color range…
- can find frame difference between two source
- Can validate metadata with Dolby Metafier
- Can convert RPU to XML
- Can overwrite L2 trims
- can remove cmv4.0
- Can tonemap pgs subtitles to different brightness
- Input must be a DV P5/P7/P8 file. (MKV/MP4/HEVC/TS/M2TS/RPU/).

:------------------------------------------------------------------------------------------------------------------------------------------------------

MODE.H (3) =
- Can convert any HDR10plus or HDR10 source to shot-by-shot or frame-by-frame DoVi.
- Dolby cm_analyze or hdr10plus to dv or madvr to dv
- can input external shot list
- can tune L1 analysis
- can leave or remove L2 trims
- can make CMV4.0 metadata, no fake static stuff...
- can batch and use external files for L5 and MD, and shot list

:------------------------------------------------------------------------------------------------------------------------------------------------------

MODE.7 (4) = Can convert any Profile 7 source(BD or rip) to single-layer Profile 8 or Profile 7 single-track dual-layers.

:------------------------------------------------------------------------------------------------------------------------------------------------------

MODE.B (5) = Can batch mux any DV source.
MKV/MP4 to TS
TS/MP4 to MKV
MKV/TS to MP4

:------------------------------------------------------------------------------------------------------------------------------------------------------

MODE.P (6) =
- can plot DV(L1/L2/L5/L6), hdr10, hdr10plus, video bitrate,

:------------------------------------------------------------------------------------------------------------------------------------------------------

MODE.S (7) =
- can export screenshots (FEL P5 HDR10 SDR ETC) fully automated or manual modes

:------------------------------------------------------------------------------------------------------------------------------------------------------
MODE.M (8) =
- Can remove hdr10plus/DV,
- can convert audio,
- can find bd playlist,
- can inject HDR10plus,
- can play P5/HDR10 movies in SDR/HDR10
- can make 5min samples
- can encode bake fel to HDR10
- can export screenshots
- can encode DV to SDR using 100nits trim pass


   L5 active area:
  a-) if the base layer is 16:9 (no black bars, fullscreen): set L5 to 0
  b-) if the base layer is 16:9 but has black bars: measure the BL letterbox and adjust L5 accordingly.                                                                                                                                     	 
  c-) if the base layer is cropped set L5 to 0
 
  Example 1:
  -------------------------------------------------------------------
  input= 3840x2160p with active area of 2.40 (16:9 with black bars)
  L5 offsets= Left:0 Right:0 Top:280 Bottom:280
  -------------------------------------------------------------------
 
  Example 2:
  -------------------------------------------------------------------
  input= 3840x2160p with active area of 1.78 (16:9 no black bars)
  L5 offsets= Left:0 Right:0 Top:0 Bottom:0
  -------------------------------------------------------------------
 
  Example 3:
  -------------------------------------------
  input= 3840x1600p (cropped)
  L5 offsets= Left:0 Right:0 Top:0 Bottom:0
  -------------------------------------------
