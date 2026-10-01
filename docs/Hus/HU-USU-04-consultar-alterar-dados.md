# HU-USU-04 – Consulta e alteração de dados cadastrais

**Como** um usuário autenticado no sistema,
**Eu quero** consultar e alterar meus dados cadastrais (nome e e-mail),
**Para que** eu possa manter minhas informações atualizadas.

## Critérios de Aceitação

1. **Dado** que estou autenticado, **quando** eu acesso a tela de perfil, **então** o sistema deve exibir meus dados cadastrais atuais (nome e e-mail).
2. **Dado** que estou na tela de perfil, **quando** eu altero meu nome ou e-mail para valores válidos e salvo, **então** o sistema deve atualizar meus dados e exibir uma confirmação.
3. **Dado** que tento alterar meu e-mail para um já utilizado por outra conta, **quando** eu salvo as alterações, **então** o sistema deve rejeitar a alteração e informar que o e-mail já está em uso.
4. **Dado** que informo dados inválidos (ex.: e-mail em formato incorreto), **quando** eu tento salvar, **então** o sistema deve impedir a alteração e exibir uma mensagem informando o problema.

## Requisitos relacionados
- RF-USU-04
