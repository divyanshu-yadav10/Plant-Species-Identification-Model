🌿 Indian Plant Species Identification using ConvNeXt and Transfer Learning
Overview

This repository presents a deep learning–based system for Indian plant species identification using a ConvNeXt-based transfer learning architecture. The project focuses on accurately classifying plant species native to India while bridging the gap between automated image recognition and traditional botanical knowledge, including medicinal, culinary, and ecological relevance.

India hosts a highly diverse range of plant species with region-specific morphological characteristics that are often underrepresented in global plant classification datasets. This work addresses that limitation by training and fine-tuning a model specifically on an Indian plant dataset comprising 112 species, enabling more reliable and region-aware classification.

Key Contributions

Developed a specialized plant classification model tailored to Indian flora.

Leveraged ConvNeXt (CNN-based architecture) with transfer learning from ImageNet to capture fine-grained visual features such as leaf textures, venation patterns, and plant structures.

Designed a hybrid feature representation approach that captures both local spatial details and global contextual information.

Integrated plant classification with metadata related to traditional uses, enhancing the practical applicability of the system for botanical research, agriculture, and traditional medicine.

Achieved high classification performance across diverse plant species.

Dataset

Source: Indian plant image dataset introduced by IIT Hyderabad
(Indic Leaf Dataset: https://github.com/vamsidharmuthireddy/Indic-Leaf-Dataset
)

Number of Classes: 112 plant species

Data Characteristics: High-quality images collected from diverse botanical sources representing varied lighting conditions, backgrounds, and plant growth stages.

Methodology
1. Data Preprocessing & Augmentation

Images resized to 224 × 224 pixels.

Preprocessing aligned with ConvNeXt requirements.

Applied data augmentation techniques such as rotation, shifting, zooming, and horizontal flipping to improve generalization.

Performed stratified train–validation splitting to maintain class balance.

2. Model Architecture

Base Model: ConvNeXtBase pretrained on ImageNet (top layers removed).

Custom Classification Head:

Global Average Pooling

Fully connected layer (256 neurons, ReLU)

Dropout for regularization

Softmax output layer for multi-class classification

Transfer Learning Strategy:

Initial training with frozen base layers

Fine-tuning by unfreezing the last 80 layers of ConvNeXt

3. Training Configuration

Optimizer: Adam

Learning Rate:

Initial training: 1e-4

Fine-tuning: Reduced dynamically using ReduceLROnPlateau

Loss Function: Categorical Crossentropy

Callbacks:

EarlyStopping

ModelCheckpoint (best model selection)

Results

Overall Accuracy: ~94% on ~4,200 validation samples

Weighted F1-Score: ~90%

Macro Average: Precision ≈ 90%, Recall ≈ 89%

Class-wise Performance:

Sago Palm: ~99% Precision, Recall, and F1-score

Acalypha: Precision ≈ 98%, F1-score ≈ 95%

Banana: Precision ≈ 100%, F1-score ≈ 97%

These results demonstrate the model’s ability to effectively capture both fine-grained details and overall structural patterns across diverse plant species.

Applications

Botanical research and species documentation

Agricultural decision support systems

Preservation of indigenous plant knowledge

Educational tools for plant identification

Support systems for traditional and herbal medicine research

Conclusion

The proposed ConvNeXt-based transfer learning approach provides a robust and scalable solution for Indian plant species classification. By combining modern deep learning techniques with region-specific datasets and traditional knowledge integration, this system offers both high accuracy and practical relevance, addressing key gaps in existing plant classification models.
