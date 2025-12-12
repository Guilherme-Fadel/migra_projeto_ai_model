# Bot de Suporte com Inteligência Artificial (RAG)

## Visão Geral

Projeto de bot inteligente desenvolvido para facilitar o trabalho do time de suporte técnico, centralizando o conhecimento da empresa em uma base única de documentação.

A solução utiliza inteligência artificial para responder dúvidas de forma automática, baseada exclusivamente nas documentações internas dos sistemas, garantindo padronização das respostas, redução de retrabalho e ganho de eficiência operacional.

Atualmente, o projeto encontra-se em fase de homologação.

---

## Evolução do Projeto

O projeto teve início com uma aplicação desenvolvida em Python integrada ao TypeBot, utilizando modelos de linguagem open source para responder dúvidas frequentes.

Com a evolução da solução e a necessidade de maior escalabilidade e facilidade de manutenção, o bot foi migrado para a plataforma n8n, onde passou a operar de forma totalmente automatizada por meio de workflows.

Repositório da versão inicial (Python + TypeBot):  
https://github.com/Guilherme-Fadel/projetoTypeBot

---

## Arquitetura Atual

A solução atual é composta por dois fluxos principais no n8n.

### Fluxo de Embeddings

Responsável pelo processamento e atualização da base de conhecimento do bot.

- Leitura de documentações armazenadas no Google Drive
- Processamento de arquivos em diferentes formatos (PDF, DOCX, TXT)
- Fragmentação do conteúdo em blocos
- Geração de embeddings
- Armazenamento vetorial utilizando PostgreSQL com pgvector
- Atualização incremental da base de conhecimento
- Registro de logs e status do processamento

Esse fluxo garante que o bot esteja sempre sincronizado com a documentação mais recente.

---

### Fluxo de Chat

Responsável pela interação com os usuários finais.

- Recebimento de mensagens via canais como Discord e WhatsApp
- Validação e tratamento das mensagens recebidas
- Recuperação de contexto utilizando arquitetura RAG
- Busca vetorial no PostgreSQL com pgvector
- Geração de respostas baseadas exclusivamente na base documental
- Suporte a mensagens de texto, imagens e XML
- Limpeza automática do histórico de conversas
- Registro de logs das interações

---

## Tecnologias Utilizadas

- Python
- n8n
- PostgreSQL
- pgvector
- Docker
- AWS (S3)
- APIs REST
- Git e GitHub

---

## Impacto da Solução

- Redução do tempo gasto pelos analistas de suporte
- Padronização das respostas técnicas
- Centralização do conhecimento técnico
- Facilidade de manutenção e escalabilidade da solução
- Base preparada para expansão para novos canais e funcionalidades

---

## Status do Projeto

Projeto em fase de homologação, com testes funcionais e validações sendo realizados junto ao time de suporte.
