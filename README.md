# Detecção e Segmentação de Tumores Cerebrais com YOLOv11 e Mask R-CNN

Este repositório contém o código-fonte, modelos treinados e dataset anotado utilizados na dissertação de mestrado sobre a detecção e segmentação de tumores cerebrais em imagens de ressonância magnética ponderadas em T1, com foco na integração de técnicas de inteligência artificial explicável.

## 📁 Estrutura do Repositório

```
.
├── dataset/
│   ├── train/
│   │   ├── images/         # Imagens de treino
│   │   └── labels/         # Anotações YOLO de treino
│   ├── valid/
│   │   ├── images/         # Imagens de validação
│   │   └── labels/         # Anotações YOLO de validação
│   ├── test/
│   │   ├── images/         # Imagens de teste
│   │   └── labels/         # Anotações YOLO de teste
│   └── data.yaml           # Arquivo de configuração do dataset
├── maskrcnn/
│   ├── train.py            # Script de treinamento com Detectron2
│   └── config.yaml         # Configuração personalizada do Mask R-CNN
├── yolov11/
│   ├── train.py            # Script de treinamento com Ultralytics YOLOv11
│   ├── gradcam.py          # Implementação manual do Grad-CAM
│   └── results/            # Curvas e métricas extraídas
├── requirements.txt        # Dependências do projeto
└── README.md
```

## 📌 Objetivo

Desenvolver um sistema capaz de detectar e segmentar tumores cerebrais a partir de imagens de ressonância magnética utilizando:

- **Mask R-CNN (Detectron2)**: modelo de referência em tarefas de segmentação por instância;
- **YOLOv11s-seg**: arquitetura moderna com foco em tempo real, com suporte a segmentação semântica;
- **Grad-CAM**: aplicação manual para interpretabilidade visual sobre as decisões do YOLOv11.

## 📊 Resultados

- **YOLOv11s-seg (validação)**:
  - mAP@0.5 (box/mask): 96.1% / 96.7%
  - F1-score: 0.938
  - Acurácia: ~96%
  - Tempo de inferência: ~6ms/img

- **Mask R-CNN (validação)**:
  - AP: 60.46%
  - Acurácia: 96.02%
  - Loss: 0.2604
  - FP: 5.61%
  - FN: 3.04%

## 🧠 Grad-CAM

A explicabilidade foi aplicada ao YOLOv11s-seg manualmente, utilizando hooks para captura de gradientes e ativações. Foram geradas visualizações interpretáveis para apoiar a validação médica dos resultados.


## 📚 Citação

Caso utilize este trabalho em sua pesquisa, cite a dissertação correspondente.

---

© 2025 - Projeto acadêmico desenvolvido para fins de pesquisa em diagnóstico assistido por IA.
