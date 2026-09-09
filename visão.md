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
Delimita o que será desenvolvidos/modificado pela equipe

#### Fora do escopo
Não sofrerá alterações pelo projeto


## 2. Visão Geral do sistema

### 2.1 Visão e Objetivos do Sistema
O sistema tem como visão apoiar a elaboração e a inspeção de artefatos de Engenharia de Requisitos por meio de uma interface acessível a usuários com diferentes níveis de conhecimento técnico, incluindo pessoas leigas na área.

Os principais objetivos do sistema são:

- Permitir que usuários submetam artefatos de Engenharia de Requisitos por meio de uma interface simples e acessível;
- Utilizar agentes baseados em Large Language Models (LLMs) para realizar a inspeção dos artefatos submetidos;
- Identificar problemas como ambiguidades, lacunas, incompletudes e imprecisões nos requisitos;
- Verificar inconsistências entre diferentes artefatos relacionados, como diagramas e suas respectivas especificações;
- Apresentar ao usuário os problemas identificados durante a inspeção;
- Gerar um documento com o resultado da análise, contendo os erros encontrados e uma versão corrigida ou aprimorada dos artefatos analisados.

### 2.2 Contexto e Limite do Sistema
### 2.2 Contexto e Limite do Sistema

O sistema está inserido no contexto da Engenharia de Requisitos e tem como finalidade apoiar a inspeção de artefatos produzidos durante o processo de especificação e documentação de requisitos.

Os usuários poderão criar uma conta, autenticar-se no sistema, submeter artefatos de Engenharia de Requisitos para inspeção e consultar posteriormente o histórico das análises realizadas. Inicialmente, serão considerados artefatos como Casos de Uso e Histórias de Usuário, incluindo representações relacionadas, como diagramas e especificações textuais.

A inspeção será realizada com o apoio de Large Language Models (LLMs), acessadas por meio de uma API externa. O sistema será responsável por preparar e encaminhar os artefatos para análise, receber os resultados produzidos pela LLM e apresentá-los ao usuário de forma estruturada.

Como resultado da inspeção, o sistema deverá identificar problemas como ambiguidades, lacunas, incompletudes, imprecisões e inconsistências entre artefatos relacionados, além de gerar um documento contendo os problemas encontrados e uma versão revisada dos artefatos.

Dentro dos limites do sistema estão o gerenciamento de usuários, autenticação, submissão e armazenamento dos artefatos, gerenciamento do histórico de inspeções, comunicação com a API da LLM, processamento dos resultados e disponibilização dos documentos gerados.

A LLM utilizada para realizar a análise não faz parte do sistema, sendo considerada um serviço externo acessado por API. Também está fora do escopo do sistema substituir completamente a avaliação humana ou executar todas as atividades do processo de Engenharia de Requisitos.

### 2.3 Estrutura Geral do Sistema

## 3. Requisitos do Sistema

## 3.1 Por subsistema/componente

## 3.2 Requisistos funcionais, de qualidade e restrições

## 3.3 Interfaces

## 4. Referências