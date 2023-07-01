# Extracting Social Determinants of Health from Unstructured Clinical Notes Using Transformer Based Natural Language Processing Models

SDoH are environmental factors that affect the health and quality of life of a population that may not be captured by healthcare providers. Instead, this information often exists in the unstructured clinical notes within an electronic health record (EHR). Natural language processing (NLP) is a powerful technique for unstructured text classification which can be used to classify clinical notes within EHRs.

Our objective was to design and validate a novel transformer-based natural language processing (NLP) model that enables social determinants of health (SDoH) classification from unstructured clinical notes at scale. We used a diverse dataset from integrated healthcare networks within the OMNY HealthTM platform. A domain adapted and fine-tuned Bidirectional Encoder Representations from Transformers (BERT)-based model was proposed to enable SDoH classification from EHR unstructured clinical notes. The application of this model for SDoH classification from a large-scale EHR database was also explored.

Experimental results showed that a domain-adapted BERT model outperformed other pre-trained models with 91.7% macro-F1 and 93.3% micro-F1 scores for the task of classifying education; unemployment and job insecurity; food insecurity; housing, basic amenities and the environment; and access to affordable health services of decent quality SDoH domains. These results demonstrate the excellent ability to extract and categorize SDoH from unstructured clinical text. Further, we demonstrated SDoH classification and categorization in a large-scale EHR database (N=540,719 patients) and reported summary statistics and interpretations based on the structured demographic information output by the model.

## Overview
Overview of the automated SDoH extraction using an NLP model and EHR feature expansion. (a) Healthcare systems collect and store patient medical information. (b) EHRs which contain patient medical history are obtained from healthcare providers. (c) Unstructured clinical notes are extracted from the EHRs. (d, e) The NLP model receives the clinical text as input and extracts SDoH categories in form of a multi-label output. (f) The extracted SDoH information are appended to the EHR in an structured format. (g) The updated EHR is stored in the OMNY Health platform. EDU: Education; UJI: Unemployment and Job Insecurity; FI: Food Insecurity: HAE: Housing, basic amenities and the environment; AHS: Access to affordable health services of decent quality; SDoH: social determinants of health; EHR: electronic health record; NLP: natural language processing.

<p align="center">
<img src="https://github.com/mohnikbakht/SDoH_NLP_Demo/blob/main/figures/figure1.png" alt="overview figure" width="600"/>
</p>

## Architecture 

Procedure of the NLP model training for the SDoH extraction downstream task. (a) The clinical notes are extracted from the EHRs. (b) The text is pre-processed to remove special characters and empty notes and become compatible with the NLP model. (c) Dataset is split into two groups, SDoH labeled and unlabeled for supervised and unsupervised training respectively. (d) Model is initialized with a pre-trained model from the Hugging Face Hub, and domain adapted using the unlabeled set and through MLM. (e) One additional layer is added after the pooling layer to the domain adapted model (classifier body) to fine-tune the domain adapted model on downstream task (multi-label SDoH classifier). (f) The multi-label output of the classifier since none or all SDoH categories can be present in a text. (g) In inference, the trained model is used for SDoH extraction from the whole dataset. MLM: masked language modeling; EHR: electronic health record.

<p align="center">
<img src="https://github.com/mohnikbakht/SDoH_NLP_Demo/blob/main/figures/figure2.png" alt="Architecture figure" width="600"/>
</p>

## Results

<p align="center">
<img src="https://github.com/mohnikbakht/SDoH_NLP_Demo/blob/main/figures/figure5.png" alt="Architecture figure" width="600"/>
</p>

<p align="center">
<img src="https://github.com/mohnikbakht/SDoH_NLP_Demo/blob/main/figures/figure4.png" alt="Architecture figure" width="600"/>
</p>

 ## Conclusion

We designed and validated a novel transformer-based NLP model for SDoH classification from EHR unstructured clinical notes of the OMNY HealthTM integrated network. We further demonstrated the effectiveness of this model for automatically extracting SDoH from large-scale EHR unstructured clinical notes. The use of an NLP model such as the one introduced in this work can help automate the classification of SDoH and converting the SDoH information within unstructured text to structured features. This inclusion could effectively enable structured inclusion of SDoH factors in medical research and make SDoH factors easier to access to clinicians and public health analysts.


