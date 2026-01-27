# Auterion Suite / Flight Logs

![The Auterion Suite: The centerpiece of your drone operation](../.gitbook/assets/Mouse%20Highlight%20Overlay%202022-05-18%2010.19.13.png)

Manage your enterprise robotics program with Auterion Suite. The Suite is where the data of your fleet is collected, analyzed and presented. Get insights on vehicles, assets and operations to keep control over your robotics program. With Auterion-powered vehicles data is delivered automatically and in real-time from the fleet to the Suite – while the drones are flying and without any manual intervention. [Learn more about the Auterion Suite on Auterion's website.](https://auterion.com/enterprise/suite/)

Freefly aircraft are built to easily integrate into the Auterion Suite and many features are enabled through this platform:

* Manage your aircraft fleet
* Access detailed flight logs, check vehicle status
* Direct Freefly customer support with integrated flight log sharing and review
* Get software updates
* [Live video sharing capabilities](https://auterion.com/enterprise/suite/live-video-feeds/)
* [Auterion's documentation](https://docs.auterion.com/vehicle-operation/auterion-suite-fleet-management) covers the Suite in depth

## How to Sign Up for the Auterion Suite and Register Your Aircraft

{% embed url="https://www.youtube.com/watch?v=3cfPFp3I17s" %}

**Watch this Quick Start video showing how to sign up and unlock the powers of your aircraft in the Auterion Suite**

{% hint style="info" %}
**Platform-Specific Notes**

* **Astro**: IO panel is on the underside of the aircraft. Use one SL8 battery.
* **Alta X Gen2**: IO panel location varies. Use one SL12 battery.

Using only one battery prevents the danger of accidentally arming the aircraft during USB setup.
{% endhint %}

1. Using a computer, connect a USB-C cable from your computer to the IO panel on the aircraft.
2. Power on the aircraft with one battery.
   * **This physical connection to the aircraft is required for security reasons as the Suite enables location data, live streaming, etc.**
3. Using a web browser, go to the following address to connect to the aircraft: [**`http://10.41.1.1`**](http://10.41.1.1)
4. This page will allow you to sign up for the Suite as well as automatically register and claim the aircraft. Click "Register Now" or scan QR code for mobile signup.
   * Note: This requires the vehicle to be online to generate a signup QR code otherwise it'll say "internet required" for the registration prompt.
   * Connect your aircraft to the internet using a WiFi or LTE network. See your aircraft's Network & Connectivity documentation:
     * [Astro Network & Connectivity](https://freefly.gitbook.io/astro-public/pilots-operating-handbook/essential-software/network-and-connectivity)
     * [Alta X Gen2 Network & Connectivity](https://freefly.gitbook.io/alta-x-gen2/pilots-operating-handbook/essential-software/network-and-connectivity)
   * If the aircraft is connected to the internet and plugged into the computer and [http://10.41.1.1](http://10.41.1.1) does not show the Register Now button, try refreshing your browser.
5. Once complete, you should see the aircraft listed under the "Vehicles" Section on the main dashboard of the Auterion Suite.
6. Go Fly!

**Alternate Signup Methods**

* Another signup method is to sign up for the Auterion Suite directly from Auterion's website.
* If you use this method, you won't have any vehicles registered for your Suite account unless you add them manually!
* You can add an aircraft using the aircraft serial number under the Vehicles page, but note that data sharing will be limited until you physically connect your aircraft to a laptop and validate you have physical access to the drone.
* To physically register an aircraft that was added by serial number, you'll need to connect the aircraft to a wifi network, then connect physically to a computer and visit [http://10.41.1.1](http://10.41.1.1) in your browser. Click the large Register button on this screen and sign in to Auterion Suite to complete the process.

## Getting Data into the Suite

Aircraft will automatically upload flight log files to the Suite when connected to the internet via WiFi or LTE.

## Flight Logs

The autopilot automatically creates log files that record the aircraft's flight path, inputs received, outputs sent, and more.

Log files are stored to the onboard SD card. If the aircraft is registered in the Auterion Suite, it will automatically upload flight log files to the Suite when a WiFi or LTE connection is available. Logs can also be downloaded to a PC.

Flight logging starts when the aircraft is armed, and ends when it is disarmed.

## Logs in the Suite

The easiest way to view the logs is with an [Auterion Suite account](https://docs.auterion.com/vehicle-operation/auterion-sign-up) (Basic version is free).

[Navigate to a particular flight](https://docs.auterion.com/vehicle-operation/auterion-suite-fleet-management/flights) to see many plots showing data such as angles, position, speed, GPS quality, vibration, etc. It will also show the build information, parameter values, and any errors detected in the flight.

The Suite allows sharing log files with the Freefly Support Team.

### Sharing Flight Logs with Support

To ask Freefly about a problem with a particular flight, use the "Share with Manufacturer" toggle.

![](../.gitbook/assets/image%20(64).png)

## Logs without the Suite

If you're not able to use the Suite, it's possible to download log files from the aircraft to a PC via USB.

### Downloading

Logs are stored in the onboard SD card in "[ulog](https://dev.px4.io/v1.9.0/en/log/ulog_file_format.html)" format. Use this procedure to download them.

Requirements: Aircraft, 1 battery, USB-C cable, [AMC PC](https://suite.auterion.com/downloads), and an Auterion Suite account (you can create a free account [here](https://docs.auterion.com/vehicle-operation/auterion-sign-up); an account is required to download AMC PC).

|    |                                                                                                         |
| -- | ------------------------------------------------------------------------------------------------------- |
| 1. | Connect a USB cable from the aircraft's IO panel to a PC                                                |
| 2. | Install one battery and power up the aircraft                                                           |
| 3. | Open [AMC PC](https://suite.auterion.com/downloads) and [activate Advanced mode](auterion-mission-control/amc-vehicle-setup/parameters.md) |
| 4. | Navigate to "Analyze" menu, select "Log Download"                                                       |
| 5. | Click "Refresh" to load the logs                                                                        |
| 6. | Select desired files and click "Download"                                                               |

{% hint style="warning" %}
QGroundControl (QGC) can be used in place of AMC PC for this procedure. However, QGC should not be used for any other purpose with Freefly aircraft as it may not accurately represent the state of the aircraft and can corrupt parameters.
{% endhint %}

{% hint style="info" %}
If AMC/QGC does not connect to the aircraft, check that it is communicating with your computer by opening a web browser and navigating to [http://10.41.1.1](http://10.41.1.1/). The aircraft's information page should load. If not, try rebooting the aircraft, remating the cable, and restarting AMC/QGC.
{% endhint %}

{% hint style="info" %}
**Downloading logs via USB is faster and more reliable.** While it is possible to download flight logs over a WiFi connection, it is considerably slower.
{% endhint %}

{% hint style="warning" %}
If internal storage is full, the earliest logs will be deleted from the aircraft to make room for the latest flight log.
{% endhint %}

### Viewing and Analysis

The easiest tool to use is [http://logs.px4.io](http://logs.px4.io). Simply upload a ulog file. It will present thorough analysis via plots showing data such as angles, position, speed, GPS quality, vibration, etc. It will also show software build information, parameter values, and any errors detected in the flight.

For other purposes, there are a variety of other [flight log analysis tools](https://docs.px4.io/v1.9.0/en/log/flight_log_analysis.html#analysis-tools).

* Using the Auterion Suite to share aircraft logs with Freefly Support (by clicking on the "Share with manufacturer" button) is the easiest and quickest way to get Freefly support and get your aircraft back in the air after an issue.

## Privacy, Data Sharing, and Security

Freefly and Auterion think of data generated by your aircraft, including flight logs, as your property. We think it's important that you are in control of your data, are confident in the measures taken to ensure security, and agree with how the data is used.

The Auterion Privacy Policy gives a layperson's description of how data can flow from the aircraft, through the Suite, and to partners you choose.

Briefly, when an aircraft is registered with a Suite account, you can choose to have flight logs automatically uploaded from the aircraft to Auterion servers when an internet connection is available. You can review this data in your Suite account. Auterion employees do not have access to your data. You may choose to share individual flight logs with Freefly Support via the Suite, for example to troubleshoot details of a specific flight.

* Freefly and Auterion understand the need for full data control and user privacy so we have built this platform for maximum user control.
* The aircraft comes with hardware to support WiFi and LTE connections to the internet or other devices.
  * If you do not want the LTE to connect, do not install a SIM card for data connection
  * If you do not want the aircraft to connect to WiFi, do not select any networks or present any passwords. You can also disable WiFi on the pilot handset.
* For security purposes the user needs to have physical access/connection to the aircraft in order to register it to the Auterion Suite because the Auterion Suite enables log uploads, live unit status tracking, live video streaming etc.

{% hint style="info" %}
Learn more about your aircraft's internet connections in the Network & Connectivity documentation:
* [Astro Network & Connectivity](https://freefly.gitbook.io/astro-public/pilots-operating-handbook/essential-software/network-and-connectivity)
* [Alta X Gen2 Network & Connectivity](https://freefly.gitbook.io/alta-x-gen2/pilots-operating-handbook/essential-software/network-and-connectivity)
{% endhint %}
