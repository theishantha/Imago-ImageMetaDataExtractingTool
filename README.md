[![forthebadge](https://forthebadge.com/images/badges/made-with-python.svg)](https://forthebadge.com) [![forthebadge](https://forthebadge.com/images/badges/built-with-love.svg)](https://forthebadge.com)


# Image Metadata Extracting Tool - Imago
### University Final Year Project

This is a python tool that extract digital evidences from images recursively.
This  tool is useful throughout a digital forensic investigation. If you need to extract digital evidences and you have a lot of images, through this tool you will be able to compare them easily. this tool allows to extract the evidences into a CSV file. If in a JPEG exif are present GPS coordinates, application can extract the longitude and latitude and it can convert them to degrees and to retrieve relevant information like city, nation, zip code...
Application offers also the possibility to calculate Error Level Analysis and perceptual image hashing.

# Setup

## Setup via cloning

1. Install imago:

Just Download the project repo and set path to imago folder

2. Once it is finished, just run for man page:

```console
$ python imago.py -h
```
And then it should output the software manual page


## Requirements:
```
python 2.7
exifread >= 2.1.2
python-magic >= 0.4.15
argparse >= 1.4.0
pillow >= 5.2.0
imagehash >= 4.0
geopy >= 1.16.0

```
# Usage

```
usage: imago.py [-h] -i INPUT [-x] [-g] [-e] [-n] [-d {md5,sha256,sha512,all}]
                [-p {ahash,phash,dhash,whash,all}] [-o OUTPUT] [-s]
                [-t {jpeg,tiff}]


optional arguments:

  -h, --help            show this help message and exit

  -i INPUT, --input INPUT
                        Input directory path

  -x, --exif            Extract exif metadata

  -g, --gps             Extract, parse and convert to coordinates, GPS exif
                        metadata from images (if any)It works only with JPEG.

  -e, --ela             Extract, Error Level Analysis image,It works only with
                        JPEG.
  

  -d {md5,sha256,sha512,all}, --digest {md5,sha256,sha512,all}
                        Calculate perceptual image hashing

  -p {ahash,phash,dhash,whash,all}, --percentualhash {ahash,phash,dhash,whash,all}
                        Calculate hash digest

  -o OUTPUT, --output OUTPUT
                        Output directory path

  -s, --sqli            Keep SQLite file after the computation

  -t {jpeg,tiff}, --type {jpeg,tiff}
                        Select the image, this flag can be JPEG or TIFF, if
                        this argument it is not provided, imago will process
                        all the image types(i.e. JPEG, TIFF)



```
The only required argument is -i which is the base directory from which imago will start to search for image file.
You should also provide at least one type of extraction (i.e. exif, data, gps, digest).

# Example:

```console
$python imago.py -i /pathtoimagefile/ -o /pathtodetinationfile/ -x -s -t jpeg -d all
```

Where:
* -i path: is the base directory, where imago will search for file
* -o path: the output directory where imago will save the CSV file, with the extracted metadata
* -x : imago will extract EXIF metadata.
* -s: the temporary SQLite database will not be deleted after the processing.
* -t jpeg: imago will search only for jpeg images.
* -d all: imago will calculate md5, sha256, sha512 for the jpeg images.

# Features:

| Functionality | Status        |
| ------------- |:-------------:|
| Recursive directory navigation  | ✔️ |
| file mtime (UTC) | ✔️ |
| file ctime (UTC) | ✔️ |
| file atime (UTC) | ✔️ |
| file size (bytes)| ✔️ |
| MIME type | ✔️ |
| Exif support  | ✔️ |
| CSV export  | ✔️ |
| md5, sha256, sha512  | ✔️ |
| Error Level Analysis | ✔️ |
| Full GPS support  | ✔️ |
| Perceptual Image Hashing | ✔️|
| aHash | ✔️ |
| pHash | ✔️ |
| dHash | ✔️ |
| wHash | ✔️ |




Comments and Suggestions are welcome 👍 


## 📑 Copyright
Code copyright 2020 Ishantha Udara

