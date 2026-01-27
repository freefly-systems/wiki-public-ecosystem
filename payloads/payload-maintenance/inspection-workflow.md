# Inspection Workflow

The LR1 and A7R4 can easily be configured to perform inspections on power lines, wind turbines, and other infrastructure! &#x20;



{% embed url="https://www.youtube.com/watch?v=A-CbErLYLuw" %}
How to use LR1 + Astro for inspection
{% endembed %}

<figure><img src="../../../.gitbook/assets/DSC00891.JPG" alt="" width="563"><figcaption><p>Sample Inspection Image (75mm Lens)</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (35) (1).png" alt="" width="563"><figcaption><p>Cropped detail section of above photo</p></figcaption></figure>

## Gimbal Setup&#x20;

For inspection use cases, we recommend using a long lens to maintain a safe distance from your subject. We have found that both the Sony FE 50mm F1.8 and Samyang 75mm F1.8 (LR1 only) work well.&#x20;

{% hint style="info" %}
The Samyang 75mm may need a [lens firmware update](https://www.samyanglens.com/en/support/support-download.php?type=3\&model=SONY) to work well in autofocus mode with the LR1&#x20;
{% endhint %}

After changing the lens, make sure to balance the gimbal, covered in this section:&#x20;

{% content-ref url="../lr1-payload/lr1-lenses-and-expansion/changing-lenses/" %}
[changing-lenses](../lr1-payload/lr1-lenses-and-expansion/changing-lenses/)
{% endcontent-ref %}

## Camera Setup

We recommend the following camera settings for sharp, detailed images:&#x20;

| Name               | Setting Range       | Explanation                                                                                                                         |
| ------------------ | ------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| Shutter Speed      | 1/4000 to 1/100th   | A faster shutter speed reduces motion blur                                                                                          |
| Aperture           | F5 or higher        | Higher the aperture makes more parts of the image in focus                                                                          |
| ISO, White Balance | Auto                | Auto for these usually work well                                                                                                    |
| JPEG Size          | Large               | More detail = better!                                                                                                               |
| Image Storage      | External USB        | Images are geotagged when saved to the external USB. This allows images to be associated with specific assets like power line poles |

All of these parameters can be setup in AMC, accessed by the 3 lines under the shutter button\
\
Additional settings we recommend:

* Focus: Auto or Tap-to-focus
* Focus mode: Center or Zone (if not using tap to focus)
* Overlay: Reticle&#x20;

## #protips&#x20;

{% hint style="warning" %}
DIU Blue Astros come with stealth logging enabled, which stops GPS data from being written to imagery and logs. [Stealth logging must be disabled](https://freefly.gitbook.io/astro-public/other-user-manuals/ecosystem/diu-blue-suas#logging) to allow GPS data to be written to photos
{% endhint %}

* Download the offline maps for the area you will be flying in&#x20;
* Check the vibration isolators are in good condition before each flight
* Check the gimbal is balanced and the thumbscrews are tight&#x20;

{% hint style="success" %}
Astro is resistant to electromagnetic interference created by high voltage power lines with our Compassesless algorithm! Make sure Astro is updated to 1.6 or later&#x20;



Pilots should still be careful when flying close wires and towers as these can often be difficult to see
{% endhint %}

{% hint style="warning" %}
Be careful when flying under structures! Astro can lose GPS signal and drift
{% endhint %}

{% hint style="warning" %}
Be careful when flying near wind turbines! Astro can fly in winds up to 12m/s (27mph), above this Astro will trigger RTL.



The current estimated windspeed is displayed in the lower right-hand corner of AMC in flight
{% endhint %}
