# HU-USU-06 – Exclusão da própria conta

**Como** um usuário autenticado no sistema,
**Eu quero** excluir minha própria conta,
**Para que** eu possa remover permanentemente meus dados do sistema quando eu não desejar mais utilizá-lo.

## Critérios de Aceitação

1. **Dado** que estou autenticado e acesso a opção de exclusão de conta, **quando** eu confirmo a exclusão (após mensagem de confirmação), **então** o sistema deve remover minha conta e encerrar minha sessão.
2. **Dado** que solicito a exclusão da minha conta, **quando** o sistema processa a solicitação, **então** meu token de autenticação deve ser invalidado e eu devo ser redirecionado para a tela inicial/login.
3. **Dado** que excluí minha conta, **quando** eu tento autenticar novamente com as mesmas credenciais, **então** o sistema deve negar o acesso informando que a conta não existe.

## Requisitos relacionados
- RF-USU-06
