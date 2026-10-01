# HU-ART-08 – Alterar status de um artefato

**Como** um usuário do sistema,
**Eu quero** alterar o status de um artefato entre os estados disponíveis no backlog de acompanhamento,
**Para que** eu possa acompanhar o progresso do artefato ao longo do fluxo de trabalho.

## Critérios de Aceitação

1. **Dado** que possuo um artefato cadastrado, **quando** eu seleciono um novo status dentre os estados disponíveis no backlog, **então** o sistema deve atualizar o status do artefato e refletir a mudança na lista de artefatos.
2. **Dado** que tento definir um status que não faz parte dos estados disponíveis no backlog, **quando** eu tento salvar, **então** o sistema deve impedir a alteração.

## Requisitos relacionados
- RF-ART-08
