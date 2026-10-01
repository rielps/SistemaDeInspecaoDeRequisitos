# HU-USU-05 – Alteração de senha

**Como** um usuário autenticado no sistema,
**Eu quero** alterar minha senha mediante confirmação da senha atual,
**Para que** eu possa manter minha conta segura.

## Critérios de Aceitação

1. **Dado** que estou autenticado e acesso a opção de alteração de senha, **quando** eu informo corretamente minha senha atual e uma nova senha válida, **então** o sistema deve atualizar minha senha e armazená-la utilizando hash, exibindo uma confirmação.
2. **Dado** que informo minha senha atual incorretamente, **quando** eu tento alterar a senha, **então** o sistema deve rejeitar a alteração e exibir uma mensagem de erro.
3. **Dado** que informo uma nova senha que não atende aos critérios mínimos exigidos (ex.: tamanho mínimo), **quando** eu tento salvar, **então** o sistema deve impedir a alteração e informar os critérios não atendidos.

## Requisitos relacionados
- RF-USU-05, RQ-USU-01
