# csfru

csfru stands for **C**reate **S**pectrograms **F**or **R**ED **U**ploads

# Use case

This tool allows you to automate the creation of spectrograms for RED uploads in ~129 lines of code.

# Dependencies

It uses curl (uploading to ptpimg.me), sox (generating spectrograms to upload/view), xsel (to clear keyboard) and xclip (optional: copying the album description and release description to clipboard)

# Usage

## Clone repository
```
git clone https://cryptid.cc/lost/csfru.git
cd csfru
```

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

To upload you must use: -a

Use -a to specify the API key you get from ptpimg.me (go to ptpimg, right click, view page source, search for api_key, copy the string in the value parameter)

A full command would look like this:
```
./csfru -i /path/to/albumfolder -a YOURAPIKEY
```

## Other

If the spectrograms are too big you can use "-s" to make it output the default sized ones:
```
./csfru -i /path/to/albumfolder -s
```
If you wish to remove the files after uploading you can use "-r":
```
./csfru -i /path/to/albumfolder -r
```
**WARNING**: this deletes the "Spectrograms" folder in the albumfolder (if no spectrogram directory is passed), and deletes the subdirectory in the spectograms folder (if a spectrogram directory is passed)
