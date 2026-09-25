---
description: >-
  How RTK, NTRIP and PPK differ, and which one fits your Astro or Alta X Gen 2
  workflow.
---

# RTK, NTRIP, PPK: Which One Do You Need?

<figure><img src="../.gitbook/assets/rtk-ntrip-ppk-hero.svg" alt="A drone receiving GNSS signals from satellites while a base station on the ground sends live corrections"><figcaption></figcaption></figure>

Standard GPS puts your aircraft within 1 to 3 m of its true position. GNSS corrections bring that down to centimeters. RTK, NTRIP and PPK are three ways to get those corrections, and each one solves a different problem. A common mistake is buying a base station before knowing which problem you actually have.

{% hint style="info" %}
Short on time? Go to [Which one should I use?](rtk-ntrip-ppk.md#which-one-should-i-use)
{% endhint %}

## Relative accuracy is not absolute accuracy

Most RTK questions we get come down to this. "Centimeter accuracy" can mean two different things, and they come from different places.

<figure><img src="../.gitbook/assets/rtk-ntrip-ppk-accuracy.svg" alt="Three targets: standard GPS scatters widely, relative accuracy is a tight cluster offset from the target, absolute accuracy is a tight cluster on the target"><figcaption><p>Same drone, three outcomes. The cross is the true position.</p></figcaption></figure>

RTK always gives you the tight cluster. Whether that cluster lands on the cross depends on how well the base station knows its own position. A base that averages its position for a few minutes (Survey-In) gives you the middle target. A base on a surveyed point, an NTRIP network, or post-processed base data gives you the one on the right.

{% hint style="warning" %}
**Survey-grade bases vs. the Freefly RTK Base Station**

What makes a surveyor's base station accurate isn't RTK itself. It's the hardware for setting up precisely over a known mark: tribrach mounts, measured antenna heights and calibrated offsets. The Freefly RTK Base Station isn't built for that. It's built to get your aircraft flying with good relative accuracy in a few minutes, without any survey experience. If your deliverables need absolute accuracy, look at NTRIP or PPK below.
{% endhint %}

## Live corrections vs. post-processing

RTK and NTRIP correct position during the flight, over a radio or internet link. PPK corrects it after the flight from log files, so there's no link to lose.

<figure><img src="../.gitbook/assets/rtk-ntrip-ppk-paths.svg" alt="RTK and NTRIP send corrections live during flight; PPK merges base and aircraft log files after the flight"><figcaption><p>When each method applies corrections. The dashed line marks the end of the flight.</p></figcaption></figure>

With RTK and NTRIP, corrections arrive while the aircraft is flying. That improves how it flies, but it also means a link dropout mid-flight shows up in your data. With PPK, the aircraft flies on standard GPS and every position is recalculated after landing from the complete log files. The math is the same, but none of it has to happen in real time.

{% hint style="success" %}
**Absolute accuracy without a surveyed point**

You don't need a survey marker to get absolute accuracy with PPK. You can post-process the base station's own position against a public CORS network (OPUS in the US, with similar services elsewhere). For most operators, that makes PPK the easiest route to absolute accuracy. You can also combine methods: fly with NTRIP for real-time positioning, then run PPK for the final deliverable.
{% endhint %}

## Which one should I use?

Pick the tab that matches your site, then the one that matches your payload and accuracy needs.

**1. Do you have internet or cell coverage at your site?**

{% tabs %}
{% tab title="Yes, I have coverage" %}
**2. What are you flying?**

{% tabs %}
{% tab title="Flux LiDAR" %}
{% hint style="success" %}
**NTRIP.** Flux saves the NTRIP stream into the .fluxscan file and uses it during processing. You get survey-grade placement with no extra hardware.
{% endhint %}
{% endtab %}

{% tab title="Need absolute accuracy" %}
{% hint style="success" %}
**NTRIP.** You get absolute accuracy with no extra hardware. Add PPK when the deliverable has to be survey-grade.
{% endhint %}
{% endtab %}

{% tab title="Relative is fine" %}
{% hint style="success" %}
**NTRIP** in most cases. You get the same real-time performance with nothing to buy or carry. Choose the **Freefly RTK Base Station** if you don't want to depend on coverage.
{% endhint %}
{% endtab %}
{% endtabs %}
{% endtab %}

{% tab title="No coverage" %}
**2. What are you flying?**

{% tabs %}
{% tab title="Flux LiDAR" %}
{% hint style="success" %}
**PPK with a logging base or a CORS file.** Log raw GNSS on a base station for the whole scan, or download a file from a nearby permanent station, and load it during Flux processing. See [Flux setup](../payloads/flux-lidar/mapping-workflow-with-flux/setup.md#setup-your-gnss-base-station) for base station requirements.
{% endhint %}
{% endtab %}

{% tab title="Need absolute accuracy" %}
{% hint style="success" %}
**PPK.** It works without internet, there's no link to drop, and CORS post-processing gives you absolute accuracy.
{% endhint %}
{% endtab %}

{% tab title="Relative is fine" %}
{% hint style="success" %}
**Freefly RTK Base Station.** It gives you better flight performance and consistent relative geotags without internet. This is the case it's designed for.
{% endhint %}
{% endtab %}
{% endtabs %}
{% endtab %}
{% endtabs %}

### Comparison

| Use case                                                                                | Method                                                    | Trade-off                                                                                                     |
| --------------------------------------------------------------------------------------- | --------------------------------------------------------- | ------------------------------------------------------------------------------------------------------------- |
| Stable position hold and consistent (relative) geotags at a site with no internet.      | **RTK**<br>Freefly RTK Base Station                       | One more device to carry, set up and power. Absolute position drifts unless the base is on a known point.   |
| Absolute accuracy with the least equipment, at a site with cell or internet coverage.   | **NTRIP**<br>Subscription or free network, no hardware    | Depends on coverage. A dropout mid-flight degrades the geotags for that part of the flight.                 |
| Survey-grade deliverables, or results that can't depend on a live link.                 | **PPK**<br>A logging GNSS base, such as Emlid Reach       | Accuracy comes after the flight, and there's a processing step back at your desk.                           |

{% hint style="info" %}
**You may not need any of them**

RTK became popular when drone GPS wasn't good enough for reliable position hold. Astro and Alta X Gen 2 hold position well on standard GPS. If you aren't producing measured deliverables, you likely don't need corrections at all.
{% endhint %}

{% hint style="info" %}
**Flying the Flux LiDAR?**

Use NTRIP when you have coverage, or a logging base station with PPK when you don't. We don't recommend the Freefly RTK Base Station for Flux. Its position comes from Survey-In, so your scan's placement can be meters off.
{% endhint %}

## Next steps

{% content-ref url="../controller/pilot-pro/operating-handbook/ecosystem/rtk.md" %}
[rtk.md](../controller/pilot-pro/operating-handbook/ecosystem/rtk.md)
{% endcontent-ref %}

{% content-ref url="photogrammetry-mapping/ppk-software.md" %}
[ppk-software.md](photogrammetry-mapping/ppk-software.md)
{% endcontent-ref %}

{% content-ref url="../payloads/flux-lidar/" %}
[flux-lidar](../payloads/flux-lidar/)
{% endcontent-ref %}

Not sure which fits your workflow? [Contact us](https://freeflysystems.com/contact).
