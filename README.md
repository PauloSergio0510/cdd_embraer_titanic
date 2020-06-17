<h1 align="center"> CDD Embraer Titanic </h1>

<p align="justify"> A construção do Titanic levou cerca de 2 anos e custou 7,5 milhões de dólares (valores da época). Com 269 metros de comprimento, 28 metros de largura e 53 metros de altura, operava com uma tripulação de 892 pessoas e poderia levar até 2435 passageiros (espalhados pelas três classes disponíveis).

Pensado para ser o mais seguro e luxuoso navio da época, foi lançado ao mar em 1911, ganhando fama de ser “inafundável”.

O naufrágio do Titanic teve como fatores contribuintes causas naturais (como o clima) e causas humanas (negligência e excesso de confiança). Independente das causas, o fato é que seu naufrágio matou 1502 pessoas de um total de 2224 passageiros.

Embora aqueles que escaparam com vida tiveram sua boa dose de sorte, alguns grupos de pessoas eram mais propensos a escaparem da morte do que outros. Por exemplo, mulheres, crianças e passageiros da 1ª Classe. Assim, nota-se que existe algum padrão que pode ser extraído dos dados brutos. </p>

<h2 align="justify"> Introdução a Análise do Acidente do Titanic </h2>
<p align="justify"> O projeto consiste em analisar os dados sobre o acidente do RMS Titanic, construindo um estudo para prever a probabilidade de quais passageiros sobreviveriam ao naufrágio e o que influenciou na morte ou não dos mesmos. </p>

<h2 align="justify"> Objetivo</h2>
<p align="justify"> O objetivo deste trabalho é aplicar os conhecimentos adquiridos em sala de aula e apresentar um modelo para análise dos dados referente ao acidente. Utilizando métodos e testes estatísticos para prever a probabilidade de o passageiro ter sobrevivido (1) ou não (0), analisando os resultados e escolhendo um bom modelo que seja satisfatório.</p>

### Instalação do repositório

Para executar local:
```bash
$git clone https://github.com/PauloSergio0510/cdd_embraer_titanic.git
```

Para acessar no Colab do Google:
```bash
https://colab.research.google.com/github/PauloSergio0510/cdd_embraer_titanic/blob/master/titanic.ipynb
```

### Obtenção dos Dados
1. Importando as bibliotecas necessárias

- O comando `import` realiza a importação das biblioetecas, as bibliotecas contêm comandos uteis para o desenvolvimento do projeto.

  - O pacote `numpy` possui funções de linear álgebra.
  - O pacote `Pandas` possui funções de data processing, CSV file I/O.
  - O pacote `matplotlib` possui funções para criação de gráficos e visualizações de dados.
  - O pacote `seaborn` possui funções para análise de dados estatísticos.

```bash
$ pip install numpy pandas matplotlib seaborn 
$ apt install python3-tk
```
  
2. Carregar arquivos CSV

<p align="justify"> Após abrir o notebook o arquivo <b>titanic.ipynb</b> é necessário carregar os arquivos CSV dentro da plataforma.</p>

- conjunto de treinamento [Train](train.csv)
- conjunto de teste [Test](test.csv)

### Exploração dos Dados
1. Listar a quantidade de variáveis `(colunas)` e o tamanho `(linhas)` do conjunto treinamento `(train.csv)`.
![energy](./img/001-3.1.png)

2. Exibir o tipo de cada variável da Dataframe.
![energy](./img/002-3.2.png)

3. Exibir as 5 primeiras entradas do conjunto de dados.
![energy](./img/003-3.3.png)

4. Exibir a distribuição estatística dos dados:
![energy](./img/004-3.4.png)

5. Exibir histograma das variáveis numéricas:
![energy](./img/005-3.5.png)

5. 1. Qual a porcentagem dos passageiros sobreviventes?
![energy](./img/006-3.5.1.png)

5. 2. Qual a faixa etária dos passageiros do Titanic?
![energy](./img/007-3.5.2.png)

5. 3. As Crianças, sobreviveram mais dos que os Adultos?
![energy](./img/008-3.5.3.png)


### Preparação dos Dados
1. Juntar os conjuntos de dados de treino e teste.
![energy](./img/009-4.1.png)

2. Selecione como recursos.
![energy](./img/010-4.2.png)

3. Exibir os valores ausentes nos conjuntos de dados de treino e teste.
![energy](./img/011-4.3.png)

4. Completar os valores ausentes:
![energy](./img/012-4.4.png)

- Depois de verificado os dados faltantes, iremos imputar essas informações substituindo os valores nulos.
Para o preenchimento da idade (age) e preço do bilhete (fare), optamos por calcular o valor da mediana para ter uma precisão melhor, já no local de embarque (embarked) adicionamos com o valor de maior frequência

5. Preparar como variáveis ​​para o modelo do Machine Learning.
![energy](./img/013-4.5.png)

- Convertemos a feature embarked para dummies, depois utilizamos o comando get_dummies que realiza a analise dos dados contidos e criar o número apropriado de features, como resultado obtivemos: Embarked_C, Embarked_Q e Embarked_S.
A feature sex será utilizada de forma binária, sendo `(1)` mulher e `(0)` homem.

6. Recuperar o conjunto de dados de treino e teste.
![energy](./img/014-4.6.png)

### Modelagem & Avaliação
1. Importar bibliotecas do modelo de Machine Learning de Regressão Logística.


2. Importar biblioteca do modelo de Machine Learning de Árvore de Decisão.
![energy](./img/015-5.1.png)

- Utilizando a regressão logística, obtivemos uma acurácia de 100%

3. Importar biblioteca do modelo de Machine Learning `(Árvore de Decisão)`


4. Avaliação do modelo utilizando Árvore de Decisão
![energy](./img/016-5.2.png)

- Utilizando o modelo de árvore de decisão, obtivemos uma acurácia de 100%

### Conclusão do Relatório Científico

<p align="justify">Podemos concluir que o projeto alcançou o seu objetivo. 
Todo o projeto ocorreu como o esperado, esse <b>Desafio do dataset Titanic</b> nos deu uma excelente oportunidade de testar na pratica, os conhecimentos adquiridos em sala de aula. Suas amostras são confirmados pela própria história do ocorrido, e sua acurácia se mostrou na média entre diversos projetos avaliados na competição da Kaggle. Evidentemente, para que se obtenha um modelo com uma acurácia maior, aconselha-se analisar melhor os dados e realizar mais testes com outras bibliotecas de Machine Learning. Para este projeto, o algoritmo de Árvore de Decisão foi o mais eficaz, retornando um bom resultado. Para projetos posteriores, será essencial o estudo mais aprofundado da exploração e preparação dos dados, assim como de outras bibliotecas de Machine Learning, a fim conseguir melhores resultados do que os obtidos neste projeto.</p>


### Equipe Embraer - Univem - CDD - 01/2020
- João Victor
- Luiz Andre
- Luiz César
- Marcos
- Michael
- Paulo Sergio
