# Emotion-Detection-with-Multiple-Data-Streams


## Introduction


Emotion is a conscious and subjective response that individuals experience when exposed to various stimuli, playing a vital role in natural social interactions. Throughout the day, individuals encounter diverse 
emotions, spanning from happiness and anger to sadness and excitement, which often propel them to undertake specific actions. In recent times, with the advancement of technology, the scientific community has endeavored to delve into the domain of Artificial Intelligence (AI) to create novel approaches for the analysis and interpretation of human emotions.


Initial research on emotion recognition primarily focused on single-mode methods, treating facial expression recognition (FER) and speech emotion recognition (SER) as separate topics. Nevertheless, numerous psychological investigations have both theoretically and experimentally underscored the significance of combining data from various modalities to create a unified depiction and understanding of emotions. Therefore, more recently, work in emotion recognition has paid more attention to multimodal emotion recognition. Emotion detection through multiple data streams like images, videos, speech, texts, and bio-signals is known as multimodal emotion detection.


In this Git Repository a novel multimodal emotion recognition model has been implemented. The model pipeline that the implementation follows is:


![image](https://github.com/Garima27dec/Emotion-Detection-with-Multiple-Data-Streams/assets/99138272/a7284339-b0a1-4c66-9970-bf8b21a03478)


## Implementation Sequence


1. [Data Extraction - MELD Dataset (using Hugging Face)](Data_extraction_MELD_Dataset.ipynb)
2. [Training the FER Model](FER) - using FER2013 dataset
3. [Training the SER Model](SER) - using RAVDESS dataset
4. [Training the Text Emotion Recognition Model](BERT_Text_Sentiment_Recognition.ipynb) - using Tweet Sentiment Data
5. [Training the Physiological signals-based Emotion Recognition Model](EEG_Brain_Signals_Emotion_Classification.ipynb) - using EEG Brainwave Dataset
6. [Model Fusion - Ensemble Model](Ensemble_Model.ipynb)
7. [Evaluation of the Ensemble Model](Models_Evaluation.ipynb) - using extracted MELD Dataset


## Conclusion


1. The ensemble model provides superior performance than the individual unimodal models - 29% higher than individual models.
2. The individual models, despite performing well with training dataset, do not perform well with an unseen dataset. This provides proof of model’s inability to generalize, or to adapt to changes in culture, context etc., which is also currently an underlying challenge in emotion recognition models.
3. Lack of adaptability in ensemble model: Decision-level fusion typically assumes that the decisions from individual sources are independent and equally reliable. However, this may not always be the case (for unseen data, one modality might have a higher weight than another).
4. The absence of physiological signals in the ensemble model has a notable impact on its overall accuracy.
5. The confusion matrices for each modality exhibit instances of misclassifications. These inaccuracies can be ascribed to a combination of factors, including suboptimal model performance and the intricate nature of emotions themselves. Emotions are intricate and multifaceted constructs, often occurring in tandem rather than in isolation. For instance, an individual may concurrently experience both happiness and surprise or anger and disgust. This inherent complexity of emotions poses a challenge in categorizing them into discrete, mutually exclusive emotional categories.
6. It is worth noting that the model's performance with regard to the anger and disgust classes has been suboptimal. This can be attributed to the limited representation of these classes in the training dataset. Despite the application of preprocessing steps, it is probable that the model would have benefited from an augmented dataset containing additional data for more effective training in these specific classes.

