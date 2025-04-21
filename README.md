# Speech Enhancement Using Deep Learning Techniques

This project implements a real-time speech enhancement model using a custom encoder-decoder architecture adapted from Demucs. The model removes ambient noise (ringtones, music, street sounds, etc.) from raw audio with low latency and is optimized to run locally on CPUs.

Developed as part of a published research paper, this project is designed for deployable use cases including voice assistants, meeting platforms, and embedded devices.

## Key Highlights

- Real-time inference with < 200ms latency on CPUs
- Accepts raw waveform inputs in .mp3, .wav, or .m4a formats
- Custom Demucs-inspired model with convolutional and LSTM layers
- Fully modular PyTorch implementation (no external frameworks)
- Designed for generalization and integration across real-world conditions

## Research Publication

Published in IJFMR:  
**“Speech Enhancement Using Deep Learning Techniques” – Pavankalyan Ghanta & Gowtham Bobbili**  
[Read the paper](https://www.ijfmr.com/research-paper.php?id=2349)

## Folder Structure

speech-enhancement-anc/
├── model_inference_final.ipynb         # Main notebook
├── encoder_decoder_trained.pt          # Pretrained model (PyTorch)
├── Demucs_architecture_end_to_end.py   # Model definition
├── resample.py / utils.py              # Support scripts
├── test_audio/                         # Sample input files
├── cleaned_output.wav                  # Output after inference
├── README.md                           # This file
├── .gitignore
└── requirements.txt

## How to Run

1. Clone the repository:

git clone https://github.com/your-username/speech-enhancement-anc.git
cd speech-enhancement-anc


2. Set up the environment:

python -m venv anc_env
.\anc_env\Scripts\activate
pip install -r requirements.txt


3. Launch the notebook:
jupyter notebook

4. Open `model_inference_final.ipynb` and run all cells.

## Output Example

After running the model in `model_inference_final.ipynb`, the following output is generated:

| Description           | Audio File                      |
|-----------------------|----------------------------------|
| Noisy Input           | `test_audio/Noise_audio_1.mp3`   |
| Cleaned Output        | `cleaned_output.wav`             |

The model processes the input waveform and returns a denoised version with background disturbances removed. Waveform plots can also be visualized in the notebook.

Original Audio → Encoder-Decoder Model → Cleaned Output

### Sample Use

from IPython.display import Audio
Audio("cleaned_output.wav")

You can replace the input file with any `.mp3`, `.wav`, or `.m4a` audio sample of your choice.

## Model Architecture
- Causal convolutional encoder with skip connections
- BLSTM in bottleneck layer
- Transposed convolution decoder
- Custom waveform-level L1 loss function
![image](https://github.com/user-attachments/assets/aeef0587-f533-49fc-be31-84dc3f736368)
![image](https://github.com/user-attachments/assets/e225a2c9-2090-4020-bf25-b37dc4922333)
![image](https://github.com/user-attachments/assets/9645426a-dcf2-4265-bfbd-0efb5db1d1e7)
![image](https://github.com/user-attachments/assets/94c03cd6-02da-4d87-a044-c9384054af03)

Supports streaming and real-time processing.

## Performance Summary

| Metric                | Value                        |
|-----------------------|------------------------------|
| Latency (CPU)         | ~180ms per second of audio   |
| Model Size            | 134 MB (.pt)                 |
| Input Formats         | .mp3, .wav, .m4a              |
| Tested Noise Types    | Ringtone, traffic, wind, baby cry |
| Evaluation Metrics    | +12 dB SNR, +1.6 PESQ, MOS > 3.5 |
| Deployment Readiness  | Yes (local/offline compatible) |

## Use Cases

- Noise suppression for virtual meetings (Zoom, Google Meet)
- Audio pre-processing for speech-to-text systems
- Mobile app voice enhancement (recording/streaming)
- Smart assistant clarity enhancement
- Audiobook or podcast background cleanup

## Academic Citation

Ghanta, Pavankalyan
“Speech Enhancement Using Deep Learning Techniques.” IJFMR, Vol. 6, Issue 2, 2024.

## Author

**Pavankalyan Ghanta**  
Email: gpavankalyan1102@gmail.com  
LinkedIn: [linkedin.com/in/your-profile](https://linkedin.com/in/your-profile)  
GitHub: [github.com/your-username](https://github.com/your-username)

## For Recruiters & Reviewers

This project demonstrates:

- Real-time neural network deployment
- Full-cycle ML development (architecture, training, inference)
- Signal-level data handling and noise augmentation
- Model optimization for performance and generalization
- A successfully published research-backed implementation

For collaboration, feedback, or production integrations, feel free to reach out.
- Paste it into `README.md` in your VS Code project  
- Or edit directly into GitHub via the browser

Let me know if you'd like me to prepare a `.zip` of the full clean repo, with:
- This `README.md`
- `requirements.txt`
- `.gitignore`
- Folder structure set up for upload/pinning on GitHub

I'll send it instantly!
