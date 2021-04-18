# About
Project to help me edit and caption video

# Usage

Create a folder on your desktop for the project, download manage.py into that project's folder, and install python.

## Commands

These commands are listed in roughly the order you'll need to use them.

`python manage.py init` - Start a new project in the same folder as the manage.py file.

The folder structure is:
- Project Folder
  - 1_Source
  - 2_Audio_Editing
  - 3_Video_Editing
  - 4_Captioning
    - captions.srt
  - 5_Final_Videos

`python manage.py finalize` - Copies the final video from '3_Video_Editing\video.mp4' to '5_Final_Videos\final_[datetime]'. It will also add the watermark in '1_Source\watermark.png' to the video in the upper left corner.

`python manage.py auto-caption` - Attempts to automatically caption the video '5_Final_Videos\final_[datetime]' (it uses the one with the most recent datetime). Will overwrite '4_Captioning\captions.srt'.

`python manage.py apply-captions` - Adds open captions to a video (this is the kind that can't be turned off). 

It assumes the video is in '5_Final_Videos\final_[datetime]' (it uses the one with the most recent datetime) and the captions file is in '4_Captioning\captions.srt'. It will write the captioned video to '5_Final_Videos\final_captioned_[datetime]'. 

`python manage.py generate-preview [HH:MM:SS] [HH:MM:SS]` - Will generate previews from the final and captioned videos in '5_Final_Videos', named '5_Final_Videos\preview_[datetime]' and '5_Final_Videos\preview_captioned_[datetime]'