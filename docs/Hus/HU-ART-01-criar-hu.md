# HU-ART-01 – Criar História de Usuário (HU)

**Como** um usuário do sistema,
**Eu quero** preencher um formulário estruturado para registrar uma História de Usuário (Papel, Ação, Benefício e Critérios de Aceitação),
**Para que** eu possa cadastrar esse artefato para posterior inspeção.

## Critérios de Aceitação

1. **Dado** que acesso a tela de criação de História de Usuário, **quando** o formulário é exibido, **então** ele deve conter os campos Papel, Ação, Benefício e Critérios de Aceitação.
2. **Dado** que estou preenchendo o formulário, **quando** eu deixo um campo obrigatório vazio, **então** o sistema deve validar em tempo real e impedir a submissão, indicando o campo pendente.
3. **Dado** que preenchi todos os campos obrigatórios corretamente, **quando** eu submeto o formulário, **então** o sistema deve salvar a HU em até 2 segundos e exibir uma confirmação.
4. **Dado** que o texto informado em algum campo ultrapassa o limite de caracteres estipulado por requisição, **quando** eu tento submeter, **então** o sistema deve rejeitar a submissão e informar o limite excedido.

## Requisitos relacionados
- RF-ART-01, RQ-ART-01, RQ-ART-02, RES-ART-01
