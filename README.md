# Objective

Precision tuning of each string is paramount for eliciting accurate notes from a violin. Conventional tuning methods, whether manual or reliant on mobile applications, pose challenges in terms of time efficiency and precision. In response to these challenges, our goal is to introduce a streamlined solution – a circuit designed to accurately and efficiently tune all four violin strings. This innovative approach aims to provide musicians with a user-friendly, time-saving, and cost-effective means of achieving optimal tuning for an enhanced musical performance. For a block diagram of the project, please refer to the accompanying diagram below.

![Adsız](https://github.com/kutaykivik/Violin-Tuner/assets/89020731/d6ad3b9a-7ae2-4ad1-aefc-cacf02480d6d)



In the pursuit of refining signal processing and analog-to-digital conversion techniques, several improvements were implemented to overcome challenges encountered in the initial design. This essay outlines key enhancements in three critical aspects: noise cancellation, the conversion of analog to digital signals, and the integration of the ADC output with a 7-segment decoder.

## Noise Cancellation:
The initial implementation of a first-order band-pass filter encountered limitations in filtering out signals with unwanted frequencies, particularly affecting the conversion of sinusoidal signals to square waves. Recognizing this issue, the band-pass filter's order was elevated to second order. This enhancement proved instrumental in addressing the challenges associated with unwanted frequencies, ultimately contributing to a more robust signal processing framework.

## Conversion of Analog to Digital:
Originally intended for a 4-bit analog-to-digital converter (ADC), the unavailability of such a component led to the utilization of an 8-bit ADC. To adapt to the original 4-bit requirement, the system selectively considered the 4 least significant bits (LSB) of the ADC output. The input range for the ADC was initially set between -1V and 1V, posing a challenge for converting inputs below 0V. To rectify this, a 1V offset was introduced to the output of the differential amplifier, expanding the input range to 0V to 2V. This modification ensured a comprehensive coverage of the desired input range.

## Driving ADC Output to 7-Segment Decoder:
To accurately determine whether the input frequency surpassed or lagged behind the reference signal within the new 0V to 2V range, a logic design incorporating three demultiplexers was devised. This logical framework facilitated the differentiation between input frequencies higher or lower than the reference signal. Subsequently, the output of the ADC was meticulously directed to one of the seven-segment decoders based on the logic design. This strategic integration ensured a precise interpretation of input frequencies, enhancing the overall functionality of the system.
