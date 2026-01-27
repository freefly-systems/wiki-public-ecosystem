---
description: How to fine-tune gimbal pointing controls
---

# Precise/Smooth Gimbal Control

## <mark style="color:blue;">Position Slow Mode</mark>&#x20;

For the best gimbal pointing control, use Position Slow Mode

Position Slow mode is a flight mode that toggles several things, including zoom rate scaling, adjustable rates, expo, window, and smooth control

{% hint style="info" %}
When the vertical and horizontal rate knobs are set to maximum, the maximum speeds of the aircraft will match Position mode
{% endhint %}

## Gimbal Control Features:

{% hint style="success" %}
As of Astro FW 2.0, new features and parameters have been added for smoother and more precise gimbal control!&#x20;
{% endhint %}

{% hint style="info" %}
The gimbal parameters described below can be found in AMC in Advanced Mode under Advanced > Parameters > Component 154.
{% endhint %}

<table><thead><tr><th width="116">Feature</th><th width="210">Description</th><th width="114">When active?</th><th width="194">How to adjust?</th><th>Range</th></tr></thead><tbody><tr><td><strong>Tilt Window</strong></td><td>Dead zone on the tilt rocker</td><td><mark style="color:blue;">Position Slow Mode</mark></td><td><p>Parameter: </p><p><code>MC_SLOW_WIN_PIT</code>  </p></td><td>0-1000</td></tr><tr><td><strong>Tilt Expo</strong></td><td>Reduces rocker sensitivity around the center for easier small, precise adjustments</td><td><mark style="color:blue;">Position Slow Mode</mark></td><td>Parameter: <code>MC_SLOW_EXPO_PIT</code> </td><td>0-100 %</td></tr><tr><td><strong>Tilt Smoothing</strong></td><td>Smooths out input pitch  commands</td><td><mark style="color:green;">All flight modes</mark></td><td>Parameter: <code>GMBL_P_STICK_SM</code></td><td>0-30 </td></tr><tr><td><strong>Tilt Rate</strong></td><td>Adjust tilt speed</td><td><mark style="color:green;">All flight modes</mark> </td><td><img src="../../../.gitbook/assets/Tilt rate (1).gif" alt="" data-size="original"></td><td>-</td></tr><tr><td><strong>Tilt Zoom Rate Scaling</strong></td><td>Reduce the tilt rate in proportion to the camera zoom level</td><td><mark style="color:green;">All flight modes</mark></td><td>-</td><td>-</td></tr><tr><td><strong>Pan Window</strong></td><td>Dead zone on the yaw stick</td><td><mark style="color:blue;">Position Slow Mode</mark></td><td>Parameter: <code>MC_SLOW_WIN_YAW</code></td><td>0-1000</td></tr><tr><td><strong>Pan Expo</strong></td><td>Reduces stick sensitivity around the center for easier small, precise adjustments</td><td><mark style="color:blue;">Position Slow Mode</mark></td><td>Parameter: <code>MC_SLOW_EXPO_YAW</code></td><td>0-100 %</td></tr><tr><td><strong>Pan Smoothing</strong></td><td>Smooths out input pitch  commands</td><td><mark style="color:green;">All flight modes</mark></td><td>Parameter: <code>GMBL_Y_STICK_SM</code></td><td>0-30</td></tr><tr><td><strong>Pan Rate</strong></td><td>Adjust yaw/pan speed</td><td><mark style="color:blue;">Position Slow Mode</mark></td><td><img src="../../../.gitbook/assets/Pan rate.gif" alt="" data-size="original"></td><td>-</td></tr><tr><td><strong>Pan Zoom Rate Scaling</strong></td><td>Reduce the pan rate in proportion to the camera zoom level</td><td><mark style="color:blue;">Position Slow Mode</mark></td><td>-</td><td>-</td></tr><tr><td><strong>Max Pan Rate</strong></td><td>Set the max yaw/pan rate of the aircraft</td><td><mark style="color:green;">All flight modes</mark></td><td>Parameter: <code>MPC_MAN_Y_MAX</code></td><td>0-75 deg/s</td></tr><tr><td><strong>Tilt Invert</strong></td><td>Change tilt rocker direction</td><td><mark style="color:green;">All flight modes</mark></td><td><img src="../../../.gitbook/assets/Tilt invert.gif" alt="" data-size="original"></td><td>-</td></tr></tbody></table>

Pilot Pro can also do input shaping on the commands sent to the gimbal, however we recommend changing the parameters above on the drone side instead. The following settings (defaults) are recommended for Pilot Pro:&#x20;

* RockLWindow = 2.5
* RockLSmooth = 0
