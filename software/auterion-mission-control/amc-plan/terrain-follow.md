# Terrain Follow

**Terrain Follow** is a feature commonly found in various flight simulation and drone control systems that enables an aircraft or vehicle to automatically adjust its altitude based on the contours of the terrain below. This capability is essential for maintaining safe and efficient flight paths over mountainous or uneven landscapes, preventing the risk of terrain collision. Enabling Terrain Follow enhances situational awareness and simplifies navigation by ensuring that the vehicle follows the natural topography without requiring constant manual altitude adjustments. This guide will walk you through the steps needed to enable and configure Terrain Follow, offering an improved and safer operational experience for pilots and operators.

{% hint style="warning" %}
Terrain Follow is only as effective as the elevation data it relies on and should not be considered a substitute for pilot vigilance. The system may not account for obstacles such as trees or buildings, which could pose a risk if not monitored manually by the operator. Therefore, while Terrain Follow enhances safety by adapting to terrain contours, pilots must remain attentive to their surroundings at all times.
{% endhint %}

{% hint style="info" %}
Terrain follow is only supported for Patterns (Survey and Corridor Scan) and is not available on waypoint missions
{% endhint %}

## How Terrain Follow Works

Terrain Follow is calculated in AMC when the mission is planned, not by the aircraft during flight. When you enable it on a pattern, AMC samples the elevation data along each survey line and adds waypoints whose altitudes keep the aircraft at your target height above the terrain model. The result is uploaded to the aircraft as a normal 3D waypoint mission.

This has a few practical consequences:

* The aircraft does not carry terrain data and does not use a rangefinder to follow the ground. It only knows the waypoint altitudes AMC gave it.
* Altitude does not change on a fixed time or distance interval. It changes at the waypoints AMC generated. Between two waypoints, the aircraft flies a straight line from one altitude to the next.
* Flat terrain produces few extra waypoints. Rolling or steep terrain produces many more.
* The accuracy of the flight path above ground can never be better than the elevation data used to plan it.

## Setting Up a Terrain Follow Mission

{% tabs %}
{% tab title="Video" %}
<figure><img src="../../../.gitbook/assets/AMCTerrainFollow.gif" alt=""><figcaption></figcaption></figure>
{% endtab %}

{% tab title="Photos" %}
<figure><img src="../../../.gitbook/assets/AMC Plan - Sidebar (1).jpg" alt=""><figcaption><p>Navigate to the Plan screen</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/AMC Pattern - Plan Screen (1).jpg" alt=""><figcaption><p>Start one of the pattern options</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/AMC Survey - Plan Screen (2).jpg" alt=""><figcaption><p>Navigate to the 'mountain' section</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/AMC Terrain Follow Disabled - Plan Screen (1).jpg" alt=""><figcaption><p>Enable Terrain Follow by checking the box</p></figcaption></figure>

<figure><img src="../../../.gitbook/assets/AMC Terrain Follow Enabled waitfordata - Plan Screen (2).jpg" alt=""><figcaption><p>Indicating Terrain Follow is enabled, but it is downloading the terrain data</p></figcaption></figure>
{% endtab %}
{% endtabs %}

## Terrain Follow Settings

### Tolerance

Tolerance is how far the planned altitude is allowed to drift from your target height above terrain before AMC adds another waypoint. After sampling the terrain along a survey line, AMC skips any intermediate point whose required altitude is within the tolerance of the last waypoint it kept, and only adds a new waypoint once the difference grows larger than the tolerance.

* **Lower tolerance:** more waypoints, closer tracking of the terrain
* **Higher tolerance:** fewer waypoints, coarser tracking, and steeper climbs and descents between waypoints

For example, flying at 100 m with a 10 m tolerance, a gentle 8 m rise may not get any added waypoint, so the aircraft would pass over the top of that rise at about 92 m above ground.

A tolerance of **5 m** is a good starting point for most missions.

### Max Climb Rate and Max Descent Rate

These set the maximum vertical speed allowed between waypoints when AMC adjusts for terrain. They are limits, not targets, so the aircraft will usually climb and descend more slowly than the values set.

{% hint style="info" %}
For Flux lidar missions, use max climb and descent rates below 1.0 m/s. See [Mission Planning and Data Capture](../../../payloads/flux-lidar/mapping-workflow-with-flux/mission-planning-and-data-capture.md) for details.
{% endhint %}

### Checking the Terrain Profile

Before uploading, open the altitude plot on the Plan screen to review the planned altitudes against the terrain profile. Red bars indicate a waypoint or segment below the terrain and must be fixed before flying.

## What Terrain Follow Does Not Cover

{% hint style="danger" %}
Terrain Follow only applies within the pattern itself. The flight to the first waypoint and the return to the launch point do not follow terrain.
{% endhint %}

**Transit to the first waypoint:** The flight from takeoff to the survey entry point is a single straight segment with no terrain waypoints. Make sure the Mission Start altitude is high enough to clear terrain and obstacles along that path. On takeoff, the aircraft adopts the above-ground altitude set on the first waypoint, so if the first waypoint sits on lower ground than the takeoff location, the takeoff altitude may be different than expected. The same applies when resuming an interrupted mission.

**Return To Launch (RTL):** RTL climbs to the RTL altitude (Climb to Altitude in the AMC Vehicle menu), which is measured relative to the launch point, then flies a straight line back to the launch point. It does not use terrain data. If the terrain between the survey area and the launch point rises higher than the launch point plus the RTL altitude, the aircraft can collide with it. When flying in hilly or mountainous areas, set the RTL altitude high enough to clear the highest terrain and obstacles between the mission area and the launch point. A Return item at the end of a mission behaves the same way.

## Mission Size

The flight controller can only store a limited number of mission items, and every command counts toward that limit (waypoints, camera triggers, speed changes, and so on). Each waypoint added by Terrain Follow is a mission item, so large surveys over rugged terrain with a low tolerance can produce far more items than the same survey over flat ground.

If a terrain following mission fails to upload or is larger than expected, try one or more of the following:

* Increase the tolerance
* Disable "Refly at 90°" if it is not needed
* Split the area into multiple smaller missions

## Offline Maps and Terrain Data

Terrain Follow requires the terrain data to be downloaded. The download can happen when you enable it on the mission, or you can preload the data. To download maps, please follow our [Offline Maps instructions](offline-maps.md)

{% hint style="info" %}
Tablet on the Pilot Pro must be connected to the internet to download maps
{% endhint %}

## Changing Terrain Data Providers

By default we use Copernicus Elevation for our terrain provider. AMC also supports Mapbox for offline maps. To change your elevation data to use Mapbox, this can be changed in the offline maps settings by entering your Mapbox Access Token

<figure><img src="../../../.gitbook/assets/Screenshot_20250120_160102 (2).jpg" alt=""><figcaption><p>Where to enter your Mapbox Access Token</p></figcaption></figure>

Once you have this saved, you can now select Mapbox when downloading an offline map

<figure><img src="../../../.gitbook/assets/Screenshot 2025-01-20 160119.png" alt=""><figcaption><p>Offline Map with Mapbox Elevation</p></figcaption></figure>

## Importing Custom Elevation Data

AMC can use your own elevation dataset instead of a provider. Supported formats are **DTED** and **Copernicus DEM**.

1. Go to **Settings > Map & Terrain > Terrain**
2. In the elevation selection, choose **Custom Elevation**, then tap **Browse**
3. Select your dataset to import

To remove an imported dataset, tap **Clear**.

{% hint style="warning" %}
A custom dataset is still only as good as its source. A bare-earth terrain model does not include trees, buildings, or towers, so plan your height above ground with obstacles in mind.
{% endhint %}
