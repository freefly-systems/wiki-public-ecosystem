# Mapping Efficiency Tips

## Flight planning&#x20;

Choose a survey flight path angle that minimizes the number of turns (or in other words, think about maximizing long, straight flight paths). For example, if surveying a complex next to a road that runs at a 30-degree angle, rotating the survey lines to match may reduce the maneuvering Astro has to do and will result in shorter missions and better pictures.

<figure><img src="https://freefly.gitbook.io/~gitbook/image?url=https%3A%2F%2F2177404587-files.gitbook.io%2F%7E%2Ffiles%2Fv0%2Fb%2Fgitbook-x-prod.appspot.com%2Fo%2Fspaces%252F8dwrGJhxGd9cIvsStziq%252Fuploads%252FpccLaU9OQPYw7hzD9kRb%252Fimage.png%3Falt%3Dmedia%26token%3D9d548428-66b1-4a0f-ad80-a1e3b1dc0f89&#x26;width=768&#x26;dpr=4&#x26;quality=100&#x26;sign=341e48a7&#x26;sv=1" alt=""><figcaption><p>Survey angle rotated to fly parallel with scan area for maximum efficiency</p></figcaption></figure>

Rotate the survey entry/exit points to start and end at logical places. It is usually more efficient and safe to start at the furthest point from your takeoff location, as your mission will likely end closer to the home point when battery levels are most critical.

Use overlap and sidelap settings suitable for your processing software and output type. AMC's defaults (70%) are reasonable starting places, but reducing these values can allow faster flight and more area coverage. Lower front overlaps will allow Astro to fly faster in a mission, but be sure the value is acceptable for whichever processing software is in use.

**Tips for Large Projects**

Astro can cover areas greater than 200 acres in a single flight at 2cm GSD. Some tips for flying these types of missions:

* Uncheck the "refly at 90°" option at the bottom of the Survey settings while planning a mission. This will cause Astro to only fly over the ground in single-direction passes as opposed to a cross-hatch pattern.
* If possible, fly from the center of a large survey to reduce the distance between the Herelink and Astro. The maximum telemetry distance is shown in AMC during mission planning if you're at the takeoff location. Being able to have a line of sight to the vehicle at all parts of the survey is important for safety as well as maintaining a solid data link.
* Fly at 10-12m/s. The aircraft can fly up to 15m/s, but the flight time will actually increase if flying above 12m/s and result in a longer flight.
* A "typical" large area survey might have the following parameters: 12m/s speed, 120m altitude, 70% front overlap, 65% side overlap, and the gimbal angle pointing down (90°).
* Astro defaults to limiting the distance between waypoints to 900m. This is intended as a safety check to ensure that an accidental waypoint doesn't send the drone out of range to an unintended location. However, this may limit the length of a reasonable survey in some edge cases. This value can be increased by changing the parameter MIS\_DIST\_WPS. Do not set it larger than necessary to maintain the safety benefit.

**Tips for Small Projects**

Smaller areas can be covered the same as a large project, but usually higher detail is desired. In these cases, a crosshatch pattern can be used with gimbal pitch to get better detail on the sides of vertical objects. This gives better 3D reconstructions.

* Check the "refly at 90°" option at the bottom of the Survey settings while planning a mission.
* Set the gimbal angle to around 70 degrees to get better imagery on the sides of objects.
* Fly lower (60m or less) depending on the situation. Lower altitude will result in higher-density photos; just make sure that safety is the highest priority and that no obstacles intersect with your flight path.
* Make sure to fly well beyond the boundaries of the object being surveyed when the gimbal is tilted to ensure that it can be seen from all sides.
* Generally speaking, slower flights will provide more accurate results.

## AMC on a computer

It's possible to plan missions and monitor flights from AMC on a computer or tablet. Here's the [procedure to connect another device to the Herelink](../../../ecosystem/components/pilot-handsets/#hotspot).
