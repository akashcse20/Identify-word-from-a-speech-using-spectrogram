# 📌 Speech Word Identification using Spectrogram & MFCC

## 📖 Overview
This project processes speech audio files to extract individual words and generate Mel Frequency Cepstral Coefficients (MFCCs). The pipeline involves:
1. **Converting Speech to a Spectrogram** for visualization and segmentation.
2. **Detecting and Extracting Words** based on spectral changes.
3. **Computing MFCC Features** for each extracted word.

## 🚀 Workflow
### Step 1: Convert Speech to Spectrogram
- **Input:** A `.wav` file containing spoken words.
- **Method:**
  - Load the audio file using `librosa`.
  - Compute the spectrogram using Short-Time Fourier Transform (STFT).
  - Apply amplitude-to-decibel conversion for better visualization.
  - Detect spectral changes using thresholding.
  - Extract individual word segments based on spectral variations.
  - Save the segmented words as separate audio files.
- **Output:**
  - A **spectrogram image** showing frequency variations over time.
  - Multiple **trimmed `.wav` files**, each containing a single spoken word.

### Step 2: Extract MFCC Features from Each Word
- **Input:** A segmented `.wav` file (single-word audio clip).
- **Method:**
  - Compute **MFCC features** from the extracted word.
  - Scale the MFCC values between -127 and 127.
  - Flatten and store only the first **250 MFCC values**.
  - Save the MFCC values as a `.txt` file.
  - Visualize the MFCCs.
- **Output:**
  - A `.txt` file containing **250 MFCC values**.
  - An **MFCC visualization** for each extracted word.

## 🛠️ Dependencies
Ensure you have the following Python libraries installed:
```bash
pip install librosa soundfile numpy matplotlib
```

## 📂 Folder Structure
```
📁 WAV to MFCC
│-- 📂 inputwav/              # Original input .wav files
│-- 📂 spectrogram_plots/     # Spectrogram images
│-- 📂 trimWord/              # Extracted words as .wav files
│-- 📂 word_mfc/              # MFCC values stored as .txt files
│-- script.py                 # Main processing script
```

## 🔧 How to Run
1. Place your `.wav` file in `inputwav/`.
2. Run the script to generate spectrograms and extract words:
   ```bash
   python script.py
   ```
3. Extract MFCC features for a specific word:
   ```bash
   python script.py --mfcc path/to/word.wav
   ```

## 📊 Example Output
### 🎵 Spectrogram Example
![Image](https://github.com/user-attachments/assets/a171b8fd-1aa5-4d8d-bc7b-d667573ed6c4)

### 📜 MFCC Values Example
```
-12.345678
 10.234567
 ...
 (Total 250 values)
```

## 🔍 Future Improvements
- Improve word segmentation accuracy.
- Enhance noise reduction techniques.
- Implement real-time speech processing.

---
📌 **Developed for Speech Processing & Machine Learning Applications** 🎤📈

