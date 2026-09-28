# Especificações de casos de uso

<a id="sumario"></a>

## Sumário

- [CDU001 — Cadastrar-se no sistema](#cdu001)
- [CDU002 — Fazer login](#cdu002)
- [CDU003 — Gerenciar perfil](#cdu003)

---

<a id="cdu001"></a>

## CDU001 — Cadastrar-se no sistema

| Campo | Descrição |
|---|---|
| **Objetivo** | Criar uma conta e acessar o sistema. |
| **Ator principal** | Usuário não autenticado. |
| **Atores secundários** | Não há. |
| **Pré-condição** | O usuário não está autenticado. |
| **Gatilho** | O usuário seleciona “Cadastrar-se”. |

### Fluxo principal

1. O usuário seleciona “Cadastrar-se”.
2. O sistema apresenta os campos nome, e-mail, senha e confirmação de senha.
3. O usuário preenche os campos e envia o formulário.
4. O sistema valida os dados conforme as regras abaixo.
5. O sistema cria a conta e autentica o usuário.
6. O sistema informa o sucesso e direciona o usuário à área autenticada.

### Fluxo alternativo

- **A1 — Cancelamento:** antes de enviar o formulário, o usuário cancela. O sistema retorna à tela de acesso sem criar a conta. **[Proposto]**

### Fluxos de exceção

- **E1 — Dados inválidos (passo 4):** campos obrigatórios vazios, e-mail inválido, senha fora das regras ou confirmação diferente. O sistema indica os problemas e retorna ao passo 3, sem criar a conta.
- **E2 — E-mail já cadastrado (passo 4):** o sistema impede o cadastro e solicita outro e-mail, retornando ao passo 3. **[Regra proposta]**
- **E3 — Falha na criação (passo 5):** o sistema informa a falha, não cria a conta e permite nova tentativa.
- **E4 — Falha na autenticação (passo 5):** o sistema mantém a conta criada e direciona o usuário à tela de entrada. **[Tratamento proposto]**

### Pós-condições

- **Sucesso:** conta criada e usuário autenticado.
- **Cancelamento ou falha antes da criação:** nenhuma conta criada; usuário não autenticado.
- **Falha apenas na autenticação:** conta criada; usuário não autenticado.

### Regras de negócio e validação

- Todos os campos são obrigatórios. **[Proposto]**
- O e-mail deve ter formato válido e ser único por conta. **[Unicidade proposta]**
- A senha deve conter pelo menos uma letra maiúscula, uma minúscula, um número e um caractere especial.
- A confirmação deve ser igual à senha.
- Após o cadastro, o usuário deve ser autenticado automaticamente.

### Pendências

- Definir tamanho mínimo/máximo da senha, caracteres especiais aceitos e limites do nome.
- Decidir se haverá confirmação de titularidade do e-mail.
- Confirmar os itens marcados como propostos.

[Voltar ao sumário](#sumario)

---

<a id="cdu002"></a>

## CDU002 — Fazer login

| Campo | Descrição |
|---|---|
| **Objetivo** | Autenticar o usuário e permitir o acesso à sua conta. |
| **Ator principal** | Usuário não autenticado. |
| **Atores secundários** | Não há. |
| **Pré-condição** | O usuário não está autenticado. |
| **Gatilho** | O usuário solicita acesso à tela de login. |

### Fluxo principal

1. O usuário acessa a opção “Entrar”.
2. O sistema apresenta os campos e-mail e senha.
3. O usuário preenche os campos e solicita o login.
4. O sistema verifica o preenchimento e valida as credenciais.
5. O sistema autentica o usuário e inicia sua sessão.
6. O sistema direciona o usuário à área autenticada.

### Fluxo alternativo

- **A1 — Cancelamento:** antes de enviar os dados, o usuário sai da tela de login. O caso de uso termina sem autenticação.

### Fluxos de exceção

- **E1 — Campos vazios (passo 4):** o sistema indica os campos obrigatórios não preenchidos e retorna ao passo 3.
- **E2 — Credenciais inválidas (passo 4):** o sistema informa “E-mail ou senha incorretos” e retorna ao passo 3, sem indicar qual credencial está incorreta.
- **E3 — Falha no serviço (passos 4 ou 5):** o sistema informa que não foi possível concluir o login e permite nova tentativa, sem liberar o acesso.

### Pós-condições

- **Sucesso:** usuário autenticado, com sessão iniciada e acesso à sua conta.
- **Falha ou cancelamento:** usuário permanece não autenticado, sem acesso à área restrita.

### Regras de negócio e validação

- E-mail e senha são obrigatórios.
- As credenciais devem corresponder a uma conta cadastrada.
- O acesso à área autenticada só deve ser liberado após a validação das credenciais.
- A senha deve ser ocultada visualmente durante a digitação.
- A mensagem de credenciais inválidas não deve revelar se o e-mail está cadastrado.

### Pendências

- Definir o limite de tentativas e o tratamento de falhas consecutivas.
- Definir o tempo de duração da sessão.
- Confirmar se haverá recuperação de senha e verificação de e-mail como condição para acesso.

[Voltar ao sumário](#sumario)

---

<a id="cdu003"></a>

## CDU003 — Gerenciar perfil

| Campo | Descrição |
|---|---|
| **Objetivo** | Alterar o nome e/ou a foto de perfil do usuário. |
| **Ator principal** | Usuário autenticado. |
| **Atores secundários** | Não há. |
| **Pré-condição** | O usuário está autenticado no sistema. |
| **Gatilho** | O usuário seleciona a opção “Editar perfil”. |

### Fluxo principal

1. O usuário solicita a edição do perfil.
2. O sistema apresenta o nome e a foto atuais, quando houver.
3. O usuário altera o nome e/ou seleciona uma nova foto.
4. O usuário solicita o salvamento.
5. O sistema valida o nome e, caso uma nova foto tenha sido enviada, valida a imagem.
6. O sistema salva as alterações e apresenta o perfil atualizado com uma mensagem de sucesso.

### Fluxo alternativo

- **A1 — Cancelamento:** antes de salvar, o usuário cancela a edição. O sistema descarta as alterações e mantém o perfil anterior.

### Fluxos de exceção

- **E1 — Nome inválido (passo 5):** o sistema indica que o nome está vazio ou não atende aos critérios definidos e retorna ao passo 3, sem salvar as alterações.
- **E2 — Imagem inválida (passo 5):** o sistema informa que o arquivo não é uma imagem válida, possui formato não aceito ou excede o tamanho permitido e retorna ao passo 3, sem salvar as alterações.
- **E3 — Falha no salvamento (passo 6):** o sistema informa a falha e permite nova tentativa, mantendo os dados anteriores.

### Pós-condições

- **Sucesso:** perfil atualizado com o nome e/ou a foto informados.
- **Falha ou cancelamento:** os dados anteriores são mantidos.

### Regras de negócio e validação

- O usuário só pode editar o próprio perfil.
- O nome é obrigatório e não pode conter apenas espaços.
- A foto é opcional; não selecionar uma nova imagem mantém a foto atual.
- Uma nova foto substitui a anterior.
- A imagem deve atender aos formatos e ao tamanho máximo permitidos.
- As alterações só são salvas quando todos os dados modificados são válidos.

### Pendências

- Definir os limites de tamanho e demais critérios de validação do nome.
- Definir os formatos de imagem aceitos e o tamanho máximo do arquivo.

[Voltar ao sumário](#sumario)