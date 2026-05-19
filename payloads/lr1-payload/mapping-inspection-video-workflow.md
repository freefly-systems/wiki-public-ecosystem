# Workflows - Mapping, Inspection, Video, Photography

## Mapping Workflow

{% content-ref url="../../workflows/photogrammetry-mapping/" %}
[photogrammetry-mapping](../../workflows/photogrammetry-mapping/)
{% endcontent-ref %}

## Inspection Workflow

{% content-ref url="../../workflows/infrastructure-inspection.md" %}
[infrastructure-inspection.md](../../workflows/infrastructure-inspection.md)
{% endcontent-ref %}

## Photography Workflow

With aircraft firmware 2.2.6, the LR1 payload can shoot in RAW or RAW+JPEG format, unlocking professional high resolution photography applications.

<figure><img src="../../.gitbook/assets/DSC00409.jpg" alt=""><figcaption><p>Shot on Astro + LR1 payload + Sony 24mm F1.4 GM</p></figcaption></figure>

The LR1 payload is natively compatible with [5 lenses.](https://docs.freeflysystems.com/ecosystem/payloads/lr1-payload/lr1-lenses-and-expansion) Other lenses can be used, but may require balancing weights and [custom gimbal tuning](https://docs.freeflysystems.com/ecosystem/payloads/lr1-payload/lr1-lenses-and-expansion/changing-lenses/advanced-gimbal-tuning).&#x20;

Full frame or APS-C mode is selectable as well. Focus options can be selected between AF-S wide, zone, center, tap-to-focus, and infinity (supported 24, 35, and 50mm only).&#x20;

{% hint style="info" %}
Due to the file size of RAW photos, all RAW images will be saved to the camera SD card. We recommended using a sufficiently fast SD card for quick write speeds.
{% endhint %}

## Video Workflow

The LR1 Payload was primary designed for photography applications (mapping, inspection, scenic photography), but can shoot video as well.

{% hint style="success" %}
Smoother gimbal control and additional parameters were added in Astro FW 2.0! Check it out here:
{% endhint %}

{% content-ref url="../../controller/pilot-pro/operating-handbook/rate-controls.md" %}
[rate-controls.md](../../controller/pilot-pro/operating-handbook/rate-controls.md)
{% endcontent-ref %}

## Video Settings

The camera is capable of shooting up to 4K, 60 fps footage in 8 bit or 10 bit, with normal and Slog profiles

{% hint style="info" %}
A V90 Class SD card is needed for some recording modes. The LR1 Payload ships with a V60 Class SD card which is fast enough for 4K30 fps 8 bit footage.
{% endhint %}

The External USB drive isn't fast enough to record high quality video, so videos will save the camera's SD card.

You can switch between taking images and video footage using this button in Photo Mode:

<figure><img src="../../.gitbook/assets/image (6) (1).png" alt=""><figcaption></figcaption></figure>

## #Protips

{% hint style="danger" %}
The Sony ILX-LR1 can get very hot when recording video, especially high frame rate and high bitrate footage. If the camera gets too hot, it will shutdown!
{% endhint %}

{% hint style="info" %}
We recommend flying in 'Slow mode' for smooth/precise yawing motions with the gimbal. Setting the vertical/horizontal speeds to max is speeds as Position mode, but allows precise control over the yaw rate of the aircraft. This is particularly useful for longer lenses
{% endhint %}

* We have been getting good video results with the Sigma 24mm, Sony 35mm lenses, and Sony 50mm. The Samyang 75mm can sometimes have issues with stability during acceleration and deceleration.
* If you are seeing any vibrations in the footage, check:
  * You are using the right vibration isolator
  * The gimbal is balanced properly
