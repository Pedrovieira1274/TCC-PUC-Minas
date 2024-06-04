# - Apresentação

A proposta é abordar os registros das informações coletadas dos Comunicados de Acidente de Trabalho (CAT).

A CAT trata-se de um comunicado, de caráter obrigatório pela Lei Nº5452 de 1943, para registro de qual empresa pertence ao fato, de que pessoa, onde, quando, como e quais os danos sofridos.

As informações coletadas são a nível Brasil, de Janeiro de 2019 a Dezembro de 2020. Abordar a necessidade de um melhor refinamento das informações e assim ter um melhor aproveitamento e análise das informações para uma rápida tomada de decisão estratégica.

A aplicação desta análise deverá ser utilizada para melhorar a percepção do cenário atual sobre o acidente de trabalho no Brasil. Tratando com os dados de registro do Instituto Nacional do Seguro Social (INSS).

# - Objetivo

Objetivoapresentar uma análise dos recentes comunicados de acidentes de trabalho para a tomada de decisões estratégicas a fim de minimizar futuras repetições.

# - Público alvo

Este trabalho destina-se a despertar percepções para todos que se interessam por ações de prevenção sobre Saúde e Trabalho (SST), mas principalmente para estudantes e profissionais de Serviço Especializado de Segurança e Medicina do Trabalho (SESMT) que possuem habitualidade para abordagem deste tema.

# - Modelo Dimensional

A imagem abaixo representa o modelo dimensional, onde apresenta os resultados disponibilizados pelo INSS, contendo informações quantitativas do evento, tais como: tempo (ano, mês e dia), sexo de quem sofreu o acidente, local do estado que ocorreu, se é típico da atividade ou de trajeto, se gerou óbito, qual o ramo de atividade da empresa, a natureza das lesões causadas e as possíveis causas que originaram o acidente.

![Imagem 01 - Modelo dimensional](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/092394d6-320e-4ba2-b6b5-fa7042631156)

# - Fatos e Dimensões

Os dados disponibilizados e coletados do INSS consistem em tabelas contendo fatos e dimensões.

Conforme imagem abaixo apresentada, a tabela fato consiste na unificação das informações apresentadas anteriormente. Sendo as informações apresentadas nas colunas contendo: CBO, CID_10, CNAE, EMITENTE_CAT, EXISTENCIA_DE_OBITO, NATUREZA_ DA_LESAO, PARTE_ATINGIDA, GENERO, TIPO_DE_ACIDENTE,MUNICÍPIO, DATA_DO_ACIDENTE, DATA_EMISSAO_CAT, CID10_LEGENDA, CID10_NUMERO, DESCRICAO_CONSOLIDADA, TIPO_CNAE, CATEGORIA_CID10.

![Imagem 02 - Fatos e Dimensões](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/098e0a14-230a-4477-894c-e4dc3ac1722a)

# - Fontes de Dados

Nessa etapa, da lista de conjuntos de dados encontrados, utilizou-se a base de informações do Portal de Dados Aberto - Governo Brasileiro. Foi realizada a extração de dados, no formato Excel, do histórico de acidentes ocorridos de Janeiro de 2019 a Dezembro de 2020. 

Para compor a base inicial, precisou realizar a extração de três bases de dados. Todas extraídas no formato Excel e no portal do Governo Brasileiro. 
Tais bases coletadas:

I. Informações de cadastro do CID-10 do período relacionado às informações. 

II. Informações de cadastro do CNAE 2.0 Classes da Estrutura superior. 

III. Informações da Tabela 14 do eSocial, utilizando a Base completa de Agentes causadores do acidente.

# - Processos de Integração e Carga (ETL)

Fluxo completo do processo ETL. Para melhor visualização, as informações estão apresentadas as etapas de cada fluxo.

![Imagem 03 - Fluxo completo do processo ETL](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/766da54e-0143-4eb0-b796-01674f175b96)

º Fluxo da consolidação do histórico de CAT de Janeiro de 2019 a Dezembro de 2020. Em seguida foi realizado a limpeza dos dados para excluir as linhas com dados nulos e com espaços desnecessários à direita do texto dos registros. Na mesma imagem contempla o segundo fluxo, sendo dentro do primeiro fluxo, foi realizado a inclusão da Tabela 14 do eSocial para se obter o texto completo do agente causador.

![Imagem 04 - Fluxo ELT de importe de dados de CAT e Agente Causador (Tabela 14 eSocial)](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/862f5920-f3ae-4fab-8295-301fe1973a4d)

º Fluxo para inclusão de uma base contendo a descrição do tipo de atividade econômica atrelado ao número do CNAE. Para assim, poder adicionar a base final a nomenclatura do CNAE

![Imagem 05 - Fluxo ETL de importe de dados de CNAE vs Atividade](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/e691b194-999c-441c-bf6a-b0f25bca9389)

º Fluxo da junção do primeiro, segundo e do terceiro fluxo

![Imagem 06 - Fluxo ETL de junção do primeiro, segundo e do terceiro fluxo](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/5a433184-d7a4-4009-9a5a-05915287cf0c)

º Fluxo para unificar as informações do quarto fluxo e acrescentou-se o tipo do Número do CID10 atrelado a nomenclatura da categoria do CID informado no histórico de CAT’s

![Imagem 07 - Fluxo ETL de unificação dos dados e geração final da base tratada](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/42fbd382-cec5-4a30-9939-d50d01aa8b15)

# - Dashboard Estratégico (desenvolvido em Power BI)

![Imagem 08 - Dashboard Estratégico](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/33043e84-9160-4e74-9206-a067a36bbc5d)

# - Dashboard Tático (desenvolvido em Power BI)

![Imagem 09 - Dashboard Tático](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/cdc6014c-eb61-436b-b142-63f23af7202b)

# - Dashboard Operacional (desenvolvido em Power BI)

![Imagem 10 - Dashboard Operacional](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/f5bf7546-328c-4e4c-b84c-a263791aef4f)

# - Registros de Homologação

° Fluxo completo do processo de Registro de Homologação:

![Imagem 12 - Registro de Homologação (completo)](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/671074f0-6e98-4094-87fe-2532a6ec0c91)

° Fluxo do processo de Registro de Homologação do total de acidentes:

![Imagem 13 - Registro de Homologação (Total de CATs)](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/ca55eea3-3014-4d96-875f-53ad97a29bf6)

° Fluxo do processo de Registro de Homologação (CATs por ano):

![Imagem 14 - Registro de Homologação (CATs por ano de 2019 e 2020)](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/fcd94f36-39eb-47ce-8e64-a3a17f0f9bfc)

° Fluxo do processo de Registro de Homologação (CATs por tipo de sexo):

![Imagem 15 - Registro de Homologação (CATs por tipo de sexo)](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/5b248a75-a268-4af7-9274-044e6ddd9ebf)

# - Análises avançadas
Para a aplicação de técnicas de aprendizado de máquina, foi utilizado a ferramenta um algoritmo de regressão linear do pacote sklearn. Para treinamento do modelo, utilizamos 40% do dataset e 60% para predição. Encontramos uma correlação baixa, utilizando uma métrica do R², que não explicou de forma linear a relação entre as variáveis D, CID10, CBO e CNAE com o somatório de óbitos.

Sendo assim, obtivemos um valor de R² muito baixo, de 0,0002. Ou seja, o modelo possui dificuldade para apresentar os dados de forma linear.

![Imagem 11 - Análises avançadas](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/9f6471fe-db0b-43d0-b190-2f1c6bb7f920)

º Passo a passo realizado
1. Utilização da ferramenta Panda em Python para acessar a base tratada do processo de ETL do Alteryx.
2. Sklearn para aplicar o modelo de regressao linear.
3. Pyplot para fazer o grafico.
4. Treinamento do modelo, sendo utilziado 40% do dataset e 60% para predição.
5. Resultado de uma correlação baixa, utilizando uma métrica do R².

Código fonte utilizado:

# Imports
 
import pandas as pd

import matplotlib.pyplot as plt

from sklearn.model_selection import train_test_split
from sklearn.linear_model import LinearRegression
from sklearn.metrics import mean_squared_error

# Dados da cat de Janeiro 2019 a Dezembro 2020)

data2 = pd.read_excel('cat3.xlsx')
data2

# Seleção de características e divisão dos dados

X = data.drop('Sum_fl_obito', axis=1)  # Usando todas as colunas exceto 'Sum_fl_obito' como variáveis independentes
y = data['Sum_fl_obito']  # 'Sum_fl_obito' sera variável dependente

# Divisao dos dados em treino e teste
# random_state = 42 garante sempre a mesma amostragem

X_train, X_test, y_train, y_test = train_test_split(X, y, test_size=0.4, random_state=42)

# Criacao da instancia de classe

model = LinearRegression()

# Fit modelo

model.fit(X_train, y_train)

# Criando um DataFrame para visualizar melhor os coeficientes
coeff_df = pd.DataFrame({
    'Feature': X.columns,
    'Coefficient': model.coef_
})
print(coeff_df)

# Mostrando também a interceptação
print("\nInterceptação:", model.intercept_)

y_pred = model.predict(X_test)

print("R quadrado = {}".format(model.score(X_test, y_test)))


# - Links e referências (utilizar navegador Microsoft Edge):

Base de dados do INSS (acessado em 10/03/2024): https://dados.gov.br/dados/conjuntos-dados/inss-comunicacao-de-acidente-de-trabalho-cat1

Referêmcoa das informações de CID-10 do período avaliado (acessado em 24/03/2024): https://www.gov.br/previdencia/pt-br/assuntos/previdencia-social/saude-e-seguranca-do-trabalhador/acidente_trabalho_incapacidade/tabelas-cid-10

Referência das informações de CNAE 2.0 Classes da Estrutura superior (acessado em 26/03/2024): https://concla.ibge.gov.br/classificacoes/download-concla.html

Referência das informações da Tabela 14 do eSocial para extrair e cruzar informações do tipo "Agentes causadores do acidente" (acessado em 07/04/2024): https://www.gov.br/esocial/pt-br/documentacao-tecnica/manuais/leiautes-esocial-v-1-1-beta/tabelas.html#14
