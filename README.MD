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

![alt text][imagem2]

[imagem2]: https://github.com/David8Fernando/Encontrar-o-melhor-modelo-de-classifica--o-com-o-Machine-Learning-Automatizado/blob/main/img/mlw-dp100.png "Azure Machine Learning"

3. Feche todos os pop-ups que aparecerem no estúdio.
4. No Azure Machine Learning Studio, navegue até a página Compute(Computação) e verifique se a instância de computação e o cluster que você criou na seção anterior existem. A instância de computação deve estar em execução, o cluster deve estar ocioso e ter 0 nós em execução.

![alt text][imagem3]

[imagem3]: https://github.com/David8Fernando/Encontrar-o-melhor-modelo-de-classifica--o-com-o-Machine-Learning-Automatizado/blob/main/img/computacao.png "Computação - Compute"

5. Na guia Instâncias de computação , encontre sua instância de computação e selecione o aplicativo Terminal .

![alt text][imagem4]

[imagem4]: https://github.com/David8Fernando/Encontrar-o-melhor-modelo-de-classifica--o-com-o-Machine-Learning-Automatizado/blob/main/img/Terminal.png "Terminal"


6. No terminal, instale o Python SDK na instância de computação executando os seguintes comandos no terminal:

```python

 pip uninstall azure-ai-ml
 pip install azure-ai-ml

 ```


 7. Execute o seguinte comando para clonar um repositório Git contendo notebooks, dados e outros arquivos para seu espaço de trabalho:

 ```
  git clone https://github.com/MicrosoftLearning/mslearn-azure-ml.git azure-ml-labs

 ```

8. Quando o comando for concluído, no painel Arquivos , clique em ↻ para atualizar a exibição e verificar se uma nova pasta Usuários/ seu-nome-de-usuário /azure-ml-labs foi criada.

![alt text][imagem5]

[imagem5]: https://github.com/David8Fernando/Encontrar-o-melhor-modelo-de-classifica--o-com-o-Machine-Learning-Automatizado/blob/main/img/azure-ml-labs.png "Pasta azure-ml-labs"



## Treine um modelo de classificação com aprendizado de máquina automatizado

Agora que você tem todos os recursos necessários, pode executar o notebook para configurar e enviar o trabalho de aprendizado de máquina automatizado.

1. Abra o notebook Labs/06/Classification with Automated Machine Learning.ipynb .

Selecione Autenticar e siga os passos necessários se uma notificação aparecer solicitando autenticação.

2. Verifique se o notebook usa o kernel Python 3.8 - AzureML .

![alt text][imagem6]

[imagem6]: https://github.com/David8Fernando/Encontrar-o-melhor-modelo-de-classifica--o-com-o-Machine-Learning-Automatizado/blob/main/img/mlJupyter.png "Treinando o modelo de Classificação com Auto ML"



3. Execute todas as células no notebook.

Um novo trabalho será criado no espaço de trabalho do Azure Machine Learning. O trabalho rastreia as entradas definidas na configuração do trabalho, o ativo de dados usado e as saídas como métricas para avaliar os modelos.

Observe que os trabalhos de aprendizado de máquina automatizado contêm trabalhos filho, que representam modelos individuais que foram treinados e outras tarefas necessárias para execução.

4. Vá para Jobs e selecione o experimento auto-ml-class-dev .
5. Selecione o trabalho na coluna Nome de exibição .
6. Aguarde até que seu status mude para Concluído .
7. Quando o status do trabalho Automate Machine Learning mudar para Concluído , explore os detalhes do trabalho no estúdio:
* A aba "Data guardrails " mostra se seus dados de treinamento tiveram algum problema.
* A aba Models + child jobs mostrará todos os modelos que foram treinados. Selecione Explain model para o melhor modelo e crie a execução do job explanation usando o aml-cluster .
* Aguarde até que uma nova coluna Explained apareça ao lado da coluna Algorithm name e selecione View explanation . Pode ser necessário atualizar a lista de algoritmos para que essa opção apareça.
* Revise o painel criado para entender quais recursos influenciaram mais o valor-alvo.


## Excluir recursos do Azure
Ao terminar de explorar o Azure Machine Learning, você deve excluir os recursos que criou para evitar custos desnecessários do Azure.

Feche a guia do Azure Machine Learning Studio e retorne ao portal do Azure.
No portal do Azure, na página inicial , selecione Grupos de recursos .
Selecione o grupo de recursos rg-dp100-… .
Na parte superior da página Visão geral do seu grupo de recursos, selecione Excluir grupo de recursos .
Insira o nome do grupo de recursos para confirmar que deseja excluí-lo e selecione Excluir .