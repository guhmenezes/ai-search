# Organização e Pesquisa de Documentos com Azure AI Search

Este repositório documenta minha experiência prática com a ingestão de dados e indexação utilizando o Azure AI Search, como parte do desafio da DIO. O objetivo principal foi aplicar as técnicas aprendidas nas aulas para organizar e pesquisar documentos com o auxílio de inteligência artificial, focando nos três passos principais: ingestão de conteúdo, criação de índices inteligentes e exploração dos dados.

## Sumário

* [Introdução](#introdução)
* [Objetivos de Aprendizagem](#objetivos-de-aprendizagem)
* [Ingestão de Conteúdo](#ingestão-de-conteúdo)
* [Criação de Índices Inteligentes](#criação-de-índices-inteligentes)
* [Exploração dos Dados](#exploração-dos-dados)
* [Desafios e Aprendizados](#desafios-e-aprendizados)
* [Conclusão](#conclusão)
* [Recursos Adicionais](#recursos-adicionais)


## Introdução

Este projeto explora a capacidade do Azure AI Search para organizar e pesquisar grandes volumes de informação. Através da prática com a ferramenta, busquei solidificar meu conhecimento sobre os conceitos de ingestão, indexação e exploração de dados com o auxílio de IA.


## Objetivos de Aprendizagem

Os principais objetivos deste desafio foram:

* Aplicar os conceitos de ingestão, indexação e pesquisa de documentos em um ambiente prático.
* Documentar o processo técnico de forma clara e estruturada.
* Utilizar o GitHub para compartilhar a documentação do projeto.


## Ingestão de Conteúdo

Nesta seção, detalho minha experiência com a ingestão de conteúdo para o Azure AI Search.

* **Fontes de Dados:** Utilizei um conjunto de aproximadamente 500 documentos no formato PDF, simulando artigos científicos sobre temas variados de biologia.  Os documentos foram armazenados em um contêiner do Azure Blob Storage.  Adicionalmente, ingeri dados de um feed RSS com notícias recentes sobre biotecnologia.
* **Conectores de Dados:**  Utilizei o conector de Blob Storage do Azure para ingerir os PDFs e o conector de dados embutido para URLs para processar o feed RSS.  A configuração dos conectores foi relativamente simples, bastando fornecer as credenciais de acesso e o caminho para os dados.
* **Processamento dos Dados:** Durante a ingestão dos PDFs, utilizei o recurso de extração de texto embutido no Azure AI Search para extrair o conteúdo textual dos arquivos.  Para o feed RSS, o conector extraiu automaticamente o título, a descrição e o link de cada notícia.


## Criação de Índices Inteligentes

Aqui, descrevo minha experiência com a criação de índices inteligentes no Azure AI Search.

* **Esquema do Índice:** Criei um índice com os seguintes campos: "título" (string, pesquisável), "autores" (string, pesquisável e filtrável), "resumo" (string, pesquisável), "data_publicacao" (datetimeoffset, filtrável e classificável), "conteudo" (string, pesquisável), "url" (string, filtrável) e "fonte" (string, filtrável).
* **Analisadores:**  Para os campos de texto ("título", "autores", "resumo" e "conteudo"), utilizei o analisador de idioma padrão "pt-BR" para o português.
* **Habilidades Cognitivas:** Explorei a habilidade de extração de frases-chave para enriquecer o índice com as principais palavras-chave de cada documento. Isso melhorou a precisão das buscas e permitiu a criação de facetas para filtrar os resultados por palavras-chave.


## Exploração dos Dados

Nesta seção, descrevo como explorei os dados organizados no Azure AI Search.

* **Consultas de Pesquisa:** Realizei diversas consultas de pesquisa, utilizando palavras-chave como "biodiversidade", "genética", "evolução", combinadas com filtros por data de publicação e fonte.  Por exemplo, busquei por artigos sobre "biodiversidade" publicados nos últimos 5 anos e originados do feed RSS.
* **Resultados da Pesquisa:** Os resultados das pesquisas foram relevantes e a performance das consultas foi satisfatória. A extração de frases-chave melhorou significativamente a precisão das buscas, permitindo encontrar documentos relevantes mesmo sem a correspondência exata das palavras-chave no título ou resumo.
* **Interface de Pesquisa:**  Utilizei o portal do Azure para realizar as consultas e explorar os resultados. A interface intuitiva facilitou a navegação e a análise dos dados indexados.


## Desafios e Aprendizados

Durante o desafio, enfrentei o desafio de configurar corretamente o pipeline de indexação para lidar com alguns PDFs corrompidos.  Resolvi o problema adicionando uma etapa de validação no pipeline para descartar os arquivos inválidos.

Os principais aprendizados foram: a compreensão do processo de ingestão e indexação de dados no Azure AI Search, a utilização de habilidades cognitivas para enriquecer o índice e a experiência prática com a construção de consultas de pesquisa eficientes.


## Conclusão

Concluindo, este desafio me proporcionou uma valiosa experiência prática com o Azure AI Search. A exploração da ferramenta me permitiu aprofundar meu conhecimento em organização e pesquisa de documentos com o auxílio de IA.


## Recursos Adicionais

* [Explore an Azure AI Search index (UI) - Laboratório no Microsoft Learning](https://microsoftlearning.github.io/mslearn-ai-fundamentals/Instructions/Labs/11-ai-search.html)
* [GitHub Quick Start - Repositório com Link para Aulas de Git e GitHub](https://github.com/digitalinnovationone/github-quickstart)
