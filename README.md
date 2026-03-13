# COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties

## Overview 
This is a laboratory report on Communication 2. In this report, viewers can see the input, process, and the output of each experiments. The theoretical explanation behind it will also be discussed and how to use each discipline pratically.

## Table of Contents 
* I - <b>Amplitude Shift Keying (ASK) & Frequency Shift Keying (FSK)</b>
* II - <b>Binary Phase Shift Keying (BPSK) & Quadrature Phase Shift Keying (QPSK)</b>
* III - <b>DSSS Modulation & Demodulation</b>
* IV - <b>Undersampling in Software Define Radio</b>
* V - Summary
* VI - Learnings

## I - Amplitude Shift Keying (ASK) & Frequency Shift Keying (FSK)

### Channel Sharing and Multiplexing
Effective telecommunications rely on the ability to share a single transmission medium (copper, fiber, or free-space) among multiple users. Without multiplexing, a channel could support only one transmitter at a time. Two primary methods achieve this:
* <b>Time Division Multiplexing (TDM)</b>: Users are granted exclusive access to the entire channel for extremely short, interleaved time intervals. While effective for digital data, increasing the number of users requires a higher bit-rate, which can lead to signal distortion if the channel bandwidth is exceeded.
* <b>Frequency Division Multiplexing (FDM)</b>: Users are assigned a specific, uninterrupted portion of the radio frequency spectrum. Messages are superimposed onto a carrier wave within an allocated frequency band. This is the standard for broadcast radio and television.

### Amplitude Shift Keying (ASK)
ASK is a digital implementation of FDM where a digital data stream modulates the amplitude of a carrier wave. It is often referred to as on-off keying, as the digital signal effectively switches the carrier connection to the channel.

#### Advantages and Limitations
* Demodulation: A primary advantage of ASK is simplicity. The signal "envelopes" mirror the original data stream, allowing for recovery using a basic envelope detector.
* Noise Sensitivity: The main disadvantage is susceptibility to atmospheric or electronic noise. Interference can alter the envelope's shape, causing the receiver to misinterpret logic levels and resulting in data errors (analogous to "static" in AM radio).

### Frequency Shift Keying (FSK)
Binary Frequency Shift Keying (BFSK or FSK) is a digital modulation scheme under Frequency Division Multiplexing (FDM). It functions by shifting the carrier frequency between two distinct values to represent digital logic levels.

* <b>Mark Frequency</b>: Represents Logic 1; typically higher than the nominal carrier frequency.

* <b>Space Frequency</b>: Represents Logic 0; typically lower than the nominal carrier frequency.

Nominal Carrier: The center frequency point; the modulator does not actually output a signal at this specific frequency during transmission.

#### Noise Immunity and Advantages
FSK offers superior noise immunity compared to Amplitude Shift Keying (ASK). Because environmental noise primarily manifests as amplitude variations, FSK receivers can use a limiter circuit to "clip" or remove these fluctuations. Since the digital information is encoded in the frequency rather than the amplitude, the data can be recovered without loss of integrity.

#### Generation and Demodulation
FSK can be implemented using standard FM hardware:

* Generation: Commonly achieved using a Voltage-Controlled Oscillator (VCO) or conventional FM modulator circuits.

* Demodulation:

* Frequency-to-Voltage: Methods include Phase-Locked Loops (PLL) or Zero Crossing Detectors.

* Filter Method: The signal is passed through a selective filter to isolate the Mark or Space frequency. This effectively converts the FSK signal into an ASK signal, which is then processed by an envelope detector.

### <b>Equipment for the experiment</b>
* Emona Telecom-Trainer 101 (plus power pack)
* Dual channel 20Mhz Oscilloscope
* Three Emona telecom-trainer 101 oscilloscope leads
* assorted emona telecom-trainer 101 patch leads


<details>
  <summary><b><i>RESULTS in ASK Experiment</i></b></summary>
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/7fbb2e1eed5cc3dd3163d4d576c5d8d2c456dda6/Exp%2015/FIGURE%203%20(LOGIC%200-LOW).png" alt="ASK">
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/7fbb2e1eed5cc3dd3163d4d576c5d8d2c456dda6/Exp%2015/FIGURE%203%20(LOGIC%201%20-HIGH).png" alt="ASK">

  <i>Generated ASK signal<i/>
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/7fbb2e1eed5cc3dd3163d4d576c5d8d2c456dda6/Exp%2015/FIGURE%204.png" alt="ASK">

  <i>Modified ASK signal<i/>
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/7fbb2e1eed5cc3dd3163d4d576c5d8d2c456dda6/Exp%2015/FIGURE%206.png" alt="ASK">

  <i>Demodulated ASK signal<i/>
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/7fbb2e1eed5cc3dd3163d4d576c5d8d2c456dda6/Exp%2015/FIGURE%208.png" alt="ASK">

<i>Restored recovered digital signal using a comparator<i/>

  </details>

  <details>
  <summary><b><i>RESULTS in FSK Experiment</i></b></summary>

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/93342ce9ee89702876a7d97961703ad682a23d91/Exp%2016/E16A.png" alt="FSK">

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/93342ce9ee89702876a7d97961703ad682a23d91/Exp%2016/E16APART2.png" alt="FSK">

 <i>Generated FSK signal</i>
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/93342ce9ee89702876a7d97961703ad682a23d91/Exp%2016/E16BPART1.png" alt="FSK">

  <i>Demodulated FSK signal using filtering and envelope detector</i>
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/93342ce9ee89702876a7d97961703ad682a23d91/Exp%2016/E16BPART2.png" alt="FSK">

<i>Recovered digital signal</i>
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/93342ce9ee89702876a7d97961703ad682a23d91/Exp%2016/E16CPART1.png" alt="FSK"> 

<i>Restored recovered data using comparator</i>
  

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

<img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/c21270890f0cc88712badec2d2cb54abd4f42c05/Exp18/1.png" alt="QPSK">

Notice the arrangement uses two product detectors to simultaneously demodulate the two BPSK signals. This simultaneously recovers the pairs of bits in the original data. The two signals are cleaned-up using a comparator or some other signal conditioner then the bits are put back in order using a 2-bit parallel-to-serial converter.

### <b>Equipment for the experiment</b>
* Emona Telecom-Trainer 101 (plus power pack)
* Dual channel 20Mhz Oscilloscope
* Three Emona telecom-trainer 101 oscilloscope leads
* assorted emona telecom-trainer 101 patch leads


<details>
  <summary><b><i>RESULTS in BPSK Experiment</i></b></summary>

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/c21270890f0cc88712badec2d2cb54abd4f42c05/Exp%2017/PART-A-fig2.png" alt="BPSK">
 
  <i>Generated BPSK signal</i>

  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/c21270890f0cc88712badec2d2cb54abd4f42c05/Exp%2017/PART-B-fig4.png" alt="BPSK">
  
  <i>Demodulated BPSK using product detector</i>
  
 
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/c21270890f0cc88712badec2d2cb54abd4f42c05/Exp%2017/PART-C-fig6.png" alt="BPSK">
  
  <i>Restored data using comparator</i>

</details>

  <details>
  <summary><b><i>RESULTS in QPSK Experiment</i></b></summary>

  [Outputs for the Experiment 18 (QPSK)](https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/23b2a2632ae30dc67587ce62ce4eab9db9635b93/Exp18/Exp18.COMS2.pdf)
</details>

## III - <b>DSSS Modulation & Demodulation</b>
Direct Sequence Spread Spectrum (DSSS) is a variation of Double Sideband Suppressed Carrier (DSBSC) modulation. Instead of a single sinusoidal carrier, DSSS utilizes a Pseudo-Noise (PN) pulse train. Since a pulse train consists of a fundamental frequency and infinite harmonics, the DSSS signal effectively represents the simultaneous DSBSC modulation of multiple sinusoidal carriers. This results in the message energy being distributed across a vast number of low-power sidebands.
The wide distribution of signal energy provides a significant advantage in anti-jamming. Because the information is spread across numerous sidebands, an interferer would need to disrupt a substantial portion of the total bandwidth to successfully jam the signal. This "processing gain" makes DSSS highly resilient to narrowband interference.

### Demodulation 
Demodulation is achieved via a product detector. For successful recovery of the original message, the receiver’s local carrier must be an identical, perfectly synchronized PN sequence (matching in frequency, phase, and timing).
* <b>Success</b>: If synchronized, the individual sidebands add constructively to reproduce the message.
* Failure: Without exact synchronization, the components add destructively, resulting in a low-power "noise-like" signal.

### Security and code complexity 
DSSS provides inherent "effective encryption" because the signal cannot be despread without the correct PN sequence. Security is scaled by increasing the length of the sequence (measured in chips).
* 8-bit sequence: 255-256 combinations.
* 20-bit sequence: ~1 million combinations.
* 256-bit sequence: Over $1.15 \times 10^{77}$ combinations.

This exponential increase in complexity makes "trial and error" or brute-force decryption computationally infeasible for longer sequences.

### <b>Equipment for the experiment</b>
* Emona Telecom-Trainer 101 (plus power pack)
* Dual channel 20Mhz Oscilloscope
* Three Emona telecom-trainer 101 oscilloscope leads
* assorted emona telecom-trainer 101 patch leads
 
<details>
  <summary><b><i>RESULTS</i></b></summary>
  
 <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/360c6fe6abb6bca974f3f8f3ba68261894561d7e/Exp%2019/FIG%201.png" alt="DSSS">

 <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/360c6fe6abb6bca974f3f8f3ba68261894561d7e/Exp%2019/fig%203.png" alt="DSSS">

 <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/360c6fe6abb6bca974f3f8f3ba68261894561d7e/Exp%2019/fig%204.png" alt="DSSS">

 <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/360c6fe6abb6bca974f3f8f3ba68261894561d7e/Exp%2019/fig%207.png" alt="DSSS">

 <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/360c6fe6abb6bca974f3f8f3ba68261894561d7e/Exp%2019/fig%208.png" alt="DSSS">

 <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/360c6fe6abb6bca974f3f8f3ba68261894561d7e/Exp%2019/fig%2010.png" alt="DSSS">

<img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/360c6fe6abb6bca974f3f8f3ba68261894561d7e/Exp%2019/fig%2011.png" alt="DSSS">

</details>

## IV - <b>Undersampling in Software Define Radio</b>
### Software Defined Radio (SDR)
1. The Challenge of Hardware Obsolescence
Historically, innovations in electronic communications—such as the transition from analog to digital cellular networks—have rendered previous hardware obsolete. In cases where established technologies like AM/FM are too pervasive to abandon, users are often forced to maintain redundant hardware systems to ensure compatibility across different modulation schemes.

2. The SDR Solution
Software Defined Radio (SDR) addresses these inefficiencies by replacing specialized hardware with a flexible, software-centric architecture. An SDR serves as a universal tuner capable of receiving and decoding a wide array of formats, including AM, FM, DSBSC, ASK, FSK, and DSSS, within a single device.

3. Architecture and Versatility
The core advantage of SDR lies in its "digitize-first" approach. Unlike traditional receivers that are hard-wired for specific bands or schemes, an SDR performs:

* <b>Wideband Reception</b>: Captures a broad range of frequencies.

* <b>Digital Conversion</b>: Converts raw radio signals into digital data.

* <b>Software Demodulation</b>: Uses digital signal processing (DSP) to decode the signal based on the active program.

This architecture ensures "future-proofing"; adapting to a new or emerging modulation scheme requires only a software update rather than a hardware replacement.


### Undersampling 
1. The Nyquist vs. Shannon Criteria
Traditional Nyquist theory suggests that a signal must be sampled at twice its highest frequency component to avoid aliasing. However, this primarily applies to baseband signals. According to Shannon’s Information Theorem, for bandwidth-limited signals (like those in radio communications), all information can be captured by sampling at twice the signal bandwidth, rather than twice the carrier frequency.

2. Mechanics of Undersampling
Undersampling—also referred to as band-pass sampling or super-Nyquist sampling—allows a high-frequency carrier to be sampled at a significantly lower rate. For example, a 2.4GHz carrier with a 30kHz bandwidth can theoretically be sampled at just 60kHz. This drastically reduces the performance requirements and cost of the Analog-to-Digital Converter (ADC).

3. Direct Demodulation
A primary advantage of undersampling in SDR is its ability to perform inherent demodulation. When the sampling frequency is correctly chosen relative to the signal bandwidth:

* One of the resulting digital aliases occurs at the original message frequency.

* The original information is "translated" down to baseband during the sampling process.

* Recovery: The original message is recovered by simply passing the sampled signal through a low-pass filter (LPF) to remove higher-frequency aliases.

### <b>Equipment for the experiment</b>
* Emona Telecom-Trainer 101 (plus power pack)
* Dual channel 20Mhz Oscilloscope
* Three Emona telecom-trainer 101 oscilloscope leads
* assorted emona telecom-trainer 101 patch leads

<details>
  <summary><b><i>RESULTS</i></b></summary>
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/93342ce9ee89702876a7d97961703ad682a23d91/Exp%2020/E20APART1.png" alt="Undersampling">
  
  <i>Bandwidth limited signal</i>
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/93342ce9ee89702876a7d97961703ad682a23d91/Exp%2020/E20PARTBPART1.png" alt="Undersampling">

<i>Direct down-conversion using undersamping</i>
  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/93342ce9ee89702876a7d97961703ad682a23d91/Exp%2020/E20BPART2.png" alt="Undersampling">
  
  <i>Demodulated DSBSC signal</i>

  
  <img src="https://github.com/Johnvy-M/COMMS-2-LAB.-Experimental-Analysis-of-Digital-Modulation-and-its-Other-Properties/blob/93342ce9ee89702876a7d97961703ad682a23d91/Exp%2020/E20CPART1.png" alt="Undersampling">

  <i>synchronized signal</i>

  </details>
 
## V - Summary
[Complete Q&A part of the report](https://github.com/EarlArugay/Digital-Comms-SDR-Advanced-Modulation-Sub-Nyquist-Signal-Analysis/blob/789ab027c875440ac44c51f9ab51f4374feb1e59/Data/Q%26A-Digital-Comms-SDR-Advanced-Modulation-Sub-Nyquist-Signal-Analysis.pdf)

## VI - Learnings
The evolution of digital modulation reflects a shift toward higher efficiency and better security by moving from basic amplitude and frequency changes to more advanced phase and spectrum-spreading methods. Just like ASK and FSK function as the digital equivalents of AM and FM, representing data bits by toggling carrier amplitude or frequency. BPSK improves on this with $180^\circ$ phase shifts, offering better noise immunity because it operates as a suppressed carrier system. To save on bandwidth, QPSK splits the data into two streams and modulates them onto carriers shifted by $90^\circ$, allowing twice the data in the same frequency space. For applications requiring high security or resistance to interference, DSSS spreads the signal energy across a wide bandwidth, which makes the transmission look like noise to unauthorized users and very hard to jam. Finally, undersampling simplifies the receiver design by sampling based on the signal’s bandwidth instead of its carrier frequency. This technique not only reduces the hardware requirements but also serves as a way to naturally demodulate the signal down to baseband during the ADC process.







  

