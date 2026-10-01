# HU-ART-05 – Editar artefato cadastrado

**Como** um usuário do sistema,
**Eu quero** editar os dados de um artefato que já cadastrei,
**Para que** eu possa corrigir ou atualizar as informações antes ou depois da inspeção.

## Critérios de Aceitação

1. **Dado** que possuo um artefato cadastrado, **quando** eu acesso a opção de edição e altero um ou mais campos, **então** o sistema deve salvar somente os campos modificados, preservando os demais dados inalterados.
2. **Dado** que estou editando um artefato, **quando** eu deixo um campo obrigatório vazio, **então** o sistema deve validar em tempo real e impedir a submissão, indicando o campo pendente.
3. **Dado** que edito um artefato com sucesso, **quando** a edição é concluída, **então** o sistema deve exibir uma confirmação da atualização.

## Requisitos relacionados
- RF-ART-05, RQ-ART-01, RQ-ART-03
