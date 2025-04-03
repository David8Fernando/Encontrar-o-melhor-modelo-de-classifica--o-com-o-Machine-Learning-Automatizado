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

1. Em um navegador, abra o portal do Azure em https://portal.azure.com/, entrando com sua conta da Microsoft.


2. Selecione o botão [>_] ( Cloud Shell ) no topo da página à direita da caixa de pesquisa. Isso abre um painel do Cloud Shell na parte inferior do portal
![alt text][shell]

[shell]: https://github.com/David8Fernando/Encontrar-o-melhor-modelo-de-classifica--o-com-o-Machine-Learning-Automatizado/blob/b77d81da8cc517b0a911c9c4596af15f2189ab74/img/shell.png "Shell"

3. Selecione Bash se solicitado. Na primeira vez que você abrir o cloud shell, será solicitado que você escolha o tipo de shell que deseja usar ( Bash ou PowerShell ).

![alt text][bash]

[bash]: https://github.com/David8Fernando/Encontrar-o-melhor-modelo-de-classifica--o-com-o-Machine-Learning-Automatizado/blob/main/img/bash.png "Bash"

4. Verifique se a assinatura correta está especificada e se Nenhuma conta de armazenamento necessária está selecionada. Selecione Aplicar .

![alt text][guiashell]

[guiashell]: https://github.com/David8Fernando/Encontrar-o-melhor-modelo-de-classifica--o-com-o-Machine-Learning-Automatizado/blob/main/img/guiashell.png "Guia Shell"

5. No terminal, digite os seguintes comandos para clonar este repositório:

```
 rm -r azure-ml-labs -f
 git clone https://github.com/MicrosoftLearning/mslearn-azure-ml.git azure-ml-labs
```
![alt text][imagem1]

[imagem1]: https://github.com/David8Fernando/Encontrar-o-melhor-modelo-de-classifica--o-com-o-Machine-Learning-Automatizado/blob/main/img/shell1.png "Guia Shell1"


6. Após o repositório ser clonado, digite os seguintes comandos para alterar a pasta deste laboratório e execute o script setup.sh que ele contém:
```
 cd azure-ml-labs/Labs/06
 ./setup.sh
```

## Clonar os materiais do laboratório
Depois de criar o espaço de trabalho e os recursos de computação necessários, você pode abrir o estúdio do Azure Machine Learning e clonar os materiais de laboratório no espaço de trabalho.

1. No portal do Azure, navegue até o espaço de trabalho do Azure Machine Learning chamado mlw-dp100-… .
2. Selecione o espaço de trabalho do Azure Machine Learning e, na página Overview , selecione Launch studio . Outra aba será aberta no seu navegador para abrir o Azure Machine Learning Studio.
3. Feche todos os pop-ups que aparecerem no estúdio.
4. No Azure Machine Learning Studio, navegue até a página Compute e verifique se a instância de computação e o cluster que você criou na seção anterior existem. A instância de computação deve estar em execução, o cluster deve estar ocioso e ter 0 nós em execução.
5. Na guia Instâncias de computação , encontre sua instância de computação e selecione o aplicativo Terminal .
6. No terminal, instale o Python SDK na instância de computação executando os seguintes comandos no terminal:

```python

 pip uninstall azure-ai-ml
 pip install azure-ai-ml

 ```