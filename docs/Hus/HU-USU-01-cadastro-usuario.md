# HU-USU-01 – Cadastro de novo usuário

**Como** um sujeito leigo interessado em utilizar o sistema,
**Eu quero** me cadastrar informando nome, e-mail e senha,
**Para que** eu possa criar uma conta e acessar as funcionalidades de submissão e inspeção de artefatos.

## Critérios de Aceitação

1. **Dado** que estou na tela de cadastro e informo nome, e-mail e senha válidos, **quando** eu submeto o formulário, **então** o sistema deve criar minha conta com sucesso e exibir uma confirmação.
2. **Dado** que estou cadastrando uma conta, **quando** o sistema armazena minha senha, **então** ela deve ser persistida utilizando o mecanismo de hash de senhas do Django, nunca em texto puro.
3. **Dado** que informo um e-mail, nome ou senha inválidos (ex.: e-mail em formato incorreto, campos obrigatórios vazios), **quando** eu tento submeter o formulário, **então** o sistema deve impedir o cadastro e exibir uma mensagem informando quais dados são inválidos.
4. **Dado** que tento me cadastrar com um e-mail já utilizado por outra conta, **quando** eu submeto o formulário, **então** o sistema deve rejeitar o cadastro e informar que o e-mail já está em uso.

## Requisitos relacionados
- RF-USU-01, RQ-USU-01, RQ-USU-04, RES-USU-02
