# Criação de um modelo de Machine Learning para prever cancelamentos de assinaturas em uma empresa de Telecomunicações

---

#### Aluno: [Bernardo Nunes Guarisco de Assumpção](https://github.com/guariscobe).
#### Orientadora: [Manoela Kohler](https://github.com/manoelakohler).

---

Trabalho apresentado ao curso [BI MASTER](https://ica.puc-rio.ai/bi-master) como pré-requisito para conclusão de curso e obtenção de crédito na disciplina "Projetos de Sistemas Inteligentes de Apoio à Decisão".

- [Link para o código]([https://github.com/link_do_repositorio](https://github.com/guariscobe/TelecomChurn/blob/main/Cria%C3%A7%C3%A3o_de_um_modelo_de_Machine_Learning_para_prever_cancelamentos_de_assinaturas_em_uma_empresa_de_Telecomunica%C3%A7%C3%B5es.ipynb)).

---

### Resumo

Os modelos de negócio baseados em assinatura, em que clientes pagam um valor recorrente para ter acesso a produto ou serviço, tem se tornado cada vez mais populares no mundo digital. Empresas de telecomunicações já possuem este modelo de negócio consolidado há muito tempo e, por isso, são referência neste assunto. Desta forma, será usada a base de clientes de uma empresa de TeleCom como benchmark para criação de um algoritmo de predição de cancelamentos. Após uma análise exploratória da base, foram aplicados os métodos de Regressão Logística, Decision Tree e Random Forest. Este último apresentou o melhor resultado para o problema, com a maior acurácia e recall, e uma precisão de 91,18%. Como a métrica de churn é essencial para a saúde de um negócio de assinatura, foram desenhados cenários em que seria possível prever e evitar cancelamentos de clientes. No cenário otimista, em que seria possível evitar 50% dos cancelamentso previstos pelo modelo, o impacto no LTV seria de 180%.

### Abstract
Businesses based on subscription, where customers pay a recurring price to access a product or service, have been more and more popular on the digital environment. Telecommunications companies have already stablished this business model for a while, so it is a guide for all the companies in the subscription industry. That is way a dataset of a french broadband provider's clients will be used as a benchmark to train a machine learning model in order to predict cancellations. After a exploratory data analysis, some models were trained: Logistic Regression, Decision Tree and Random Forest. The last one has shown the best result for the problem, with the biggest accurary as well as recall, and a precision of 91,18&. Considering that some cancellations predicted by the model could be avoided, 3 scenarios were built. In optimictic scenario, which 50% of predicted cancellations could be avoided, LTV could increase 180%. 

### 1. Introdução

Modelos de negócio baseados em assinatura são aqueles em que os clientes pagam um valor mensal para ter acesso a um produto, serviço ou pacote de benefícios. No ponto de vista das empresas, assinaturas representam um pote de ouro, pois cria lealdade de seus clientes e as receitas recorrentes geram previsibilidade do negócio. No ponto de vista dos clientes, muitas vezes a assinatura representa praticidade e qualidade de serviço.

Com as facilidades em disponibilizar serviços e realizar pagamentos, o modelo de assinatura revolucionou como as empresas geram receita no mundo digital. Seja no mercado de mídia com o streaming, no setor de tecnologia com a assinatura de software ou no varejo online com pacotes de benefícios para clientes de e-commerce.

Porém, o modelo de assinatura digital é essencialmente uma evolução dos negócios físicos, como jornais, revistas, TV paga e telefone fixo. Por isso, empresas de telecomunicações costumam ser referência para as demais empresas que trabalham assinatura, seja pela maturidade do mercado ou devido a complexidade envolvida na entrega de serviços.

Será utilizada uma [base de dados do Kaggle](https://www.kaggle.com/datasets/mnassrib/telecom-churn-datasets) da empresa francesa Orange TeleCom, com dados de 2019. A base de dados traz diversas informações sobre os clientes e se houve cancelamento ou não. Para uma empresa de assinatura, uma base de clientes com pagamento recorrente é essencial. Por isso, os cancelamentos são um ponto importante a ser evitado por estas empresas, daí a importância de conseguir prever e evitar o churn de clientes.

Desta forma, o objetivo do trabalho é criar um algoritmo de predição de cancelamentos (também chamado de churn) para essa base de dados.

### 2. Modelagem

O dataset do Kaggle é dividido em duas bases, que o criador indicou para serem usadas cada uma para treino e teste. Entretanto, as duas bases serão concatenadas em uma só e as manipulações de dados serão feitas a partir desta base única.

Será feita então a importação dos dados, análise exploratória, escolha de atributos e tratamento de outliers para assim fazer o treinamento do modelo. Serão testados alguns modelos de classificação com aprendizado supervisionado, começando por Regressão Logística. Dependendo do resultado, será testado também outros modelos como Decision Tree e Random Forest.

### 3. Resultados

A partir da aplicação dos diferentes modelos, foi possível entender qual deles funciona melhor para a base em questão.

O modelo de Regressão Logística, que foi o primeiro testado e costuma funcionar bem para problemas do tipo, não apresentou bons resultados. Os resultados não melhoraram inclusive após a aplicação de técnicas de balanceamento da base.

Por outro lado, os modelos de Decision Tree e Random Forest foram melhores, com este último apresentando melhor resultado nas métricas de Acurácia, Precisão e Recall.

Tendo em vista que o objetivo do problema é prever cancelamentos da base de clientes para que fosse possível tomar medidas para evitar tais cancelamentos, o modelo com maior precisão deveria ser escolhido - sendo este, então, o Random Forest.

A precisão de 91,18% indica que existiria um potencial de evitar 91,18% dos cancelamentos. Os demais resultados podem são mostrados abaixo:

| Modelo              | Acurácia | Precisão | Recall | F1 Score |
| ------------------- | -------- | -------- | ------ | -------- | 
| Decision Tree       | 0.898    | 0.661    | 0.712  | 0.685    |
| Regressão Logística | 0.858    | 0.646    | 0.199  | 0.304    |
| Random Forest       | 0.934    | 0.917    |	0.635  |	0.750   |



### 3. Conclusões

Para entender os impactos no negócio que o modelo de previsão poderia gerar, foram considerados os cenários pessimista, realista e otimista. Esses cenários foram baseados na quantidade de cancelamentos que poderiam ser evitados, uma vez que dar maior atenção aos clientes mais suscetíveis a cancelar pode ser uma maneira de evitar o churn.

No cenário otimista, em que seria possível evitar 20% dos cancelamentos, o LTV poderia crescer em 22,5%. No realista, onde seria possível evitar 50% dos cancelamentos, o LTV teria o potencial de crescer 84,6%. No otimista, considerando evitar 70% dos cancelamentos, existiria o potencial de aumentar o LTV em até 179,2%. Para todos os cenários, o ARPU foi considerado constante.

Uma sugestão de trabalhos futuros seria a aplicação do modelo em bases de clientes ativos desta mesma empresa ou utilizar a mesma lógica para outros modelos de assinatura, como streaming de vídeo/áudio, software ou serviços.

---

Matrícula: 211.100.189

Pontifícia Universidade Católica do Rio de Janeiro

Curso de Pós Graduação *Business Intelligence Master*
