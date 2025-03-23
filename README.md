# Identify-word-from-a-speech-using-spectrogram

This code performs speech processing using Librosa, SoundFile, Matplotlib, and NumPy. The code follows two major steps:

Speech Segmentation: The script loads a speech WAV file, generates a spectrogram, detects changes in the spectrum, and segments the audio into individual words or meaningful sound parts.

MFCC Feature Extraction: The segmented audio files are then processed to extract Mel-Frequency Cepstral Coefficients (MFCCs), which are stored in a text file for further use in machine learning models.

1. Input
The script takes a speech audio file (WAV format) as input. It expects:

A single WAV file containing spoken words.

The WAV file should be stored at:
"C:/Users/ZBOOK 14U G5/Documents/WAV to MFCC/inputwav/f01w01r1.wav"

2. Methodology (Step-by-Step Explanation)
Step 1: Speech Segmentation Using Spectrogram
Purpose:
The goal of this step is to analyze the spectrogram of the speech audio and segment the audio into individual words or meaningful parts.

Process:
Load the Audio File

Uses librosa.load() to load the WAV file, extracting the waveform (y) and sample rate (sr).

Compute Spectrogram

Uses Short-Time Fourier Transform (STFT) to compute the frequency domain representation.

Converts amplitude to decibels using librosa.amplitude_to_db().

Plot Spectrogram

Uses librosa.display.specshow() to visualize the spectrogram.

Saves the spectrogram image as "C:/Users/ZBOOK 14U G5/Documents/WAV to MFCC/spectrogram_plots/".

Detect Changes in the Spectrogram

Applies a thresholding technique to detect points where there is a significant change in sound intensity.

Segment Audio into Words

Uses librosa.effects.split() to segment audio based on detected changes.

Saves each segmented portion as a separate WAV file in:
"C:/Users/ZBOOK 14U G5/Documents/WAV to MFCC/trimWord/".

Step 2: MFCC Feature Extraction
Purpose:
The goal of this step is to extract MFCC features from each segmented word’s audio file for speech recognition.

Process:
Load the segmented word audio file

Uses librosa.load() to load the segmented WAV file.

Compute MFCC Features

Uses librosa.feature.mfcc() to extract 13 MFCCs per frame.

Normalizes the MFCC values between -127 and 127.

Format the MFCC Values

Flattens the MFCC matrix into a one-dimensional array.

Ensures exactly 250 MFCC values by padding with zeros if necessary.

Saves the formatted MFCCs as a text file at:
"C:/Users/ZBOOK 14U G5/Documents/WAV to MFCC/word_mfc/".

Plot MFCC Spectrogram

Uses librosa.display.specshow() to visualize MFCC features.

Displays the MFCC plot for analysis.

3. Output
1. Spectrogram Analysis & Segmentation
A visual spectrogram image is saved at:
"C:/Users/ZBOOK 14U G5/Documents/WAV to MFCC/spectrogram_plots/".

Segmented audio files (words) are stored at:
"C:/Users/ZBOOK 14U G5/Documents/WAV to MFCC/trimWord/".

2. MFCC Feature Extraction
MFCC feature text files (one per word) are stored at:
"C:/Users/ZBOOK 14U G5/Documents/WAV to MFCC/word_mfc/".

MFCC visualization plot is displayed.

Summary
This script automates the process of speech segmentation and feature extraction using spectrogram analysis and MFCC computation. The extracted MFCCs can be used for speech recognition, word classification, or deep learning models.
