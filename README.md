# Image-Caption-Generator
🖼️ Image Caption Generator using CNN & LSTM
Automatically generate natural language descriptions for images using a deep learning model combining Convolutional Neural Networks (CNN) and Long Short-Term Memory (LSTM) networks.

📌 Project Overview
This project tackles the problem of image captioning — generating descriptive captions for images. It uses a combination of CNNs (for extracting visual features) and LSTMs (for generating text), enabling machines to interpret and describe visual content in human-like language.

🚀 Workflow
1. Dataset Used
Flickr8k Dataset:

~8,000 images and 40,000+ captions

Each image has 5 human-annotated captions

Contains both image files and a text file mapping image names to captions

2. Data Preprocessing
Text Cleaning:

Lowercasing, removing punctuation, filtering short/long words

Tokenization:

Built a vocabulary, mapped words to integers

Sequence Padding:

Padded input sequences to uniform length

Special Tokens:

Added <start> and <end> tokens for training

3. Feature Extraction (CNN)
Used InceptionV3 (pre-trained on ImageNet) to extract feature vectors from each image

Stripped final classification layer, used bottleneck features of size (2048,)

4. Caption Generation Model (LSTM)
Architecture:

Image Features → Dense Layer

Caption Sequences → Embedding + LSTM

Combined Output → Dense → Softmax (vocab size)

Optimizer: Adam

Loss Function: Sparse Categorical Crossentropy

EarlyStopping and ModelCheckpoint used during training

5. Model Training
Input: (image features, partial captions)

Output: next word in the caption

Trained for several epochs with a batch generator

6. Caption Prediction
Greedy Search: Generates a caption word-by-word using maximum probability

(Optional) Beam Search (can improve results but more complex)

Evaluated predictions qualitatively by comparing with human captions

7.Future Improvements
Add attention mechanism (e.g., Bahdanau attention)

Evaluate with BLEU / METEOR scores

Deploy using Streamlit or Gradio

Use a larger dataset (e.g., MSCOCO)
