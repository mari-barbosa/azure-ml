# Previsão de Aluguel de Bicicletas com Aprendizado de Máquina Automatizado do Azure

Este repositório contém o arquivo JSON de saída da etapa final de um projeto do Azure Machine Learning focado na previsão de aluguel de bicicletas. O projeto utiliza aprendizado de máquina automatizado (AutoML) para treinar e avaliar um modelo baseado em dados históricos de aluguel de bicicletas.

## Visão Geral do Projeto

Este projeto demonstra o uso dos recursos de AutoML do Azure Machine Learning para construir um modelo de regressão que prevê o número de aluguéis de bicicletas com base em características sazonais e meteorológicas. Os dados utilizados são derivados do Capital Bikeshare (usados de acordo com o contrato de licença de dados) e incluem informações como dia, mês, ano, estação, feriado, dia da semana, situação climática, temperatura, umidade e velocidade do vento.

## Etapas:

1. **Criação do Workspace:** Um workspace do Azure Machine Learning foi criado para gerenciar os recursos do projeto.
2. **Aprendizado de Máquina Automatizado:** O AutoML foi usado para treinar vários modelos com diferentes algoritmos (especificamente RandomForest e LightGBM neste exemplo) e hiperparâmetros, identificando automaticamente o modelo de melhor desempenho com base no Erro Quadrático Médio Raiz Normalizado. O processo explorou várias configurações de modelo dentro de restrições definidas (número máximo de tentativas, tentativas simultâneas, limites de tempo e uma pontuação de métrica alvo).
3. **Implantação do Modelo:** O melhor modelo treinado foi implantado como um endpoint em tempo real, tornando-o acessível para previsões.
4. **Teste do Modelo:** O modelo implantado foi testado usando dados de entrada de amostra para verificar sua funcionalidade e precisão.

## Conteúdo do Repositório

Este repositório contém a saída JSON da etapa final do experimento AutoML. Este arquivo encapsula informações cruciais sobre o endpoint, como URIs de acesso, configurações de autenticação, detalhes de implantação e metadados gerais. Ele serve como um "manual" do endpoint, fornecendo todos os detalhes necessários para interagir com o modelo implantado.

## Uso

Este repositório serve principalmente como um registro do modelo final do projeto Azure ML. Para usar o modelo para previsões, você precisaria:

1. Recriar o ambiente do Azure ML (ou ter acesso ao workspace original).
2. Importar os detalhes do modelo do arquivo JSON fornecido.
3. Implantar o modelo como um endpoint em tempo real.
4. Enviar solicitações de previsão para o endpoint com dados de entrada formatados adequadamente.

## Detalhes do Projeto (do Exercício Original)

O exercício original usou os seguintes parâmetros para o trabalho AutoML:

* **Tipo de Tarefa:** Regressão
* **Conjunto de Dados:** `bike-rentals` (dados históricos de aluguel de bicicletas)
* **Coluna Alvo:** `rentals` (inteiro)
* **Métrica Primária:** Erro Quadrático Médio Raiz Normalizado
* **Modelos Permitidos:** RandomForest, LightGBM
* **Tentativas Máximas:** 3
* **Tentativas Concorrentes Máximas:** 3
* **Limite de Pontuação da Métrica:** 0,085
* **Computação:** Computação sem servidor com uma máquina virtual `Standard_DS3_V2` (ou equivalente).

## Tutorial Original

O tutorial original para este projeto pode ser encontrado em [Microsoft Learn - Explore o Aprendizado de Máquina Automatizado no Azure Machine Learning](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/01-machine-learning.html). Este recurso fornece um guia passo a passo para todo o processo, desde a criação do workspace até a implantação e teste do modelo.

## Aviso

Este repositório contém apenas a saída JSON. Ele não inclui os dados originais, o código de treinamento ou outros artefatos do projeto. Para reproduzir totalmente o projeto, você precisaria seguir o tutorial original e, potencialmente, adaptar os dados JSON fornecidos ao seu ambiente.