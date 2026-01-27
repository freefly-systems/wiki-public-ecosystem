# Hovermap ST-X and ST Lidar

The Emesent Hovermap ST-X and ST lidars are excellent payloads for creating detailed, accurate lidar point clouds, while enabling operations in challenging, GPS-denied environments.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-12-13 at 10.08.05 AM.jpg" alt=""><figcaption><p>Astro + Hovermap ST-X flying inside Alcatraz Cell House </p></figcaption></figure>

### Setting up Hovermap

{% content-ref url="hovermap-setup-on-astro.md" %}
[hovermap-setup-on-astro.md](hovermap-setup-on-astro.md)
{% endcontent-ref %}

### Operation modes

Hovermap can interact with Astro as a passive payload, for mapping applications that can be flown with good GPS signal in open spaces with few obstacles. &#x20;

{% content-ref url="mapping-with-hovermap.md" %}
[mapping-with-hovermap.md](mapping-with-hovermap.md)
{% endcontent-ref %}

Hovermap can also use the lidar data of the environment around Astro, and build a 3D model in real time. It can use that data for obstacle avoidance, and even allow Astro to autonomously explore GPS-denied areas like under bridges and inside tunnels and mines.&#x20;

{% embed url="https://drive.google.com/file/d/1E1IJqVptU_CEoJ5mKBL6M3PxekiDd3TQ/view?usp=drive_link" %}
Bridge scan with Hovermap ST-X
{% endembed %}

{% embed url="https://youtu.be/045shpvB-m4" %}
Astro navigating using Hovermap Assisted Mode
{% endembed %}

{% content-ref url="assisted-autonomous-flight.md" %}
[assisted-autonomous-flight.md](assisted-autonomous-flight.md)
{% endcontent-ref %}
