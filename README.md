# Classificador de Emoções Faciais com Redes Neurais Convolucionais (CNNs)

## Descrição
Este projeto implementa um **classificador de emoções faciais** utilizando **Redes Neurais Convolucionais (CNNs)**. Nosso modelo foi projetado para reconhecer sete emoções em imagens faciais:  
**Raiva, Nojo, Medo, Felicidade, Neutro, Tristeza e Surpresa**.  

As aplicações incluem:  
- Monitoramento psicológico e análise de comportamento.  
- Interfaces humano-computador mais intuitivas.  
- Sistemas de segurança, marketing e educação adaptativa.  

O projeto foi desenvolvido em **Python**, no ambiente **Jupyter Notebook**, utilizando bibliotecas como **TensorFlow**, **OpenCV** e **Matplotlib**.

---

## Dataset
Utilizamos o dataset **FER2013**, amplamente reconhecido na área de aprendizado profundo, contendo:
- **28.709 imagens** para treinamento.
- **3.589 imagens** para validação.
- Imagens com resolução de **48x48 pixels** convertidas para escala de cinza.

[FER2013 Dataset no Google Drive](https://drive.google.com/drive/folders/1acCAM0Y8VAnCCk3LX1NxqK-SqwqOKshC?usp=sharing)

---

## Estrutura da Rede Neural
O modelo é baseado na arquitetura **LittleVGG**, composta por:
1. **Blocos Convolucionais** com filtros de tamanho 3x3.
2. **Camadas de Pooling** para redução de dimensionalidade.
3. **Dropout** (20%) para evitar overfitting.
4. **Batch Normalization** para acelerar o treinamento.
5. **Camadas Fully Connected** para classificação final.

### Configurações
- **Função de perda**: Cross-Entropy Categórica.
- **Otimizador**: Adam.
- **Hiperparâmetros**:
  - Épocas: 70
  - Batch size: 16
  - Taxa de aprendizado inicial: 0.001

---

## Resultados
### Métricas de Avaliação
- **Acurácia de Treinamento**: 75.4%  
- **Acurácia de Validação**: 58.6%

### Tabela de Métricas
| Classe        | Precisão | Recall | F1-Score | Amostras |
|---------------|----------|--------|----------|----------|
| **Raiva**     | 0.55     | 0.60   | 0.57     | 491      |
| **Nojo**      | 0.57     | 0.65   | 0.61     | 55       |
| **Medo**      | 0.49     | 0.42   | 0.45     | 528      |
| **Felicidade**| 0.75     | 0.90   | 0.82     | 879      |
| **Neutro**    | 0.27     | 0.20   | 0.23     | 626      |
| **Tristeza**  | 0.55     | 0.50   | 0.52     | 594      |
| **Surpresa**  | 0.69     | 0.76   | 0.73     | 416      |

### Matriz de Confusão
O modelo apresentou boas predições para a classe **Felicidade**, mas confusões significativas entre **Medo** e **Tristeza**.

---

## Casos de Uso
### 1. Classificação de Imagens Individuais
O modelo foi testado com imagens únicas, mostrando bom desempenho em classes claras como **Felicidade** e **Raiva**, mas enfrentando dificuldades em **Neutro** e **Surpresa**.

### 2. Classificação de Múltiplas Faces
O modelo detecta múltiplos rostos em imagens, classificando as emoções de cada face individualmente com o auxílio do **OpenCV**.

### 3. Análise de Vídeos
O classificador foi integrado a um pipeline para análise de vídeos, rotulando as emoções em cada frame.  
[Vídeo processado no Google Drive](https://drive.google.com/drive/folders/1acCAM0Y8VAnCCk3LX1NxqK-SqwqOKshC?usp=sharing)

---

## Limitações e Melhorias Futuras
### Limitações
- **Desbalanceamento do dataset**: Classes como "Nojo" possuem poucas amostras.  
- **Generalização**: O modelo tem dificuldade em generalizar para imagens fora do dataset.  

### Melhorias Futuras
1. **Oversampling** para aumentar amostras das classes menores.  
2. Experimentar **arquiteturas avançadas**, como **ResNet** ou **EfficientNet**.  
3. **Treinamento transferido** com redes pré-treinadas para melhorar a performance.  
