# HU-USU-03 – Encerramento de sessão

**Como** um usuário autenticado no sistema,
**Eu quero** encerrar minha sessão,
**Para que** eu possa sair do sistema com segurança, especialmente em dispositivos compartilhados.

## Critérios de Aceitação

1. **Dado** que estou autenticado no sistema, **quando** eu seleciono a opção de encerrar sessão (logout), **então** o sistema deve invalidar meu token de autenticação atual e redirecionar-me para a tela de login.
2. **Dado** que encerrei minha sessão, **quando** eu tento acessar uma funcionalidade restrita utilizando o token anterior, **então** o sistema deve negar o acesso e solicitar nova autenticação.

## Requisitos relacionados
- RF-USU-03
