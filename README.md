# csfru

csfru stands for **C**reate **S**pectrograms **F**or **R**ED **U**ploads

# Use case

This tool allows you to automate the creation of spectrograms for RED uploads in ~122 lines of code.

# Dependencies

It uses bash (version 4 or higher), curl (uploading to ptpimg.me), sox (generating spectrograms to upload/view), ffmpeg (to find length of each song), and xclip (optional on macos: copying the album description and release description to clipboard)

## MacOS warning.

Make sure you install the latest coreutils with brew:
```
brew install coreutils
```
This is needed because this script uses features that are only present in bash 4.x or higher while by default MacOS only has bash 3.x

# Usage

## Clone repository
```
git clone https://cryptid.cc/lost/csfru.git
cd csfru
```

## Personal use in same directory

If I wanted to create spectrograms for personal use and not upload it anywhere I could do this:
```
./csfru -i /path/to/albumdir
```
This would create a subdirectory in albumdir called "spectrograms" that contained all the spectrograms of the songs in "albumdir".

## Personal use in specified directory

But what if you wanted to output them to a seperate "spectrograms" directory?

To do that you would use the -o option:
```
./csfru -i /path/to/albumdir -o /path/to/spectrogramsdir
```
This would place the spectrograms in the specified directory.

## Uploading 

Use -a to specify the API key you get from ptpimg.me (go to ptpimg, right click, view page source, search for api_key, copy the string in the value parameter)

A full command would look like this:
```
./csfru -i /path/to/albumdir -a api_key
```

## Other

If you wish to remove the files after uploading you can use "-r":
```
./csfru -i /path/to/albumdir -r
```
**WARNING**: this deletes the "Spectrograms" folder in the albumfolder (if no spectrogram directory is passed), and deletes the subdirectory in the spectograms folder (if a spectrogram directory is passed)
