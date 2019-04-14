# csfru

csfru stands for **C**reate **S**pectrograms **F**or **R**ED **U**ploads

# Use case

This tool allows you to automate the creation of spectrograms for RED uploads in under 100 lines of code.

# Dependencies

It uses curl (uploading to ptpimg.me), sox (generating spectrograms to upload/view) and xclip (optional: copying the album description and release description to clipboard)

# Usage

## Personal use in same directory

If I wanted to create spectrograms for personal use and not upload it anywhere I could do this:
```
./csfru -i /path/to/albumfolder
```
This would create a subdirectory in albumfolder called "Spectrograms" that contained all the spectrograms of the songs in "albumfolder".

## Personal use in specified directory

But what if you wanted to output them to a seperate "Spectrograms" folder?

To do that you would use the -o option:
```
./csfru -i /path/to/albumfolder -o /path/to/spectrogramsfolder
```
This would place the spectrograms in the specified directory.

## Uploading 

To upload you must use 2 additional options: -a and -u

Use -a to specify the API key you get from ptpimg.me (go to ptpimg, right click, view page source, search for api_key, copy the string in the value parameter)

Use -u to specify you want to upload the images

A full command would look like this:
```
./csfru -i /path/to/albumfolder -u -a YOURAPIKEY
```
