# \[Beta] Flux Desktop App

## Flux Desktop App - \[Beta] Quick Start Guide

The Flux Desktop App enables SLAM-like alignment and cross-platform support for Fluxscan files, as well as several other small improvements.

{% embed url="https://youtu.be/pUIqPO8AGWo" %}

### New Features/Differences from Flow App

* SLAM-like alignment engine for super sharp scans&#x20;

{% hint style="info" %}
Recommended 32GB RAM or higher. Some large scans may need more than this
{% endhint %}

* Greater OBS file flexibility
  * Can process with only L1/L2 signals, or no OBS file&#x20;
* More CRS flexibility
* Windows, Mac, Linux support

### Installing

Currently, the Flux Desktop app is a closed beta program. Reach out to support@freeflysystems.com if you are interested in joining.

Check your email for a link to download the app

{% tabs %}
{% tab title="Windows" %}
* Unzip the file
* Navigate to the viewer\_cpp-windows-x64/viewer\_cpp.exe file
* Double click to open it
  * You may need to agree to 'run anyway' to open the program
{% endtab %}

{% tab title="Mac" %}
* Open the folder, then drag the app in the Applications folder
* Double click the app in the Applications folder
  * You may need to click 'ok' to allow the app to open
{% endtab %}
{% endtabs %}

### Processing a Fluxscan

#### Import the file

<img src="../../.gitbook/assets/unknown (5).png" alt="" height="194" width="499">

#### Set the Obs file source and CRS.&#x20;

* If Flux was flown with NTRIP was used, this will be selected by default&#x20;
  *

      <img src="../../.gitbook/assets/unknown (6).png" alt="" height="196" width="516">
  * You can also use an external base station or CORS file. Ensure you have selected the correct coordinates for the base station point and CRS
  * Unlike the Flow app, Obs files with only L1/L2 signals can be used.&#x20;
  * The Flux Desktop app can also process without a base station file

{% hint style="warning" %}
&#x20;The scan may have a decrease in global/relative accuracy and sharpness compared to using an OBS file
{% endhint %}

#### Device Geometry

*   Select the aircraft and isolator type you flew the mission with. This is important for calculating offsets from the GNSS antennas&#x20;

    <img src="../../.gitbook/assets/unknown (7).png" alt="" height="295" width="464">

#### Solver&#x20;

* Select the Advanced alignment option, Normal works well in the vast majority of cases
*

    <img src="../../.gitbook/assets/unknown (8).png" alt="" height="249" width="624">

{% hint style="info" %}
The default is to do a Trajectory Solve only, which will not use the SLAM-like alignment feature. We recommend using the Normal advanced alignment
{% endhint %}

#### Project Coordinates

* Set as desired. You don't have to specify a coordinate frame unless you want to
*

    <img src="../../.gitbook/assets/unknown (9).png" alt="" height="151" width="481">

#### GCPs

* GCPs can be imported if desired, but are not required

{% hint style="success" %}
GCPs are not used to align the map or modify the point cloud, and are only shown as reference
{% endhint %}

#### Process

* On the Summary and Process page, click Process and Align
* The progress is shown on the bottom bar

{% hint style="info" %}
Known issues:

* The estimated processing times given are not accurate
* The Trajectory Solve process may take a few minutes, but the progress bar will remain at 0%. This is normal
{% endhint %}

#### View

* Once the process is complete, you can view the scan in the View tab
* Multiple options exist to view and adjust color pallets, color mode, and more

{% hint style="success" %}
Protip: if your machine can handle it, you can increase the viewable points under the settings>display>point cloud display budget for a more detailed view of the scan&#x20;
{% endhint %}
