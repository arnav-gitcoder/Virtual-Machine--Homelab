# Audio Steganography Challenge – Morse Code to Binary Flag Recovery

## Overview

This project documents the investigation and solution of an audio-based Capture The Flag (CTF) challenge.

The challenge provided an audio file containing a Morse code transmission. The Morse sequence was decoded into binary data using an online Morse Code Audio Decoder. The resulting binary stream was then converted into readable text using CyberChef, revealing the final challenge flag.

This exercise demonstrates a multi-stage decoding workflow involving audio analysis, Morse code interpretation, binary conversion, and digital forensics techniques.

---

## Objectives

* Analyze audio-based CTF challenges
* Decode Morse code transmissions
* Interpret binary-encoded data
* Use CyberChef for data transformation
* Recover hidden flags from encoded information
* Apply practical steganography and forensic techniques

---

## Tools Used

* Kali Linux
* aplay
* Morse Code Audio Decoder
* CyberChef

---

## Challenge Workflow

```text
Download Audio File
       │
       ▼
Play Audio
       │
       ▼
Identify Morse Code
       │
       ▼
Decode Morse Audio
       │
       ▼
Extract Binary Data
       │
       ▼
CyberChef Binary Conversion
       │
       ▼
Recover Flag
```

---

## Step 1 – Download the Audio File

The challenge audio was downloaded using:

```bash
wget <audio-url>
```

The download completed successfully and produced:

```text
Audio.wav
```

---

## Step 2 – Analyze the Audio

The audio file was played using:

```bash
aplay Audio.wav
```

During playback, the audio consisted of a sequence of Morse code tones rather than normal speech or sound.

### Screenshot
![Audio Terminal](https://github.com/arnav-gitcoder/Virtual-Machine--Homelab/blob/main/CTF/The%20Suspicious%20Audio%20Transmission/Download_Audio.png)

This indicated that the challenge required decoding Morse code.

---

## Step 3 – Decode the Morse Code

The audio file was uploaded to an online Morse Code Audio Decoder.

The decoder automatically converted the Morse code tones into binary values.

### Screenshot
![Morse Translate]https://github.com/arnav-gitcoder/Virtual-Machine--Homelab/blob/main/CTF/The%20Suspicious%20Audio%20Transmission/Morse_Translate.png
### Extracted Binary Data

```text
110001001101010010110111001100001011100100
1111001001111011000010111010101100100011010
0101101111010111101110011011001010110001101
11001001100101011101000111001101111101
```

---

## Step 4 – Convert Binary to Text

The extracted binary stream was imported into CyberChef.

Using the following operation: From Binary

CyberChef successfully converted the binary data into readable text.

### Screenshot
![CyberChef Conversion](https://github.com/arnav-gitcoder/Virtual-Machine--Homelab/blob/main/CTF/The%20Suspicious%20Audio%20Transmission/Cyberchef_fromBinary.png)
---

## Results

### Recovered Flag

```text
flag{binary_audio_secrets}
```

---

## Technical Analysis

### Encoding Layers

```text
Audio Signal
      ↓
Morse Code
      ↓
Binary Data
      ↓
ASCII Text
      ↓
Flag
```

This challenge used multiple encoding layers to conceal the final message, requiring each layer to be decoded sequentially.

---

## Skills Demonstrated

* Audio Forensics
* Morse Code Analysis
* Binary Data Interpretation
* CyberChef Usage
* Digital Forensics
* Linux Command Line
* CTF Methodology
* Multi-Stage Data Decoding

---

## Key Takeaways

* Audio files can be used as carriers for hidden information.
* Morse code remains a common encoding technique in CTF challenges.
* Binary data is often used as an intermediate encoding layer.
* CyberChef provides a powerful platform for decoding and data transformation.
* Multi-stage challenges require identifying and decoding each layer individually.

---

## Conclusion

This challenge demonstrated a complete audio steganography workflow. Starting from an audio file containing Morse code, the encoded message was decoded into binary data and subsequently transformed into readable text using CyberChef. The final result was the successful recovery of the challenge flag:

```text
flag{binary_audio_secrets}
```

The exercise provided practical experience in audio analysis, Morse code decoding, binary interpretation, and layered data recovery techniques commonly encountered in CTF competitions and digital forensic investigations.
