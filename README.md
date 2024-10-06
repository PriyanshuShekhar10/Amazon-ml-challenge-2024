# Amazon-ML Hackathon: Feature Extraction from Images

## Overview

This project was developed for the **Amazon-ML Hackathon 2024**, where we ranked **22nd nationally**. The objective was to build a machine learning model to extract relevant feature entities, such as dimensions, weights, and other product-specific information, directly from images.

## Machine Learning Approach

### Primary Model: **InternVL**

Our primary model, **InternVL** ([GitHub Repository](https://github.com/OpenGVLab/InternVL)), is a multi-modal open-source large language model. InternVL's deep understanding of spatial and contextual relationships between visual elements and text allowed us to extract entities such as dimensions directly from images.

### Supplementary OCR Tools

To handle cases where InternVL did not provide sufficient predictions or detailed textual recognition was required, we utilized the following open-source OCR tools:

1. **[EasyOCR](https://github.com/JaidedAI/EasyOCR)**: Used for initial text extraction from images.
2. **[PaddleOCR](https://github.com/PaddlePaddle/PaddleOCR)**: Employed as a backup to cross-verify results from EasyOCR.
3. **[AppleOCR](https://github.com/louisbrulenaudet/apple-ocr)**: Used as the final step due to its superior accuracy in extracting detailed textual information.

### Combined Model Approach

We combined the outputs from **InternVL** and **AppleOCR** to ensure maximum accuracy and coverage in extracting entity values from images.

## Experiments Conducted

### 1. **Exploratory Data Analysis (EDA)**

We conducted extensive exploratory data analysis (EDA) on the dataset to identify key entity types. The majority of entities were related to dimensions, which guided our decision to prioritize **InternVL**.

### 2. **Model Selection and Evaluation**

- **InternVL** was primarily used to extract entities with a focus on dimension-related data due to its expertise in visual-language tasks.
- For cases where InternVL's predictions were insufficient, we utilized **EasyOCR**, **PaddleOCR**, and **AppleOCR**, with **AppleOCR** proving to be the most reliable.

### 3. **Integration and Fine-Tuning**

We combined the predictions from **InternVL** and **AppleOCR** and fine-tuned the model to address noisy data and outliers. Special attention was given to optimizing predictions for dimension entities.

### 4. **Handling Outliers**

We performed data preprocessing and normalization to handle outliers, refine entity extraction, and ensure robustness against rare or ambiguous cases.

## Conclusion

By integrating **InternVL** and **AppleOCR**, we developed a robust solution for entity extraction from images, achieving an **F1 score of 0.673**. The model's ability to interpret visual-language relationships, combined with accurate OCR performance, highlights the value of using a multi-model approach for data extraction challenges.

## Acknowledgements

We are proud to have achieved a **rank of 22nd nationally** in the Amazon-ML Hackathon 2024, thanks to the innovative approach and collaboration of the team.
