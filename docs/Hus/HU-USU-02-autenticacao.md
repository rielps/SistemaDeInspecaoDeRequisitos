# HU-USU-02 – Autenticação de usuário

**Como** um usuário cadastrado no sistema,
**Eu quero** autenticar-me com meu e-mail e senha,
**Para que** eu tenha acesso às funcionalidades restritas do sistema.

## Critérios de Aceitação

1. **Dado** que possuo uma conta cadastrada, **quando** eu informo e-mail e senha corretos, **então** o sistema deve conceder acesso e emitir um token de autenticação JWT com tempo de expiração configurável.
2. **Dado** que informo e-mail ou senha incorretos, **quando** eu tento autenticar, **então** o sistema deve negar o acesso e exibir uma mensagem de erro genérica, sem indicar qual campo está incorreto.
3. **Dado** que realizo 5 tentativas consecutivas de login com credenciais inválidas, **quando** eu tento autenticar novamente, **então** o sistema deve bloquear novas tentativas de autenticação por um período de 15 minutos.
4. **Dado** que uso um token de autenticação expirado ou inválido, **quando** eu realizo uma requisição a uma funcionalidade protegida, **então** o sistema deve rejeitar a requisição e solicitar nova autenticação.

## Requisitos relacionados
- RF-USU-02, RQ-USU-02, RQ-USU-03, RES-USU-01
