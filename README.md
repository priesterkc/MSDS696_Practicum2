# MSDS696_Practicum2
MSDS 696 - Practicum 2 project (Spring 2023)

[Video Presentation: Singing Voice Detection for Audio Classification](https://drive.google.com/file/d/10fJ62fQ-F5ZrOLldd-1-a9RKtN7jk61_/view?usp=sharing)

[Presentation slides (PDF)](https://drive.google.com/file/d/10EKdY89VFAiH3OTIuP6kRFFP0J_ZE23D/view?usp=sharing)

## Background

Using songs from a seven member idol group (IDOLiSH7), the objective of this project was to detect and distinguish between the members' singing voices using deep learning for audio signal proccessing and voice recognition. The purpose was to understand what makes a singing voice unique and apply foundational knowledge of audio classification in music.

## Highlights

- **Audio classification** is the process of analyzing and identifying audio signals
  - Audio signal is the analog or digital representation of sound waves
    - More samples (measurement of signal strength, called amplitude) create a more accurate sound replication
  - Audio features can be categorized based on level of abstraction
    - High-level features are basic human understandable musical constructs, whereas low-level abstraction contains statistical features for machine understanding
- **Data preparation**
  - 21 songs, separated into 999 3-second MP3 audio file clips
    - Background music was removed from songs to reduce data noisiness
  - Used Mel Frequency Cepstral Coefficients (MFCCs) as significant acoustic features
    - MFCCs represent information about the spectral envelope (phonemes and timbre)
      - Timbre is the unique tone quality of a sound
- **Modeling**
  - Model 1
    - 22.5 kHz sample rate audio data
    - 40 MFCCs as input features
    - Trained for 100 epochs
    - 87% accuracy
  - Model 2
    - 44.1 sample rate audio data
    - 60 input features (20 MFCCs, 20 1st order derivative MFCCs, 20 2nd order derivative MFCCs)
    - Trained for 200 epochs
    - 84% accuracy
- **Discussions**
  - Model 1's better performance was unexpected, due to lower quality sample rate and use of fewer MFCCs (no derivatives)
  - Model 1 is best at predicting Sougo (91%), worst at predicting Nagi (82%)
  - Model 2 is best at predicting Mitsuki (94%), worst at predicting Sougo (82%)
  - Based on raw incorrect prediction totals, both models did not predict Iori well
  - No suspicion of overfitting; both models' training and test data accuracy rates were similar
- **Takeaways**
  - MP3 vs WAV files: WAV files have richer audio data information; MP3s are condensed and simplified information
  - Use less data: Audio clips from choruses are duplicative; would model place more importance on features if there was less data?
  - Standardize model testing: Use similar sample rates, MFCCs, and/or model types, then only change one variable to better observe signficant diffferences
  - Add validation data to model training: Help model have immediate feedback while training

## References and project material

[Vocal Remover website](https://vocalremover.org/)

[Audacity](https://www.audacityteam.org/)

[Apple iTunes](https://www.apple.com/itunes/)

[Video: Mel-Frequency Cepstral Coefficients Explained Easily](https://www.youtube.com/watch?v=4_SH2nfbQZ8&ab_channel=ValerioVelardo-TheSoundofAI)

[Article: Implementing Audio Classification Project using Deep Learning](https://www.analyticsvidhya.com/blog/2022/03/implementing-audio-classification-project-using-deep-learning/)

[Article: Understanding sample rates in digital audio](https://routenote.com/blog/what-is-sample-rate-in-audio/)

[Article: Audio Feature Extraction](https://devopedia.org/audio-feature-extraction)

[Article: Audio Deep Learning Made Simple: Sound Classification, Step-by-Step](https://towardsdatascience.com/audio-deep-learning-made-simple-sound-classification-step-by-step-cebc936bbe5)

[Article: Audio Data Analysis Using Deep Learning with Python (Part 1)](https://www.kdnuggets.com/2020/02/audio-data-analysis-deep-learning-python-part-1.html)

[Article: The dummy’s guide to MFCC](https://medium.com/prathena/the-dummys-guide-to-mfcc-aceab2450fd)
