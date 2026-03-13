# COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties

## Overview 
This is a laboratory report on Communication 2. In this report, viewers can see the input, process, and the output of each experiments. The theoretical explanation behind it will also be discussed and how to use each discipline pratically.

## Table of Contents 
* I - <b>Amplitude Shift Keying (ASK) & Frequency Shift Keying (FSK)</b>
* II - <b>Binary Phase Shift Keying (BPSK) & Quadrature Phase Shift Keying (QPSK)</b>
* III - <b>DSSS Modulation & Demodulation</b>
* IV - <b>Undersampling in Software Define Radio</b>

## I - Amplitude Shift Keying (ASK) & Frequency Shift Keying (FSK)

### Channel Sharing and Multiplexing
Effective telecommunications rely on the ability to share a single transmission medium (copper, fiber, or free-space) among multiple users. Without multiplexing, a channel could support only one transmitter at a time. Two primary methods achieve this:
* <b>Time Division Multiplexing (TDM)</b>: Users are granted exclusive access to the entire channel for extremely short, interleaved time intervals. While effective for digital data, increasing the number of users requires a higher bit-rate, which can lead to signal distortion if the channel bandwidth is exceeded.
* <b>Frequency Division Multiplexing (FDM)</b>: Users are assigned a specific, uninterrupted portion of the radio frequency spectrum. Messages are superimposed onto a carrier wave within an allocated frequency band. This is the standard for broadcast radio and television.

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

### <b>equipment for the experiment</b>
* Emona Telecom-Trainer 101 (plus power pack)
* Dual channel 20Mhz Oscilloscope
* Three Emona telecom-trainer 101 oscilloscope leads
* assorted emona telecom-trainer 101 patch leads


<details>
  <summary><b><i>RESULTS in ASK Experiment</i></b></summary>
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/7fbb2e1eed5cc3dd3163d4d576c5d8d2c456dda6/Exp%2015/FIGURE%203%20(LOGIC%200-LOW).png" alt="ASK">
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/7fbb2e1eed5cc3dd3163d4d576c5d8d2c456dda6/Exp%2015/FIGURE%203%20(LOGIC%201%20-HIGH).png" alt="ASK">
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/7fbb2e1eed5cc3dd3163d4d576c5d8d2c456dda6/Exp%2015/FIGURE%204.png" alt="ASK">
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/7fbb2e1eed5cc3dd3163d4d576c5d8d2c456dda6/Exp%2015/FIGURE%206.png" alt="ASK">
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/7fbb2e1eed5cc3dd3163d4d576c5d8d2c456dda6/Exp%2015/FIGURE%208.png" alt="ASK">

  </details>

  <details>
  <summary><b><i>RESULTS in FSK Experiment</i></b></summary>

  <img src="" alt="FSK">
  <img src="" alt="FSK">
  <img src="" alt="FSK">
  <img src="" alt="FSK">
  <img src="" alt="FSK"> 
  <img src="" alt="FSK">
    </details>

  ## II - Binary Phase Shift Keying (BPSK) & Quadrature Phase Shift Keying (QPSK)
  ASK (Amplitude Shift Keying) and FSK (Frequency Shift Keying) are digital adaptations of AM and FM, respectively.        These schemes are used when digital data (1s and 0s) replaces analog messages like speech or music, allowing for         efficient channel sharing.

  $ASK$: Switches a carrier between two different amplitudes.

  $FSK$: Switches a carrier between two different frequencies.
  
  <i>$BPSK$ (Binary Phase Shift Keying)</i>: An alternative method that switches the carrier between two different phases based on the digital data stream.

 <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/fd3a95af9d2a8ad2bd575a10a25bc3433651d5a6/Exp%2017/1.png" alt="BPSK">

 ### BPSK Performance and Implementation
 The key takeaways regarding Binary Phase Shift Keying (BPSK) compared to other modulation schemes are as follows:
 * <i><b>Phase Shift Mechanism</b></i>: When a logic level change occurs, the BPSK signal undergoes a 180° phase shift. This causes the carrier wave to immediately reverse direction (e.g., switching from heading toward a positive peak to heading toward a negative peak).
 * <i><b>Relationship to DSBSC</b></i>: The envelope of a BPSK signal shares the same shape as the message signal, identifying it as a form of Double-Sideband Suppressed Carrier (DSBSC) modulation. Consequently, it can be generated and demodulated using standard DSBSC techniques.
 * <i><b>Noise Immunity</b></i>: BPSK is the most robust system for ignoring noise, resulting in the lowest bit-error rate at the receiver. In terms of performance, BPSK is superior to FSK (FM-based), which is in turn superior to ASK (AM-based).
 * <i><b>Trade-offs</b></i>: Despite its superior performance, BPSK is often more complex to implement than FSK or ASK, which may make the latter two more suitable for simpler or cost-sensitive applications.
  
### Quadrature Phase Shift Keying (QPSK)
Quadrature Phase Shift Keying (QPSK) is an evolution of BPSK that utilizes Double-Sideband Suppressed Carrier (DSBSC) modulation to transmit two bits of digital data simultaneously.
* <b>Operation</b>: While BPSK transmits one bit per symbol, QPSK groups bits into pairs. To achieve this without a second carrier frequency, it uses two orthogonal carriers (shifted by 90°).
* <b>Bit-Rate vs. Symbol Rate</b>: Although QPSK sends two bits at once, the process of pairing bits halves the base bit-rate. Consequently, QPSK is not "faster" than BPSK in terms of raw data throughput.
* <b>Key Advantage (Spectral Efficiency)</b>: The primary benefit of QPSK is bandwidth conservation. By halving the required bit-rate for the same amount of information, QPSK occupies only half the radio-frequency spectrum required by BPSK. This efficiency allows for higher user density within the same channel.

<img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/53c9cb4d9f72906e35e8134c9f156716c6277c87/Exp18/2.png" alt="QPSK">
Block diagram of the mathematical operation of QPSK

#### The "secret" to Quadrature Phase Shift Keying (QPSK) is its ability to transmit two separate bitstreams simultaneously on the same frequency by using phase orthogonality.
* <b>Bit Splitting</b>: A "bit-splitter" divides the incoming digital data into two streams: even bits (In-phase, $I$) and odd bits (Quadrature, $Q$).
* <b>Dual Modulation</b>: * The even bits modulate a standard carrier to create a BPSK signal ($PSK_I$).
* <b>Signal Summation</b>: These two BPSK signals are added together for transmission.
* <b>Phase Separation</b>: Because the carriers are 90° apart (orthogonal), they do not interfere with each other. This allows the receiver to use phase discrimination to separate and recover both bitstreams perfectly.



  

