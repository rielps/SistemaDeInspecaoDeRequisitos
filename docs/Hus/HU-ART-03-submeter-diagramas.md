# HU-ART-03 – Submeter e associar diagramas a um artefato

**Como** um usuário do sistema,
**Eu quero** submeter um ou mais diagramas e associá-los a uma História de Usuário ou Caso de Uso, durante a criação ou posteriormente,
**Para que** o artefato fique mais completo para a inspeção.

## Critérios de Aceitação

1. **Dado** que estou criando ou editando um artefato, **quando** eu seleciono um arquivo de diagrama em formato PDF, JPG ou PNG, **então** o sistema deve aceitar o envio e associá-lo ao artefato.
2. **Dado** que seleciono um arquivo de diagrama em formato diferente de PDF, JPG ou PNG, **quando** eu tento enviá-lo, **então** o sistema deve rejeitar o envio e informar os formatos aceitos.
3. **Dado** que já salvei um artefato anteriormente sem diagrama, **quando** eu acesso esse artefato posteriormente, **então** o sistema deve permitir que eu associe um ou mais diagramas a ele.
4. **Dado** que associo múltiplos diagramas a um mesmo artefato, **quando** o envio é concluído, **então** todos os diagramas devem ficar vinculados a esse artefato.

## Requisitos relacionados
- RF-ART-03, RES-ART-02
