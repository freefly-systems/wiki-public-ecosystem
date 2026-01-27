# Protips, Limitations, and Troubleshooting

## First things first&#x20;

{% hint style="success" %}
The Wiris Pro Payload is supported in Astro firmware version 1.3.2 or later. Update your astro!
{% endhint %}

{% hint style="info" %}
Make sure to update AMC to the latest version too!
{% endhint %}

{% embed url="https://freefly.gitbook.io/astro-public/astro/maintenance-manual/software" %}

## #Protips

{% hint style="success" %}
Slow speed mode makes the gimbal easier to precisely control when zooming in.
{% endhint %}

&#x20;Learn about it under the [Precise Gimbal Control](../payload-maintenance/precise-smooth-gimbal-control.md) section

{% hint style="success" %}
If you want images to be geotagged, insert a USB thumbdrive in Astro and set the image storage mode to 'External USB'
{% endhint %}

{% hint style="warning" %}
Be careful not to become disoriented when flying with the camera zoomed in. We recommend resetting the camera zoom to 1x before flying to a new inspection location.
{% endhint %}



## Limitations

#### Gimbal

{% hint style="warning" %}
Do not hotswap or plug in the gimbal when the aircraft is powered on. This can damage the aircraft or gimbal
{% endhint %}

{% hint style="warning" %}
Make sure you are using the correct vibration isolator
{% endhint %}

More details can be found in the isolator section

#### Wiris&#x20;

{% hint style="info" %}
The Wiris Pro takes about 3 minutes to fully calibrate the thermal sensor. You can still use the camera right after boot, but temperature readings may be slightly off
{% endhint %}

{% hint style="info" %}
Make sure to eject the Wiris drive from you computer before unplugging the cable. Power cycle the aircraft and gimbal before capturing any additional video or photos.&#x20;
{% endhint %}

{% hint style="info" %}
The video feed may stop after disconnecting from a PC. This is normal, the video will resume after a reboot of the aircraft
{% endhint %}

{% hint style="danger" %}
**Do NOT format the SSD of the Wiris Pro when connected to a PC. This can brick the camera and will require it being sent back for repair.**&#x20;
{% endhint %}

Check out the [Formatting Media section](operating-handbook/downloading-media-example-output.md) for more info

## Troubleshooting

#### Video doesn't come up

{% hint style="info" %}
Occasionally, we have observed that the Wiris Pro gets 'stuck' during bootup. If you are having trouble getting connecting to the camera, check status light on the back of the camera. If the camera has flashing red/blue lights or a solid red light, this is likely the case. In our testing, rebooting the aircraft resolves this issue.&#x20;
{% endhint %}

#### IR video is black

This can happen if the thermal exposure is set very far off from what the camera is looking at.&#x20;

{% hint style="info" %}
Set the thermal exposure mode to auto or adjust your exposure temperature in the camera settings menu
{% endhint %}

#### Gimbal tilt controls are backwards

{% hint style="info" %}
You can invert the gimbal tilt control under camera settings
{% endhint %}
