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
- **Gerenciamento de contexto**: responsável por estruturar e fornecer à LLM as instruções, regras, critérios de inspeção e informações relavantes para a análise dos artefatos, utilizando e aplicando técnicas de engenharia de prompts e mecanismos de recuperação de informações (RAG);
- **Inspeção de Artefatos:** responsável pela preparação dos artefatos e pela comunicação, por meio de API, com o serviço externo de Large Language Model (LLM) utilizado na inspeção;
- **Resultados da Inspeção:** responsável por organizar e apresentar os problemas identificados, além de disponibilizar a versão revisada dos artefatos analisados;
- **Armazenamento e histórico:** responsável pelo armazenamento e consulta das inspeções realizadas anteriormente pelo usuário.


## 3. Requisitos do Sistema

## 3.1 Por subsistema/componente
Requisitos organizados por subsistemas, definidos pelos componentes estruturados no módulo 2.3. Ao total, são 6 subsistemas trabalhados. 
Em cada subsistema os requisitos são separados em: Requisitos Funcionais (RF); Requisitos de Qualidade (RQ) e Restrições (RES).

### 3.1.1 Subsistema de gerenciamento de usuários

#### Requisitos Funcionais:

| ID | Requisito |
|---|---|
| RF-USU-01 | O sistema deve permitir o cadastro de novos usuários com nome, e-mail e senha |
| RF-USU-02 | O sistema deve realizar a autenticação do usuário para concessão de acesso às funcionalidades |
| RF-USU-03 | O sistema deve permitir que o usuário encerre sua sessão |
| RF-USU-04 | O sistema deve permitir que o usuário consulte e altere seus dados cadastrais |
| RF-USU-05 | O sistema deve permitir que o usuário alterinha sua senha mediante a confirmação da senha atual |
| RF-USU-06 | O sistema deve permitir que o usuário exclua sua própria contra |

#### Requisitos de Qualidade

| ID | Categoria | Requisito |
|---|---|---|
| RQ-USU-01 | Segurança | O sistema deve armazenar as senhas dos usuários utilizando o mecanismo de hash de senhas disponibilizado pelo Django, não armazenando as senhas em texto puro |
| RQ-USU-02 | Segurança | O sistema deve bloquear novas tentativas de autenticação após 5 tentativas consecutivas de login com credenciais inválidas durante um período de 15 minutos |
| RQ-USU-03 | Segurança | O sistema deve rejeitar requisições realizada com tokens de autenticação expirados ou inválidos |
| RQ-USU-04 | Usabilidade | O sistema deve informar ao suuário quando os dados fornecidos durante o cadastro forem inválidos |

#### Restrições

| ID | Restrição |
|---|---|
| RES-USU-01 | A autenticação de sessão deve utilizar tokens JWT com tempo de expiração configurável |
| RES-USU-02 | O sistema não deve armazenar as senhas dos usuários em texto puro |

### 3.1.2 Subsistema de gerenciamento de artefatos

#### Requisitos Funcionais:

| ID | Requisito |
|---|---|
| RF-ART-01 | O sistema deve disponibilizar um formulário estruturado para preenchimento de histórias de usuário (Papel, Ação, Benefício e Critérios de Aceitação |
| RF-ART-02 | O sistema deve disponibilizar um formulário estruturado para preenchimento de Casos de Uso (Ator Principal, Pré-Condições, Fluxo principal e alternativos, Pós-condições)
| RF-ART-03 | O sistema deve permitir ao usuário submeter e associar um ou mais diagramas a uma História de usuário ou Caso de Uso durante sua criação ou posteriormente |
| RF-ART-04 | O sistema deve permitir ao usuário visualizar os artefatos cadastrados, apresentando suas respectivas informações, como prioridade e status |
| RF-ART-05 | O sistema deve permitir ao usuário editar os dados dos artefatos cadastrados |
| RF-ART-06 | O sistema deve permitir ao usuário excluir os artefatos cadastrados |
| RF-ART-07 | O sistema deve permitir ao usuário alterar a prioridade de um artefato cadastrado |
| RF-ART-08 | O sistema deve permitir ao usuário alterar o status de um artefato entre os estados disponíveis no backlog de acompanhamento |
| Rf-ART-09 | O sistema deve permitir ao usuário visualizar os diagramas associados aos respectivos artefatos |
| RF-ART-10 | O sistema deve permitir ao usuário remover ou substituir um diagrama associado a um artefato |

#### Requisitos de Qualidade

| ID | Tipo | Requisito |
|---|---|---|
| RQ-ART-01 | Usabilidade | Os formulários devem conter validações em tempo real para impedir a submissão de campos obrigatórios vazios |
| RQ-ART-02 | Desempenho | O sistema deve concluir a operação de salvamento de um artefato em até 2 segundos |
| RQ-ART-03 | Integridade | O sistema deve preservar os dados de um artefato durante operações de edição, não alterando campos que não tenham sido modificados pelo usuário |
| RQ-ART-04 | Usabilidade | O sistema deve apresentar uma mensagem de confirmação antes da exclusão definitiva de um artefato |

#### Restrições

| ID | Restrição |
|---|---|
| RES-USU-01 | O tamanho total do texto do artefato enviado não pode ultrapassar o limite estipulado de caracteres por requisição |
| RES-USU-02 | Os diagramas associados aos artefatos devem ser enviados em formatos de arquivo PDF, JPG ou PNG |


### 3.1.3 Subsistema de gerenciamento de contexto

#### Requisitos Funcionais:

| ID | Requisito |
|---|---|
| RF-CTX-01 | O sistema deve fornecer à LLM instruções estruturadas contendo os critérios, regras e etapas definidos para a inspeção dos artefatos de Engenharia de Requisitos (o prompt) |
| RF-CTX-02 | O sistema deve recuperar, por meio de RAG, informações relevantes da base de conhecimento para complementar o contexto utilizado na inspeção do artefato |
| RF-CTX-03 | O sistema deve considerar, na construção do contexto da inspeção, o artefato submetido pelo usuário e os critérios de Engenharia de Requisitos aplicáveis ao seu tipo recuperados via RAG |
| RF-CTX-04 | O sistema deve fornecer à LLM instruções que definam a estrutura e os campos obrigatórios da resposta esperada para a inspeção (template de resposta) |

#### Requisitos de qualidade

| ID | Tipo | Requisito |
|---|---|
| RQ-CTX-01 | Integrudade | O sistema não deve alterar o conteúdo original do artefato durante a construção do contexto enviado à LLM |
| RQ-CTX-02 | Segurança | O sistema deve tratar o conteúdo fornecido pelo usuário como dado não confiável e impedir que instruções presentes no artefato alterem as instruções de inspeção fornecidas pelo sistema (injeção de prompt) |

#### Restrições

| ID | Restrição |
|---|---|
| RES-CTX-01 |A base de conhecimento utilizada pelo mecanismo de RAG deve conter apenas conteúdos previamente definidos como fontes de referência para os critérios de inspeção do projeto |
| RES-CTX-02 | O contexto enviado à LLM deve respeitar o limite de entrada suportado pelo modelo utilizado pela aplicação |

### 3.1.4 Subsistema de inspeção e artefatos

#### Requisitos Funcionais:

| ID | Requisito |
|---|---|
| RF-INS-01 | O sistema deve permitir ao usuário solicitar a inspeção de um artefato cadastrado |
| RF-INS-02 | O sistema deve permitir a inspeção conjunta de artefatos relacionados para verificar inconsistências entre eles |
| RF-INS-03 | O sistema deve utilizar o contexto preparado para a inspeção dos artefatos selecionados |
| RF-INS-04 | O sistema deve enviar os artefatos e o contexto de inspeção à LLM por meio de API |
| RF-INS-05 | O sistema deve receber a resposta retornada pela LLM após a inspeção |
| RF-INS-6 | O sistema informar ao usuário quanto ao tempo restante para a conclusão da inspeção |
| RF-INS-07 | O sistema deve informar ao usuário quando a inspeção não puder ser concluída |

#### Requisitos de qualidade:

| ID | Requisito |
|---|---|
| RQ-INS-01 | O sistema deve manter a integridade dos artefatos e do contexto enviados para inspeção |
| RQ-INS-02 | O sistema deve tratar falhas na comunicação com a LLM sem comprometer o funcionamento das demais funcionalidades |
| RQ-INS-03 | O sistema deve realizar a comunicação com o serviço de LLM de forma segura |

#### Restrições:

| ID | Requisito |
|---|---|
| RES-INS-01 | A inspeção dos artefatos deve ser realizada utilizando um serviço externo de LLM por meio de API |
| RES-INS-02 | A execução das inspeções está sujeita à disponibilidade e aos limites de uso da API da LLM utilizada |

### 3.1.5 Subsistema de resultados da inspeção

#### Requisitos Funcionais:

| ID | Requisito |
|---|---|
| RF-RST-01 | O sistema deve apresentar ao usuário os resultados obtidos após a inspeção dos artefatos |
| RF-RST-02 | O sistema deve apresentar os problemas identificados de acordo com o tipo de irregularidade encontrada |
| RF-RST-03 | O sistema deve indicar em qual parte do artefato cada problema foi identificado |
| RF-RST-04 | O sistema deve apresentar uma descrição dos problemas encontrados e sugestões para sua correção |
| RF-RST-05 | O sistema deve disponibilizar uma versão corrigida do artefato com base nos resultados da inspeção |
| RF-RST-06 | O sistema deve permitir a geração de um documento contendo os problemas identificados e as correções sugeridas |

#### Requisitos de qualidade:

| ID | Requisito |
|---|---|
| RQ-RST-01 | Os resultados da inspeção devem ser apresentados de forma clara e organizada |
| RQ-RST-02 | O sistema deve manter a correspondência entre os problemas apresentados e os artefatos inspecionados |
| RQ-RST-03 | O sistema deve diferenciar visualmente os tipos de problemas identificados durante a inspeção |

#### Restrições:

| ID | Requisito |
|---|---|
| RES-RST-01 | Os resultados apresentados devem ser baseados na resposta retornada pelo serviço de LLM utilizado na inspeção |
| RES-RST-02 | A versão corrigida do artefato deve preservar as informações originais que não tenham sido identificadas como problemáticas |

### 3.1.6 Subsistema de Armazenamento e Histórico

#### Requisitos Funcionais:

| ID | Requisito |
|---|---|
| RF-HIS-01 | O sistema deve armazenar as inspeções realizadas e seus respectivos resultados |
| RF-HIS-02 | O sistema deve associar cada inspeção ao usuário e aos artefatos analisados |
| RF-HIS-03 | O sistema deve registrar a data e o horário de realização de cada inspeção |
| RF-HIS-04 | O sistema deve permitir ao usuário consultar o histórico de inspeções realizadas |
| RF-HIS-05 | O sistema deve permitir ao usuário visualizar os detalhes e resultados de uma inspeção anterior |
| RF-HIS-06 | O sistema deve permitir ao usuário excluir registros de inspeções do seu histórico |

#### Requisitos de qualidade:

| ID | Requisito |
|---|---|
| RQ-HIS-01 | O sistema deve manter a integridade dos dados armazenados das inspeções |
| RQ-HIS-02 | O histórico deve ser organizado de forma que facilite a identificação e consulta das inspeções realizadas |
| RQ-HIS-03 | O sistema deve garantir que cada usuário tenha acesso apenas ao seu próprio histórico de inspeções |

#### Restrições:

| ID | Requisito |
|---|---|
| RES-HIS-01 | As informações das inspeções e do histórico devem ser armazenadas em banco de dados |
| RES-HIS-02 | Cada registro do histórico deve permanecer associado ao usuário e aos artefatos correspondentes |

## 3.3 Interfaces
Não há interfaces definidas no momento para este projeto. 

## 4. Referências
1. **ISO/IEC/IEEE 29148:2018:** *Systems and software engineering — Life cycle processes — Requirements engineering.*
2.  **Guia de Estudos CPRE Foundation Level (v1.2):** *International Requirements Engineering Board (IREB).*
3. **International Requirements Engineering Board (IREB):** Site oficial do IREB e materiais sobre Requirements Engineering e CPRE. Disponível em: https://ireb.org/