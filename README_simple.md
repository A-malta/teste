# Desafio IA — Segmentação de Vegetação

Este projeto realiza a segmentação de imagens aéreas (ortomosaicos) para detecção de vegetação, utilizando técnicas de visão computacional e aprendizado de máquina.

## Estrutura do Projeto

```
Desafio-IA/
│
├── dataset/
│   ├── crops/                # Blocos do ortomosaico
│   ├── masks/                # Máscaras binarizadas
│   └── images_validation/    # Imagens para validação/inferência
│
├── model/
│   └── model.h5              # Modelo treinado
│
├── results/                  # Resultados da inferência
│
├── divide_orthomosaic.py     # Etapa 1
├── binarize_images.py        # Etapa 2
├── train_model.py            # Etapa 3
├── model_inference.py        # Etapa 4
└── README.md
```

## Requisitos

Instale as dependências necessárias:

```bash
pip install -r requirements.txt
```

Bibliotecas recomendadas:
```
tensorflow
opencv-python
numpy
matplotlib
scikit-learn
```

## Execução

### 1. Divisão do Ortomosaico

```bash
python divide_orthomosaic.py --input orthomosaic.tif --output dataset/crops
```

### 2. Binarização das Imagens

```bash
python binarize_images.py --input dataset/crops --output dataset/masks
```

### 3. Treinamento do Modelo

```bash
python train_model.py --rgb dataset/crops --groundtruth dataset/masks --modelpath model/model.h5
```

### 4. Inferência com o Modelo Treinado

```bash
python model_inference.py --rgb dataset/images_validation --modelpath model/model.h5 --output results
```

## Resultados
![Resultado](results/01.jpg)
![Resultado](results/03.jpg)

