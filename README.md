#  Laboratório: Organização e Pesquisa de Documentos com Inteligência Artificial

Este repositório documenta as etapas realizadas no laboratório prático de **ingestão, indexação e pesquisa de documentos usando serviços de IA do Azure**, simulando a construção de uma solução de busca inteligente por meio do **Azure Cognitive Search** e do **Azure Document Intelligence (Form Recognizer)**.

---

##  Objetivo

O objetivo deste laboratório foi aplicar técnicas de inteligência artificial para organizar grandes volumes de documentos, extraindo informações relevantes e estruturando dados para facilitar a pesquisa e o entendimento dos conteúdos.

---

##  Ferramentas Utilizadas (via portal do Azure)

- **Azure Cognitive Search** (serviço de busca inteligente)
- **Azure Document Intelligence** (para extração de texto e estrutura)
- **Azure Blob Storage** (repositório de documentos)
- **Habilidades Cognitivas** (OCR, extração de entidades, análise de texto)

> Todo o processo foi realizado via **portal do Azure**, simulando o uso real dos serviços com recursos visuais e assistentes de configuração.

---

##  Etapas Realizadas

### 1.  Criação do Armazenamento de Documentos

- Acesse o portal do Azure.
- Crie um recurso do tipo **Storage Account (conta de armazenamento)**.
- No container do Blob Storage, crie uma pasta e **faça upload dos documentos** (PDFs, DOCX, imagens etc).

### 2.  Criação do Serviço de IA Document Intelligence

- No portal, procure por **"Document Intelligence"** (ou "Form Recognizer").
- Crie um novo recurso selecionando a região.
- Acesse o recurso e use a **opção "Explorar layout" ou "Extrair chave/valor"** para processar os documentos previamente carregados no Blob Storage.
- Teste a extração diretamente no portal para visualizar os campos identificados automaticamente (tabelas, campos, textos livres etc.).

### 3.  Criação do Serviço de Azure Cognitive Search

- Pesquise por **"Azure Cognitive Search"** no portal e crie um novo serviço.
- Defina nome, região e plano gratuito (Free ou Basic).

### 4.  Conexão com o Blob Storage e Ingestão dos Dados

- No recurso do **Cognitive Search**, acesse a aba de **Importação de Dados**.
- Escolha **"Azure Blob Storage"** como fonte de dados.
- Selecione o container com os documentos enviados na Etapa 1.

### 5.  Habilidades Cognitivas (Skillset)

- O assistente perguntará se deseja aplicar um **skillset cognitivo**: marque **sim**.
- Habilidades aplicadas automaticamente:
  - **OCR**: leitura de texto de PDFs e imagens
  - **Extração de layout**: tabelas e posições do conteúdo
  - **Extração de entidades**: nomes, locais, datas, números
  - **Detecção de linguagem** e **análise de sentimento** (opcional)

### 6.  Criação do Índice de Pesquisa

- Após a aplicação dos skills, o Azure irá sugerir campos para o índice, como:
  - `content` (texto principal)
  - `people` (pessoas identificadas)
  - `locations` (locais)
  - `organizationNames`, `keyPhrases`, entre outros
- Configure os campos como **pesquisáveis**, **filtráveis**, **retornáveis** conforme desejado.
- Finalize a criação do índice.

### 7.  Teste da Pesquisa

- Ainda no portal do Azure Cognitive Search, acesse a aba **"Search explorer"**.
- Realize testes com palavras-chave (ex: `"contrato"`, `"Recife"`, `"Janeiro 2023"`).
- Os resultados retornam os documentos correspondentes com trechos de texto e metadados extraídos.

---

##  Insights Obtidos

- A organização dos dados por IA torna possível **buscar informações específicas** em milhares de documentos com rapidez.
- A aplicação de **OCR e extração semântica** amplia a capacidade de análise mesmo em documentos digitalizados ou escaneados.
- O processo via portal do Azure é guiado e **acessível para quem não tem conhecimento avançado em código**.
- Apesar da automatização, é importante **validar os dados extraídos**, especialmente em documentos com layout complexo.

---  
