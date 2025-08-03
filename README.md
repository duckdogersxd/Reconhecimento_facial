# Projeto de Reconhecimento Facial com MediaPipe, TensorFlow e FaceNet

Este repositório apresenta um **Sistema de Reconhecimento Facial** desenvolvido em duas abordagens distintas:

## 📌 Abordagem 1: MediaPipe + CNN Simples (TensorFlow)

Nesta abordagem inicial, foi desenvolvido um classificador a partir de uma rede neural convolucional (CNN) simples, com as seguintes etapas:

### 🔧 Ferramentas Utilizadas
- **MediaPipe Face Detection**: Detecção e recorte dos rostos.
- **TensorFlow/Keras**: Construção e treinamento do classificador CNN.
- **Dataset LFW (Labeled Faces in the Wild)**: Conjunto de imagens de pessoas famosas.

### 📝 Processo
1. Carregamento do dataset LFW via TensorFlow Datasets.
2. Detecção e recorte das faces usando MediaPipe.
3. Organização das imagens em pastas por identidade.
4. Treinamento de uma CNN simples do zero para classificar as identidades.
5. Avaliação com imagens de teste.

### 📊 Resultados
- Acurácia observada: **~10%**.
- Limitação: Arquitetura da CNN muito simples e quantidade reduzida de imagens por pessoa.

---

## 📌 Abordagem 2: FaceNet Embeddings + KNN

Na segunda abordagem, foi utilizado um modelo pré-treinado (FaceNet) para extrair embeddings faciais e classificar as identidades com KNN.

### 🔧 Ferramentas Utilizadas
- **MTCNN (Mediapipe + PyTorch)**: Detecção e alinhamento facial.
- **FaceNet (InceptionResNetV1)**: Extração de embeddings faciais (pré-treinado em VGGFace2).
- **Scikit-learn KNN**: Classificador K-Nearest Neighbors (k=3).

### 📝 Processo
1. Detecção e alinhamento das faces com MTCNN.
2. Extração de embeddings faciais (vetores de 512 dimensões) com FaceNet.
3. Treinamento de um KNN utilizando os embeddings extraídos.
4. Testes de reconhecimento em imagens aleatórias do dataset.

### 📊 Resultados
- Acurácia observada: **100%**.
- Destaque: Abordagem robusta mesmo com datasets pequenos, graças ao uso de embeddings faciais pré-treinados.

---

## 🚀 Tecnologias
- MediaPipe
- TensorFlow / Keras
- Facenet-PyTorch
- Scikit-learn
- Google Colab
