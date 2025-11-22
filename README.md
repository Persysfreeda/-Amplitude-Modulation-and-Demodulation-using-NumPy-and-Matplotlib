# -Amplitude-Modulation-and-Demodulation-using-NumPy-and-Matplotlib

__Aim__: 

To implement and analyze amplitude modulation (AM) using Python's NumPy and Matplotlib libraries. 

__Apparatus Required__: 

Software: Python with NumPy and Matplotlib libraries 
Hardware: Personal Computer 

__Theory__: 

Amplitude Modulation (AM) is a technique used in electronic communication, primarily for transmitting 
information via a radio carrier wave. In AM, the amplitude of the carrier wave is varied in proportion to that of 
the message signal. The general form of an AM signal is: 


__Algorithm__:
1. Initialize Parameters: Set the values for carrier frequency, message frequency, and sampling frequency. 
2. Generate Time Axis: Create a time vector for the signal duration. 
3. Generate Message Signal: Define the message signal as a cosine wave. 
4. Generate Carrier Signal: Define the carrier signal as a cosine wave. 
5. Modulate Signal: Apply the AM formula to obtain the modulated signal. 
6. Plot the Signals: Use Matplotlib to plot the message signal, carrier signal, and modulated signal.


__Program__:
```
import numpy as np
import matplotlib.pyplot as plt

# Parameters
Am = 36.3       # Message amplitude
Ac = 72.6       # Carrier amplitude
fm = 450        # Message frequency
fc = 900        # Carrier frequency
fs = 20000      # Sampling frequency (must be high for smooth signal)

t = np.arange(0, 0.01, 1/fs)   # Time vector

# Message Signal
message = Am * np.cos(2 * np.pi * fm * t)

# Carrier Signal
carrier = Ac * np.cos(2 * np.pi * fc * t)

# Modulation Index
m = Am / Ac

# AM Modulated Signal
am_signal = Ac * (1 + m * np.cos(2 * np.pi * fm * t)) * np.cos(2 * np.pi * fc * t)

# Demodulation (Envelope Detector)
demodulated = np.abs(am_signal)

# Plotting
plt.figure(figsize=(12,10))

plt.subplot(4,1,1)
plt.plot(t, message)
plt.title("Message Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,2)
plt.plot(t, carrier)
plt.title("Carrier Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,3)
plt.plot(t, am_signal)
plt.title("AM Modulated Signal")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.subplot(4,1,4)
plt.plot(t, demodulated)
plt.title("Demodulated Signal (Envelope)")
plt.xlabel("Time")
plt.ylabel("Amplitude")

plt.tight_layout()
plt.show()

```
__Calculation__:
<![WhatsApp Image 2025-11-22 at 6 45 58 PM](https://github.com/user-attachments/assets/3557f47c-b427-459c-a5b2-face6a58e499)>

__Table__:
<![WhatsApp Image 2025-11-22 at 6 46 28 PM](https://github.com/user-attachments/assets/67372d84-b2ee-4731-b5cf-df42c7b288f8)>

 __Output__:

<img width="1572" height="1198" alt="Screenshot 2025-11-17 140236" src="https://github.com/user-attachments/assets/15dc7992-2d79-4319-a7ff-d05ac00f81d3" />

 __Result__:
 
 The amplitude modulation and demodulation were successfully implemented using Python. The message, carrier, modulated, and recovered signals were generated and verified correctly.

