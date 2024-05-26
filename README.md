- Apresentação

A proposta é abordar os registros das informações coletadas dos Comunicados de Acidente de Trabalho (CAT).

A CAT trata-se de um comunicado, de caráter obrigatório pela Lei Nº5452 de 1943, para registro de qual empresa pertence ao fato, de que pessoa, onde, quando, como e quais os danos sofridos.

As informações coletadas são a nível Brasil, de Janeiro de 2019 a Dezembro de 2020. Abordar a necessidade de um melhor refinamento das informações e assim ter um melhor aproveitamento e análise das informações para uma rápida tomada de decisão estratégica.

A aplicação desta análise deverá ser utilizada para melhorar a percepção do cenário atual sobre o acidente de trabalho no Brasil. Tratando com os dados de registro do Instituto Nacional do Seguro Social (INSS).

Fonte: [https://dados.gov.br](https://dados.gov.br/dados/conjuntos-dados/inss-comunicacao-de-acidente-de-trabalho-cat1)

- Objetivo

Objetivoapresentar uma análise dos recentes comunicados de acidentes de trabalho para a tomada de decisões estratégicas a fim de minimizar futuras repetições.

- Público alvo

Este trabalho destina-se a despertar percepções para todos que se interessam por ações de prevenção sobre Saúde e Trabalho (SST), mas principalmente para estudantes e profissionais de Serviço Especializado de Segurança e Medicina do Trabalho (SESMT) que possuem habitualidade para abordagem deste tema.

- Modelo Dimensional

A imagem abaixo representa o modelo dimensional, onde apresenta os resultados disponibilizados pelo INSS, contendo informações quantitativas do evento, tais como: tempo (ano, mês e dia), sexo de quem sofreu o acidente, local do estado que ocorreu, se é típico da atividade ou de trajeto, se gerou óbito, qual o ramo de atividade da empresa, a natureza das lesões causadas e as possíveis causas que originaram o acidente.

![Imagem 01 - Modelo dimensional](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/092394d6-320e-4ba2-b6b5-fa7042631156)

- Fatos e Dimensões

Os dados disponibilizados e coletados do INSS consistem em tabelas contendo fatos e dimensões.

Conforme imagem abaixo apresentada, a tabela fato consiste na unificação das informações apresentadas anteriormente. Sendo as informações apresentadas nas colunas contendo: CBO, CID_10, CNAE, EMITENTE_CAT, EXISTENCIA_DE_OBITO, NATUREZA_ DA_LESAO, PARTE_ATINGIDA, GENERO, TIPO_DE_ACIDENTE,MUNICÍPIO, DATA_DO_ACIDENTE, DATA_EMISSAO_CAT, CID10_LEGENDA, CID10_NUMERO, DESCRICAO_CONSOLIDADA, TIPO_CNAE, CATEGORIA_CID10.

![Imagem 02 - Fatos e Dimensões](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/098e0a14-230a-4477-894c-e4dc3ac1722a)

- Fontes de Dados

Nessa etapa, da lista de conjuntos de dados encontrados, utilizou-se a base de informações do Portal de Dados Aberto - Governo Brasileiro. Foi realizada a extração de dados, no formato Excel, do histórico de acidentes ocorridos de Janeiro de 2019 a Dezembro de 2020. Para compor a base inicial, precisou realizar a extração de três bases de dados. Todas extraídas no formato Excel e no portal do Governo Brasileiro. Tais bases coletadas: I. Informações de cadastro do CID-10 do período relacionado às informações. II. Informações de cadastro do CNAE 2.0 Classes da Estrutura superior. III. Informações da Tabela 14 do eSocial, utilizando a Base completa de Agentes causadores do acidente.

- Processos de Integração e Carga (ETL)
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

- Dashboard Estratégico (desenvolvido em Power BI)

![Imagem 08 - Dashboard Estratégico](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/33043e84-9160-4e74-9206-a067a36bbc5d)

- Dashboard Tático (desenvolvido em Power BI)

![Imagem 09 - Dashboard Tático](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/cdc6014c-eb61-436b-b142-63f23af7202b)

- Dashboard Operacional (desenvolvido em Power BI)

![Imagem 10 - Dashboard Operacional](https://github.com/Pedrovieira1274/TCC-PUC-Minas/assets/170687062/f5bf7546-328c-4e4c-b84c-a263791aef4f)

