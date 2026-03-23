# Doodle Channel Selection

## Channel Selection

Unlike the Herelink radios that automatically hop channels to avoid interferences, the Doodle radios operate on a fixed channel.

It is important to select an optimal channel to maximize radio range and performance.

Astro's Doodle radios operate on the 2.4 GHz band, which is also commonly used by other WiFi systems. By default, units are shipped from factory with channel 3 selected. This is a channel that avoids most of the typical WiFi routers.

### How to scan and change channels

{% hint style="danger" %}
Only change channels on the ground with the aircraft disarmed.
{% endhint %}

{% hint style="success" %}
Update to the latest Pilot Pro app for the most reliable channel scans
{% endhint %}

* Ensure the Astro is powered off prior to scanning
*   Go Pilot Pro App > Radio Settings > Channel Select, then press "Scan"

    <figure><img src="../../../../../.gitbook/assets/image (6).png" alt=""><figcaption><p>Navigating to Radio Settings in the Pilot Pro App</p></figcaption></figure>



    <figure><img src="../../../../../.gitbook/assets/image (8).png" alt=""><figcaption><p>Starting a Channel Scan in the Pilot Pro App</p></figcaption></figure>
*   After the app starts scanning, a visual is displayed after the scan completes

    <figure><img src="../../../../../.gitbook/assets/image (9).png" alt=""><figcaption><p>Pilot Pro app with Completed Channel Scan</p></figcaption></figure>

    * Older versions needed scans stopped manually. On older versions it's recommended to let the controller scan for 3 minutes for the most accurate results.&#x20;
      * Losing connection is expected when scanning/changing channels.
      * To stop scanning in older versions, do one of the following: Change a channel, stop scanning manually, go to a different menu, or exit app. This will take a few seconds.
* After scanning, the best channels available will show as a bar graph, and color code by quality
  * While new versions show absolute quality, old versions of the Pilot Pro app rate by relateive quality with the best radio space is highlighted with green.
* Turning on the aircraft, waititing for connection, and tapping on any of the channel numbers will initiate a channel switch.
  * It will take up to a minute for the system to change channels on both sides and confirm that change has been applied successfully.
* Starting in Pilot Pro app version 2.6.2, more detailed statistics can be found in the Advanced menu of the radio configuration

<figure><img src="../../../../../.gitbook/assets/image (10).png" alt=""><figcaption><p>Accesing Doodle Labs Scan Diagnostics</p></figcaption></figure>

<figure><img src="../../../../../.gitbook/assets/image (13).png" alt=""><figcaption><p>Pilot Pro Scan Diagnostics</p></figcaption></figure>

## Doodle Channel Allocation

Each channel is a 10MHz channel and follows the same center frequency as 2.4GHz Wifi with the following allocations:

<table><thead><tr><th>Channel Number</th><th>Center Frequency (MHz)</th><th>Frequency Range (MHz)</th><th data-hidden></th></tr></thead><tbody><tr><td>1</td><td>2412</td><td>2407-2417</td><td></td></tr><tr><td>2</td><td>2417</td><td>2412-2422</td><td></td></tr><tr><td>3</td><td>2422</td><td>2417-2427</td><td></td></tr><tr><td>4</td><td>2427</td><td>2422-2432</td><td></td></tr><tr><td>5</td><td>2432</td><td>2427-2437</td><td></td></tr><tr><td>6</td><td>2437</td><td>2432-2442</td><td></td></tr><tr><td>7</td><td>2442</td><td>2437-2447</td><td></td></tr><tr><td>8</td><td>2447</td><td>2442-2452</td><td></td></tr><tr><td>9</td><td>2452</td><td>2447-2457</td><td></td></tr><tr><td>10</td><td>2457</td><td>2452-2462</td><td></td></tr><tr><td>11</td><td>2462</td><td>2457-2467</td><td></td></tr></tbody></table>
