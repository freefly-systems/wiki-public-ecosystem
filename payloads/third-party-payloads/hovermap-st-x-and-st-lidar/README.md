# Hovermap ST-X and ST Lidar

|                             |                                             |
| --------------------------- | ------------------------------------------- |
| **Description**             | LiDAR with SLAM for GPS-denied environments |
| **Weight**                  | 1.6-1.7kg                                   |
| **NDAA Compliant**          | No                                          |
| **Offered By**              | Emesent                                     |
| **Latest Emesent Software** | Cortex v4.1.3 and Commander v2.2.1          |

The Emesent Hovermap ST-X and ST lidars are excellent payloads for creating detailed, accurate lidar point clouds, while enabling operations in challenging, GPS-denied environments.

<figure><img src="../../../.gitbook/assets/Screenshot 2023-12-13 at 10.08.05 AM.jpg" alt=""><figcaption><p>Astro + Hovermap ST-X flying inside Alcatraz Cell House</p></figcaption></figure>

### Compatibility

<table><thead><tr><th>Drone Compatibility</th><th>Emesent ST<select><option value="SHv8oMwmiIbF" label="Yes" color="blue"></option><option value="eGG9b32rkoLv" label="No" color="blue"></option><option value="uC8MMpP6mCOA" label="Coming Soon" color="blue"></option></select></th><th>Emesent ST-X<select><option value="ig7orSicsUPZ" label="Yes" color="blue"></option><option value="ZSmD19mOwe80" label="No" color="blue"></option><option value="RgPFbTdmduQn" label="Coming Soon" color="blue"></option></select></th></tr></thead><tbody><tr><td>Astro (F45)</td><td><span data-option="eGG9b32rkoLv">No</span></td><td><span data-option="ig7orSicsUPZ">Yes</span></td></tr><tr><td>Astro Max</td><td><span data-option="SHv8oMwmiIbF">Yes</span></td><td><span data-option="ig7orSicsUPZ">Yes</span></td></tr><tr><td>Alta X</td><td><span data-option="eGG9b32rkoLv">No</span></td><td><span data-option="ZSmD19mOwe80">No</span></td></tr><tr><td>Alta X Gen2</td><td><span data-option="uC8MMpP6mCOA">Coming Soon</span></td><td><span data-option="RgPFbTdmduQn">Coming Soon</span></td></tr></tbody></table>



### Setting up Hovermap

{% content-ref url="hovermap-setup-on-astro.md" %}
[hovermap-setup-on-astro.md](hovermap-setup-on-astro.md)
{% endcontent-ref %}

### Operation modes

Hovermap can interact with Astro as a passive payload, for mapping applications that can be flown with good GPS signal in open spaces with few obstacles.

{% content-ref url="mapping-with-hovermap.md" %}
[mapping-with-hovermap.md](mapping-with-hovermap.md)
{% endcontent-ref %}

Hovermap can also use the lidar data of the environment around Astro, and build a 3D model in real time. It can use that data for obstacle avoidance, and even allow Astro to autonomously explore GPS-denied areas like under bridges and inside tunnels and mines.

{% embed url="https://drive.google.com/file/d/1E1IJqVptU_CEoJ5mKBL6M3PxekiDd3TQ/view?usp=drive_link" %}
Bridge scan with Hovermap ST-X
{% endembed %}

{% embed url="https://youtu.be/045shpvB-m4" %}
Astro navigating using Hovermap Assisted Mode
{% endembed %}

{% content-ref url="assisted-autonomous-flight.md" %}
[assisted-autonomous-flight.md](assisted-autonomous-flight.md)
{% endcontent-ref %}
