---
description: Technical Specifications for the Pilot Pro RF Module
---

# Radio Technical Specs

All radio backpacks use the Freefly Standard Radio Mounting Pattern

{% hint style="info" %}
These are the radio's technical specifications, and features may or may not be implemented
{% endhint %}

{% tabs %}
{% tab title="Herelink" %}
| Manufacturer:            | Herelink                   |                                                     |
| ------------------------ | -------------------------- | --------------------------------------------------- |
| Model/Part Number:       | Custom Freefly Herelink Tx |                                                     |
| NDAA Compliant           | No                         |                                                     |
| Blue Cleared             | No                         |                                                     |
| Frequency Band:          | 2.4 GHz                    | <p>2.400 GHz - 2.4835 GHz</p><p>Global ISM Band</p> |
| Radio Configuration:     | 2x2                        |                                                     |
| OTA Encryption           | AES-128-CTR                |                                                     |
| Max RF Power at SMA port | 200mW                      | 23dB                                                |
| Receiver Sensitivity     | -99dBm                     | At 20MHz Bandwidth                                  |
{% endtab %}

{% tab title="Doodle Labs" %}
| Manufacturer:                                     | Doodle Labs                                                                                        |                                                              |
| ------------------------------------------------- | -------------------------------------------------------------------------------------------------- | ------------------------------------------------------------ |
| Model/Part Number:                                | RM-1700-22M3                                                                                       |                                                              |
| NDAA Compliant                                    | Yes                                                                                                |                                                              |
| Blue Cleared                                      | Yes                                                                                                |                                                              |
| Frequency Type 1:                                 | 915 MHz (Disabled)                                                                                 | <p>902 MHz to 928 MHz<br>Global ISM Band</p>                 |
| Frequency Type 2:                                 | 2450 MHz                                                                                           | <p>2400 MHz to 2482 MHz<br>Global ISM Band</p>               |
| Radio Configuration:                              | 2x2 MIMO                                                                                           |                                                              |
| OTA Encryption                                    | <p>128-bit AES <br>256-bit AES (Disabled)</p>                                                      | <p>128 - Full throughput<br>256 - 12 Mbps max throughput</p> |
| Command & Control                                 | Ultra-Reliable Low Latency Channel (URLLC)                                                         | Latency 1.5-10ms                                             |
| Max RF Power at SMA port                          | 1.0W (30 dBm) @ MCS 0,8 0.8W (29 dBm) @ MCS 3,11 0.5W (27 dBm) @ MCS 5,13 250mW (24 dBm) @MCS 7,15 |                                                              |
| Antenna Receive Signal Strength                   | -30 to -90 dBm (Recommended)                                                                       | Absolute Maximum= +12 dBm                                    |
| Receiver LNA Gain                                 | 15 dB                                                                                              |                                                              |
| RF Power Control                                  | 1 dBm step                                                                                         | Tolerance ±1 dBm                                             |
| Automatic Transmit Power Control (ATPC)           | Intelligently adjusts the transmit power for very close range operation                            |                                                              |
| Wireless Error Correction                         | FEC, ARQ                                                                                           |                                                              |
| Receive Noise Figure                              | +4 dB                                                                                              |                                                              |
| Receive Adjacent Channel Rejection (ACRR)         | 34 dB                                                                                              | @ MCS0 for 20 MHz channel (Typ)                              |
| Transmitter Adjacent Channel Leakage Ratio (ACLR) | < 28 dBr (Fc ± ChBW)                                                                               |                                                              |
| Transmitter Spurious Emission Suppression         | < 40 dBc                                                                                           |                                                              |
| Frequency Accuracy                                | ±10 ppm max over life                                                                              |                                                              |
{% endtab %}

{% tab title="RFD900" %}
| Manufacturer:            | RFDesign                                                                    |                                                |
| ------------------------ | --------------------------------------------------------------------------- | ---------------------------------------------- |
| Model/Part Number:       | RFD900x-US                                                                  |                                                |
| NDAA Compliant           | Yes                                                                         |                                                |
| Blue Cleared             | Yes                                                                         |                                                |
| FCC Acceptance Number:   | 2ADLE-900UX2                                                                |                                                |
| Frequency Band:          | 915 MHz                                                                     | <p>902 MHz - 928 MHz</p><p>Global ISM Band</p> |
| Radio Configuration:     | 2x2                                                                         | Diversity Switched                             |
| OTA Encryption           | AES-128-CTR                                                                 |                                                |
| Max RF Power at SMA port | 1W                                                                          | +30dBm                                         |
| RF Power Control         | 1dB steps                                                                   | +/- 1dB @=20dBm typical                        |
| Receive Sensitivity      | <p>-111 dBm at 12kbps</p><p>-105 dBm at 64kbps</p><p>-98 dBm at 200kbps</p> |                                                |
| Temp. Range:             | -40 to +85 deg C                                                            |                                                |
{% endtab %}
{% endtabs %}
