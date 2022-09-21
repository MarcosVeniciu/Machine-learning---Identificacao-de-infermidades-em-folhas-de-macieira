# Machine learning - Identificação de doenças em folhas de maçã.

Identificação de doenças em folhas de maçã, utilizando rede neural convolucional.  
Utilizando as imagens do dataset do kaggle Plant Pathology 2020, com imagens de folhas de macieira saudaveis, com rust, scab e com multiplas doenças.  
Serão treinados alguns modelos de CNN para tentar identificando as folhas que estão saudáveis, as que estão infectadas com a ferrugem da macieira, as que têm sarna da macieira e as que têm mais de uma doença.  
E comparar os resultados dos modelos com e sem Dada Augmentation.  <p>

Fonte do dataset: https://www.kaggle.com/competitions/plant-pathology-2020-fgvc7/data


Exemplos de imagens utilizadas para algumas das classes testadas. sendo saudaveis = 0,  
multiple_diseases = 1, rust = 2, scab = 3.  
![exemplo folhas](https://user-images.githubusercontent.com/42542651/191594601-b4b00d42-4585-4107-b318-7d2b98aa3730.jpg)

## MobileNetV2 sem Data Augmentation

### Ajuste do Hyperparâmetro - Taxa de Aprendizado
Para o ajuste da taxa de aprendizado foram realizadas 10 iterações, onde tentou minimizar a taxa de loss, com um limite maximo de 40 epocas.  
O DataSet possui 1821 imagens de folhas de maçã, sendo: 516 amostras de folhas saudaveis, 91 com multiple diseases, 622 com rust e 592 com scab. Sendo Distribuidos 80% para treinamento e 20% para validação. <p>

Valor da taxa de loss ao longo das iterações.  
![Curva de convergencia](https://user-images.githubusercontent.com/42542651/191589715-786e6e12-aa6c-426b-be74-6cff60e3ac14.jpg)


Melhor Parametros encontrado: Taxa de Aprendizado: 0.004694027 com uma taxa de Loos de 0.22845.

## Curva de prendizado do melhor modelo encontrado
Para os gráficos abaixo, o primeiro é do comportamento da taxa de loos para os dados de treinemento e validação, o segundo é o gráfico da acurácia de treinamento e 
validação e o terceiro é a diferença em pontos percentuais da acurácia de treinamento e validação.  
![Curva de aprendizado](https://user-images.githubusercontent.com/42542651/191591409-d8ef9b98-177d-4f4f-b7d0-cab153d4a74e.jpg)  

O melhor modelo encontrado após as 10 iterações possui uma acurácia de  0.9203 e uma taxa de loss de 0.2806. Resultado obtido com a função evaluate() utilizando o dataset de validação. <p>

## MobileNetV2 Com Data Augmentation

### Ajuste do Hyperparâmetro - Taxa de Aprendizado
Para o ajuste da taxa de aprendizado foram realizadas 10 iterações, onde tentou minimizar a taxa de loss, com um limite maximo de 40 epocas.  
O DataSet possui 2548 imagens de folhas de maçã, sendo: 637 amostras de folhas saudaveis, 637 com multiple diseases, 637 com rust e 637 com scab. Sendo Distribuidos 80% para treinamento e 20% para validação. <p>

Valor da taxa de loss ao longo das iterações.  
 (grafico 1)


Melhor Parametros encontrado: Taxa de Aprendizado: 0.004694027 com uma taxa de Loos de 0.22845.

## Curva de prendizado do melhor modelo encontrado
Para os gráficos abaixo, o primeiro é do comportamento da taxa de loos para os dados de treinemento e validação, o segundo é o gráfico da acurácia de treinamento e 
validação e o terceiro é a diferença em pontos percentuais da acurácia de treinamento e validação.  
(grafico 2)

O melhor modelo encontrado após as 10 iterações possui uma acurácia de  0.9203 e uma taxa de loss de 0.2806. Resultado obtido com a função evaluate() utilizando o dataset de validação.

