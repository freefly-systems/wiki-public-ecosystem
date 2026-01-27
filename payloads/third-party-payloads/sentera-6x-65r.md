# Sentera 6X/65R



<figure><img src="../../.gitbook/assets/Astro-6X.png" alt=""><figcaption></figcaption></figure>

Astro can fly both the Sentera 6X and 65R!

Both payloads are compatible with Astro using the Smart Dovetail connector, which sends power and capture commands to the cameras in flight.&#x20;

## Setup

{% embed url="https://youtube.com/shorts/dvRUX83XV48?feature=share" fullWidth="false" %}

* Upgrade the payload software to a compatible version (3.7.0+). Follow the Sentera documentation found [here](https://support.sentera.com/portal/en/kb/articles/firmware-upgrade-6x#6X_Firmware________6X_Thermal_Firmware_______________Download_Update_352_Part__21214_______Download_Update_352_Part__21216).

{% hint style="success" %}
Live video for 65R and other features are available with a firmware update! V4.1.3
{% endhint %}

{% hint style="info" %}
[65R installation for Astro](https://sentera.gitbook.io/65r-sensor-user-guide/65r-sensor/installation/freefly-astro)

[6X Installation for Astro](https://sentera.gitbook.io/6x-multispectral-sensor-user-guide/6x-multispectral-sensor/installation/freefly-astro)
{% endhint %}

* Install the payload in the Smart Dovetail mount
* Install the GPS mast and cabling securely&#x20;

{% hint style="danger" %}
Make sure any cables are constrained and can't get caught in the propellers
{% endhint %}

## Mission Planning

As of Astro firmware v1.5 or later, the 6X and 65R camera settings are selectable in the survey dropdown of the plan screen. Simply select the camera you are using and adjust the mission flight path as needed.&#x20;

See Sentera's wiki for the recommended flight settings:&#x20;

* [65R User Guide](https://sentera.gitbook.io/65r-sensor-user-guide)
* [6X User Guide](https://sentera.gitbook.io/6x-multispectral-sensor-user-guide)

{% hint style="info" %}
**When planning a mission in AMC** - Be sure to set the Camera Action field to 'Survey' and at the bottom of the settings page. This will set the camera to be triggered to take photos during the mission
{% endhint %}



## Post Processing

[65R Data Offload Process](https://sentera.gitbook.io/65r-sensor-user-guide/65r-sensor/data-offload/offload-process)

[6X Data Offload Process](https://sentera.gitbook.io/6x-multispectral-sensor-user-guide/6x-multispectral-sensor/data-offload/offload-process)

{% hint style="success" %}
Use **192.168.42.1** for the IP address
{% endhint %}

{% hint style="info" %}
You MUST plug in the USB-C to pull data, data is not stored on the SD card on the Astro thumbdrive.
{% endhint %}

#### Tips:

* Turn off your computer wifi connection and ensure the wired network connection is showing connected to "Sentera 65R".&#x20;
  * Sentera 65R (use this one) > "Data" folder > "snapshots" folder > select date of flight (folder)s
  * Sentera 65 SMB (don't use this one)
* If you leave the Astro on or hotswap between missions, it'll save all the image in the same folder (annoying for post processing) so ensure you power cycle between missions to make processing easier (create seperate folders).
* In Field Agent (sentera's processing software)
  * Create the field boundary
    * Then in the field menu select said field
    * Go to the map layers tab
    * press the + button in the right corner of the tab
    * Select individual photos from the upload map layer menu
    * Add the images to the upload section

## Technical Specifications

|                          | Sentera 6X Multispectral                                                                                                                                                          | Sentera 6X Thermal                                                                                                                                                                                           | Sentera 65R               |
| ------------------------ | --------------------------------------------------------------------------------------------------------------------------------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | ------------------------- |
| Resolution               | <p>2048px by 1536px (Multispectral) </p><p>5184px by 3888px (RGB)</p>                                                                                                             | <p>2048px by 1536px (Multispectral) </p><p>5184px by 3888px (RGB) </p><p>320px by 256px (Thermal)</p>                                                                                                        | 9344px by 7000px          |
| Shutter Type             | <p>Global (Multispectral) </p><p>Electronic Rolling Shutter (RGB)</p>                                                                                                             | <p>Global (Multispectral) </p><p>Electronic Rolling Shutter (RGB) </p><p>Shutterless (Thermal)</p>                                                                                                           | Global                    |
| Sensor                   | <p>Sony IMX147 (RGB) </p><p>Sony IMX265 (Multispectral)</p>                                                                                                                       | <p>Sony IMX147 (RGB) </p><p>Sony IMX265 (Multispectral) </p><p>FLIR Boson 320R (Thermal)</p>                                                                                                                 | Gpixel GMAX3265           |
| Power Input              | 10.5 - 26V                                                                                                                                                                        | 10.5 - 26V                                                                                                                                                                                                   | 10.5 - 26V                |
| Power Consumption        | 15W Typical, 18W Max                                                                                                                                                              | 15W Typical, 18W Max                                                                                                                                                                                         | 12W Typical, 15W Max      |
| Capture Rate             | 5 FPS (0.2s interval)                                                                                                                                                             | 5 FPS (0.2s interval)                                                                                                                                                                                        | 3 FPS (0.333s)            |
| Storage                  | 512 GB Internal SSD                                                                                                                                                               | 512 GB Internal SSD                                                                                                                                                                                          | 512 GB NVMe SSD           |
| Filter/Sensitivity       | <p>Blue: 475nm CWL x 30nm </p><p>Green: 550nm CWL x 20nm </p><p>Red: 670nm CWL x 30nm </p><p>Red Edge: 715nm CWL x 10nm </p><p>NIR: 840nm CWL x 20nm </p><p>RGB: IR cut 650nm</p> | <p>Green: 550nm CWL x 20nm </p><p>Red: 670nm CWL x 30nm </p><p>Red Edge: 715nm CWL x 10nm </p><p>NIR: 840nm CWL x 20nm </p><p>RGB: IR cut 650nm </p><p>Thermal Infrared: </p><p>Radiometric: 8um to 14um</p> | N/A                       |
| Image Format             | <p>8-bit JPEG (RGB)</p><p>12-bit TIFF (MSP)</p>                                                                                                                                   | <p>8-bit JPEG (RGB) </p><p>12-bit TIFF (MSP)</p><p>16-bit TIFF (Thermal)</p>                                                                                                                                 | JPEG                      |
| Weight (With Gimbal)     | 515g with Smart Dovetail                                                                                                                                                          | 515g with Smart Dovetail                                                                                                                                                                                     | 588g with Smart Dovetail  |
| GSD @ 200ft (60m)        | <p>1.0in / 2.6cm (MSP)</p><p>0.4in / 1.0cm (RGB)</p>                                                                                                                              | <p>1.0in / 2.6cm (MSP)</p><p>0.4in / 1.0cm (RGB)</p><p>6.9in / 17.5cm (LWIR)</p>                                                                                                                             | 0.28in (0.7cm)            |
| Field of View            | 47° HFOV (MSP and RGB)                                                                                                                                                            | <p>47° HFOV (MSP and RGB) </p><p>50° HFOV (Thermal)</p>                                                                                                                                                      | 58° HFOV                  |
| Dimensions (Sensor Only) | 79.5mm x 66mm x 67.5mm                                                                                                                                                            | 79.5mm x 66mm x 67.5mm                                                                                                                                                                                       | 3.5mm x 70.6mm x 106.4mm  |
| Dimensions (With Gimbal) | 111.8mm x 126.2mm x 106.4mm                                                                                                                                                       | 111.8mm x 126.2mm x 106.4mm                                                                                                                                                                                  | 101mm x 144.8mm x 150.6mm |

### Spectral Bands

{% tabs %}
{% tab title="6X Multispectral" %}
<figure><img src="../../.gitbook/assets/image (167).png" alt=""><figcaption><p>Spectral bands of the Sentera 6X Multispectral</p></figcaption></figure>
{% endtab %}

{% tab title="6X Thermal" %}
<figure><img src="../../.gitbook/assets/image (168).png" alt=""><figcaption><p>Spectral bands of the Sentera 6X Thermal</p></figcaption></figure>
{% endtab %}
{% endtabs %}

## More Information

Additional information can be found on Sentera's website:

* [Sentera 6X ](https://sentera.com/products/fieldcapture/sensors/6x/)
* [Sentera 65R](https://sentera.com/products/fieldcapture/sensors/65r/)
