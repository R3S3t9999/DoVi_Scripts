# DoVi_Scripts

[<img src="https://i.ibb.co/QCq3trg/Paypal-donate.png">]( https://www.paypal.com/donate/?hosted_button_id=6ML5KUZG9XGB6)

-------------------------------------------------------------------------------------------------------------------------

## Drag-and-drop batch scripts designed for effortless management of HDR/Dolby Vision files, ensuring a user-friendly and easy-to-use experience. These versatile scripts can tackle many tasks, making your digital journey enjoyable and straightforward.

-------------------------------------------------------------------------------------------------------------------------

[<img src="https://i.ibb.co/ZGs6XMT/introduction.gif">](https://github.com/R3S3t9999/DoVi_Scripts/releases)

-------------------------------------------------------------------------------------------------------------------------

## MOST OF THE TOOLS NEEDED (MINUS EAE AND DOLBY TOOLS):

https://mega.nz/file/NXFlBQoZ#dv3nNrbq_O-kMfWnfUQiJvV6wBKx-DspLMA0hX-78-o

-------------------------------------------------------------------------------------------------------------------------

## YOU MUST INSTALL:

- https://www.python.org/downloads/release/python-390/ (3.8 should work too)

- https://avs-plus.net/ (64bit)

- https://www.videohelp.com/software/LAV-Filters

- https://www.videohelp.com/software/madVR

Dolby tools can be found here: 

- https://customer.dolby.com/content-creation-and-delivery/dolby-vision-professional-tools

EAE folder is only needed for 7.1 EC3 encoding. see links: https://github.com/R3S3t9999/DoVi_Scripts/blob/main/TOOLS%20%26%20INSTALLATION

-------------------------------------------------------------------------------------------------------------------------

## EXTERNAL SETTINGS AND CONFIG FILE EXAMPLES (optional)

- config file(L5 - MD)example for 3-1 and 2-1-2 batch modes: https://mega.nz/file/5CcAkACQ#w7M5DQFpJ_WKvD148uEtgM2OG6HcXtk9YQYozcd8VpU

- Settings file example: https://mega.nz/file/hfUg2DoT#m7PSo4UXdQZ-LIsSgWzFpM8HzNvmEGHgugah0biRiyM

-------------------------------------------------------------------------------------------------------------------------

## MUXING BEHAVIOR AND SCRIPT FOLDER:
The script's behavior for muxing (MKV, MP4, or TS) is determined by the filename of the .bat file. If you decide to remove these tags, the default muxing mode will be MKV but muxing can be completely disabled at line 55

I advise against using the script on your OS drive (usually C:) as it may result in certain functions being disabled or not functioning correctly. Furthermore, remuxing large files will slowdown the Windows operating system.

To ensure optimal performance, make sure that your path and script folder (containing both tools and the .bat file) adhere to the following format: It's preferable not to include special characters or spaces in the path.

[<img src="https://i.ibb.co/xJFzDvj/folder-look.jpg">](https://github.com/R3S3t9999/DoVi_Scripts/releases)


/////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

# SCRIPTS MODES

## MODE.I (1) =
- Can do all the extracting parsing, injecting, and editing of two input sources. (P8 hybrid maker)
- One static HDR base layer input and one dynamic HDR file input (MKV/MP4/HEVC/TS/M2TS/RPU/XML/JSON HDR10+).
- Can easily resynchronize RPUs, edit parameters like L5/L6, convert the profile to P8. (P8 hybrid maker)
- Add "P5BL" in the filename for raw HEVC P5 to P5 injection otherwise, the output will always be Profile 8
- For XML injection, it defaults to removing L2 trims, although you have the flexibility to adjust this behavior by modifying lines 83-87.
- Can remove cmv4.0 default = NO (line 91)

--------------------------------------------------------------------------------------------------------------------------

## MODE.F (2) =
- Can get info(fel or mel, profile, l1/l2/l5) from any DV source as well as extract and edit any DV source.
- Can verify the RPU synchronization
- Can fix fps bitstream, color range
- Can find frame difference between two sources
- Can validate metadata with Official Dolby Metafier
- Can convert RPU to XML
- Can overwrite L2 trims
- can batch remove cmv4.0
- Can tonemap pgs subtitles to different brightness
- This mode does not convert the RPU profile

-------------------------------------------------------------------------------------------------------------------------

## MODE.H (3) =
- Can convert any HDR10plus or HDR10 source to shot-by-shot or frame-by-frame DoVi.  CMV4.0 metadata, no fake static crap
- Official Dolby cm_analyze.exe (best) or hdr10plus to dv or madvr to dv
- can input external shot list
- L1 analysis can be tuned (line 95)
- it defaults to removing generated L2 trims, although you have the flexibility to adjust this behavior by modifying lines 83-87.
- can batch generate with external files for L5/ MD, and shot list
- Shot list source is selected in this order:

1- any external file with the same filename as the input (rpu, json, text)
2- internal RPU (in case of original rpu that has no shot, add ''IGNORERPU'' in the input filename.)
3- internal hdr10plus
4- if no dynamic metadata is found, it uses madvr to generate a shot list which means that if your source doesn't have any dynamic metadata, you can use the generated RPU from your previous 6-2 measurement.

------------------------------------------------------------------------------------------------------------------------

## MODE.7 (4) = 
- Can process any Profile 7 source(BD or Rip) to Single-layer Profile 8 or Profile 7 single-track dual-layers.
- Can remove cmv4.0 default = NO (line 91)

------------------------------------------------------------------------------------------------------------------------

MODE.B (5) = Can batch mux any DV source.

- MKV/MP4 to TS

- *TS/MP4 to MKV (the mkv version is intended for batch remuxing DV TS files which need to be demuxed first)

- MKV/TS to MP4

-----------------------------------------------------------------------------------------------------------------------

## MODE.P (6) =
- Can batch plot DoVi Level 1,2,3,5,6,8 and hdr10, hdr10plus, video bitrate

----------------------------------------------------------------------------------------------------------------------

## MODE.S (7) =
- can export screenshots (FEL P5 HDR10 SDR ETC) fully automated or manual modes
- can play FEL + BL or Profile 5 DV in HDR10 or SDR with madVR+MPC (if your pc can handle it)
- can export HDR heatmap and gamut visualization 

---------------------------------------------------------------------------------------------------------------------

## MODE.M (8) =
- Can remove hdr10plus or DV
- can convert audio (DDP 7.1 / Add silent or encoded core to TrueHD)
- can find bd playlist
- can inject HDR10plus
- can make 5 min samples. timestamp configurable at line: 109
- can encode bake fel to HDR10/P8 with dovibaker+ffmpeg/x265
- can encode DV to SDR using official Level-2 100nits trim pass (Official Dolby cm_offline.exe)

---------------------------------------------------------------------------------------------------------------------

 ## L5 active area and cropping:
  
 - if the base layer is 16:9 (no black bars, fullscreen): set L5 to 0
  
 - if the base layer is 16:9 but has black bars: measure the BL letterbox and adjust L5 accordingly.
                                                                                                                                     	 
 - if the base layer is cropped set L5 to 0
 
 ##  Example 1:
  
  input= 3840x2160p with active area of 2.40 (16:9 with black bars)
  
  L5 offsets= Left:0 Right:0 Top:280 Bottom:280
  
  -------------------------------------------------------------------
 
 ##  Example 2:

  input= 3840x2160p with active area of 1.78 (16:9 no black bars)
  
  L5 offsets= Left:0 Right:0 Top:0 Bottom:0
  
  -------------------------------------------------------------------
 
 ##  Example 3:

  input= 3840x1600p (cropped)
  
  L5 offsets= Left:0 Right:0 Top:0 Bottom:0

---------------------------------------------------------------------------------------------------------------------
  
## Input filename keywords:

- P5BL : force p5 to p5 injection in 1-1
- KEEPTRIMS : keep trims in XML injection for 1-1
- DONTUPSCALE : Keep original resolution in 7-2
- KEEPAUDIO : Keep all the audio when the script local settings are set to keep only main audio
- DONTMUX : Disable muxing when the script is set to mux
- IGNORERPU : Ignore internal rpu for shot list in 3-1
- REMOVECMV4 : Force CMV4.0 removal in 1-1
- KEEPPRORES : Keep prores when the script is set to delete it
- FORCESDR : Force SDR tonemapping in 7-1 7-2

---------------------------------------------------------------------------------------------------------------------

   ##  Interesting links:

   - WEB vs BD comparisons: https://docs.google.com/spreadsheets/d/1jBIGF8XTVi9VmDBZ8a5hEyongYMCDlUiLHU9n1f_S74/edit#gid=0

   - More comparisons: https://docs.google.com/spreadsheets/d/1jBIGF8XTVi9VmDBZ8a5hEyongYMCDlUiLHU9n1f_S74/edit#gid=917134052

   - HDR movies brightness plot: https://drive.google.com/drive/u/1/folders/154fBNllwOHL4Lckc7wDV8QKFJwFxnDt-

   - DV device playback supports: https://docs.google.com/spreadsheets/d/1jBIGF8XTVi9VmDBZ8a5hEyongYMCDlUiLHU9n1f_S74/edit#gid=427220017

   - How to make P8 hybrid properly : https://www.youtube.com/watch?v=hVWZpat34oc

   - How to batch generate DV: https://www.youtube.com/watch?v=jBqbG5XM54g

   - Convert HDR to SDR with Dolby Vision: https://www.youtube.com/watch?v=lM56zLpKDQ8

  ---------------------------------------------------------------------------------------------------------------------
