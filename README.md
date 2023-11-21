# TESTE - FIRST DECISION

O presente repositório contem os códigos dos exercícios de teste para seleção de vaga da empresa Material do teste de seleção para vaga de **Cientista de Dados** da **First Decision**

## TESTE 1
### 1) Exercício 1
Suponha que você possui uma base de dados rotulada com 10 classes não balanceadas, essa base é formada por 40 features de metadados e mais 3 de dados textuais abertos. 
Para todos os itens:  Informe as bibliotecas usadas, se necessário, o motivo de cada decisão, explore as possibilidades.

**_a) Descreva como faria a modelagem dessas classes._**
Inicialmente eu faria uma análise exploratória com algumas aplicações estatísticas. Posteriormente faria o pré-processamento dos dados verificando dados ausentes e normalizando os desequilíbrios.
Após isso, avaliaria as Features e verificaria se seria necessário utilizar NLP com os dados textuais.
Buscaria depois o melhor modelo de classificação. Pessoalmente gosto de usar o Random Forest. 
Por fim, separaria os dados em treino e teste e faria o treinamento do modelo.

**_b) Ao finalizar essa modelagem, como iria apresentar essa modelagem para a área contratante?_**
Antes de elaborar um relatório final, eu montaria um Jupyter Notebook com descrição e possíveis gráficos e uma análise do modelo de Machile Learning escolhido.
Numa segunda versão eu iria gerar um Relatório Técnico sem apresentar a programação utilizada e seguindo um formato que seja amigável ou padrão do cliente.

**_c) Como faria a validação desse modelo?_**
Para validar o modelo eu poderia utilizar o Cross-Validation (Validação Cruzada) e Matriz de Confusão.

**_d) Supondo que esses dados são recebidos diariamente, como iria trabalhar com esse desafio?_**
Primeiramente desenvolveria um pipeline de dados automatizado e um sistema para monitoramento dos dados e desempenho do modelo.

**_e) Como levaria esse projeto para um ambiente produtivo? _**
Hoje trabalho com Container através do Docker e acredito ser uma excelente ferramenta para empacotamento do modelo e pipeline.
Criaria o acesso ao modelo através de API, permitindo o desenvolvimento de Front-End amigável aos usuários finais.

### EXTRA - Existe mais algo que gostaria de relatar sobre esse caso?
Eu procuraria buscar o Feedback constante para melhorias e nova implementações.
 
### 2) Exercício 2:
Suponha que você tenha uma base de dados de vendas de uma loja de varejo que inclui informações sobre produtos, clientes, datas de compra e valores das vendas. A base de dados possui, em média, 10.000 registros diários.
Para todos os itens:  Informe as bibliotecas usadas, se necessário, o motivo de cada decisão, explore as possibilidades.

**_a) Como você iria explorar os dados para obter insights sobre o desempenho das vendas._**
Inevitavelmente a primeira biblioteca a ser usada é o Pandas para exploração dos dados e criação dos Dataframes.
Para análise dos dados imagino inicialmente utilizar as bibliotecas Numpy, Seaborn e Matplotlib.

**_b) Como você responderia as seguintes questões:_**

   **i. Qual é o desempenho de vendas ao longo do tempo?**
     Por serem dados ao longo do tempo, eu utilizaria uma análise de série temporal para responder uma série de perguntas. O Desempenho de venda ao longo do tempo poderia ser analisado através de um gráfico de linha ou um gráfico de Barras com a aceleração mensal de vendas.

   **ii. Quais são os produtos mais vendidos?**
    A pergunta não define o período, ou seja, poderia responder quais os produtos mais vendidos mensalmente ou os produtos mais vendidos considerando todo o período do Dataframe.
    Para os dois casos eu utilizaria o manuseio dos dados com Pandas ordenando por volume de vendas e separando os “Top 5” de cada mês ou os “Top 5” do todo o período.
    Para o caso de apresentar mensalmente eu utilizaria um gráfico de Barras mensal com a identificação de cada “Top 5” mês a mês para facilitar a comparação entre eles.
    Para o caso de apresentar o “Top 5” do período completo, faria um gráfico de barras de um único período com os 5 produtos para facilitar a comparação entre eles.

   **iii. Como as vendas variam por categoria de produtos?**
    Para visualização dessa informação, com o Pandas, faria um “Group” por categoria somando as vendas de cada categoria.
    Novamente essa informação poderia ser apresentada dentro de forma periódica ou resumida de forma totalizada para o período.
    Em ambos os casos eu utilizaria novamente gráfico de barras para a apresentação dos dados.

**iv. Qual é a distribuição dos valores de venda?**
Entendi nessa pergunta que a informação a ser apresentada seria a divisão dos dados conforme os percentis, considerando os valores individuais das vendas.
Nesse caso eu utilizaria um Histograma apresentando os percentis e os Outlliers.

**v. Como os preços dos produtos afetam as vendas?** 
Nessa situação cabe uma análise de correlação. Aplicaria uma função de correlação verificando o volume de vendas em função do preço.

**vi. Qual é o perfil dos principais clientes em termos de compras?**
Para esse tipo e análise, eu selecionaria os dados de vendas por cliente e utilizaria métrica de frequência e valor médio de compra. A partir desses indicadores realizaria o comparativo entre os clientes.

**_c) Como você faria para identificar grupos de clientes nessa base de dados?_**
Para identificação de grupos de clientes eu utilizaria algoritmos de clusterização, nesse caso, eu preferiria utilizar o k-means. Eu agruparia os clientes com comportamentos de compras semelhantes. Consideraria as compras por volume de gasto, frequência de compra e tipo de produto.
Essa clusterização pode ser utilizada para iniciar um trabalho mais simples de recomendação de produtos, considerando as compras de cada grupo.

d)	Qual teste estatístico você usaria para provar uma hipótese referente aos segmentos de clientes? e como iria aplicá-lo?
Eu utilizaria um método de comparação para provar alguma hipótese envolvendo os segmentos de clientes.

Extra - Pensando nos dados acima, seria possível fazer mais algum tipo de análise?

O dataframe permite uma análise mais profunda de série temporal. Não falo em utilizar o algoritmo de Sarima ou Arima, mas sim uma análise mais aprofundada de Aceleração de Vendas, Quantidades acumuladas, Tendência/Sazonalidade e média móvel.
 
3)	Exercício 3

Suponha que você tenha uma base de dados contendo textos jurídicos, como decisões judiciais, petições e documentos legais. A base de dados inclui informações sobre o conteúdo do texto, data, jurisdição e outras informações relevantes. Seu objetivo é criar um sistema de recomendação que sugira textos jurídicos semelhantes a um texto de referência.
Para todos os itens:  Informe as bibliotecas usadas, se necessário, o motivo de cada decisão, explore as possibilidades.
a)	Descreva como você desenvolveria o sistema de recomendação que recebe um texto de referência e sugere os textos mais semelhantes a ele na base de dados.
A primeira coisa que eu faria seria o pré-processamento do texto removendo os Stop words e fazendo a lematização.
Faria o armazenamento dos textos numa base em jason.
Aqui vou propor algo que não domino, mas estou iniciando meus estudos. Eu faria a vetorização das palavras para um Vector Database.

b)	Como você avaliaria esse sistema de recomendação?
Separava a base de dados em treino e teste.
Utilizava alguma métrica de precisão

c)	Suponha que novos textos jurídicos sejam adicionados diariamente. Como você manteria o sistema de recomendação atualizado e garantiria que ele continue a fornece recomendações relevantes?
Faria o mesmo processo de pré-processamento dos novos textos.
Se necessário atualizaria os índices da base de dados Jason
Treinava novamente o Algoritmo
Criava uma rotina automatizada
 

TESTE 2 – 

1)	Como funciona o teste de hipóteses e qual é a sua finalidade na análise estatística?
O teste de hipótese tem como finalidade avaliar se existe evidências suficientes que rejeite uma hipótese nula em favor de uma hipótese alternativa.
Utiliza amostras de uma população e através de cálculos estatísticos, testes e tomadas de decisão com base na comparação de resultados entre uma Hipótese Nula e uma hipótese alternativa.

2)	O que são redes generativas adversárias (GANs) e quais são os possíveis usos dessas redes?
As GANs são algoritmos generativos que possuem duas redes neurais sendo uma geradora e outra discriminadora que são treinadas simultaneamente.
É usado para geração de imagens e textos.

3)	O que são modelos de linguagem? Qual a diferença entre LLMs e modelos de linguagem tradicionais?
Os modelos de linguagem trabalham com a previsão de palavras numa frase utilizando regras ou estatísticas simples.
As LLMs já utilizam arquiteturas de Redes Neurais para conhecer padrões e propor textos de forma mais eficiente 

4)	Suponha que você tenha um conjunto de dados com três ou mais grupos para comparar e deseja determinar se há diferenças significativas entre eles. Descreva como você escolheria entre o teste ou outras técnicas estatísticas
Eu faria uma análise através da variância para determinar se utilizaria um teste ou técnica estatística.

5)	Qual é a importância do pré-processamento de texto em tarefas de NLP? Quais são as etapas comuns no pré-processamento de texto?
O pré-processamento do texto para trabalhar com Linguagem Natural é fundamental para deixar o texto num formato e padrão que esteja adequado para a leitura do Algoritmo. Retira informações desnecessárias e normaliza o texto.
As etapas desse pré-processamento consistem em retirada dos stop words e caracteres especiais, tokenização e lematização.

6)	Descreva o processo de vetorização de texto e como modelos de linguagem como o Word2Vec ou o TF-IDF podem ser usados para representar palavras e documentos.
O processo de vetorização é uma coisa relativamente nova para mim. Comecei a estudar recentemente, mas basicamente consiste em transformar uma palavra em uma sequência numérica, ou seja, transformar uma palavra num vetor numérico (word embaddings).
Sinônimos ou palavra dentro do mesmo contexto ficam numericamente mais próximas.
O Word2Vec faz exatamente essa proximidade entre palavras semelhantes. Já o TF-IDF já utiliza pesos com base na frequência da palavra no texto.

7)	O que é a análise de sentimento em NLP e quais são os principais métodos para realizar essa tarefa? Como você avaliaria a eficácia de um modelo de análise de sentimento?
A Análise de sentimento basicamente avalia um texto e, com base num algoritmo treinado, classifica esse texto de forma positiva, negativa ou neutra.
Considerando os modelos mais atuais, poderia utilizar o TF-IDF ou word embeddings. Um modelo mais clássico utilizaria o Bag of Words ou NLTK.

8)	Qual é a diferença entre a classificação de texto e o agrupamento (clustering) de texto em NLP? Em que situações cada um é mais apropriado?
A classificação de textos em NLP consiste em atribuir rótulos ou categorias a um texto como o caso de identificar os textos de um sistema de Ouvidoria em categorias predefinidas como. O agrupamento clusteriza os documentos por semelhança de conteúdo. Um exemplo poderia ser no mesmo sistema de ouvidoria classificar os textos por categorias que não foram predefinidas para identificar padrões naturais dentro dos textos.

9)	Explique o conceito de reconhecimento de entidades nomeadas (NER) em NLP e suas aplicações práticas.
O NER identifica textos específicos como Nomes de pessoas, Empresas e outros. Hoje utilizo num projeto que separa diversos Olerites existentes em um único PDF identificando cada empregado e atribuindo o olerite individual a esse funcionário.

10)	Como você lidaria com problemas de desequilíbrio de classe em tarefas de classificação de texto em NLP? Quais estratégias seriam eficazes?
Passei por essa situação pouquíssimas vezes e utilizei a técnica de reamostragem (Sobreamostragem e Bubamostragem) onde pode Aumentar a quantidade de instâncias da classe menos ou Diminuir da classe maior.


