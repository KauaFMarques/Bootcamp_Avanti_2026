# Atividade 01 - Conceitos Básicos de Machine Learning
  
**Aluno: Kauã Ferreira Marques**

---

## 1. Explique, com suas palavras, o que é machine learning?

Um modelo de aprendizado de máquina é um programa que é usado para detectar padrões ou tomar decisões a partir de um conjunto de dados que antes não havia visto. 

Por exemplo, no processamento de linguagem natural, modelos de aprendizado de máquina conseguem analisar e reconhecer corretamente a intenção através de frases ou combinações de palavras nunca antes ouvidas. No reconhecimento de imagens, um modelo pode ser utilizado para identificar e analisar os objetos. 

Um modelo de aprendizado de máquina pode realizar essas funções ao passar por um treinamento com base em um conjunto de dados que ensinam a máquina a atender tarefas encontrando padrões.

---

## 2. Explique o conceito de conjunto de treinamento, conjunto de validação e conjunto de teste em machine learning.

### Conjunto de Treinamento
O conjunto de treinamento é o conjunto de dados central base para o desenvolvimento do modelo. É a parte que é usada para treinar um algoritmo para identificar padrões, relacionamentos e estruturas dentro dos dados. Ele é literalmente o "material de aprendizado" para o modelo realizar as tarefas para construir a compreensão interna de como fazer previsões ou decisões. 

Ele influencia diretamente o nível de aprendizado do modelo. Um conjunto de treinamento maior e mais diversificado geralmente leva a um melhor desempenho porque o modelo está exposto a mais variações e casos extremos. Dados de treinamento de baixa qualidade ou desbalanceados podem levar a modelos tendenciosos ou imprecisos.

### Conjunto de Validação
O conjunto de validação é usado para avaliar um determinado modelo durante o processo de desenvolvimento. É necessário para ajustar os hiperparâmetros do modelo. Por isso, o modelo ocasionalmente vê esses dados, mas nunca "aprende" com eles, mas o desenvolvedor os utiliza para escolher qual versão do modelo funciona melhor. Assim, o conjunto de validação afeta um modelo, mas apenas indiretamente.

> **Exemplo:** Usamos a validação para testar se um modelo com 100 árvores de decisão (Random Forest) performa melhor do que um com 200 árvores.

### Conjunto de Teste
O conjunto de dados de Teste fornece o padrão ouro usado para avaliar o modelo. Ele só é usado quando um modelo está completamente treinado. O conjunto de teste geralmente é usado para avaliar modelos concorrentes. O conjunto de testes geralmente é bem selecionado. Ele contém dados cuidadosamente amostrados que abrangem as várias classes que o modelo enfrentaria, quando usado no mundo real.

> **Exemplo:** É a "prova final" que o modelo nunca viu, servindo para estimar de forma justa o seu erro de generalização.

---

## 3. Explique como você lidaria com dados ausentes em um conjunto de dados de treinamento.

A decisão mais importante no tratamento de dados ausentes não é qual algoritmo ou técnica usar, mas sim qual suposição fazer sobre por que os dados estão faltando. A teoria estatística classifica a ausência de dados em três mecanismos. Entender essa taxonomia é a base para qualquer abordagem metodologicamente sólida. 

É importante notar que essa classificação é uma suposição baseada no conhecimento de domínio e no processo de coleta de dados, não uma propriedade que pode ser matematicamente provada a partir dos dados em si.

### Missing Completely at Random (MCAR) - A Verdadeira Aleatoriedade
**Definição:** A probabilidade de um valor estar ausente é completamente independente de qualquer outra variável no dataset e do próprio valor que estaria presente. Em outras palavras, a ausência é um evento puramente estocástico.

> **Exemplo:** Um sensor falha por um pico de energia aleatório, perdendo uma leitura de temperatura de forma completamente aleatória.

### Missing at Random (MAR) - A Ausência Preditiva
**Definição:** A probabilidade de um valor estar ausente não depende do valor ausente em si, mas pode ser explicada por outras variáveis observadas no conjunto de dados. O termo "ao acaso" aqui é um tanto enganador; a ausência não é puramente aleatória, mas é aleatória após levar em conta as outras variáveis.

> **Exemplo:** A probabilidade de uma pessoa não informar a renda (dado ausente) é maior se ela for jovem, e a idade é uma variável observada.

### Missing Not at Random (MNAR) - O Cenário Mais Complexo
**Definição:** A probabilidade de um valor estar ausente está diretamente relacionada ao valor que estaria presente. A ausência é sistemática e informativa, dependendo de fatores não observados.

> **Exemplo:** Pessoas com altos salários tendem a não responder à pergunta sobre seu salário. A ausência está diretamente ligada ao valor ausente.

---

## 4. O que é uma matriz de confusão e como ela é usada para avaliar o desempenho de um modelo preditivo?

A matriz de confusão é uma ferramenta usada para avaliar o desempenho de um modelo e é representada visualmente como uma tabela. Ela fornece uma camada mais profunda de informações aos profissionais de dados sobre o desempenho, os erros e os pontos fracos do modelo. Isso permite que os profissionais de dados analisem ainda mais seu modelo por meio de ajustes finos.

### Componentes da Matriz de Confusão
- **Verdadeiro Positivo (TP):** Seu modelo previu a classe positiva. Por exemplo, identificar um e-mail de spam como spam.
- **Verdadeiro Negativo (TN):** Seu modelo previu corretamente a classe negativa. Por exemplo, identificar um e-mail normal como não sendo spam.
- **Falso Positivo (FP):** Seu modelo previu incorretamente a classe positiva. Por exemplo, identificar um e-mail normal como spam.
- **Falso Negativo (FN):** Seu modelo previu incorretamente a classe negativa. Por exemplo, identificar um e-mail de spam como um e-mail normal.

### Métricas Derivadas da Matriz de Confusão
A partir da matriz de confusão, calculamos métricas-chave que avaliam o modelo de forma mais robusta do que a simples acurácia, especialmente em problemas com classes desbalanceadas. As principais são:

- **Acurácia:** (TP + TN) / (TP + TN + FP + FN) - Mede a taxa geral de acertos.
- **Precisão:** TP / (TP + FP) - Mede, dentre todas as previsões positivas feitas, quantas estavam corretas. É útil quando o custo de um Falso Positivo é alto (ex: classificar um e-mail normal como spam).
- **Recall (Sensibilidade):** TP / (TP + FN) - Mede, dentre todos os casos positivos reais, quantos o modelo conseguiu capturar. É útil quando o custo de um Falso Negativo é alto (ex: não diagnosticar uma doença grave).
- **F1-Score:** A média harmônica entre Precisão e Recall, usada quando se busca um equilíbrio entre as duas métricas.

---

## 5. Em quais áreas você acha mais interessante aplicar algoritmos de machine learning?

### 1. Agricultura (Agro 4.0)
A aplicação de Machine Learning na agricultura permite a transição para a agricultura de precisão, tornando as lavouras mais eficientes e sustentáveis.

- **Monitoramento de pragas e doenças:** Algoritmos de visão computacional analisam imagens de drones e satélites para identificar focos de doenças nas plantas antes que se espalhem.
- **Previsão de safra e clima:** Modelos preditivos cruzam dados históricos e meteorológicos para otimizar o uso da água e prever o rendimento das colheitas.

### 2. Saúde e Medicina
O aprendizado de máquina na saúde tem um potencial transformador, impactando desde o diagnóstico até a gestão hospitalar.

- **Diagnóstico por imagem:** Redes neurais são treinadas para identificar anomalias em raios-X, ressonâncias magnéticas e tomografias (como detecção precoce de câncer), muitas vezes com precisão superior à média humana.
- **Medicina personalizada:** Algoritmos analisam o histórico genético e clínico do paciente para sugerir tratamentos customizados e prever o risco de doenças crônicas.

### 3. Construção Civil
Tradicionalmente um setor de baixa margem e reativo, a construção civil tem adotado o aprendizado de máquina para se tornar mais proativa.

- **Previsão de riscos e atrasos:** O uso de algoritmos preditivos na análise de projetos ajuda a antecipar estouros de orçamento e gargalos de cronograma.
- **Segurança no canteiro de obras:** Câmeras inteligentes monitoram imagens em tempo real para detectar se os trabalhadores estão utilizando Equipamentos de Proteção Individual (EPIs) adequados.

### 4. Manufatura e Indústria
Na manufatura, o aprendizado de máquina é o "cérebro" por trás da automação inteligente, impulsionando a eficiência e a segurança.

- **Manutenção preditiva:** Analisa dados de sensores em máquinas industriais para prever falhas mecânicas antes que elas ocorram, evitando paradas não programadas na linha de produção.
- **Controle de qualidade:** Modelos de visão computacional inspecionam peças e produtos na linha de montagem para identificar defeitos milimétricos com alta velocidade.

---