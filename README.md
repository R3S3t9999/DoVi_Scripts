# DoVi_Scripts
Users-friendly scripts to work with HDR / Dolby Vision files and more...

link: https://drive.google.com/drive/u/1/folders/1keTxo5RoH8V_kqcZn4ZWF_J2M9DvOQRu

:: You have to download and edit the paths(notepad++) of all the tools below (you may not have to download them all).
:: The default output folder is wherever you place the "DoVi_Scripts" folder.  A Windows drive (C:\) is not recommended
:: You can change the output path: Example: " set output_path=D:\Video.Folder\ "
:: You can use an external settings file, see the example below
:: Click on the DoVi_Scripts.bat, select a mode, a workflow, drag and drop input, and wait...
:: MANY THANKS TO ALL THE CREATORS OF THE TOOLS/CODES I'M USING IN THESE SCRIPTS.
:: In case of issues, most of the time, just remove special characters or space from the path/filename
:: If drag and drop doesnt work on Windows 11, reset your Windows security to default and reboot.
:: You can use external bat files for the paths and settings. (PATHS.bat / SETTINGS.bat)
:: Sorry for my English...
 
\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\\

CONTACT/BUG/QUESTION: R3S3T_9999@proton.me
DONATE: https://www.paypal.com/donate/?hosted_button_id=6ML5KUZG9XGB6

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


set dovi_tool_path=https://github.com/quietvoid/dovi_tool
set dovi_tool_FIX_path=https://github.com/quietvoid/dovi_tool/releases/tag/1.3.2
set hdr10plus_parser_path=https://github.com/quietvoid/hdr10plus_tool
set tsmuxer_path=https://github.com/justdan96/tsMuxer/releases
set tsmuxer.GUI_path=https://github.com/justdan96/tsMuxer/releases
set ffmpeg_path=https://www.videohelp.com/software/ffmpeg
set ffprobe_path=https://www.videohelp.com/software/ffmpeg
set mkvmerge_path=https://www.videohelp.com/software/MKVToolNix
set mkvtoolnix_path=https://www.videohelp.com/software/MKVToolNix
set mkvextract_path=https://www.videohelp.com/software/MKVToolNix
set madvr_path=https://www.videohelp.com/software/madVR  (you need a madvr folder with madMeasureHDR.exe)
set AC3.64kbps_path= https://drive.google.com/file/d/1aaCp3OHA3_haD3qyExWSnds0dAwOqG3m/view?usp=share_link only needed if you opt for TS files
set thdmerge_path=http://rationalqm.us/board/viewtopic.php?f=16&p=15406#p15406 only needed if you opt for TS files
set mp4muxer_path=https://github.com/bbeny123/mp4muxer/releases (not needed if you dont use the mp4 workflows)
set mp4muxerNEW_path=https://github.com/DolbyLaboratories/dlb_mp4base only needed if you opt for MP4 files
set mp4demuxer_path=https://github.com/DolbyLaboratories/dlb_mp4demux only needed if you opt for MP4 files
set mp4box_path=https://www.videohelp.com/download/gpac-1.1.0-DEV-latest-master-x64.exe only needed if you opt for MP4 files
set mp4box2_path=https://www.videohelp.com/software/MP4Box only needed if you opt for MP4 files
set detectborders_path=dont remember the github where i got it. PM me (not needed if you only use manual L5 edits)
set mediainfo_path=https://mediaarea.net/en/MediaInfo/Download/Windows
set delaycut=https://www.videohelp.com/software/delaycut
set DGDemux_path=https://www.rationalqm.us/dgdemux/dgdemux.html
set eac3to_path=https://www.videohelp.com/software/eac3to
set JQ_path=https://stedolan.github.io/jq/
set MPV_path=https://mpv.io/
set MPC_path=https://www.videohelp.com/software/Media-Player-Classic-Home-Cinema (need to be the portable version)
set plotbitrate_path= https://github.com/zeroepoch/plotbitrate
set EAE_path=download/install plex server and copy the files from the installation folder in this folder (you can uninstall it once you got the files)(not needed if you dont encode audio to DDP 7.1)
set EAE=https://github.com/pabloromeo/clusterplex/files/9396885/EasyAudioEncoder.zip(not needed if you dont encode audio to DDP 7.1)
set wave=dont remember the github where i got it (PM me) (not needed if you dont plot audio waveforms)
set PLEX=download/install plex server and get the transcoder from the installation folder (you can uninstall it once you got the files) (not needed if you dont encode audio to DDP 7.1)
set supfoe=https://forum.makemkv.com/forum/viewtopic.php?t=20964 (not needed if you dont export subs)
set imagemagick=https://imagemagick.org/script/download.php#windows (not needed if you dont plot HDR10)
set RPU.to.XML=https://github.com/saindriches/dovi_meta/releases/tag/0.1.0-fix
set scenedetect_path= https://github.com/Breakthrough/PySceneDetect/releases/download/v0.6.1-release/PySceneDetect-0.6.1-win64-portable.zip
set gnuplot=https://sourceforge.net/projects/gnuplot/files/gnuplot/
set AvsPmod_path=https://www.videohelp.com/software/AvsP
set DGIndexNV_path=https://www.rationalqm.us/dgdecnv/dgdecnv.html
set ffms2=https://mega.nz/file/pD9wRQqZ#i1mTXxanWgqSodHPOsNBAEiAhuX64WLSx3weICtNqQk
set ffmsindex=https://mega.nz/file/pD9wRQqZ#i1mTXxanWgqSodHPOsNBAEiAhuX64WLSx3weICtNqQk
set heat_map= https://drive.google.com/file/d/1VuGz1pCH2FPJ085IglwZ4FP5Jru532k-/view?usp=sharing
set metafier_path=https://customer.dolby.com/content-creation-and-delivery/dolby-vision-professional-tools  only needed if you want to remove trims and do metadata validation
set cm_analyzer_path=https://customer.dolby.com/content-creation-and-delivery/dolby-vision-professional-tools  only needed for 3-1 3-2
set cm_offline_path=https://customer.dolby.com/content-creation-and-delivery/dolby-vision-professional-tools only needed for 8-7-1
set subtitle_tonemap=https://github.com/quietvoid/subtitle_tonemap/releases only needed for 2-9
set DEE_path=D:\other\DEE\dee.exe


///////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////////

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
- can measure dv hdr10 hdr10plus video bitrate audio waveforms,

:------------------------------------------------------------------------------------------------------------------------------------------------------

MODE.S (7) =
- can export screenshots

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



