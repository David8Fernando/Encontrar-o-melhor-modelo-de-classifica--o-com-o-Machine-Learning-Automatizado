# Encontrar o Melhor Modelo de Classificação com o Machine Learning Automatizado

Este projeto tem como objetivo explorar e identificar o melhor modelo de classificação utilizando ferramentas de Machine Learning Automatizado (AutoML).

## Objetivo

- Prepare os dados.
- Configurar um experimento de Machine Learning automatizado.
- Execute um trabalho de Machine Learning automatizado.

## Pré-requisitos

subscrição na Azure que tenha acesso de nível administrador

## Provision an Azure Machine Learning workspace

Um espaço de trabalho do Azure Machine Learning fornece um local central para gerenciar todos os recursos e ativos necessários para treinar e gerenciar seus modelos. Você pode interagir com o espaço de trabalho do Azure Machine Learning por meio do estúdio, do Python SDK e do Azure CLI.

Você usará a CLI do Azure para provisionar o espaço de trabalho e a computação necessária e usará o SDK do Python para treinar um modelo de classificação com o Automated Machine Learning.

### Crie o espaço de trabalho e os recursos de computação

Para criar o espaço de trabalho do Azure Machine Learning, uma instância de computação e um cluster de computação, você usará o Azure CLI. Todos os comandos necessários são agrupados em um script Shell para você executar.

1 . Em um navegador, abra o portal do Azure em https://portal.azure.com/, entrando com sua conta da Microsoft.

[bash]: https://github.com/David8Fernando/Encontrar-o-melhor-modelo-de-classifica--o-com-o-Machine-Learning-Automatizado/blob/b77d81da8cc517b0a911c9c4596af15f2189ab74/img/shell.png