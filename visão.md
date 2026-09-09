# Documento de Visão

## 1. Introdução

### 1.1 Objetivo do sistema
O objetivo do Sistema é fazer uma revisão e análise de requisitos e artefatos feitos por pessoas leigas, durante a fase de especificação. 

O Sistema deve através dessa inspeção identificar ambiguidades, armadilhas e incompletudes dos requisitos especificados, entre outros defeitos de estrutura e semântica.
Para além disso, deve também detectar inconsistências entre os artefatos produzidos. Tudo isso afim de gerar relatórios com a correção e feedback das falhas encontradas. 

### 1.2 Escopo do Desenvolvimento do Sistema de Stakeholders

#### Stakeholders 
- Sujeitos leigos que entendem de negócios mas desconhece jargões da área de engenharia de requisitos 
- Clientes
- Desenvolvedores
- Estudantes de TI

#### No escopo
Delimita o que será projetado e desenvolvidos pela equipe:

- **Módulo de Gerenciamento de usuários**: lógica das funcionalidades relacionadas ao cadastro, autenticação, gerenciamento e identificação dos usuários do sistema. 
- **Tela de História de Usuário (HU):** Formulário pré-definido com campos estruturados para requisitos em formato de Histórias de Usuário, com permissão de submissão de diagramas;
- **Tela de Caso de Uso (CDU):**  Formulário pré-definido com campos estruturados para requisitos em formato de Casos de Uso, com permissão de submissão de diagramas;
- **Módulo de Engenharia de Prompts e Comunicação:** lógica interna responsável por capturar texto digitado dos requisitos, formatar prompt e enviar requisição para API da LLM integrada; 
- **Módulo de Gerenciamento de Contexto**: lógica de organizar a fornecer à LLm as instruções, critérios de inspeção, regras e informações relevantes para análise dos artefatos;
- **Tela/Módulo de Exibição de Resultados:** Interface que exibe feedback do agente, onde o usuário poderá visualizar os resultados da análise. 
- **Módulo de Armazenamento e Histórico:** Banco de dados para persistir as HUs, CDUs e os relatórios de análise gerados pela IA;

#### Fora do escopo
Não sofrerá alterações pelo projeto

- **Uso da LLM via API**: será apenas consumido a API e não criado uma LLM do zero; 
- **Provedor de Hospedagem/Nuvem:** a infrestrutura de nuvem onde a aplicação rodará. 

## 2. Visão Geral do sistema

### 2.1 Visão e Objetivos do Sistema
O sistema tem como visão apoiar a elaboração e a inspeção de artefatos de Engenharia de Requisitos por meio de uma interface acessível a usuários com diferentes níveis de conhecimento técnico, incluindo pessoas leigas na área.

Os principais objetivos do sistema são:

- Permitir que usuários submetam artefatos de Engenharia de Requisitos por meio de uma interface simples e acessível;
- Utilizar uma Large Language Model (LLM), acessada por meio de uma API externa, para realizar a inspeção dos artefatos.
- Identificar problemas como ambiguidades, lacunas, incompletudes e imprecisões nos requisitos;
- Verificar inconsistências entre diferentes artefatos relacionados, como diagramas e suas respectivas especificações;
- Apresentar ao usuário os problemas identificados durante a inspeção;
- Gerar um documento com o resultado da análise, contendo os erros encontrados e uma versão corrigida ou aprimorada dos artefatos analisados.

### 2.2 Contexto e Limite do Sistema
O sistema está inserido no contexto da Engenharia de Requisitos e tem como finalidade apoiar a inspeção de artefatos produzidos durante o processo de especificação e documentação de requisitos.

Os usuários poderão criar uma conta, autenticar-se no sistema, submeter artefatos de Engenharia de Requisitos para inspeção e consultar posteriormente o histórico das análises realizadas. Inicialmente, serão considerados artefatos como Casos de Uso e Histórias de Usuário, incluindo representações relacionadas, como diagramas e especificações textuais.

A inspeção será realizada com o apoio de Large Language Models (LLMs), acessadas por meio de uma API externa. O sistema será responsável por preparar e encaminhar os artefatos para análise, receber os resultados produzidos pela LLM e apresentá-los ao usuário de forma estruturada.

Como resultado da inspeção, o sistema deverá identificar problemas como ambiguidades, lacunas, incompletudes, imprecisões e inconsistências entre artefatos relacionados, além de gerar um documento contendo os problemas encontrados e uma versão revisada dos artefatos.

Dentro dos limites do sistema estão o gerenciamento de usuários, autenticação, submissão e armazenamento dos artefatos, gerenciamento do histórico de inspeções, comunicação com a API da LLM, processamento dos resultados e disponibilização dos documentos gerados.

### 2.3 Estrutura Geral do Sistema
O sistema será estruturado em componentes responsáveis pelas principais funcionalidades oferecidas ao usuário. Essa divisão tem como objetivo organizar as responsabilidades do sistema e facilitar a definição dos requisitos associados a cada parte.

Os principais componentes são:

- **Gerenciamento de Usuários:** responsável pelo cadastro, autenticação e gerenciamento das contas dos usuários;
- **Gerenciamento de Artefatos:** responsável pela submissão, armazenamento e consulta dos artefatos de Engenharia de Requisitos enviados ao sistema;
- **Inspeção de Artefatos:** responsável pela preparação dos artefatos e pela comunicação, por meio de API, com o serviço externo de Large Language Model (LLM) utilizado na inspeção;
- **Gerenciamento de contexto**: responsável por estruturar e fornecer à LLM as instruções, regras, critérios de inspeção e informações relavantes para a análise dos artefatos, utilizando e aplicando técnicas de engenharia de prompts e mecanismos de recuperação de informações (RAG);
- **Resultados da Inspeção:** responsável por organizar e apresentar os problemas identificados, além de disponibilizar a versão revisada dos artefatos analisados;
- **Histórico de Inspeções:** responsável pelo armazenamento e consulta das inspeções realizadas anteriormente pelo usuário.

A LLM utilizada na análise não faz parte da estrutura interna do sistema, sendo considerada um serviço externo acessado por API.

## 3. Requisitos do Sistema

## 3.1 Por subsistema/componente

## 3.2 Requisistos funcionais, de qualidade e restrições

## 3.3 Interfaces

## 4. Referências