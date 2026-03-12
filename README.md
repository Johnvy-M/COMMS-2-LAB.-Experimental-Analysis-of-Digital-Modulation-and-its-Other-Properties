# COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties

## Overview 
This is a laboratory report on Communication 2. In this report, viewers can see the input, process, and the output of each experiments. The theoretical explanation behind it will also be discussed and how to use each discipline pratically.

## Table of Contents 
* I - Amplitude Shift Keying (ASK) & Frequency Shift Keying (FSK)
* II - Binary Phase Shift Keying (BPSK) & Quadrature Phase Shift Keying (QPSK)
* III - DSSS Modulation & Demodulation
* IV - Undersampling in Software Define Radio

## I - Amplitude Shift Keying (ASK) & Frequency Shift Keying (FSK)

### Channel Sharing and Multiplexing
Effective telecommunications rely on the ability to share a single transmission medium (copper, fiber, or free-space) among multiple users. Without multiplexing, a channel could support only one transmitter at a time. Two primary methods achieve this:
* Time Division Multiplexing (TDM): Users are granted exclusive access to the entire channel for extremely short, interleaved time intervals. While effective for digital data, increasing the number of users requires a higher bit-rate, which can lead to signal distortion if the channel bandwidth is exceeded.
* Frequency Division Multiplexing (FDM): Users are assigned a specific, uninterrupted portion of the radio frequency spectrum. Messages are superimposed onto a carrier wave within an allocated frequency band. This is the standard for broadcast radio and television.

### Amplitude Shift Keying (ASK)
ASK is a digital implementation of FDM where a digital data stream modulates the amplitude of a carrier wave. It is often referred to as on-off keying, as the digital signal effectively switches the carrier connection to the channel.
####Advantages and Limitations
* Demodulation: A primary advantage of ASK is simplicity. The signal "envelopes" mirror the original data stream, allowing for recovery using a basic envelope detector.
* Noise Sensitivity: The main disadvantage is susceptibility to atmospheric or electronic noise. Interference can alter the envelope's shape, causing the receiver to misinterpret logic levels and resulting in data errors (analogous to "static" in AM radio).

### Frequency Shift Keying (FSK)
Binary Frequency Shift Keying (BFSK or FSK) is a digital modulation scheme under Frequency Division Multiplexing (FDM). It functions by shifting the carrier frequency between two distinct values to represent digital logic levels.

Mark Frequency: Represents Logic 1; typically higher than the nominal carrier frequency.

Space Frequency: Represents Logic 0; typically lower than the nominal carrier frequency.

Nominal Carrier: The center frequency point; the modulator does not actually output a signal at this specific frequency during transmission.

#### Noise Immunity and Advantages
FSK offers superior noise immunity compared to Amplitude Shift Keying (ASK). Because environmental noise primarily manifests as amplitude variations, FSK receivers can use a limiter circuit to "clip" or remove these fluctuations. Since the digital information is encoded in the frequency rather than the amplitude, the data can be recovered without loss of integrity.

#### Generation and Demodulation
FSK can be implemented using standard FM hardware:

Generation: Commonly achieved using a Voltage-Controlled Oscillator (VCO) or conventional FM modulator circuits.

Demodulation:

Frequency-to-Voltage: Methods include Phase-Locked Loops (PLL) or Zero Crossing Detectors.

Filter Method: The signal is passed through a selective filter to isolate the Mark or Space frequency. This effectively converts the FSK signal into an ASK signal, which is then processed by an envelope detector.


