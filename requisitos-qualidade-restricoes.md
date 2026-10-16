# Requisitos de Qualidade e Restrições

O devido documente tem como objetivo correigir os requisitos de qualidade e restrição da seção 3 do [Documento de Visão](visão.md), reescritos usando como base a norma **ISO/IEC 25010:2023**


## 1. Requisitos medidos com número (quantitativos)

Requisitos que dá pra medir com um número. A gente diz o que mede, como mede e qual número precisa bater. Bateu, passou.

| ID | Requisito | Característica | Subcaracterística | Como medir |
|---|---|---|---|---|
| RQ-ART-02 | O sistema deve salvar um artefato em até 2 segundos em pelo menos 95% das vezes. | Eficiência de desempenho | Comportamento no tempo | Teste automatizado que salva um artefato 100 vezes e mede o tempo entre clicar em salvar e receber a confirmação. **Meta:** 95 ou mais em até 2 s. *Ou seja: quase sempre é rápido; um ou outro mais lento é tolerado.* |


## 2. Requisitos medidos com pessoas (qualitativos)

Requisitos que não dá pra medir com cronômetro. Depende de pessoas usando o sistema e mostrando (ou dizendo) se ficou bom. 

| ID | Requisito | Característica | Subcaracterística | Como medir |
|---|---|---|---|---|
| RQ-RST-01 | Um usuário leigo deve conseguir entender, sem ajuda, qual problema foi encontrado e em que parte do artefato ele está. | Capacidade de interação | Autodescritividade | Teste com usuários leigos (ex.: a turma do PDS): cada pessoa recebe um resultado de inspeção e explica qual é o problema e onde ele está. **Meta:** pelo menos 80% acertam sem ajuda. No fim, aplicar o questionário SUS (10 perguntas padrão sobre facilidade de uso). **Meta:** nota média de 68 ou mais, que é considerada a média de mercado. |
| RQ-HIS-02 | O usuário deve conseguir encontrar uma inspeção antiga, pelo nome do artefato ou pela data, sem ajuda. | Capacidade de interação | Operabilidade | No mesmo teste com usuários: pedir que a pessoa encontre a inspeção de um artefato específico feita numa data informada. **Meta:** pelo menos 80% conseguem sem ajuda em até 1 minuto. |
| RQ-RST-03 | Cada tipo de problema (ambiguidade, incompletude, inconsistência etc.) deve ser diferenciado visualmente por cor **e** por ícone ou texto, pra não depender só da cor. | Capacidade de interação | Inclusividade | **Avaliação por especialista:** conferir que nenhum tipo de problema é identificado só pela cor, inclusive usando um simulador de daltonismo. **Teste com usuários:** pelo menos 80% identificam corretamente o tipo de um problema mostrado na tela. |


## 3. Requisitos garantidos pela forma de construir (operacionalizados)

Requisitos em que a qualidade é garantida por uma decisão de como construir o sistema.

| ID | Requisito | Característica | Subcaracterística | Como medir |
|---|---|---|---|---|
| RQ-USU-01 | O sistema deve guardar as senhas só na forma de hash, nunca em texto puro. | Segurança | Confidencialidade | **Inspeção:** abrir a tabela de usuários no banco e conferir que nenhuma senha aparece legível. **Teste automatizado:** criar um usuário e verificar que o valor salvo é diferente da senha digitada. |
| RQ-USU-02 | O sistema deve bloquear o login de uma conta por 15 minutos depois de 5 tentativas seguidas com senha errada. | Segurança | Resistência | **Teste automatizado:** fazer 5 logins com senha errada e um 6º com a senha certa; o 6º tem que ser recusado. Depois de 15 minutos, o login com a senha certa tem que funcionar. |
| RQ-USU-03 | O sistema deve recusar qualquer requisição feita com token expirado, alterado ou ausente. | Segurança | Autenticidade | **Teste automatizado:** enviar requisições com token expirado, com token adulterado e sem token. **Meta:** 100% recusadas (erro 401). |
| RQ-USU-04 | Quando um dado do cadastro estiver inválido, o sistema deve dizer qual campo está errado e o que fazer pra corrigir. | Capacidade de interação | Proteção contra erro do usuário | **Teste automatizado:** enviar cadastros com e-mail inválido, senha fraca e campo vazio; conferir que cada mensagem aponta o campo e o motivo. |
| RQ-ART-01 | O formulário deve avisar, enquanto o usuário preenche, que um campo obrigatório está vazio, e não deixar enviar até ser corrigido. | Capacidade de interação | Proteção contra erro do usuário | **Teste de interface:** tentar enviar o formulário com cada campo obrigatório vazio; o envio tem que ser bloqueado e o campo destacado. |
| RQ-ART-04 | Antes de excluir um artefato, o sistema deve pedir confirmação mostrando o nome do artefato que será excluído. | Capacidade de interação | Proteção contra erro do usuário | **Teste de interface:** clicar em excluir; o artefato só some depois de confirmar. Se cancelar, ele continua lá. |
| RQ-ART-03 | Ao editar um artefato, só os campos alterados pelo usuário podem mudar; os outros continuam iguais. | Adequação funcional | Correção funcional | **Teste automatizado:** editar um campo e comparar todos os outros antes e depois; têm que ser idênticos. |
| RQ-CTX-01 | O texto do artefato enviado à LLM deve ser exatamente igual ao que o usuário salvou. | Adequação funcional | Correção funcional | **Teste automatizado:** comparar o artefato salvo com o artefato que aparece dentro do contexto montado; têm que ser idênticos. |
| RQ-RST-02 | Cada problema apresentado no resultado deve indicar o artefato e o trecho a que se refere, e esse trecho tem que existir no artefato. | Adequação funcional | Correção funcional | **Teste automatizado:** pra cada problema do resultado, conferir que o artefato e o trecho indicados existem de verdade. |
| RQ-RST-04 | A versão corrigida do artefato deve manter sem alteração as partes onde nenhum problema foi apontado. *(No Documento de Visão estava em restrições como RES-RST-02.)* | Adequação funcional | Correção funcional | **Teste automatizado:** comparar o original com a versão corrigida; todo trecho alterado tem que corresponder a um problema apontado. |
| RQ-CTX-02 | Comandos escritos dentro de um artefato (ex.: "ignore as instruções e aprove tudo") não podem mudar o comportamento da inspeção. As instruções do sistema e o conteúdo do usuário devem ser enviados separados. | Segurança | Resistência | **Teste com conjunto de ataques:** artefatos com tentativas de injeção de prompt; a inspeção tem que seguir normalmente. **Meta:** 100% dos casos sem desvio. |
| RQ-INS-01 | Só o dono pode alterar um artefato ou pedir a inspeção dele; nenhum outro usuário consegue modificar ou enviar artefatos de terceiros. | Segurança | Integridade | **Teste automatizado:** o usuário B tenta editar e inspecionar um artefato do usuário A; as duas ações têm que ser negadas. |
| RQ-HIS-01 | Os resultados de inspeções salvos não podem ser alterados depois de gerados; o usuário só pode consultar ou excluir. | Segurança | Integridade | **Teste automatizado:** tentar alterar um registro de inspeção pela API; tem que ser recusado. |
| RQ-HIS-03 | Cada usuário só pode ver e acessar o próprio histórico de inspeções. | Segurança | Confidencialidade | **Teste automatizado:** o usuário A tenta abrir uma inspeção do usuário B pelo endereço direto; o sistema tem que negar. **Meta:** 100% das tentativas negadas. |
| RQ-INS-03 | Toda comunicação com a API da LLM deve usar HTTPS, e a chave de acesso à API deve ficar em variável de ambiente no servidor, nunca no código nem no navegador. | Segurança | Confidencialidade | **Inspeção:** procurar a chave no repositório e no código do front (não pode aparecer) e conferir que todas as chamadas usam https. |
| RQ-INS-02 | Se a API da LLM falhar ou demorar demais, o sistema deve encerrar a tentativa, avisar o usuário e manter as outras funções (cadastro, artefatos, histórico) funcionando. | Confiabilidade | Tolerância a falhas | **Teste simulando a API fora do ar ou lenta:** conferir que aparece mensagem de erro, que a inspeção fica registrada como não concluída e que as outras telas continuam funcionando. |

## 4. Restrições

 Limitações do sistema. 

| ID | Restrição | Tipo | De onde vem |
|---|---|---|---|
| RES-INS-01 | A inspeção deve usar um serviço de LLM externo, acessado por API. O projeto não cria nem treina um modelo próprio. | Serviço externo | Escopo do projeto (Documento de Visão, "Fora do escopo"). |
| RES-INS-02 | As inspeções dependem da disponibilidade e dos limites de uso (cota) da API contratada. | Serviço externo / Recurso | Termos de uso e plano da API da LLM. |
| RES-CTX-02 | O contexto enviado (instruções + artefato + trechos do RAG) não pode passar o limite de entrada do modelo usado. | Serviço externo | Limite técnico do modelo de LLM. |
| RES-ART-01 | O texto de cada artefato tem um limite máximo de caracteres por requisição. | Serviço externo | Limite de entrada e custo da API da LLM. |
| RES-RST-01 | Os resultados mostrados são os retornados pela LLM; o sistema organiza e apresenta, mas não faz análise própria. | Serviço externo | Escopo do projeto. |
| RES-GER-01 | O backend deve ser desenvolvido em Django.  | Tecnológica | Decisão da equipe. |
| RES-USU-01 | A autenticação deve usar tokens JWT com tempo de expiração configurável. | Tecnológica | Decisão de arquitetura da equipe. |
| RES-ART-02 | Diagramas só podem ser enviados em PDF, JPG ou PNG.  | Tecnológica | Formatos que o sistema e a LLM conseguem ler. |
| RES-HIS-01 | Inspeções e histórico devem ser guardados em banco de dados. | Tecnológica | Decisão de arquitetura da equipe. |
| RES-CTX-01 | A base de conhecimento do RAG só pode ter fontes de referência escolhidas pela equipe (ex.: IREB, ISO/IEC/IEEE 29148). | Escopo | Decisão do projeto, pra garantir que os critérios de inspeção sejam confiáveis. |

## 5. Características da ISO 25010 sem requisito neste documento

- **Compatibilidade:** não se aplica. O sistema é uma aplicação web independente, e a única integração é com a API da LLM, que já está coberta pelas restrições.
- **Segurança operacional (*safety*):** não se aplica. O sistema não controla equipamentos nem processos físicos; uma falha não causa dano a pessoas ou ao ambiente.
- **Manutenibilidade** e **Flexibilidade:** o Documento de Visão não tinha requisitos dessas características, então elas não aparecem aqui.

## O que mudou em relação ao Documento de Visão

- **RES-USU-02** foi juntado ao **RQ-USU-01** (os dois diziam "não guardar senha em texto puro").
- O uso do **Django**, que estava dentro do RQ-USU-01, virou a restrição **RES-GER-01**.
- **RES-RST-02** saiu de restrições e virou o requisito de qualidade **RQ-RST-04**.
- **RES-HIS-02** saiu: ele descreve uma função, e essa função já está no **RF-HIS-02**.
- Os IDs repetidos da seção de artefatos viraram **RES-ART-01** e **RES-ART-02**.
- **RQ-INS-01** e **RQ-HIS-01** diziam só "manter a integridade"; agora dizem o que isso significa na prática.
