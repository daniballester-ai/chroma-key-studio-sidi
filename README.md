# 🎨 Chroma Key Studio

**Laboratório — Processamento de Imagens Digitais com OpenCV**  
🏫 Residência Tecnológica do SiDi · Professor: Thierry Moreira  

---

## 📝 Descrição

Chroma Key Studio é uma ferramenta de processamento de imagens que combina **segmentação por cor HSV**, **detecção facial por Haar Cascade** e **filtros artísticos** para criar composições criativas. O trabalho final engloba os três módulos da disciplina: transformações geométricas, filtragem espacial e segmentação.

## ✨ Funcionalidades

| Modo         | Descrição                                                  | Conceito do Curso                           |
| ------------ | ------------------------------------------------------------ | ------------------------------------------- |
| `chroma`   | 🌿 Remove fundo verde/azul/rosa e substitui por outra imagem | Segmentação HSV (Módulo 3)               |
| `overlay`  | 🎭 Detecta rostos e sobrepõe PNG com transparência         | Detecção facial (Haar Cascade)            |
| `completo` | 🔀 Chroma key + overlay simultaneamente                      | Combinação dos anteriores                 |
| `vintage`  | 🟫 Efeito sépia envelhecido                                 | Transformação de cores (Módulo 1)        |
| `vinheta`  | 🌑 Escurecimento gradual das bordas                          | Operações aritméticas (Módulo 2)        |
| `cartoon`  | 🖌️ Suavização + bordas para efeito cartoon               | Filtragem bilateral + threshold (Módulo 2) |
| `sketch`   | ✏️ Desenho em tons de cinza (dodge blend)                  | Filtragem + divisão de imagens (Módulo 2) |

## 🧠 Conceitos do Curso Aplicados

| Conceito                             | Técnica                      | Código                                                                 |
| ------------------------------------ | ----------------------------- | ----------------------------------------------------------------------- |
| 🎯**Segmentação por cor**    | Espaço HSV +`inRange`      | `cv2.cvtColor(BGR2HSV)`, `cv2.inRange()`                            |
| 🔲**Morfologia matemática**   | Abertura + fechamento         | `cv2.morphologyEx()`                                                  |
| 🫗**Filtragem espacial**       | Bilateral, Gaussiano, Mediana | `cv2.bilateralFilter()`, `cv2.GaussianBlur()`, `cv2.medianBlur()` |
| ✂️**Detecção de bordas**   | Threshold adaptativo          | `cv2.adaptiveThreshold()`                                             |
| 👤**Detecção facial**        | Haar Cascade                  | `cv2.CascadeClassifier()`                                             |
| ➗**Operações aritméticas** | AND, ADD, DIVIDE              | `cv2.bitwise_and()`, `cv2.add()`, `cv2.divide()`                  |
| 🔄**Transformações**         | Redimensionamento             | `cv2.resize()`                                                        |

## 🚀 Como Executar

Abra o notebook no Google Colab e execute célula por célula:

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)]([https://colab.research.google.com/github/daniballester-ai/chroma-key-studio-sidi/blob/main/chroma_key_studio.ipynb])

1. Faça upload das imagens de teste para o ambiente do Colab
2. Execute as células de setup (imports e função `mostrar()`)
3. Execute cada efeito em sequência: vintage → vinheta → cartoon → sketch → chroma → overlay → completo
4. Os resultados aparecem inline com `matplotlib`

Também é possível executar localmente:

```bash
pip install opencv-python numpy jupyter
jupyter notebook chroma_key_studio.ipynb
```

## 📸 Imagens Utilizadas no Notebook

| Imagem                                 | Finalidade                                                                                      |
| -------------------------------------- | ----------------------------------------------------------------------------------------------- |
| 🖼️`yatch.png`                      | Imagem principal para filtros (vintage, vinheta, cartoon, sketch) e cena de teste do chroma key |
| 🖼️`Lenna.png`                      | Detecção facial com Haar Cascade (rosto frontal)                                              |
| 👩`mulher.png`                       | Imagem com rosto frontal para teste de overlay                                                  |
| 🎩`chapeu_feminino.png`              | Elemento PNG com transparência para sobreposição facial                                      |
| 🟩 Cena sintética (gerada no código) | Fundo verde artificial para teste do chroma key                                                 |

> ℹ️ Faça upload de todas as imagens para o ambiente do Colab antes de executar as células.

## 📁 Estrutura do Repositório

```
📂 chroma-key-studio/
├── 📓 chroma_key_studio.ipynb   # Notebook principal (submeter)
├── 📄 README.md                  # Este relatório
├── 🖼️ yatch.png                 # Imagem principal para filtros e chroma key
├── 🖼️ Lenna.png                 # Detecção facial (Haar Cascade)
├── 👩 mulher.png                 # Rosto frontal para overlay
└── 🎩 chapeu_feminino.png       # Elemento PNG para sobreposição
```


---

> 🏫 **Residência Tecnológica do SiDi** · Processamento de Imagens com OpenCV · 2026

#SiDi #ResidenciaTecnologica #IA #OpenCV #Python

Este laboratório faz parte da **Fase 2** da residência tecnológica oferecida pelo **SiDi** através dos **Projetos Prioritários de Interesse Nacional (PPIs)**, que são iniciativas estratégicas reconhecidas pelo Governo Federal com o objetivo de impulsionar o desenvolvimento econômico e a inovação no país. Essas ações abrangem diferentes áreas, como tecnologia da informação e comunicação (TIC), infraestrutura e outros setores considerados essenciais para o avanço da competitividade nacional.
