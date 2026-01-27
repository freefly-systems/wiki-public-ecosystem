---
description: High Res Mapping Payload Output Specification
---

# Output Specification

The standard workflow for mapping with Astro takes photos from the camera, geotags them, and writes them to the attached USB stick. The usb stick will contain data from each flight in separate folders.&#x20;

{% hint style="info" %}
Photos can be saved to either SD card or USB drive. \
\
When photos are saved to the SD card, no geotag is applied. However, all other files will be written to USB drive if one is connected, as well as small thumbs of the RAW photos.
{% endhint %}

### **Directory structure on the USB drive is as follows**

### Folder name

Naming: <`SequentialFlightNumber>_<DATE>_<TIME>`

There may be multiple folders that start with the same <`SequentialFlightNumber>` if photos were taken on the ground but without a flight.

Each folder will contain the following:

#### Observation file: \<SequentialFlightNumber>\_\<DATE>\_\<TIME>.obs

This file contains the GNSS observations from the aircraft's RTK GPS, and is used in conjunction with the base station data to precisely locate the astro in space. The file also includes RTKlib-style "marker" entries at the timestamp when each photo was taken

#### &#x20;Photo capture information file: \<SequentialFlightNumber>\_\<DATE>\_\<TIME>-sequence.json

This JSON formatted file includes the precise timestamp and gimbal angle for each photo captured.

#### Aircraft capture state information file: imagelog.json

This JSON formatted file includes the aircraft position, attitude, timestamp, and capture url for each photo taken.&#x20;

#### **Photo capture information file**

Name: `YYYY-MM-DD-[SequentialNumber matching directory].json`

#### **Photos**

File type: JPG

Naming: per camera settings

Geotags: Each photo is geotagged in its EXIF header, including geographic position and altitude in WGS84 (GPS) coordinate frame. The altitude in the aircraft geotags is based on the EGM96 geoid.

Note that additional tag information may be written later when post processed by a PPK app.

#### **thumb**

This folder contains small 512x341 thumbnails of the photos taken. They are geotagged as well, and are sometimes useful to upload to a photo photogrammetry site such as ESRI sitescan to ensure that photos are geotagged as expected. They can even be used to create a quick, coarse map.

## Example output

[Link to example datasets](https://drive.google.com/file/d/1N9WW4LT2t7WqmPISMYEeWG79VP3nVQxp/view?usp=sharing). These datasets have been copied from the USB drive attached to Astro.

Note that Base Station observation files are also included in separate folders in case you'd like to perform PPK.

## Camera Calibration Parameters

This is a set of example calibration values for the Sony A7R-IV with Sigma 24 mm lens, which can be used for photogrammetry initial conditions. The LR1 also matches this specification with the 24mm lens. Each lens is slightly different, but these values are good initial values if the software in use can't solve them directly.

| Parameter                  | Value    |
| -------------------------- | -------- |
| Focal Length (mm)          | 24.351   |
| Principle Point X (pixels) | 4714.485 |
| Principle Point Y (pixels) | 3172.286 |
| R1                         | -0.017   |
| R2                         | 0.071    |
| R3                         | 0.009    |
| T1                         | 0.001    |
| T2                         | 0        |

