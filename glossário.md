# Glossário

| Termo | Definição|
| ---------------------------------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ |
| **Artefato** | Produto ou representação produzido durante o processo de Engenharia de Requisitos, utilizado para registrar, especificar ou representar requisitos. Neste projeto, são considerados inicialmente Histórias de Usuário, Casos de Uso, diagramas e suas especificações textuais. |                                                                            
| **Engenharia de Requisitos (ER)** | Área da Engenharia de Software responsável por atividades relacionadas à elicitação, análise, especificação, validação e gerenciamento de requisitos.|
| **História de Usuário (HU)** | Forma de especificação de requisitos que descreve uma necessidade ou funcionalidade sob a perspectiva de um usuário, normalmente estruturada a partir de papel, ação e benefício. |
| **Incompletude** | Defeito caracterizado pela ausência de informações necessárias para compreender ou implementar adequadamente um requisito. |
| **Inconsistência**| Defeito caracterizado pela existência de informações conflitantes ou incompatíveis entre requisitos ou artefatos relacionados.|
| **Ambiguidade**| Defeito em que um requisito pode ser interpretado de mais de uma maneira devido à falta de clareza ou precisão em sua especificação. |                                                                                                                            
| **Large Language Model (LLM)** | Modelo de inteligência artificial capaz de processar e gerar texto a partir de informações fornecidas como entrada. Neste projeto, a LLM será utilizada por meio de uma API externa para apoiar a inspeção dos artefatos. |
| **Prompt**| Conjunto de instruções e informações fornecidas a uma LLM para orientar o processamento e a geração de sua resposta. |
| **RAG (Retrieval-Augmented Generation)** | Técnica que combina a recuperação de informações de uma base de conhecimento com a geração de respostas por uma LLM, fornecendo informações recuperadas como parte do contexto utilizado na geração.|
| **Inspeção de Requisitos**| Processo sistemático de análise de requisitos ou artefatos com o objetivo de identificar defeitos, como ambiguidades, incompletudes, imprecisões e inconsistências.                                                                                                            |
| **Base de Conhecimento** | Conjunto de informações utilizadas como fonte de referência para orientar a inspeção realizada pelo sistema, podendo conter critérios, regras, definições, exemplos e outras informações relacionadas à Engenharia de Requisitos.|
| **Gerenciamento de Contexto** | Processo de organizar e fornecer à LLM as instruções, critérios de inspeção, regras, artefatos e demais informações relevantes para uma determinada análise. |
| **Contexto** | Conjunto de informações e instruções disponibilizadas à LLM durante uma determinada execução, utilizado para orientar a análise e a geração da resposta.|
| **Injeção de Prompt (Prompt Injection)** | Técnica de ataque em que conteúdo fornecido como entrada tenta introduzir ou modificar instruções destinadas à LLM, buscando alterar seu comportamento esperado |
| **JWT (JSON Web Token)** | Formato de token utilizado para transmitir informações de autenticação entre partes de uma aplicação, podendo ser utilizado para representar a sessão ou autorização de um usuário. |
| **API** | Interface que permite a comunicação programática entre diferentes sistemas ou componentes de software.|
| **API Externa** | API disponibilizada por um serviço externo à aplicação desenvolvida pelo projeto. Neste projeto, é utilizada para acessar a LLM.|
