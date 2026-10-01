# HU-ART-10 – Remover ou substituir diagrama associado a um artefato

**Como** um usuário do sistema,
**Eu quero** remover ou substituir um diagrama associado a um artefato,
**Para que** eu possa corrigir ou atualizar as representações gráficas vinculadas.

## Critérios de Aceitação

1. **Dado** que um artefato possui um diagrama associado, **quando** eu seleciono a opção de remover esse diagrama, **então** o sistema deve desvincular e excluir o diagrama do artefato.
2. **Dado** que um artefato possui um diagrama associado, **quando** eu envio um novo arquivo para substituí-lo em formato PDF, JPG ou PNG, **então** o sistema deve substituir o diagrama anterior pelo novo.
3. **Dado** que tento substituir um diagrama por um arquivo em formato diferente de PDF, JPG ou PNG, **quando** eu tento enviá-lo, **então** o sistema deve rejeitar o envio e informar os formatos aceitos.

## Requisitos relacionados
- RF-ART-10, RES-ART-02
