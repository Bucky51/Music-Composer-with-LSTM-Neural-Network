# Music-Composer-with-LSTM-Neural-Network
Music Composer is a deep learning project that generates original music using an LSTM neural network trained on MIDI files. It learns musical patterns and outputs new compositions as MIDI files, ready to be played or edited in any digital audio workstation.
Absolutely! Here's a clean, professional `README.md` for your **Music Composer** project, ideal for use on GitHub or sharing the project with others:

---

```markdown
# 🎵 Music Composer with LSTM Neural Network

This project is a deep learning pipeline for generating original music using MIDI data and an LSTM-based neural network. The system learns musical patterns from a dataset of MIDI files and generates new compositions, outputting them as playable MIDI files.

---

## 🚀 Features

- ✅ Extracts MIDI files from a ZIP in Google Drive  
- ✅ Parses notes and chords using `music21`  
- ✅ Prepares sequence data for LSTM models  
- ✅ Balances training data via oversampling  
- ✅ Trains an LSTM model with dropout regularization  
- ✅ Generates music sequences using temperature sampling  
- ✅ Converts generated notes into MIDI output  
- ✅ Supports saving model checkpoints and outputs to Google Drive

---

## 🗂 Project Structure

```
Music_Composer/
│
├── Songs/                         # Extracted MIDI dataset
├── Output/                        # Generated MIDI files
├── Lo-Fi Hip Hop MIDIs.zip       # Input dataset (Google Drive)
├── notes                          # Pickled notes file
└── generated_music.mid           # Final output
```

---

## 🛠 Setup & Installation

### ✅ Install Required Libraries
```bash
pip install numpy tensorflow music21 matplotlib pretty_midi
```

### ✅ Verify Installations
```python
import tensorflow as tf
import numpy as np
import music21
import matplotlib
import pretty_midi
```

---

## 📁 Dataset

The project uses a ZIP file containing Lo-Fi MIDI files stored in Google Drive.

- Mount Google Drive and extract:
```python
from google.colab import drive
drive.mount('/content/drive')
```
dataset link : 🎼 Dataset: Lo-Fi Hip Hop MIDIs (Google Drive)
---

## 🧠 Model Architecture

```text
Input Shape: (sequence_length, 1)

LSTM (512 units)
Dropout (0.3)
LSTM (512 units)
Dropout (0.3)
Dense (256, relu)
Dropout (0.3)
Dense (n_vocab, softmax)
```

- Loss Function: `categorical_crossentropy`
- Optimizer: `Adam`
- Output: Probability distribution over possible next notes

---

## 🎼 Music Generation

- The model generates sequences of notes using **temperature sampling**.
- The output is converted into a MIDI file using `music21`.

Example usage:
```python
prediction_output = generate_notes(model, network_input, pitchnames, n_vocab, num_notes=500, temperature=1.2)
create_midi(prediction_output, output_file='/content/drive/MyDrive/Music_composer/Output/generated_music.mid')
```

---

## 🎹 Output

- Generated MIDI files are saved to:
```
/content/drive/MyDrive/Music_composer/Output/
```

You can open them in any MIDI editor or DAW (Digital Audio Workstation) like:
- LMMS
- FL Studio
- Ableton Live
- MuseScore

---

## 💡 Tips

- Enable GPU in Google Colab for faster training
- You can change the `sequence_length` and `temperature` for different musical variations
- The more MIDI files in your dataset, the better the model will perform!

---

## 📬 Contact

For questions or improvements, feel free to reach out or contribute!

---

## 📄 License

This project is open-source under the MIT License.
```

---

Let me know if you want to include visuals (like loss plots or sample audio links), or if you’re planning to share it on GitHub and need help writing a `requirements.txt` or `.gitignore`!
