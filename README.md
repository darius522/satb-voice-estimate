# satb-voice-estimate
repository for the MIR class final paper which tackles voice number estimation for SATB choral recordings

# Title:
Source Number Estimation for monoaural SATB choral recording
## Description:
Source number estimation is a task which consists in estimating the number of different sound sources that are present in an audio recording. Previously, there have been several approaches proposed in order to tackle the issue. Some of them are directly derived from source localization methodologies and are thus relying on the spatial information the recording may convey [1]. In the field of MIR, this task depends mainly on the fact that the spectra of common musical sources in a song are largely uncorrelated. The case of choral singing however, involves groups of people singing in harmony, which leads to higher correlation amongst the constituent signals. In this work, we will attempt in proposing a methodology which would allow to predict accurately the number of singer in a given SATB recording.
## Datasets:
For this task, the following datasets will be used:
• Choral Singing Dataset: https://zenodo.org/record/1286570#.Xkp7yi2ZPRY
• EsmucChoralSet: Soon publicly available
• A proprietary dataset: /
## Methods:
### Pre-processing:
- Short segments (song snippets) of audio with randomized SATB part configurations will be
created from the above-mentioned dataset as a first pre-processing step
- Upon creation of these segments, the ground truth represented by the number of singers for
each segment will be saved as one-hot vectors
- Compute the snippets’ Mel-Spectrograms
- ... Additional Steps TBD
### Training:
- Step 1 - Baseline: train Keras DNN model using previously-computed Mel-Spectrogram features (possibly using other, more relevant, features as well).
- Step 2 - Deep Salience approach: use the DeepSalience model from [2] in order to get a multi-pitch contour estimation. From there, we get the estimated numbers of singers.
## Evaluation:
Standard classifier evaluation metrics such as accuracy, F1,.. will be used. In addition, other standard ways of more detailed analysis (such as use of confusion matrices) will be presented.
[1] https://biblio.ugent.be/publication/8585239/file/8585241.pdf [2] https://github.com/rabitt/ismir2017-deepsalience
Darius Petermann MIR Task Proposal

