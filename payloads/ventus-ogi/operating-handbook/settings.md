---
description: This page describes the OGI settings.
---

# Settings

* **Brightness**:\
  Adjusts the brightness of the images. Higher values result in a lighter image.
  * **Min:** 0 **Max:** 255 **Default:** 128
* **Contrast:**\
  Adjusts image contrast. Higher values result in more contrast.
  * **Min:** 0 **Max:** 255 **Default:** 128
* **Sharpen:**\
  Adjusts the edge sharpening filter to bring out edges within an image. Higher values increase the sharpening effect.
  * **Min:** 0 **Max:** 15 **Default:** 0
* **Denoise:**\
  This averages the image over time with image-to-image registration to dampen possible disruptive visual effects such as heat shimmer, scintillation, and turbulence.
  * **Min:** 0 **Max:** 255 **Default:** 0
* **AGC ROI:**\
  Adjusts the region of interest (ROI) when performing automatic gain corrections. This percentage controls the percentage of the frame used for AGC. The default performs AGC on the entire frame.
  * **Min:** 0 **Max:** 100 **Default:** 100
* **Manual AGC:**\
  This option freezes the current AGC settings.
  * Options:
    * **On**
    * **Off**
  * **Default:** Off
* **Gas Detection:**\
  This setting controls gas enhancement mode (GEM), which enhances and colorizes gas detectable by the OGI sensor.
  * Options:
    * **On**
    * **Off**
  * **Default:** Off
* **Stabilization Mode:**\
  Enables digital stabilization.
  * Options:
    * **On**
    * **Off**
  * **Default:** Off
* **Enhancement Mode:**\
  Two different contrast enhancement modes are available: CLAHE and LAP. Once an enhancement mode is selected, additional settings can be configured to configure it.\
  \
  Contrast Limited Adaptive Histogram Equalization (CLAHE) brings out hard-to-see (low contrast) features in the video, including those with brighter and darker areas.<br>

<figure><img src="../../../.gitbook/assets/image (156).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (159).png" alt=""><figcaption></figcaption></figure>

<br>

Local Area Processing (LAP) brings out hard-to-see (low-contrast) features. LAP emphasizes differences from the local image average to provide an increased amount of detail in low-contrast areas of a video or image. The algorithm makes details visible in underexposed or overexposed portions of the image.<br>

<figure><img src="../../../.gitbook/assets/image (156).png" alt=""><figcaption></figcaption></figure>

<figure><img src="../../../.gitbook/assets/image (158).png" alt=""><figcaption></figcaption></figure>

* **Strength:**
  * **In CLAHE, the Strength parameter controls the contrast limit**. A larger value allows the algorithm to map a larger contrast but can also tend to bring out more noise.
  * **In LAP, the Strength parameter controls the kernel size used in the processing.** A larger value provides more enhancement. Values are between 0 (minimal enhancement) and 18 (maximum enhancement). For LAP mode, there are no additional enhancement benefits after 18.
  * **Min:** 0 **Max:** 128 **Default:** 0
* **Alpha Blend:**\
  This allows mixing (alpha blending) the output of the enhancement algorithm with the input to the Enhance Stage. This allows a user to soften the effects of the contrast enhancement stage. Higher values blend more of the enhanced image, while lower values use less of it.
  * **Min:** 0 **Max:** 1.0 **Default:** 0.8
* **NUC Table:**\
  The OGI has two NUC tables that provide optimum performance for different scene temperature ranges. You may switch between them anytime using the NUC Table radio buttons in WIND Viewer. A shorter integration time is recommended in the overlapping range of 25°C – 40°C (where either table is applicable).
  * Options:
    * **Table 0**
    * **Table 1**
  * **Default:** Table 1

| NUC Table | Temperature Range | Integration Time |
| --------- | ----------------- | ---------------- |
| 0         | 10 - 40 °C        | 20 ms            |
| 1         | 25 - 55 °C        | 10 ms            |

* **FFC:**\
  The Ventus OGI offers a 1-point FFC (flat field offset correction) using an internal shutter and two 2-point NUC (gain) tables. An FFC should be performed to remove spatial noise and non-uniformities, which may develop as the camera and optics reach a stable operating temperature.\
  \
  Select **Run** to execute an FFC.
*   **Color Palette:**\
    Various false-color palettes may be applied to the video.

    *   Options:<br>

        <figure><img src="../../../.gitbook/assets/image (161).png" alt=""><figcaption></figcaption></figure>
    * **Default:** None



