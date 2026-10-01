# Histórias de Usuário (HUs)

Esta pasta reúne a especificação de requisitos em formato de **Histórias de Usuário (HU)**, derivadas dos requisitos descritos em `visão.md` (seção 3.1).

Cada HU segue a estrutura:

- **Papel:** quem solicita a funcionalidade;
- **Ação:** o que deseja fazer;
- **Benefício:** por que deseja fazer;
- **Critérios de Aceitação:** condições, no formato Dado/Quando/Então, que determinam quando a HU pode ser considerada concluída;
- **Requisitos relacionados:** referência aos RF/RQ/RES de origem, para rastreabilidade com `visão.md`.

## Subsistema especificado

### Gerenciamento de Usuários
Componente responsável pelo cadastro, autenticação e gerenciamento das contas dos usuários (seção 2.3 e 3.1.1 de `visão.md`).

| HU | Título |
|---|---|
| [HU-USU-01](HU-USU-01-cadastro-usuario.md) | Cadastro de novo usuário |
| [HU-USU-02](HU-USU-02-autenticacao.md) | Autenticação de usuário |
| [HU-USU-03](HU-USU-03-logout.md) | Encerramento de sessão |
| [HU-USU-04](HU-USU-04-consultar-alterar-dados.md) | Consulta e alteração de dados cadastrais |
| [HU-USU-05](HU-USU-05-alterar-senha.md) | Alteração de senha |
| [HU-USU-06](HU-USU-06-excluir-conta.md) | Exclusão da própria conta |

### Gerenciamento de Artefatos
Componente responsável pela submissão, armazenamento e consulta dos artefatos de Engenharia de Requisitos enviados ao sistema (seção 2.3 e 3.1.2 de `visão.md`).

| HU | Título |
|---|---|
| [HU-ART-01](HU-ART-01-criar-hu.md) | Criar História de Usuário (HU) |
| [HU-ART-02](HU-ART-02-criar-cdu.md) | Criar Caso de Uso (CDU) |
| [HU-ART-03](HU-ART-03-submeter-diagramas.md) | Submeter e associar diagramas a um artefato |
| [HU-ART-04](HU-ART-04-visualizar-artefatos.md) | Visualizar artefatos cadastrados |
| [HU-ART-05](HU-ART-05-editar-artefato.md) | Editar artefato cadastrado |
| [HU-ART-06](HU-ART-06-excluir-artefato.md) | Excluir artefato cadastrado |
| [HU-ART-07](HU-ART-07-alterar-prioridade.md) | Alterar prioridade de um artefato |
| [HU-ART-08](HU-ART-08-alterar-status.md) | Alterar status de um artefato |
| [HU-ART-09](HU-ART-09-visualizar-diagramas.md) | Visualizar diagramas associados a um artefato |
| [HU-ART-10](HU-ART-10-remover-substituir-diagrama.md) | Remover ou substituir diagrama associado a um artefato |
