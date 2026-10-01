# HU-ART-02 – Criar Caso de Uso (CDU)

**Como** um usuário do sistema,
**Eu quero** preencher um formulário estruturado para registrar um Caso de Uso (Ator Principal, Pré-Condições, Fluxo Principal e Alternativos, Pós-Condições),
**Para que** eu possa cadastrar esse artefato para posterior inspeção.

## Critérios de Aceitação

1. **Dado** que acesso a tela de criação de Caso de Uso, **quando** o formulário é exibido, **então** ele deve conter os campos Ator Principal, Pré-Condições, Fluxo Principal, Fluxos Alternativos e Pós-Condições.
2. **Dado** que estou preenchendo o formulário, **quando** eu deixo um campo obrigatório vazio, **então** o sistema deve validar em tempo real e impedir a submissão, indicando o campo pendente.
3. **Dado** que preenchi todos os campos obrigatórios corretamente, **quando** eu submeto o formulário, **então** o sistema deve salvar o CDU em até 2 segundos e exibir uma confirmação.
4. **Dado** que o texto informado em algum campo ultrapassa o limite de caracteres estipulado por requisição, **quando** eu tento submeter, **então** o sistema deve rejeitar a submissão e informar o limite excedido.

## Requisitos relacionados
- RF-ART-02, RQ-ART-01, RQ-ART-02, RES-ART-01
