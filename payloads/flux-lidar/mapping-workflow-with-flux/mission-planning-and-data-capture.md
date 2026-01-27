# Mission Planning and Data Capture

## Plan a mission in AMC <a href="#setup-your-gnss-base-station" id="setup-your-gnss-base-station"></a>

{% hint style="success" %}
Flux sensor presets are available in AMC under the camera presets. Update to AMC version 1.36.22 or later
{% endhint %}

In AMC, go to the plan screen and tap Pattern --> Survey or Corridor Scan and draw out the area you would like to scan.

Next, select your Flux variant under the camera settings. This will apply the default settings for Flux and simplify the mission planning process.&#x20;

<figure><img src="../../../.gitbook/assets/image (181).png" alt=""><figcaption></figcaption></figure>

We recommend the following mission settings for Flux:&#x20;

|                  | Flux H1                                                                                         | Flux L1                                                                                         | Flux O1                                                                                         |
| ---------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------- |
| Flight Height    | Between 20 m to 150 m, depending on surrounding obstacles.                                      | Between 20 m to 150 m, depending on surrounding obstacles.                                      | Between 20 m to 150 m, depending on surrounding obstacles.                                      |
| Track Separation | Set automatically if Flux H1 is selected                                                        | Set automatically if Flux L1 is selected                                                        | Set automatically if Flux O1 is selected                                                        |
| Speed            | 2 to 15 m/s, depending on the point density required. The slower, the higher the point density. | 2 to 10 m/s, depending on the point density required. The slower, the higher the point density. | 2 to 15 m/s, depending on the point density required. The slower, the higher the point density. |

{% hint style="info" %}
If you are using terrain following, use max climb and descent rates <1.5 m/s
{% endhint %}

## Connecting an iPad to Pilot Pro <a href="#start-lidar-capture-and-execute-the-mission" id="start-lidar-capture-and-execute-the-mission"></a>

In the app store, download the Freefly Flow app. Then, follow these instructions to connect your iPad to Pilot Pro using the included ethernet to USB-C cable.&#x20;

{% embed url="https://freefly.gitbook.io/pilot-pro-public/operating-handbook/ecosystem#adding-a-second-tablet-ipad" %}

Use the following settings on the iPad:&#x20;

* IP address: 192.168.144.120
* Subnet mask: 255.255.255.0&#x20;

## Start LiDAR capture and execute the mission <a href="#start-lidar-capture-and-execute-the-mission" id="start-lidar-capture-and-execute-the-mission"></a>

When you are ready to execute your planned mission, power on the drone. The LiDAR sensor will start loading, and the LED will blink blue. Once it is ready for data capture, the LED will turn solid green.

If an iPad is connected to Pilot Pro, you can connect the Flow app to Flux and see Flux status including:

* GNSS satellites and accuracy
* Lidar scanning mode and points/second
* USB storage remaining
* Internal temperature

{% hint style="success" %}
Flux relies heavily on GNSS for good performance



For the best results, wait for the left and right GNSS modules to both have 22+ satellites for >1 minute before starting to record and takeoff
{% endhint %}

Before takeoff, push the REC button on the Flux LiDAR or in the Flow app to start capturing LiDAR data. Once the LED turns red, begin flying the mission. There is no need for calibration figures or particular paths.

{% hint style="info" %}
The L1 will likely display 0 pts (red) while Astro is on the ground. This is normal, the L1 minimum range is 1 meter and L1 will be able to collect points while flying.
{% endhint %}

{% hint style="info" %}
Flux will calibrate itself on the way to the entry point of the mission.&#x20;



We recommend placing the start point as the farthest point from the takeoff point. This will give Flux the best calibration and will allow Astro to be closer to the home point at the end of the mission, allowing for longer flight times before the time-based RTL triggers
{% endhint %}

<table data-header-hidden><thead><tr><th align="right"></th><th width="249"></th><th></th></tr></thead><tbody><tr><td align="right"><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdCjObRNycudiUoGxd8H4%2Fuploads%2FOtUUeXkhfx66sXm6bn28%2Fblue.png?alt=media&#x26;token=999289e1-3d69-4d89-b7d4-b2620c4b54f1" alt="" data-size="line"></td><td>Blinking Blue</td><td>Sensor loading</td></tr><tr><td align="right"><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdCjObRNycudiUoGxd8H4%2Fuploads%2Fq66HlJfrtQVvIaJfDoqy%2Fyellow.png?alt=media&#x26;token=cb38ed89-fb0d-4fcb-acd3-d38a621c9383" alt="" data-size="line"></td><td>Blinking Yellow</td><td>GNSS starting and acquiring satellites</td></tr><tr><td align="right"><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdCjObRNycudiUoGxd8H4%2Fuploads%2FkN4Z038eVTNDY5xbumMj%2Fmagenta.png?alt=media&#x26;token=6cd3b3a6-f573-4a10-83f9-544bdcb8b1ee" alt="" data-size="line"></td><td>Blinking Magenta</td><td>Flash drive missing, not ExFAT formatted or busy after recording.</td></tr><tr><td align="right"><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdCjObRNycudiUoGxd8H4%2Fuploads%2FULg4zqxa6aVKIiCAjtPx%2Fgreen.png?alt=media&#x26;token=b6d1b197-612b-477e-8123-106e092976f3" alt="" data-size="line"></td><td>Solid Green</td><td>Sensor ready to start LiDAR capture. Standby.</td></tr><tr><td align="right"><img src="https://files.gitbook.com/v0/b/gitbook-x-prod.appspot.com/o/spaces%2FdCjObRNycudiUoGxd8H4%2Fuploads%2F0wgDLOiN8jKDdMWw2Btv%2Fred.png?alt=media&#x26;token=7b84228b-12b1-4a61-96b6-c4376d3d93f9" alt="" data-size="line"></td><td>Solid Red</td><td>Sensor recording.</td></tr></tbody></table>

After landing, push the REC button to stop recording, either in the app or on the lidar. The LED will start blinking magenta, indicating the Flash Drive is busy. Once it is ready, the LED will go back to solid green.

{% hint style="danger" %}
Remember to stop recording before turning off the aircraft! If Flux is powered down while recording, the scan data will be corrupted and may not be recoverable.&#x20;
{% endhint %}

## Process your LiDAR data in the field just after landing <a href="#process-your-lidar-data-in-the-field-just-after-landing" id="process-your-lidar-data-in-the-field-just-after-landing"></a>

Remove the Flash Drive from the LiDAR sensor and connect it to the iPad to process the data

{% content-ref url="processing-lidar-data-on-an-ipad.md" %}
[processing-lidar-data-on-an-ipad.md](processing-lidar-data-on-an-ipad.md)
{% endcontent-ref %}
