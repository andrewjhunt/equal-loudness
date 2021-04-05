# EQ for Equal Loudness

## Overview

Human hearing perceives the balance of low-mid-high frequencies differently at different volumes. Typically, louder volumes will boost the perception of bass (particularly) and highs more than mid-range.

This project estimated equalisation curves (EQ) to adapt audio for different sound pressure levels -- but without changing the volume.

For example, if a speaker system is configured for a SPL 70dB reference level, then a +10dB EQ will simulate the perceived balance as if the actual SPL is 80dB (with boosted bass and highs).

The estimates are derived from the [equal-loudness contour](https://en.wikipedia.org/wiki/Equal-loudness_contour) from the ISO 226:2003 standard.

The EQ Parameters has sample EQ settings. The sections below explain how these parameters are estimated.

## EQ Parameters

NOTE: the Q parameter may need adjustment for different EQ systems. See the section on "EQ for 80dB" for EQ charts.

| Simulated dB | Low filter | Mid filter   | High filter  |
| --------     | ------     | ------       | ------       |
|              | Type: Bell | Type: Bell   | Type: Bell   |
|              | Freq: 25Hz | Freq: 2500Hz | Freq: 16kHz  |
|              | Q: 0.1     | Q: 0.4       | Q: 0.2       |
| Δ +10dB      | Boost: +2.82db | Boost: −2.52dB | Boost: −0.30dB |
| Δ +5dB       | Boost: +1.41dB | Boost: −1.26dB | Boost: −0.15dB |
| Δ 0dB (flat) | Boost:  0.00dB | Boost:  0.00dB | Boost:  0.00dB |
| Δ -5dB       | Boost: −1.40dB | Boost: +1.25dB | Boost: +0.15dB |
| Δ -10dB      | Boost: −2.81dB | Boost: +2.50dB | Boost: +0.31dB  |

![+10dB Simulator in Logic Pro EQ](./images/logic-pro-eq.png)
_+10dB Simulator in Logic Pro EQ_


## Equal-Loudness Contours

[Source: Wikipedia "Equal-loudness contour"](https://en.wikipedia.org/wiki/Equal-loudness_contour)

An "equal-loudness contour" is a measure of sound pressure level, over the frequency spectrum, for which a listener perceives a constant loudness when presented with pure steady tones. The unit of measurement for loudness levels is the phon and is arrived at by reference to equal-loudness contours. By definition, two sine waves of differing frequencies are said to have equal-loudness level measured in phons if they are perceived as equally loud by the average young person without significant hearing impairment.  

![ISO equal-loudness contours with frequency in Hz.](./images/equal-loudness-contours.png)

These curves show that changes in volume affect perception of different frequencies differently which changes the balance of frequencies. For example, increasing volume tends to disproportionately increase the perceived volume of the bass and high-frequencies.

Correct audio balance is critical to audio engineering - particularly when mixing and mastering. The typical sound-pressure-level (SPL) for audio engineering is around 85dB. However, if an engineer is mixing at quieter levels, the low-end and high-end will be perceived relatively more quiet that the mid-range. So engineering at a quieter level can lead to audio that is imbalanced -- likely with too much bass and highs.



## EQ for 80dB

![](./images/eq-80db.png)

| Simulated dB | 25Hz | 200Hz | 2500Hz | 16kHz | Average | Bal 25Hz | Bal 200Hz | Bal 2500Hz | Bal 16kHz | Description |
| -------- | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ | ------ |
| Δ +10dB | 5.04dB | 2.04dB | −0.30dB | 1.92dB | 2.22dB | 2.82dB | −0.18dB | −2.52dB | −0.30dB | ...to approximate the balance of 90dB when listening at 80dB |
| Δ +5dB | 2.52dB | 1.02dB | −0.15dB | 0.96dB | 1.11dB | 1.41dB | −0.09dB | −1.26dB | −0.15dB | ...to approximate the balance of 85dB when listening at 80dB |
| Δ +0dB | 0.00dB | 0.00dB | 0.00dB | 0.00dB | 0.00dB | 0.00dB | 0.00dB | 0.00dB | 0.00dB | ...to approximate the balance of 80dB when listening at 80dB |
| Δ -5dB | −2.50dB | −0.98dB | 0.16dB | −0.94dB | −1.10dB | −1.40dB | 0.11dB | 1.25dB | 0.15dB | ...to approximate the balance of 75dB when listening at 80dB |
| Δ -10dB | −5.00dB | −1.97dB | 0.31dB | −1.88dB | −2.19dB | −2.81dB | 0.22dB | 2.50dB | 0.31dB | ...to approximate the balance of 70dB when listening at 80dB |


## References

* Wikipedia article: [Equal-loudness contour](https://en.wikipedia.org/wiki/Equal-loudness_contour)
* ISO Standard: [ISO 226:2003 Acoustics — Normal equal-loudness-level contours](https://www.iso.org/standard/34222.html) (not free)
* Sweetwater: [How Loud Should You Mix?](https://www.sweetwater.com/insync/how-loud-should-you-mix/)
* [Sample ISO 226 chart](https://chart-studio.plotly.com/~mrlyule/16.embed)
