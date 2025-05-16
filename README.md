# 🖼️ Classificação de Imagens com Machine Learning
Este código usa inteligência artificial para analisar fotos e tentar identificar se a pessoa é uma mulher branca ou preta. Ele combina técnicas de visão computacional e aprendizado de máquina para classificar imagens, treinar um modelo próprio e dar um palpite com porcentagem de certeza sobre a raça da pessoa na imagem.
Utiliza algumas bibliotecas como: transformers, Python Imaging Library, tensorflow keras, matplotlib e os e shutil.

## 🎯 Objetivo do Projeto

Este projeto é um "olho digital" 👀 que tenta identificar, com técnicas de Machine Learning e Visão Computacional, se uma pessoa em uma foto é **mulher branca** ou **mulher preta**. Ele:

- Usa modelos pré-treinados (como ViT e MobileNetV2);
- Treina uma CNN personalizada com dataset balanceado;
- Testa imagens da internet e retorna a classificação com porcentagem de confiança.

> 🧠 Analogia: É como ensinar uma criança a separar balas azuis e vermelhas, mas com fotos e algoritmos!

## 📦 Bibliotecas Utilizadas

| Biblioteca     | Função                                                                 | Analogia                                 |
|----------------|------------------------------------------------------------------------|------------------------------------------|
| `transformers` | Modelos pré-treinados como o ViT                                        | Um professor experiente 📚               |
| `PIL`          | Manipulação de imagens (abrir, redimensionar, etc.)                    | Um mini Photoshop em código 🖼️          |
| `tensorflow/keras` | Criação e treinamento de redes neurais                         | O cérebro do projeto 🧠                  |
| `matplotlib`   | Visualização de gráficos e imagens                                     | Canivete suíço para dados 📊             |
| `os / shutil`  | Organização de arquivos e diretórios                                   | O "organizador" do seu HD 🗂             |

## 🧠 Etapas do Projeto

### 1️⃣ Usando Modelos Pré-Treinados
- Utilização de modelos como `google/vit-base-patch32-384`.
- Reconhecimento geral de categorias (não apenas raciais).
- Ideal para testes rápidos.

### 2️⃣ Treinamento de CNN personalizada
- Pipeline com `ImageDataGenerator`, `Conv2D`, `MaxPooling`, `Flatten` e `Dense`.
- Acurácia controlada com `binary_crossentropy` e otimizador `Adam`.
- Classificação entre **mulheres brancas** e **mulheres pretas**.

### 3️⃣ MobileNetV2 com Transfer Learning
- Congelamento dos pesos base.
- Adição de camadas densas para especialização.
- Alta eficiência para datasets pequenos.

## 🖼️ Organização do Dataset

Pasta estruturada para o `ImageDataGenerator`:

```
dataset_organizado/
└── treinamento/
    ├── brancas/
    │   └── img1.jpg
    └── pretas/
        └── img2.jpg
```

## 🔄 Data Augmentation

Utiliza técnicas como:
- Rotação (`rotation_range`)
- Espelhamento (`horizontal_flip`)
- Deslocamento horizontal e vertical
- Normalização (rescale para [0,1])

## 🌐 Testando com Imagens da Web

Inclui função que:
1. Baixa a imagem via URL;
2. Redimensiona e pré-processa;
3. Mostra a imagem;
4. Faz a predição;
5. Exibe o resultado com porcentagem.
