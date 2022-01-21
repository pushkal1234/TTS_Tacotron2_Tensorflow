# TTS_Tacotron2_Tensorflow

Text-to-Speech Recognition system using tacotron 2 architecture and Tensorflow Framework.

I had trained the model on LJ Speech Dataset open source speech datasets.

LJ Speech Dataset is recently widely used as a benchmark dataset in the TTS task because it is publicly available. It has 24 hours of reasonable quality samples.
We can get the dataset from https://keithito.com/LJ-Speech-Dataset/  


# About the Dataset:

This is a public domain speech dataset consisting of 13,100 short audio clips of a single speaker reading passages from 7 non-fiction books. A transcription is provided for each clip. Clips vary in length from 1 to 10 seconds and have a total length of approximately 24 hours.

The audio was recorded in 2016-17 by the LibriVox project and is also in the public domain.

# File Format
Metadata is provided in transcripts.csv. This file consists of one record per line, delimited by the pipe character (0x7c). The fields are:

1) **ID:** this is the name of the corresponding .wav file

2) **Transcription:** words spoken by the reader (UTF-8)
 
3) **Normalized Transcription:** transcription with numbers, ordinals, and monetary units expanded into full words (UTF-8).
Each audio file is a single-channel 16-bit PCM WAV with a sample rate of 22050 Hz.

# Training

1) Download LJ Speech Dataset from the link mentioned above.

2) Adjust hyper parameters in model_hyperparameters.py. (If you want to do preprocessing, set prepro True).

3) Run python train_data.py. (If you set prepro True, run python Data_preprocessing.py first)

4) Run python evaluation.py regularly during training.

# File description

1) model_hyperparameters.py --> includes all hyper parameters that are needed.

2) Model_synthesis.py --> creates sliced sound files from raw sound data, and constructs necessary information.
  
3) Data_preprocessing.py --> loads vocabulary, training/evaluation data.

4) load_data_LJSpeech.py --> loads data and put them in queues so multiple mini-bach data are generated in parallel.

5) utils.py --> has several custom operational functions.

6) modules.py --> contains building blocks for encoding/decoding networks.

7) networks.py --> has three core networks, that is, encoding, decoding, and postprocessing network.

8) train_data.py --> is for training.

9) evaluation.py --> is for sample synthesis.

# Sample Synthesis

Run python Model_Synthesis.py and check the files in samples.

I had generated the samples for inference and testing after training it for 200k steps

# Requirements

1) NumPy >= 1.11.1
 
2) TensorFlow == 1.2

3) librosa

4) tqdm
