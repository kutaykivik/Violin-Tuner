# Objective
In order to get accurate notes from Violin, each string of the Violin must be tuned correctly. Tuning each string one by one is very difficult and takes a lot of time. We wanted to find a solution to this, since tuning is difficult to do with the ear and on the other hand, tuning applications on phones cannot perform tuning operations precisely. In this direction, our goal is to design a circuit that can tune all four strings of the violin accurately and precisely. This circuit will be simple to use, time-saver and cheap.

# Introduction:
In the pursuit of refining signal processing and analog-to-digital conversion techniques, several improvements were implemented to overcome challenges encountered in the initial design. This essay outlines key enhancements in three critical aspects: noise cancellation, the conversion of analog to digital signals, and the integration of the ADC output with a 7-segment decoder.

## Noise Cancellation:
The initial implementation of a first-order band-pass filter encountered limitations in filtering out signals with unwanted frequencies, particularly affecting the conversion of sinusoidal signals to square waves. Recognizing this issue, the band-pass filter's order was elevated to second order. This enhancement proved instrumental in addressing the challenges associated with unwanted frequencies, ultimately contributing to a more robust signal processing framework.

## Conversion of Analog to Digital:
Originally intended for a 4-bit analog-to-digital converter (ADC), the unavailability of such a component led to the utilization of an 8-bit ADC. To adapt to the original 4-bit requirement, the system selectively considered the 4 least significant bits (LSB) of the ADC output. The input range for the ADC was initially set between -1V and 1V, posing a challenge for converting inputs below 0V. To rectify this, a 1V offset was introduced to the output of the differential amplifier, expanding the input range to 0V to 2V. This modification ensured a comprehensive coverage of the desired input range.

## Driving ADC Output to 7-Segment Decoder:
To accurately determine whether the input frequency surpassed or lagged behind the reference signal within the new 0V to 2V range, a logic design incorporating three demultiplexers was devised. This logical framework facilitated the differentiation between input frequencies higher or lower than the reference signal. Subsequently, the output of the ADC was meticulously directed to one of the seven-segment decoders based on the logic design. This strategic integration ensured a precise interpretation of input frequencies, enhancing the overall functionality of the system.


# Technical Description
Block Diagram of Violin Tuner:
![image](https://github.com/kutaykivik/Violin-Tuner/assets/89020731/44f261c8-2945-4619-ad70-20958c40c11f)

## Noise Cancellation
In the development of a high-quality Violin Tuner, meticulous attention has been given to the requisite frequency range of the instrument's strings. Specifically, the system is designed to accurately analyze signals within the frequency spectrum of 196 Hz to 659.26 Hz, ensuring precision in the tuning process.

### Amplifying Input Signal




